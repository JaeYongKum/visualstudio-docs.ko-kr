---
title: '연습: Outlook에서 디자인 한 양식 영역 가져오기'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- importing form regions
- form regions [Office development in Visual Studio], importing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 646fa57ac351fab9b2527c3527ce1864c42519ce
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56631564"
---
# <a name="walkthrough-import-a-form-region-that-is-designed-in-outlook"></a>연습: Outlook에서 디자인 한 양식 영역 가져오기
  이 연습에서는 **새 양식 영역** 마법사를 사용하여 Microsoft Office Outlook에서 양식 영역을 디자인한 다음 Outlook VSTO 추가 기능 프로젝트로 양식 영역을 가져오는 방법을 보여 줍니다. Outlook에서 양식 영역을 디자인하면 Outlook 데이터에 바인딩되는 양식 영역에 네이티브 Outlook 컨트롤을 추가할 수 있습니다. 양식 영역을 가져온 후에 각 컨트롤의 이벤트를 처리할 수 있습니다.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

 이 연습에서는 다음 작업을 수행합니다.

- Outlook에서 양식 영역 디자이너를 사용하여 양식 영역 디자인

- Outlook VSTO 추가 기능 프로젝트에 양식 영역을 가져옵니다.

- 양식 영역의 컨트롤 이벤트 처리

  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>전제 조건
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.

-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

-   [!INCLUDE[Outlook_15_short](../vsto/includes/outlook-15-short-md.md)] 또는 [!INCLUDE[Outlook_14_short](../vsto/includes/outlook-14-short-md.md)]

> [!NOTE]
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.

 ![비디오 링크](../vsto/media/playvideo.gif "비디오 링크") 관련된 비디오 데모를 참조 하세요. [어떻게 할까요? Visual Studio 2008을 사용 하 여 Outlook 양식 영역 만들기 ](http://go.microsoft.com/fwlink/?LinkID=130305).
## <a name="design-a-form-region-by-using-the-form-region-designer-in-outlook"></a>Outlook에서 양식 영역 디자이너를 사용 하 여 양식 영역 디자인
 이 단계에서는 Outlook에서 양식 영역을 디자인합니다. 그런 다음 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]로 가져올 수 있도록 찾기 쉬운 위치에 양식 영역을 저장합니다.

 이 예제 양식 영역은 일반적인 작업 양식을 완전히 바꿉니다. 이 양식 영역은 주 작업을 수행하기 위해 완료되어야 하는 모든 작업의 진행률을 추적하는 방법을 제공합니다(사전 요구 작업). 양식 영역은 필수 조건 작업의 목록을 표시하고 목록의 각 작업에 대한 완료 상태를 보여 줍니다. 사용자는 작업을 목록에 추가하고 제거할 수 있습니다. 또한 각 작업의 완료 상태를 새로 고칠 수 있습니다.

### <a name="to-design-a-form-region-by-using-the-form-region-designer-in-outlook"></a>Outlook에서 양식 영역 디자이너를 사용하여 양식 영역을 디자인하려면

1.  Microsoft Office Outlook을 시작합니다.

2.  Outlook의 **개발자** 탭에서 **양식 디자인**을 클릭합니다. 자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)합니다.

3.  **양식 디자인** 상자에서 **작업**을 클릭한 다음 **열기**를 클릭합니다.

4.  Outlook에서 **개발자** 탭의 **디자인** 그룹에서 **새 양식 영역**을 클릭합니다.

     새 양식 영역을 엽니다. **필드 선택** 이 나타나지 않으면 **도구** 그룹에서 **필드 선택** 을 클릭합니다.

5.  **필드 선택** 에서 **제목** 필드 및 **% 완료** 필드를 양식 영역으로 끌어 놓습니다.

6.  **도구** 그룹에서 **컨트롤 도구 상자** 를 클릭하여 **도구 상자**를 엽니다.

7.  **도구 상자** 에서 레이블을 양식 영역으로 끌어 놓습니다. 레이블을 **제목** 및 **% 완료** 필드 아래에 배치합니다.

8.  레이블을 마우스 오른쪽 단추로 클릭한 다음 **고급 속성**을 클릭합니다.

9. **속성** 창에서 **Caption** 속성을 **이 작업은 다음 작업에 따라 다름**으로 설정하고 **Width** 속성을 **200**으로 설정한 다음 **적용**을 클릭합니다.

10. **도구 상자** 에서 ListBox 컨트롤을 양식 영역으로 끌어 놓습니다. 목록 상자를 **이 작업은 다음 작업에 따라 다름** 레이블 아래에 배치합니다.

