---
title: Attribute(XElement 동적 속성) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 750e84a386360880cf30e76fc0157145820c654c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550314"
---
# <a name="attribute-xelement-dynamic-property"></a>특성(XElement 동적 속성)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [Attribute (XElement 동적 속성)](https://docs.microsoft.com/visualstudio/designers/attribute-xelement-dynamic-property)합니다.  
  
지정한 확장된 이름에 해당하는 특성 인스턴스를 검색하는 데 사용되는 인덱서를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
elem.Attribute[{namespaceName}attribName]  
```  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 `XAttribute Item(String expandedName)` 형식의 인덱서입니다. 이 인덱서는 지정된 특성의 확장된 이름을 사용하여 해당하는 <xref:System.Xml.Linq.XAttribute>를 반환하거나 지정된 이름을 가진 특성이 없는 경우 `null`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 속성은 <xref:System.Xml.Linq.XElement.Attribute%2A> 클래스의 <xref:System.Xml.Linq.XElement?displayProperty=fullName> 메서드와 동일합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>   
 [XAttribute 클래스 동적 속성](../designers/xelement-class-dynamic-properties.md)   
 [Value](../designers/value-xattribute-dynamic-property.md)



