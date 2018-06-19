---
title: 구문 색 지정을 구현 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- syntax coloring, implementing
- editors [Visual Studio SDK], colorizing text
- text, colorizing in editors
ms.assetid: 96e762ca-efd0-41e7-8958-fda4897c8c7a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5502bd30378130e5977d427acb9df5b73226a05b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31131857"
---
# <a name="implementing-syntax-coloring"></a>구문 색 지정을 구현합니다.
언어 서비스 제공 구문 색 지정, 파서가 색 항목 배열에 텍스트 줄을 변환한 색 이러한 항목에 해당 하는 토큰 형식을 반환 합니다. 파서가 색 항목 목록에 속해 있는 토큰 유형을 반환 해야 합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 토큰 유형이 적절 한 색 지정 기 개체에 의해 할당 된 속성에 따라 코드 창에서 각 색 항목을 표시 합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 파서 인터페이스를 지정 하지 않는 및 파서 구현으로 완전히 사용자 자신이 결정 합니다. 그러나 Visual Studio 언어 패키지를 프로젝트에 기본 파서 구현이 제공 됩니다. 관리 코드에 대 한 관리 되는 패키지 프레임 워크 MPF ()는 텍스트의 색을 지정 하는 것에 대 한 완전히 지원 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 된 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 최신 방법입니다. 구문 색 지정을 구현 하는 새로운 방법에 대해 자세히 알아보려면 참조 [연습: 텍스트 강조 표시](../../extensibility/walkthrough-highlighting-text.md)합니다.  
  
> [!NOTE]
>  편집기를 사용 하 여 새 API 가능한 한 빨리 시작 하는 것이 좋습니다. 언어 서비스의 성능이 향상 되 고 새 편집기 기능을 이용할 수 있도록 합니다.  
  
## <a name="steps-followed-by-an-editor-to-colorize-text"></a>텍스트 색을 지정 하는 편집기에서 다음 단계  
  
1.  편집기는 색 지정 기를 호출 하 여 가져옵니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 개체입니다.  
  
2.  편집기를 호출 하 여는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.GetStateMaintenanceFlag%2A> 각 줄의 색 지정 기 외부 유지 관리의 상태는 색 지정 기에 필요한 지 여부를 결정 하는 메서드.  
  
3.  편집기를 호출 하는 상태는 색 지정 기 외부 유지 관리 해야 하는 색 지정 기가 필요한 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.GetStartState%2A> 메서드 첫 번째 줄의 상태를 가져옵니다.  
  
4.  편집기 버퍼의 각 줄에 대 한 호출는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드로, 다음 단계를 수행 합니다.  
  
    1.  텍스트 줄의 텍스트를 토큰으로 변환할 스캐너에 전달 됩니다. 각 토큰 토큰 텍스트와 토큰 형식을 지정합니다.  
  
    2.  토큰 유형이 색 항목 목록에 대 한 인덱스도 변환 됩니다.  
  
    3.  토큰 정보는 줄의 문자에 해당 하는 배열의 각 요소를 배열에 맞게 사용 됩니다. 배열에 저장 된 값은 색 항목 목록으로 인덱스입니다.  
  
    4.  줄의 끝에서 상태는 각 줄에 대해 반환 됩니다.  
  
5.  편집기는 색 지정 기 상태를 유지가 필요한 경우 해당 줄에 대 한 상태를 캐시 합니다.  
  
6.  반환 된 정보를 사용 하 여 텍스트의 줄을 렌더링 하는 편집기는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드. 이 경우 다음 단계를 수행해야 합니다.  
  
    1.  줄에 각 문자에 대해 색 항목 인덱스를 가져옵니다.  
  
    2.  기본 색 항목을 사용 하는 경우 편집기의 색 항목 목록에 액세스 합니다.  
  
    3.  그렇지 않은 경우 언어 서비스를 호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> 메서드 색 항목에 얻으려고 합니다.  
  
    4.  화면에 텍스트를 렌더링 하는 색 항목의 정보를 사용 합니다.  
  
## <a name="managed-package-framework-colorizer"></a>관리 되는 패키지 프레임 워크 색 지정 기  
 관리 패키지 프레임 워크 MPF ()는 색 지정 기를 구현 하는 데 필요한 모든 클래스를 제공 합니다. 언어 서비스 클래스에서 상속 해야는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스 하 고 필요한 메서드를 구현 합니다. 구현 하 여 스캐너 및 파서를 제공 해야 합니다는 <xref:Microsoft.VisualStudio.Package.IScanner> 인터페이스, 및에서 해당 인터페이스의 인스턴스를 반환 된 <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> 메서드 (에서 구현 해야 하는 방법 중 하나는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스). 자세한 내용은 참조 [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 기본 제공 색 항목 사용](../../extensibility/internals/how-to-use-built-in-colorable-items.md)   
 [사용자 지정 색 항목](../../extensibility/internals/custom-colorable-items.md)   
 [레거시 언어 서비스 개발](../../extensibility/internals/developing-a-legacy-language-service.md)   
 [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)