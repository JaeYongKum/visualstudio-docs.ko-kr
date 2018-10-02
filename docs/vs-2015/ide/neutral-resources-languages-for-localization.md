---
title: 지역화를 위한 중립 리소스 언어 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- localization [Visual Studio], resources
- NeutralResourcesLanguageAttribute class
- globalization [Visual Studio], resources
- resources [Visual Studio], fallback system
- culture, locating resources
- neutral resources
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a9470718743e506a7a8cd5ad03d9b6f69b1d5477
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543085"
---
# <a name="neutral-resources-languages-for-localization"></a>지역화를 위한 중립 리소스 언어
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:System.Resources.NeutralResourcesLanguageAttribute> 클래스는 주 어셈블리에 포함된 리소스의 문화권을 지정합니다. 이 특성은 성능 향상으로 사용되므로 <xref:System.Resources.ResourceManager> 개체는 주 어셈블리에 포함된 리소스를 검색하지 않습니다.  
  
 다음 코드에서는 중립 리소스 언어를 설정하는 방법을 보여 줍니다. 코드는 AssemblyInfo.vb 또는 AssemblyInfo.cs 파일이나 빌드 스크립트에 삽입할 수 있습니다.  
  
```vb  
' Set neutral resources language for assembly.  
<Assembly: NeutralResourcesLanguageAttribute("en")>  
  
```  
  
```csharp  
// Set neutral resources language for assembly.  
[assembly: NeutralResourcesLanguageAttribute("en")]  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Resources.ResourceManager>   
 [.NET Framework 기반의 국가별 응용 프로그램 소개](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
 [지역화를 위한 리소스의 계층적 구성](../ide/hierarchical-organization-of-resources-for-localization.md)   
 [응용 프로그램 지역화](../ide/localizing-applications.md)   
 [응용 프로그램 전역화 및 지역화](../ide/globalizing-and-localizing-applications.md)

