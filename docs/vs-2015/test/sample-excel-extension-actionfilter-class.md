---
title: '샘플 Excel 확장: ActionFilter 클래스 | Microsoft 문서'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c69fe3c7-f797-4e90-b21c-f2cc4dddf152
caps.latest.revision: 13
ms.author: gewarren
manager: douge
ms.openlocfilehash: 5e6aff4a57dfb84760ceb4513e06d063c01a5af0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554003"
---
# <a name="sample-excel-extension-actionfilter-class"></a>샘플 Excel 확장: ActionFilter 클래스
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [샘플 Excel 확장: ActionFilter 클래스](https://docs.microsoft.com/visualstudio/test/sample-excel-extension-actionfilter-class)합니다.  
  
이 내부 클래스는 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> 클래스를 확장하며 [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 요소에 대한 테스트 작업용 필터를 나타냅니다.  
  
## <a name="simple-properties"></a>단순 속성  
 개발자는 이러한 읽기 전용 속성을 통해 코딩된 UI 테스트 프레임워크에서 이 테스트 작업 필터를 실행할 방법을 지정할 수 있습니다. 예를 들어 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> 속성은 작업 필터의 이름을 제공합니다. 기타 속성은 작업 필터의 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>, 이 테스트 작업 필터로 필터링되는 테스트 작업의 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> 이름을 가져옵니다. 기타 속성은 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A>을 수행할지 여부 및 테스트 작업이 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>인지 여부를 나타냅니다.  
  
## <a name="processrule-method"></a>ProcessRule 메서드  
 이 메서드는 코딩된 UI 테스트 프레임워크에서 호출되고 제공된 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>을 대상으로 필터를 실행합니다. 이 특정 재정의는 스택의 다음 작업에서 키 입력을 셀로 보낼 경우 해당 셀의 마우스 선택 작업을 제거합니다. 그런 다음 `false`를 반환합니다.  
  
## <a name="private-methods"></a>Private 메서드  
 `IsLeftClick` 메서드는 제공된 작업이 마우스 왼쪽 클릭을 나타내는지지를 확인합니다. `AreActionsOnSameExcelCell` 메서드는 제공된 두 작업이 Excel의 같은 셀에서 실행되는지를 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>   
 [Microsoft Excel을 지원하도록 코딩된 UI 테스트 및 작업 기록 확장](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)


