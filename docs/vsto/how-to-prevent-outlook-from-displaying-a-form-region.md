---
title: '방법: Outlook에서 양식 영역 표시 하지 않기'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], canceling display
- canceling form region display
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 87a03e62c77730c7be2c9487c5e344d668ea62cc
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254790"
---
# <a name="how-to-prevent-outlook-from-displaying-a-form-region"></a>방법: Outlook에서 양식 영역 표시 하지 않기
  원하지 않는 Microsoft Office Outlook 특정 항목에 대 한 양식 영역을 표시 하는 경우가 있을 수 있습니다. 예를 들어 연락처 항목에 회사 주소를 찾을 수 없는 경우 표시 되 지도에 비즈니스의 위치를 보여 주는 양식 영역을 방지할 수 있습니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="to-prevent-outlook-from-displaying-a-form-region"></a>Outlook 양식 영역 표시 하지 않도록 설정 하려면  
  
1.  수정 하려는 양식 영역에 대 한 코드 파일을 엽니다.  
  
2.  확장 된 **양식 영역 팩터리** 코드 영역.  
  
3.  코드를 추가 하는 `FormRegionInitializing` 설정 하는 이벤트 처리기는 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 의 속성을 <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> 클래스를 **true**.  
  
 이 예제에서는 연락처 항목에 주소를이 없는 경우는 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성이 **true**, 양식 영역이 표시 되지 않습니다.  
  
## <a name="example"></a>예  
 [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
 [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]  
  
## <a name="see-also"></a>참고자료  
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [연습: Outlook에서 디자인 한 양식 영역 가져오기](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  