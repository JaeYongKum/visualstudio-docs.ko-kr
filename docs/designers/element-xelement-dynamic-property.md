---
title: 요소(XElement 동적 속성)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bf8d964a41193d1db845a608749b0ca671dd9349
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924055"
---
# <a name="element-xelement-dynamic-property"></a>요소(XElement 동적 속성)

지정한 확장된 이름에 해당하는 자식 요소 인스턴스를 검색하는 데 사용되는 인덱서를 가져옵니다.

## <a name="syntax"></a>구문

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>속성 값/반환 값

`XElement Item(String expandedName)` 형식의 인덱서입니다. 이 인덱서는 확장된 이름 매개 변수를 사용하여 해당하는 <xref:System.Xml.Linq.XElement>를 반환하거나, 지정된 이름을 가진 요소가 없는 경우 `null`을 반환합니다.

## <a name="remarks"></a>설명

이 속성은 <xref:System.Xml.Linq.XContainer.Element%2A> 클래스의 <xref:System.Xml.Linq.XContainer?displayProperty=fullName> 메서드와 동일합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [XElement 클래스 동적 속성](../designers/xelement-class-dynamic-properties.md)
- [요소](../designers/elements-xelement-dynamic-property.md)