11. 방금 추가한 목록 상자를 선택합니다.

12. **속성** 창에서 **너비** 를 **300**으로 설정한 다음 **적용**을 클릭합니다.

13. **도구 상자** 에서 레이블을 양식 영역으로 끌어 놓습니다. 레이블을 목록 상자 아래에 배치합니다.

14. 방금 추가한 레이블을 선택합니다.

15. **속성** 창에서 **Caption** 속성을 **종속 작업 목록에 추가할 작업 선택**으로 설정하고, **Width** 속성을 **200**으로 설정한 다음 **적용**을 클릭합니다.

16. **도구 상자** 에서 ComboBox 컨트롤을 양식 영역으로 끌어 놓습니다. 콤보 상자를 **종속 작업 목록에 추가할 작업 선택** 레이블 아래에 배치합니다.

17. 방금 추가한 콤보 상자를 선택합니다.

18. **속성** 창에서 **Width** 속성을 **300**으로 설정한 다음 **적용**을 클릭합니다.

19. **도구 상자** 에서 CommandButton 컨트롤을 양식 영역으로 끌어 놓습니다. 명령 단추를 콤보 상자 옆에 배치합니다.

20. 방금 추가한 명령 단추를 선택합니다.

21. **속성** 창에서 **Name** 을 **AddDependentTask**로, **Caption** 을 **종속 작업 추가**로, **Width** 를 **100**으로 설정한 다음 **적용**을 클릭합니다.

22. **필드 선택**에서 **새로 만들기**를 클릭합니다.

23. **새 필드** 대화 상자에서 **이름** 필드에 **hiddenField** 를 입력한 다음 **확인**을 클릭합니다.

24. **필드 선택** 에서 **hiddenField** 필드를 양식 영역으로 끌어 놓습니다.

25. **속성** 창에서 **Visible** 를 **0 - False**로 설정한 다음 **적용**을 클릭합니다.

26. Outlook에서 **개발자** 탭의 **디자인** 그룹에서 **저장** 단추를 클릭한 다음 **다른 이름으로 양식 영역 저장**을 클릭합니다.

     양식 영역 이름을 **TaskFormRegion** 으로 지정하고 컴퓨터의 로컬 디렉터리에 저장합니다.

     Outlook 양식 영역을 Outlook 양식 저장으로 저장 (*.ofs*) 파일입니다. 양식 영역 이름으로 저장 됩니다 *TaskFormRegion.ofs*합니다.

27. Outlook을 종료합니다.

## <a name="create-a-new-outlook-add-in-project"></a>새 Outlook 추가 기능 프로젝트를 만들려면
 이 단계에서는 Outlook VSTO 추가 기능 프로젝트를 만듭니다. 이 연습 뒷부분에서는 양식 영역을 프로젝트로 가져옵니다.

### <a name="to-create-a-new-outlook-vsto-add-in-project"></a>새 Outlook VSTO 추가 기능 프로젝트를 만들려면

1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 이름이 **TaskAddIn**인 Outlook VSTO 추가 기능 프로젝트를 만듭니다.

2.  **새 프로젝트** 대화 상자에서 **솔루션용 디렉터리 만들기**를 선택합니다.

3.  기본 프로젝트 디렉터리에 프로젝트를 저장합니다.

     자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)합니다.

## <a name="import-the-form-region"></a>양식 영역 가져오기
 **새 Outlook 양식 영역** 마법사를 사용하여 Outlook에서 디자인한 양식 영역을 Outlook VSTO 추가 기능 프로젝트로 가져올 수 있습니다.

### <a name="to-import-the-form-region-into-the-outlook-vsto-add-in-project"></a>양식 영역을 Outlook VSTO 추가 기능 프로젝트로 가져오려면

1.  **솔루션 탐색기**에서 **TaskAddIn** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 항목**을 클릭합니다.

2.  **템플릿** 창에서 **Outlook 양식 영역**을 선택하고 파일 이름을 **TaskFormRegion**으로 지정한 다음 **추가**를 클릭합니다.

     합니다 **NewOutlook 양식 영역** 마법사가 시작 됩니다.

3.  **양식 영역을 만드는 방법 선택** 페이지에서 **Outlook 양식 저장 파일(.ofs) 가져오기**를 선택한 다음 **찾아보기**를 클릭합니다.

4.  **기존 Outlook 양식 영역 파일 위치** 대화 상자에서 *TaskFormRegion.ofs*의 위치로 이동하여 **TaskFormRegion.ofs**를 선택하고 **열기**를 클릭한 다음 **다음**을 클릭합니다.

