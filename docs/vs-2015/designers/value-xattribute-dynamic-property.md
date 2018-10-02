---
title: Value(XAttribute 동적 속성) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- XAttribute.Value
api_type:
- Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: af8f122bfbf2ce37b161afb5f0665a9677ef2f3b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47555901"
---
# <a name="value-xattribute-dynamic-property"></a>Value(XAttribute 동적 속성)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [Value (XAttribute 동적 속성)](https://docs.microsoft.com/visualstudio/designers/value-xattribute-dynamic-property)합니다.  
  
XML 특성의 값을 가져오거나 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
attrib.Value   
```  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 이 특성의 값을 포함하는 <xref:System.String>  
  
## <a name="exceptions"></a>예외  
  
|예외 형식|조건|  
|--------------------|---------------|  
|<xref:System.ArgumentNullException>|설정할 때 `value`가 `null`인 경우|  
  
## <a name="remarks"></a>설명  
 이 속성은 <xref:System.Xml.Linq.XAttribute.Value%2A> 클래스의 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> 속성과 동일하지만 이 동적 속성은 변경 알림도 지원합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>   
 [XAttribute 클래스 동적 속성](../designers/xattribute-class-dynamic-properties.md)   
 [특성](../designers/attribute-xelement-dynamic-property.md)



