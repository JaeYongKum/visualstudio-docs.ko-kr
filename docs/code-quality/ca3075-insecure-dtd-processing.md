---
title: 'CA3075: DTD 처리가 안전하지 않습니다.'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 65798d66-7a30-4359-b064-61a8660c1eed
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ec4ea49b9b5563382786b5cf83f577e0b8e96386
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55921408"
---
# <a name="ca3075-insecure-dtd-processing"></a>CA3075: DTD 처리가 안전하지 않습니다.

|||
|-|-|
|TypeName|InsecureDTDProcessing|
|CheckId|CA3075|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

안전하지 않은 <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> 인스턴스를 사용하거나 외부 엔터티 소스를 참조하면 파서는 신뢰할 수 없는 입력을 허용하고 공격자에게 중요 한 정보를 공개할 수 있습니다.

## <a name="rule-description"></a>규칙 설명

*DTD(문서 종류 정의)* 는 XML 파서가  [W3C(World Wide Web Consortium) XML(Extensible Markup Language) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/)에 정의된 대로 문서의 유효성을 확인할 수 있는 두 가지 방법 중 하나입니다. 이 규칙은 신뢰할 수 없는 데이터가 허용되는 속성 및 인스턴스를 찾아 [DoS(서비스 거부)](/dotnet/framework/wcf/feature-details/information-disclosure) 공격을 야기할 수 있는 잠재적인 [Information Disclosure](/dotnet/framework/wcf/feature-details/denial-of-service) 위협을 개발자에게 경고합니다. 다음 경우에 이 규칙이 트리거됩니다.

- <xref:System.Xml.XmlReader> 를 사용하여 외부 XML 엔터티를 확인하는 <xref:System.Xml.XmlUrlResolver>인스턴스에서 DtdProcessing이 사용되도록 설정된 경우

- XML의 <xref:System.Xml.XmlNode.InnerXml%2A> 속성이 설정된 경우

- <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> 속성이는 Parse로 설정 됩니다.

- 신뢰할 수 없는 입력이 <xref:System.Xml.XmlResolver> 대신 <xref:System.Xml.XmlSecureResolver> 를 사용하여 처리되는 경우

- XmlReader입니다.<xref:System.Xml.XmlReader.Create%2A> 메서드가 호출 됩니다는 안전 하지 않은 <xref:System.Xml.XmlReaderSettings> 인스턴스 또는 모든 인스턴스가 없습니다.

- <xref:System.Xml.XmlReader> 안전 하지 않은 기본 설정이 나 값을 사용 하 여 생성 됩니다.

이러한 경우 모두 결과는 동일합니다. XML이 처리되는 컴퓨터의 파일 시스템 또는 네트워크 공유의 내용이 공격자에게 노출되어 DoS 벡터로 사용될 수 있습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- Catch 하 고 적절 하 게 경로 정보가 공개 되지 않도록 모든 XmlTextReader 예외를 처리 합니다.

- <xref:System.Xml.XmlSecureResolver> 를 사용하여  XmlTextReader에서 액세스할 수 있는 리소스를 제한할 수 있습니다.

- <xref:System.Xml.XmlReader> 속성을 <xref:System.Xml.XmlResolver> null **로 설정하여**가 외부 리소스를 열 수 없도록 합니다.

- <xref:System.Data.DataViewManager.DataViewSettingCollectionString%2A> 의 <xref:System.Data.DataViewManager> 속성이 신뢰할 수 있는 소스에서 할당되었는지 확인합니다.

**.NET 3.5 및 이전 버전**

-  <xref:System.Xml.XmlReaderSettings.ProhibitDtd%2A> 속성을 **true** 로 설정하여 신뢰할 수 없는 소스를 처리하는 경우 DTD 처리를 사용하지 않도록 설정합니다.

- XmlTextReader 클래스에는 완전 신뢰 상속 요청이 있습니다.

**.NET 4 이상**

- 설정 하 여 신뢰할 수 없는 소스를 처리 하는 경우 DtdProcessing을 설정 하지 않도록 합니다 <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A?displayProperty=nameWithType> 속성을 **금지** 또는 **무시**합니다.

- Load() 메서드가 모든 InnerXml 경우에서 XmlReader 인스턴스를 사용하는지 확인합니다.

> [!NOTE]
> 이 규칙은 일부 유효한 XmlSecureResolver 인스턴스에 대해 가양성(false positive)을 보고할 수 있습니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

입력 출처를 신뢰할 수 있는지 확신할 수 없으면 이 경고의 규칙이 표시되지 않도록 설정하지 않도록 합니다.

## <a name="pseudo-code-examples"></a>의사 코드 예제

### <a name="violation"></a>위반

```csharp
using System.IO;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlSchema schema = XmlSchema.Read(tr, null); // warn
            return schema;
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.IO;
using System.Xml;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlTextReader reader = new XmlTextReader(tr) { DtdProcessing = DtdProcessing.Prohibit };
            XmlSchema schema = XmlSchema.Read(reader , null);
            return schema;
        }
    }
}
```

### <a name="violation"></a>위반

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings();
        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);  // warn
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings()
        {
            DtdProcessing = DtdProcessing.Prohibit
        };

        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);
        }
    }
}
```

### <a name="violations"></a>위반

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseSetInnerXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument() { XmlResolver = null };
            doc.InnerXml = xml; // warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseLoadXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument(){ XmlResolver = null };
            doc.LoadXml(xml); // warn
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;

public static void TestMethod(string xml)
{
    XmlDocument doc = new XmlDocument() { XmlResolver = null };
    System.IO.StringReader sreader = new System.IO.StringReader(xml);
    XmlTextReader reader = new XmlTextReader(sreader) { DtdProcessing = DtdProcessing.Prohibit };
    doc.Load(reader);
}
```

### <a name="violation"></a>위반

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            serializer.Deserialize(stream); // warn
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            XmlTextReader reader = new XmlTextReader(stream) { DtdProcessing = DtdProcessing.Prohibit } ;
            serializer.Deserialize(reader );
        }
    }
}
```

### <a name="violation"></a>위반

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XPathDocument doc = new XPathDocument(path); // warn
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XmlTextReader reader = new XmlTextReader(path) { DtdProcessing = DtdProcessing.Prohibit };
            XPathDocument doc = new XPathDocument(reader);
        }
    }
}
```

### <a name="violation"></a>위반

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = new XmlUrlResolver() };
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = null }; // or set to a XmlSecureResolver instance
    }
}
```

### <a name="violations"></a>위반

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            XmlReaderSettings settings = new XmlReaderSettings(){ DtdProcessing = DtdProcessing.Parse };
            XmlReader reader = XmlReader.Create(path, settings); // warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod()
        {
            var reader = XmlTextReader.Create(""doc.xml""); //warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            try {
                XmlTextReader reader = new XmlTextReader(path); // warn
            }
            catch { throw ; }
            finally {}
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            XmlReaderSettings settings = new XmlReaderSettings(){ DtdProcessing = DtdProcessing.Prohibit };
            XmlReader reader = XmlReader.Create(path, settings);
        }
    }
}
```