5.  **만들 양식 영역 형식 선택** 페이지에서 **모두 대체**를 클릭한 후 **다음**을 클릭합니다.

     *모두 대체* 양식 영역은 전체 Outlook 양식을 바꿉니다. 양식 영역 형식에 대 한 자세한 내용은 참조 하세요. [만들 Outlook 양식 영역](../vsto/creating-outlook-form-regions.md)합니다.

6.  **설명 텍스트를 입력하고 디스플레이 기본 설정을 선택하세요.** 페이지에서 **다음**을 클릭합니다.

7.  **이 양식 영역을 표시할 메시지 클래스를 지정하세요.** 페이지에서 **이 양식 영역을 표시할 사용자 지정 메시지 클래스** 필드에 **IPM.Task.TaskFormRegion**을 입력한 다음 **마침**을 클릭합니다.

     A *TaskFormRegion.cs* 하거나 *TaskFormRegion.vb* 파일이 프로젝트에 추가 됩니다.

## <a name="handle-the-events-of-controls-on-the-form-region"></a>양식 영역의 컨트롤 이벤트를 처리 합니다.
 이제 프로젝트에 양식 영역이 있으므로 Outlook의 양식 영역에 추가한 단추의 `Microsoft.Office.Interop.Outlook.OlkCommandButton.Click` 이벤트를 처리하는 코드를 추가할 수 있습니다.

 또한 양식 영역이 표시될 때 양식 영역의 컨트롤을 업데이트하는 <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> 이벤트에 코드를 추가합니다.

### <a name="to-handle-the-events-of-controls-on-the-form-region"></a>양식 영역의 컨트롤 이벤트를 처리하려면

1. **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 *TaskFormRegion.cs* 또는 *TaskFormRegion.vb*를 클릭 하 고 **코드 보기**합니다.

    *TaskFormRegion.cs* 나 *TaskFormRegion.vb* 코드 편집기에서 열립니다.

