---
title: "Excel 및 Word 프로젝트는.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 업데이트 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: Office projects [Office development in Visual Studio], migrating to .NET Framework 4
ms.assetid: 282c8876-fd49-462e-875b-4a0a79ad951c
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7d3783eb2bd87decc0e01bb589b08f3d0c05803e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="updating-excel-and-word-projects-that-you-migrate-to-the-net-framework-4-or-the-net-framework-45"></a>.NET Framework 4 또는 .NET Framework 4.5로 마이그레이션하는 Excel 및 Word 프로젝트 업데이트
  다음 기능 중 하나를 사용하는 Excel 또는 Word 프로젝트가 있는 경우 대상 프레임워크가 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상으로 변경되면 코드를 수정해야 합니다.  
  
-   [GetVstoObject 및 HasVstoObject 메서드](#GetVstoObject)  
  
-   [문서 수준 프로젝트에 생성된 클래스](#generatedclasses)  
  
-   [문서의 Windows Forms 컨트롤](#winforms)  
  
-   [Word 콘텐츠 컨트롤 이벤트](#ccevents)  
  
-   [OLEObject 및 OLEControl 클래스](#ole)  
  
-   [Controls.Item(Object) 속성](#itemproperty)  
  
-   [CollectionBase에서 파생되는 컬렉션](#collections)  
  
 Microsoft.Office.Tools.Excel.ExcelLocale1033Attribute 및으로 대상이 변경 된 Excel 프로젝트에서 Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy 클래스에 대 한 참조도 제거 해야는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상. Visual Studio 사용자에 대 한이 특성 또는 클래스 참조 제거 되지 않습니다.  
  
## <a name="removing-the-excellocale1033-attribute-from-excel-projects"></a>Excel 프로젝트에서 ExcelLocale1033 특성 제거  
 Microsoft.Office.Tools.Excel.ExcelLocale1033Attribute에서에서 제거한 부분의 Visual Studio 2010 Tools for Office Runtime 대상으로 하는 솔루션에 사용 되는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상. [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상의 CLR(공용 언어 런타임)은 항상 Excel 개체 모델에 로캘 ID 1033을 전달하며, 더 이상 이 특성을 통해 이 동작을 사용하지 않도록 설정할 수 없습니다. 자세한 내용은 [Globalization and Localization of Excel Solutions](../vsto/globalization-and-localization-of-excel-solutions.md)을 참조하세요.  
  
#### <a name="to-remove-the-excellocale1033attribute"></a>ExcelLocale1033Attribute를 제거하려면  
  
1.  Visual Studio에서 프로젝트를 열고 **솔루션 탐색기**를 엽니다.  
  
2.  **속성** 노드(C#의 경우) 또는 **My Project** 노드(Visual Basic의 경우) 아래에서 AssemblyInfo 코드 파일을 두 번 클릭하여 코드 편집기에서 엽니다.  
  
    > [!NOTE]  
    >  Visual Basic 프로젝트에서 AssemblyInfo 코드 파일을 보려면 **솔루션 탐색기** 에서 **모든 파일 표시** 단추를 클릭해야 합니다.  
  
3.  Microsoft.Office.Tools.Excel.ExcelLocale1033Attribute를 찾아 파일에서 제거 하거나 주석으로 처리 하거나 합니다.  
  
    ```vb  
    <Assembly: ExcelLocale1033Proxy(True)>  
    ```  
  
    ```csharp  
    [assembly: ExcelLocale1033Proxy(true)]  
    ```  
  
## <a name="removing-a-reference-to-the-excellocal1033proxy-class"></a>ExcelLocal1033Proxy 클래스에 대한 참조 제거  
 Microsoft Office System 용 Microsoft Visual Studio 2005 Tools를 사용 하 여 만든 프로젝트에 Excel 인스턴스화할 <xref:Microsoft.Office.Interop.Excel.Application> Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy 클래스를 사용 하 여 개체입니다. 이 클래스에서에서 제거한 부분의 Visual Studio 2010 Tools for Office Runtime 대상으로 하는 솔루션에 대 한 사용는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상. 따라서 이 클래스를 참조하는 코드 줄을 제거하거나 주석으로 처리해야 합니다.  
  
#### <a name="to-remove-the-reference-to-the-excellocal1033proxy-class"></a>ExcelLocal1033Proxy 클래스에 대한 참조를 제거하려면  
  
1.  Visual Studio에서 프로젝트를 열고 **솔루션 탐색기**를 엽니다.  
  
2.  **솔루션 탐색기**에서 ThisAddin.cs(C#의 경우) 또는 ThisAddin.vb(Visual Basic의 경우)에 대한 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.  
  
3.  코드 편집기의 `VSTO generated code` 영역에서 다음 코드 줄을 주석으로 처리합니다.  
  
    ```vb  
    Me.Application = CType(Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy.Wrap(GetType(Excel.Application), Me.Application), Excel.Application)  
  
    ```  
  
    ```csharp  
    this.Application = (Excel.Application)Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy.Wrap(typeof(Excel.Application), this.Application);  
  
    ```  
  
##  <a name="GetVstoObject"></a> GetVstoObject 및 HasVstoObject 메서드를 사용하는 코드 업데이트  
 GetVstoObject 또는 HasVstoObject 메서드는.NET Framework 3.5를 대상으로 하는 프로젝트에서 프로젝트의 네이티브 개체 중 하나에서 확장명 메서드로 사용할 수는: <xref:Microsoft.Office.Interop.Word.Document>, <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet>, 또는 <xref:Microsoft.Office.Interop.Excel.ListObject>합니다. 이러한 메서드를 호출하는 경우 매개 변수를 전달할 필요가 없습니다. 다음 코드 예제는 Word VSTO 추가 기능에서.NET Framework 3.5를 대상으로 GetVstoObject 메서드를 사용 하는 방법을 보여 줍니다.  
  
```vb  
Dim vstoDocument as Microsoft.Office.Tools.Word.Document = _  
    Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject()  
```  
  
```csharp  
Microsoft.Office.Tools.Word.Document vstoDocument =   
    Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject();  
```  
  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 프로젝트에서는 다음 방법 중 하나로 이러한 메서드에 액세스하도록 코드를 수정해야 합니다.  
  
-   <xref:Microsoft.Office.Interop.Word.Document>, <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet>또는 <xref:Microsoft.Office.Interop.Excel.ListObject> 개체에서 확장 메서드로 이러한 메서드에 계속 액세스할 수 있습니다. 그러나 이러한 메서드에 Globals.Factory 속성에서 반환 되는 개체 이제 통과 해야 합니다.  
  
    ```vb  
    Dim vstoDocument as Microsoft.Office.Tools.Word.Document = _  
        Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject(Globals.Factory)  
    ```  
  
    ```csharp  
    Microsoft.Office.Tools.Word.Document vstoDocument =   
        Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject(Globals.Factory);  
    ```  
  
-   또는 Globals.Factory 속성에서 반환 되는 개체에서 이러한 메서드에 액세스할 수 있습니다. 이런 방식으로 이러한 메서드에 액세스하는 경우 확장하려는 네이티브 개체를 메서드로 전달해야 합니다.  
  
    ```vb  
    Dim vstoDocument as Microsoft.Office.Tools.Word.Document = _  
        Globals.Factory.GetVstoObject(Globals.ThisAddIn.Application.ActiveDocument)  
    ```  
  
    ```csharp  
    Microsoft.Office.Tools.Word.Document vstoDocument =   
        Globals.Factory.GetVstoObject(Globals.ThisAddIn.Application.ActiveDocument);  
    ```  
  
 자세한 내용은 [Extending Word Documents and Excel Workbooks in VSTO Add-ins at Run Time](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)을 참조하세요.  
  
##  <a name="generatedclasses"></a> 문서 수준 프로젝트에서 생성된 클래스의 인스턴스를 사용하는 코드 업데이트  
 .NET Framework 3.5를 대상으로 하는 문서 수준 프로젝트에서는 프로젝트에서 생성된 클래스가 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]의 다음 클래스에서 파생됩니다.  
  
-   `ThisDocument`: <xref:Microsoft.Office.Tools.Word.Document>  
  
-   `ThisWorkbook`: <xref:Microsoft.Office.Tools.Excel.Workbook>  
  
-   `Sheet` *n*: <xref:Microsoft.Office.Tools.Excel.Worksheet>  
  
-   `Chart` *n*: <xref:Microsoft.Office.Tools.Excel.ChartSheet>  
  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 프로젝트에서는 위에 나열된 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 의 형식이 클래스가 아닌 인터페이스입니다. [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 프로젝트에서 생성된 클래스는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]의 다음 새 클래스에서 파생됩니다.  
  
-   `ThisDocument`: <xref:Microsoft.Office.Tools.Word.DocumentBase>  
  
-   `ThisWorkbook`: <xref:Microsoft.Office.Tools.Excel.WorkbookBase>  
  
-   `Sheet` *n*: <xref:Microsoft.Office.Tools.Excel.WorksheetBase>  
  
-   `Chart` *n*: <xref:Microsoft.Office.Tools.Excel.ChartSheetBase>  
  
 프로젝트의 코드가 생성된 클래스 중 하나의 인스턴스를 파생되는 기본 클래스로 참조하는 경우 코드를 수정해야 합니다.  
  
 예를 들어 .NET Framework 3.5를 대상으로 하는 Excel 통합 문서 프로젝트에서는 프로젝트에서 생성된 `Sheet`*n* 개 클래스의 인스턴스에 대해 일부 작업을 수행하는 도우미 메서드가 있을 수도 있습니다.  
  
```vb  
Private Sub DoSomethingToSheet(ByVal worksheet As Microsoft.Office.Tools.Excel.Worksheet)  
    ' Do something to the worksheet object.  
End Sub  
```  
  
```csharp  
private void DoSomethingToSheet(Microsoft.Office.Tools.Excel.Worksheet worksheet)  
{  
    // Do something to the worksheet object.  
}  
```  
  
 프로젝트의 대상을 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상으로 변경하는 경우 다음 중 하나와 같이 코드를 변경해야 합니다.  
  
-   프로젝트에서 `DoSomethingToSheet` 개체의 <xref:Microsoft.Office.Tools.Excel.WorksheetBase.Base%2A> 속성을 전달하도록 <xref:Microsoft.Office.Tools.Excel.WorksheetBase> 메서드를 호출하는 코드를 수정합니다. 이 속성은 <xref:Microsoft.Office.Tools.Excel.Worksheet> 개체를 반환합니다.  
  
    ```vb  
    DoSomethingToSheet(Globals.Sheet1.Base)  
    ```  
  
    ```csharp  
    DoSomethingToSheet(Globals.Sheet1.Base);  
    ```  
  
-   대신 `DoSomethingToSheet` 개체를 예상하도록 <xref:Microsoft.Office.Tools.Excel.WorksheetBase> 메서드 매개 변수를 수정합니다.  
  
    ```vb  
    Private Sub DoSomethingToSheet(ByVal worksheet As Microsoft.Office.Tools.Excel.WorksheetBase)  
        ' Do something to the worksheet object.  
    End Sub  
    ```  
  
    ```csharp  
    private void DoSomethingToSheet (Microsoft.Office.Tools.Excel.WorksheetBase worksheet)  
    {  
        // Do something to the worksheet object.  
    }  
    ```  
  
##  <a name="winforms"></a> 문서에서 Windows Forms 컨트롤을 사용하는 코드 업데이트  
 추가 해야 합니다는 **를 사용 하 여** (C#) 또는 **Imports** (Visual Basic) 문에 <xref:Microsoft.Office.Tools.Excel> 또는 <xref:Microsoft.Office.Tools.Word> Controls 속성을 사용 하 여 Windows Forms를 추가 하는 코드 파일의 맨 위에 네임 스페이스 문서 또는 워크시트에 프로그래밍 방식으로 제어합니다.  
  
 에 정의 되어 AddButton 메서드) (예: Windows Forms 컨트롤을 추가 하는 메서드는.NET Framework 3.5를 대상으로 하는 프로젝트는 <xref:Microsoft.Office.Tools.Excel.ControlCollection> 및 <xref:Microsoft.Office.Tools.Word.ControlCollection> 클래스입니다.  
  
 대상으로 하는 프로젝트에서 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 또는 이상 버전에서는 이러한 메서드는 Controls 속성에서 사용할 수 있는 확장 메서드입니다. 이러한 확장 메서드를 사용하려면 메서드를 사용하는 코드 파일에 **Controls** 또는 **N:Microsoft.Office.Tools.Excel** 네임스페이스에 대한 <xref:Microsoft.Office.Tools.Excel> 또는 <xref:Microsoft.Office.Tools.Word> 문이 있어야 합니다. 이 문은 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 새 프로젝트에서 자동으로 생성됩니다. 그러나 .NET Framework 3.5를 대상으로 하는 프로젝트에서는 이 문이 자동으로 추가되지 않으므로 프로젝트를 변경할 때 추가해야 합니다.  
  
 자세한 내용은 [Adding Controls to Office Documents at Run Time](../vsto/adding-controls-to-office-documents-at-run-time.md)을 참조하세요.  
  
##  <a name="ccevents"></a> Word 콘텐츠 컨트롤 이벤트를 처리하는 코드 업데이트  
 .NET Framework 3.5를 대상으로 하는 프로젝트에서 Word 콘텐츠 컨트롤의 이벤트는 제네릭 <xref:System.EventHandler%601> 대리자에 의해 처리됩니다. [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 프로젝트에서는 이러한 이벤트가 다른 대리자에 의해 처리됩니다.  
  
 다음 표에서는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 프로젝트에서 Word 콘텐츠 컨트롤 이벤트 및 연결된 대리자를 보여 줍니다.  
  
|이벤트|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상 프로젝트에서 사용할 대리자|  
|-----------|---------------------------------------------------------------------------------------------------|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Added>|<xref:Microsoft.Office.Tools.Word.ContentControlAddedEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.ContentUpdating>|<xref:Microsoft.Office.Tools.Word.ContentControlContentUpdatingEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Deleting>|<xref:Microsoft.Office.Tools.Word.ContentControlDeletingEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Entering>|<xref:Microsoft.Office.Tools.Word.ContentControlEnteringEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Exiting>|<xref:Microsoft.Office.Tools.Word.ContentControlExitingEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.StoreUpdating>|<xref:Microsoft.Office.Tools.Word.ContentControlStoreUpdatingEventHandler>|  
  
##  <a name="ole"></a> OLEObject 및 OLEControl 클래스를 사용하는 코드 업데이트  
 프로젝트에서.NET Framework 3.5를 대상으로 하면 사용자 지정 컨트롤을 추가할 수 (예: Windows Forms 사용자 정의 컨트롤) 문서 또는 워크시트 Microsoft.Office.Tools.Excel.OLEObject 및 Microsoft.Office.Tools.Word.OLEControl 클래스를 사용 하 여 합니다.  
  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 프로젝트에서 이러한 클래스는 <xref:Microsoft.Office.Tools.Excel.ControlSite> 및 <xref:Microsoft.Office.Tools.Word.ControlSite> 인터페이스로 바뀌었습니다. 참조를 대신 참조 하도록 Microsoft.Office.Tools.Excel.OLEObject 및 Microsoft.Office.Tools.Word.OLEControl 하는 코드를 수정 해야 <xref:Microsoft.Office.Tools.Excel.ControlSite> 및 <xref:Microsoft.Office.Tools.Word.ControlSite>합니다. 새 이름을 제외하면 이러한 컨트롤은 .NET Framework 3.5를 대상으로 하는 프로젝트와 동일한 방식으로 동작합니다.  
  
 자세한 내용은 [Adding Controls to Office Documents at Run Time](../vsto/adding-controls-to-office-documents-at-run-time.md)을 참조하세요.  
  
##  <a name="itemproperty"></a> Controls.Item(Object) 속성을 사용하는 코드 업데이트  
 .NET Framework 3.5를 대상으로 하는 프로젝트에서 문서 또는 워크시트에 있는지 확인 하려면 Microsoft.Office.Tools.Word.Document.Controls 또는 Microsoft.Office.Tools.Excel.Worksheet.Controls 컬렉션의 Item(Object) 속성을 사용할 수 있습니다는 지정 된 컨트롤입니다.  
  
 프로젝트에서 대상으로 하는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] Item(Object) 속성은 이러한 컬렉션에서 제거 되었습니다 이상 또는 합니다. 문서 또는 워크시트에 지정 된 컨트롤이 포함 여부를 확인 하려면의 Contains(System.Object) 메서드 사용은 <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> 또는 <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> 컬렉션 대신 합니다.  
  
 문서 및 워크시트의 Controls 컬렉션에 대 한 자세한 내용은 참조 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)합니다.  
  
##  <a name="collections"></a> CollectionBase에서 파생되는 컬렉션을 사용하는 코드 업데이트  
 여러 컬렉션 형식은.NET Framework 3.5를 대상으로 하는 프로젝트에서는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 에서 파생 되는 <xref:System.Collections.CollectionBase> Microsoft.Office.Tools.SmartTagCollection, 같은 Microsoft.Office.Tools.Excel.ControlCollection, 클래스 및 Microsoft.Office.Tools.Word.ControlCollection 합니다.  
  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 프로젝트에서 이러한 컬렉션 형식은 이제 <xref:System.Collections.CollectionBase>에서 파생되지 않는 인터페이스입니다. <xref:System.Collections.CollectionBase.Capacity%2A>, <xref:System.Collections.CollectionBase.List%2A>및 <xref:System.Collections.CollectionBase.InnerList%2A>와 같은 일부 멤버는 이러한 컬렉션 형식에서 더 이상 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Migrating Office Solutions to the .NET Framework 4 or later](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [콘텐츠 컨트롤](../vsto/content-controls.md)   
 [런타임에 Word 문서 및 VSTO 추가 기능에서 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)  
  
  