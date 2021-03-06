---
title: '방법: ListObject 컨트롤 크기 조정'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], resizing
- ListObject control, resizing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e6d996cfcfb9dd8c63cf31b203905b486b3a1c82
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56598468"
---
# <a name="how-to-resize-listobject-controls"></a>방법: ListObject 컨트롤 크기 조정
  <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤의 크기는 Microsoft Office Excel 통합 문서에 추가할 때 설정하지만 나중에 크기를 조정할 수 있습니다. 예를 들어 2열로 된 목록을 3열로 변경할 수 있습니다.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 크기를 조정할 수 <xref:Microsoft.Office.Tools.Excel.ListObject> 디자인 타임 또는 런타임에 문서 수준 프로젝트에서 컨트롤입니다. 크기를 조정할 수 <xref:Microsoft.Office.Tools.Excel.ListObject> 에서 VSTO 추가 기능 프로젝트에서 런타임에 컨트롤입니다.

 이 항목에서는 다음 작업에 대해 설명합니다.

- [디자인 타임에 ListObject 컨트롤 크기 조정](#designtime)

- [런타임에 문서 수준 프로젝트에서 ListObject 컨트롤 크기 조정](#runtimedoclevel)

- [런타임에 VSTO 추가 기능 프로젝트에서 ListObject 컨트롤 크기 조정](#runtimeaddin)

  에 대 한 자세한 내용은 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 참조 하세요 [ListObject 컨트롤](../vsto/listobject-control.md)합니다.

  ![비디오 링크](../vsto/media/playvideo.gif "비디오 링크") 관련된 비디오 데모를 참조 하세요. [어떻게 할까요? 런타임에 데이터 바인딩된 목록 개체에 열 추가 ](http://go.microsoft.com/fwlink/?LinkID=130318).

##  <a name="designtime"></a> 디자인 타임에 ListObject 컨트롤 크기 조정
 목록 크기를 조정하려면 크기 조정 핸들 중 하나를 클릭하여 끌거나 **목록 크기 조정** 대화 상자에서 크기를 재정의합니다.

### <a name="to-resize-a-list-by-using-the-resize-list-dialog-box"></a>목록 크기 조정 대화 상자를 사용하여 목록 크기를 조정하려면


1.  아무 곳 이나 클릭 합니다 <xref:Microsoft.Office.Tools.Excel.ListObject> 테이블입니다. 합니다 **테이블 도구** > **디자인** 리본에서 탭이 표시 됩니다.

2.  속성 섹션에서 클릭 **테이블의 크기를 조정**합니다.

    ![VSTO_ResizeTable](../vsto/media/vsto-resizetable.png)

3.  테이블에 대 한 새 데이터 범위를 선택 합니다.

4.  **확인**을 클릭합니다.

##  <a name="runtimedoclevel"></a> 런타임에 문서 수준 프로젝트에서 ListObject 컨트롤 크기 조정
 크기를 조정할 수는 <xref:Microsoft.Office.Tools.Excel.ListObject> 를 사용 하 여 런타임에 컨트롤을 <xref:Microsoft.Office.Tools.Excel.ListObject.Resize%2A> 메서드. 이 메서드를 사용하여 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 워크시트의 새 위치로 이동할 수는 없습니다. 머리글은 동일한 행에 유지되고 크기 조정된 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤은 원래 목록 개체에 겹쳐져야 합니다. 크기 조정된 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤에는 하나의 머리글 행과 하나 이상의 데이터 행이 있어야 합니다.

### <a name="to-resize-a-list-object-programmatically"></a>프로그래밍 방식으로 목록 개체의 크기를 조정하려면

1.  <xref:Microsoft.Office.Tools.Excel.ListObject> 에서 **A1** 부터 **B3** 까지의 셀을 포함하도록 `Sheet1`컨트롤을 만듭니다.

     [!code-csharp[Trin_VstcoreHostControlsExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreHostControlsExcel#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#6)]

2.  **A1** 부터 **C5**까지의 셀을 포함하도록 목록의 크기를 조정합니다.

     [!code-csharp[Trin_VstcoreHostControlsExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreHostControlsExcel#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#7)]

##  <a name="runtimeaddin"></a> 런타임에 VSTO 추가 기능 프로젝트에서 ListObject 크기 조정
 크기를 조정할 수는 <xref:Microsoft.Office.Tools.Excel.ListObject> 런타임에 열려 있는 워크시트에 컨트롤입니다. 추가 하는 방법에 대 한 자세한를 <xref:Microsoft.Office.Tools.Excel.ListObject> VSTO 추가 기능을 사용 하 여 워크시트에 컨트롤을 참조 하세요 [방법: 워크시트에 ListObject 컨트롤 추가](../vsto/how-to-add-listobject-controls-to-worksheets.md)합니다.

### <a name="to-resize-a-list-object-programmatically"></a>프로그래밍 방식으로 목록 개체의 크기를 조정하려면

1.  <xref:Microsoft.Office.Tools.Excel.ListObject> 에서 **A1** 부터 **B3** 까지의 셀을 포함하도록 `Sheet1`컨트롤을 만듭니다.

     [!code-csharp[Trin_Excel_Dynamic_Controls#12](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#12)]
     [!code-vb[Trin_Excel_Dynamic_Controls#12](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#12)]

2.  **A1** 부터 **C5**까지의 셀을 포함하도록 목록의 크기를 조정합니다.

     [!code-csharp[Trin_Excel_Dynamic_Controls#13](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#13)]
     [!code-vb[Trin_Excel_Dynamic_Controls#13](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#13)]

## <a name="see-also"></a>참고자료
- [Word 문서 및 런타임에 VSTO 추가 기능에서 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)
- [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)
- [확장 된 개체를 사용 하 여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)
- [ListObject 컨트롤](../vsto/listobject-control.md)
- [방법: 워크시트에 ListObject 컨트롤 추가](../vsto/how-to-add-listobject-controls-to-worksheets.md)
- [방법: 책갈피 컨트롤 크기 조정](../vsto/how-to-resize-bookmark-controls.md)
- [방법: NamedRange 컨트롤 크기 조정](../vsto/how-to-resize-namedrange-controls.md)
