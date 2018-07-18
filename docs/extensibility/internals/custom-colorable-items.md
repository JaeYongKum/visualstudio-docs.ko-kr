---
title: 사용자 지정 색 항목 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- colorable items
- language services, custom colorable items
ms.assetid: b4d0ddee-c04b-48dc-ba82-f6068570cef0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b23ff39abcb9a1354ea28becab3b7df867378ddf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133374"
---
# <a name="custom-colorable-items"></a>사용자 지정 색 항목
언어 서비스의 일부로 사용자 지정 색 항목을 구현 하 여 키워드 및 주석 등의 색을 지정 하는 것에 대 한 형식의 목록을 재정의할 수 있습니다.  
  
## <a name="user-settings-of-colorable-items"></a>색 항목 사용자 설정  
 표시할 수 있습니다는 **글꼴 및 색** 대화 상자를 선택 하 여 **옵션** 에 **도구** 메뉴를 선택한 다음 **글꼴 및 색** 아래 **환경**합니다. 선택 하면 표시 되는 같은 **텍스트 편집기** 또는 **명령 창**, **항목 표시** 목록 상자에 표시 하는 모든 색 항목을 표시 합니다. 보고 하 고 글꼴, 크기, 전경색 및 배경색 색 각 항목에 대 한 변경할 수 있습니다. 선택 사항을 레지스트리에 캐시에 저장 하 고 색 항목 이름으로 액세스 됩니다.  
  
## <a name="presentation-of-colorable-items"></a>색 항목 표시  
 IDE 사용자 재정의에 색 항목을 처리 하기 때문에 **글꼴 및 색** 대화 상자, 해야만 이름으로 각 사용자 지정 색 항목을 제공 합니다. 이 이름은 표시 됩니다는 **항목 표시** 목록입니다. 색 항목 사전순으로 표시 합니다. 언어 서비스의 사용자 지정 색 항목을 그룹화 하려면 시작할 수 있습니다 각 이름을 언어 이름의 예를 들어 **NewLanguage-주석** 및 **NewLanguage-키워드**합니다.  
  
> [!CAUTION]
>  기존 색 항목 이름으로 충돌을 피하기 위해 색 항목 이름에 언어 이름을 포함 해야 합니다. 개발 중에 색 항목 중 하나의 이름을 변경 하면 색 항목에 액세스 된 처음으로 만들어진 캐시를 다시 설정 해야 합니다. 실험적 캐시 디렉터리에 일반적으로 Visual Studio SDK, 함께 설치 된 CreateExpInstance 도구를 다시 설정할 수 있습니다.  
>   
>  **C:\Program 파일 (x86) \Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin**  
>   
>  캐시를 다시 설정 하려면 호출 `CreateExpInstance /Reset`합니다. CreateExpInstance에 대 한 자세한 내용은 참조 [CreateExpInstance 유틸리티](../../extensibility/internals/createexpinstance-utility.md)합니다.  
  
 색 항목 목록에 첫 번째 항목은 참조 되지 않습니다. 0의 색 항목 인덱스에 해당 하는 첫 번째 항목 및 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 항상 기본 텍스트 색과 해당 항목에 대 한 특성을 제공 합니다. 이 참조 되지 않은 항목을 처리 하는 첫 번째 항목으로 목록에 있는 자리 표시자 색 항목을 제공 하는 가장 쉬운 방법은 합니다.  
  
## <a name="implementing-custom-colorable-items"></a>색 사용자 지정 항목을 구현합니다.  
  
1.  정의 어떤 색이 언어에서 예를 들어 키워드, 연산자 및 식별자 지정 해야 합니다.  
  
2.  이러한 색 항목의 열거형을 만듭니다.  
  
3.  파서 또는 열거 값을 가진 스캐너에서 반환 된 토큰 형식을 연결 합니다.  
  
     예를 들어 토큰 형식을 나타내는 값에는 사용자 지정 색 항목 열거형의 값이 동일한 수 있습니다.  
  
4.  구현에서는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드에서 프로그램 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 개체, 특성 목록에 해당 하는 파서 또는 스캐너에서 반환 된 토큰 형식은 사용자 지정 색 항목 열거의 값으로 채웁니다.  
  
5.  구현 하는 동일한 클래스에는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 인터페이스를 구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> 인터페이스 및 해당 두 메서드 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A>합니다.  
  
6.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> 인터페이스를 구현합니다.  
  
7.  24 비트 또는 높은 색 값을 지원 하려는 경우 구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> 인터페이스입니다.  
  
8.  언어 서비스 개체를 포함 하는 목록을 만듭니다 프로그램 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> 개체, 파서 또는 스캐너를 식별할 수 색 각 항목에 대 한 합니다.  
  
     사용자 지정 색 항목 열거형에서 해당 값을 사용 하 여 목록에서 각 항목에 액세스할 수 있습니다. 인덱스 속성을 목록에 열거형 값을 사용 합니다. 목록에서 첫 번째 항목을 액세스 하는 경우가 절대, 기본 텍스트에 해당 하기 때문에 스타일을 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 항상 자체를 처리 합니다. 이 대 한 자리 표시자 색 항목 목록 맨 앞에 삽입 하 여 보완할 수 있습니다.  
  
9. 구현에서는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> 메서드를 사용자 지정 색 항목 목록에서 항목의 수를 반환 합니다.  
  
10. 구현에서는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> 메서드를 목록에서 요청 된 색 항목을 반환 합니다.  
  
 구현 하는 방법의 예는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> 인터페이스 참조 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스의 모델](../../extensibility/internals/model-of-a-legacy-language-service.md)   
 [사용자 지정 편집기에서 색을 지정 하는 구문](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [구문 색에 레거시 언어 서비스](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [구문 색 지정을 구현합니다.](../../extensibility/internals/implementing-syntax-coloring.md)   
 [방법: 기본 제공 색 항목 사용](../../extensibility/internals/how-to-use-built-in-colorable-items.md)