2. `TaskFormRegion` 클래스에 다음 코드를 추가합니다. 이 코드는 양식 영역의 콤보 상자를 Outlook 작업 폴더에 있는 각 작업의 제목 줄로 채웁니다.

    [!code-csharp[Trin_Outlook_FR_Import#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#1)]
    [!code-vb[Trin_Outlook_FR_Import#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#1)]

3. `TaskFormRegion` 클래스에 다음 코드를 추가합니다. 이 코드는 다음 작업을 수행합니다.

   - `FindTaskBySubjectName` 도우미 메서드를 호출하고 원하는 작업의 제목을 전달하여 작업 폴더에서 `Microsoft.Office.Interop.Outlook.TaskItem`를 찾습니다. 다음 단계에서는 `FindTaskBySubjectName` 도우미 메서드를 추가합니다.

   - `Microsoft.Office.Interop.Outlook.TaskItem.Subject` 및 `Microsoft.Office.Interop.Outlook.TaskItem.PercentComplete` 값을 종속 작업 목록 상자에 추가합니다.

   - 작업 제목을 양식 영역의 숨겨진 필드에 추가합니다. 숨겨진 필드는 이러한 값을 Outlook 항목의 일부로 저장합니다.

     [!code-csharp[Trin_Outlook_FR_Import#2](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#2)]
     [!code-vb[Trin_Outlook_FR_Import#2](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#2)]

4. `TaskFormRegion` 클래스에 다음 코드를 추가합니다. 이 코드에서는 이전 단계에서 설명한 `FindTaskBySubjectName` 도우미 메서드를 제공합니다.

    [!code-csharp[Trin_Outlook_FR_Import#3](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#3)]
    [!code-vb[Trin_Outlook_FR_Import#3](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#3)]

5. `TaskFormRegion` 클래스에 다음 코드를 추가합니다. 이 코드는 다음 작업을 수행합니다.

   - 양식 영역의 목록 상자를 각 종속 작업의 현재 완료 상태로 새로 고칩니다.

   - 숨겨진 텍스트 필드를 구문 분석하여 각 종속 작업의 제목을 얻습니다. 각 찾은 다음 `Microsoft.Office.Interop.Outlook.TaskItem` 에 *작업* 호출 하 여 폴더를 `FindTaskBySubjectName` 도우미 메서드와 각 작업의 제목을 전달 합니다.

   - `Microsoft.Office.Interop.Outlook.TaskItem.Subject` 및 `Microsoft.Office.Interop.Outlook.TaskItem.PercentComplete` 값을 종속 작업 목록 상자에 추가합니다.

     [!code-csharp[Trin_Outlook_FR_Import#4](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#4)]
     [!code-vb[Trin_Outlook_FR_Import#4](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#4)]

6. `TaskFormRegion_FormRegionShowing` 이벤트 처리기를 다음 코드로 바꿉니다. 이 코드는 다음 작업을 수행합니다.

   - 양식 영역이 표시될 때 작업 제목으로 양식 영역의 콤보 상자를 채웁니다.

   - 양식 영역이 표시될 때 `RefreshTaskListBox` 도우미 메서드를 호출합니다. 그러면 이전에 항목이 열렸을 때 목록 상자에 추가된 모든 종속 작업이 표시됩니다.

     [!code-csharp[Trin_Outlook_FR_Import#5](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#5)]
     [!code-vb[Trin_Outlook_FR_Import#5](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#5)]

## <a name="test-the-outlook-form-region"></a>Outlook 양식 영역 테스트
 양식 영역을 테스트하려면 양식 영역의 사전 요구 작업 목록에 작업을 추가합니다. 사전 요구 작업의 완료 상태를 업데이트한 다음 사전 요구 작업 목록에서 업데이트된 작업의 완료 상태를 봅니다.

### <a name="to-test-the-form-region"></a>양식 영역을 테스트하려면

1.  **F5** 키를 눌러 프로젝트를 실행합니다.

     Outlook이 시작됩니다.

2.  Outlook의 **홈** 탭에서 **새 항목**을 클릭한 다음 **작업**을 클릭합니다.

3.  작업 양식에서 **제목** 필드에 **종속 작업** 을 입력합니다.

4.  에 **태스크** 리본 메뉴의 탭에서를 **작업** 그룹에서 클릭 **저장 후 닫기**.

5.  Outlook의 **홈** 탭에서 **새 항목**, **추가 항목**을 차례로 클릭한 다음 **양식 선택**을 클릭합니다.

6.  **양식 선택** 대화 상자에서 **TaskFormRegion**을 클릭한 다음 **열기**를 클릭합니다.

     **TaskFormRegion** 양식 영역이 표시됩니다. 이 양식은 전체 작업 양식을 바꿉니다. **종속 작업 목록에 추가할 작업 선택** 콤보 상자가 작업 폴더의 다른 작업으로 채워집니다.

7.  작업 양식에서 **제목** 필드에 **주 작업**을 입력합니다.

8.  **종속 작업 목록에 추가할 작업 선택** 콤보 상자에서 **종속 작업**을 선택한 다음 **종속 작업 추가**를 클릭합니다.

     **이 작업은 다음 작업에 따라 다름** 목록 상자에 **0% 완료 -- 종속 작업** 이 표시됩니다. 이는 단추의 `Microsoft.Office.Interop.Outlook.OlkCommandButton.Click` 이벤트가 잘 처리되었음을 보여 줍니다.

9. **주 작업** 항목을 저장한 후 닫습니다.

10. Outlook에서 종속 작업 항목을 다시 엽니다.

11. 종속 작업 양식에서 **% 완료** 필드를 **50%** 로 변경합니다.

12. 에 **태스크** 종속 작업 리본의 탭에서를 **작업** 그룹에서 클릭 **저장 후 닫기**.

13. Outlook에서 **주 작업** 항목을 다시 엽니다.

     이제**이 작업은 다음 작업에 따라 다름** 목록 상자에 **50% 완료 -- 종속 작업** 이 표시됩니다.

## <a name="next-steps"></a>다음 단계
 다음 항목에서 Outlook 애플리케이션의 UI를 사용자 지정하는 방법에 대해 자세히 알아볼 수 있습니다.

-   관리 되는 컨트롤을 비주얼 디자이너로 끌어서 양식 영역의 모양을 디자인 하는 방법에 대 한 자세한 내용은를 참조 하세요. [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)합니다.

-   Outlook 항목의 리본을 사용자 지정 하는 방법에 알아보려면 [Outlook에 대 한 리본을 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)합니다.

-   Outlook에 사용자 지정 작업창을 추가 하는 방법에 대 한 자세한 내용은 참조 하세요 [사용자 지정 작업창](../vsto/custom-task-panes.md)합니다.

## <a name="see-also"></a>참고자료
- [런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)
- [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)
- [Outlook 양식 영역 만들기 지침](../vsto/guidelines-for-creating-outlook-form-regions.md)
- [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)
- [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)
- [Outlook 메시지 클래스를 사용 하 여 양식 영역을 연결 합니다.](../vsto/associating-a-form-region-with-an-outlook-message-class.md)
- [Outlook 양식 영역의 사용자 지정 작업](../vsto/custom-actions-in-outlook-form-regions.md)
- [방법: Outlook에서 양식 영역 표시 하지 않기](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)
