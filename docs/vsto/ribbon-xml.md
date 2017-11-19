---
title: "리본 XML | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSTO.Ribbon.RibbonXMLItem
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, XML
- customizing the Ribbon, XML
- Ribbon [Office development in Visual Studio], XML
- callback methods
- custom Ribbon, displaying
- custom Ribbon, defining behavior
- XML [Office development in Visual Studio], Ribbon
- customizing the Ribbon, defining behavior
- Ribbon [Office development in Visual Studio], customizing
- customizing the Ribbon, displaying
ms.assetid: a5945667-40e8-4191-9f1e-71c18ec30a2e
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7c0a4dd8bb577ddc52ed6a97b2e412109c214335
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ribbon-xml"></a>리본 XML
  리본(XML) 항목을 사용하면 XML을 통해 리본을 사용자 지정할 수 있습니다. 리본(비주얼 디자이너) 항목에서 지원하지 않는 방법으로 리본을 사용자 지정하려는 경우 리본(XML) 항목을 사용합니다. 각 항목으로 수행할 수 있는 한 비교를 참조 하십시오. [리본 개요](../vsto/ribbon-overview.md)합니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## <a name="adding-a-ribbon-xml-item-to-a-project"></a>프로젝트에 리본(XML) 항목 추가  
 **새 항목 추가** 대화 상자에서 Office 프로젝트에 **리본(XML)** 항목을 추가할 수 있습니다. Visual Studio에서 자동으로 다음 파일을 프로젝트에 추가합니다.  
  
-   리본 XML 파일. 이 파일에서는 리본 UI(사용자 인터페이스)를 정의합니다. 이 파일을 사용하여 탭, 그룹 및 컨트롤과 같은 UI 요소를 추가할 수 있습니다. 자세한 내용은 이 항목의 뒷부분에 있는 [리본 XML 파일 참조](#RibbonDescriptorFile) 를 참조하세요.  
  
-   리본 코드 파일. 이 파일에는 *리본 클래스*가 포함되어 있습니다. 이 클래스는 **새 항목 추가** 대화 상자에서 **리본(XML)** 항목에 대해 지정한 이름을 사용합니다. Microsoft Office 응용 프로그램은 이 클래스의 인스턴스를 사용하여 사용자 지정 리본을 로드합니다. 자세한 내용은 이 항목의 뒷부분에 있는 [리본 클래스 참조](#RibbonExtensionClass) 를 참조하세요.  
  
 기본적으로 이러한 파일은 리본 메뉴의 **추가 기능** 탭에 사용자 지정 그룹을 추가합니다.  
  
## <a name="displaying-the-custom-ribbon-in-a-microsoft-office-application"></a>Microsoft Office 응용 프로그램에서 사용자 지정 리본 메뉴 표시  
 추가한 후는 **리본 (XML)** 항목을 프로젝트에 코드를 추가 해야 하는 **ThisAddin**, **ThisWorkbook**, 또는 **ThisDocument** 클래스 프로젝트 메서드를 재정의 하 고 Office 응용 프로그램에 리본 XML 클래스를 반환 합니다.  
  
 다음 코드 예제에서는 프로젝트 메서드를 재정의 하 고 MyRibbon 이라는 리본 XML 클래스를 반환 합니다.  
  
 [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.cs#1)]
 [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.vb#1)]  
  
## <a name="defining-the-behavior-of-the-custom-ribbon"></a>사용자 지정 리본 메뉴의 동작 정의  
 *콜백 메서드*를 만들어 리본 메뉴의 단추 클릭과 같은 사용자 작업에 응답할 수 있습니다. 콜백 메서드는 Windows Forms 컨트롤의 이벤트와 비슷하지만 UI 요소의 XML에서 특성으로 식별됩니다. 리본 클래스에서 메서드를 작성하고 컨트롤이 특성 값과 동일한 이름을 가진 메서드를 호출합니다. 예를 들어 사용자가 리본 메뉴의 단추를 클릭할 때 호출되는 콜백 메서드를 만들 수 있습니다. 콜백 메서드를 만들려면 다음 두 단계가 필요합니다.  
  
-   리본 XML 파일의 컨트롤에 코드에서 콜백 메서드를 식별하는 특성을 할당합니다.  
  
-   리본 클래스에서 콜백 메서드를 정의합니다.  
  
> [!NOTE]  
>  Outlook에는 추가 단계가 필요합니다. 자세한 내용은 참조 [Outlook에 대 한 리본 메뉴 사용자 지정](../vsto/customizing-a-ribbon-for-outlook.md)합니다.  
  
 리본에서 응용 프로그램을 자동화하는 방법을 보여 주는 연습은 [Walkthrough: Creating a Custom Tab by Using Ribbon XML](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)를 참조하세요.  
  
### <a name="assigning-callback-methods-to-controls"></a>컨트롤에 콜백 메서드 할당  
 리본 XML 파일의 컨트롤에 콜백 메서드를 할당하려면 콜백 메서드의 형식 및 메서드 이름을 지정하는 특성을 추가합니다. 예를 들어 다음 요소는 **OnToggleButton1** 이라는 `OnToggleButton1`을 참조하세요.  
  
```  
<toggleButton id="toggleButton1" onAction="OnToggleButton1" />  
```  
  
 **onAction** 은 사용자가 특정 컨트롤에 연결된 기본 작업을 수행할 때 호출됩니다. 예를 들어 토글 단추의 **onAction** 콜백 메서드는 사용자가 단추를 클릭할 때 호출됩니다.  
  
 특성에 지정하는 메서드는 아무 이름이나 사용할 수 있습니다. 그러나 리본 코드 파일에서 정의하는 메서드 이름과 일치해야 합니다.  
  
 리본 컨트롤에 할당할 수 있는 다양한 형식의 콜백 메서드가 있습니다. 각 컨트롤에 대해 사용할 수 있는 콜백 메서드의 전체 목록은 기술 문서 [개발자용 Office(2007) 리본 사용자 인터페이스 사용자 지정(3/3부)](http://msdn.microsoft.com/en-us/a16c7df5-93f3-4920-baa8-7b7290794c15)를 참조하세요.  
  
###  <a name="CallBackMethods"></a> 콜백 메서드 정의  
 리본 코드 파일의 리본 클래스에서 콜백 메서드를 정의합니다. 콜백 메서드에는 다음과 같은 여러 요구 사항이 있습니다.  
  
-   public으로 선언해야 합니다.  
  
-   해당 이름은 리본 XML 파일에서 컨트롤에 할당한 콜백 메서드의 이름과 일치해야 합니다.  
  
-   해당 서명은 연결된 리본 컨트롤에 사용할 수 있는 콜백 메서드의 형식 서명과 일치해야 합니다.  
  
 리본 컨트롤에 대한 콜백 메서드 서명의 전체 목록은 기술 문서 [개발자용 Office(2007) 리본 사용자 인터페이스 사용자 지정(3/3부)](http://msdn.microsoft.com/en-us/a16c7df5-93f3-4920-baa8-7b7290794c15)를 참조하세요. Visual Studio는 리본 코드 파일에서 만든 콜백 메서드에 대해 IntelliSense 지원을 제공하지 않습니다. 유효한 서명과 일치하지 않는 콜백 메서드를 만드는 경우 코드가 컴파일되지만 사용자가 컨트롤을 클릭할 때 아무 작업도 수행되지 않습니다.  
  
 모든 콜백 메서드에 메서드를 호출한 컨트롤을 나타내는 <xref:Microsoft.Office.Core.IRibbonControl> 매개 변수가 있습니다. 이 매개 변수를 사용하여 여러 컨트롤에 대해 동일한 콜백 메서드를 다시 사용할 수 있습니다. 다음 코드 예제에서는 사용자가 클릭하는 컨트롤에 따라 다른 작업을 수행하는 **onAction** 콜백 메서드를 보여 줍니다.  
  
 [!code-csharp[Trin_RibbonOutlookBasic#2](../vsto/codesnippet/CSharp/Trin_RibbonOutlookBasic/Ribbon1.cs#2)]
 [!code-vb[Trin_RibbonOutlookBasic#2](../vsto/codesnippet/VisualBasic/Trin_RibbonOutlookBasic/Ribbon1.vb#2)]  
  
##  <a name="RibbonDescriptorFile"></a> 리본 XML 파일 참조  
 리본 XML 파일에 요소 및 특성을 추가하여 사용자 지정 리본 메뉴를 정의할 수 있습니다. 기본적으로 리본 XML 파일에는 다음 XML이 포함되어 있습니다.  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<customUI xmlns="http://schemas.microsoft.com/office/2006/01/customui" onLoad="OnLoad">  
  <ribbon>  
    <tabs>  
      <tab idMso="TabAddIns">  
        <group id="MyGroup"  
               label="My Group">  
        </group>  
      </tab>  
    </tabs>  
  </ribbon>  
</customUI>  
```  
  
 다음 표에서는 리본 XML 파일의 기본 요소를 설명합니다.  
  
|요소|설명|  
|-------------|-----------------|  
|**customUI**|VSTO 추가 기능 프로젝트의 사용자 지정 리본 메뉴를 나타냅니다.|  
|**T:Microsoft.Office.Core.IRibbonControl**|리본 메뉴를 나타냅니다.|  
|**탭**|리본 탭 집합을 나타냅니다.|  
|**탭**|리본 탭 하나를 나타냅니다.|  
|**group**|리본 탭의 컨트롤 그룹을 나타냅니다.|  
  
 이러한 요소에는 사용자 지정 리본 메뉴의 모양 및 동작을 지정하는 특성이 있습니다. 다음 표에서는 리본 XML 파일의 기본 특성을 설명합니다.  
  
|특성|부모 요소|설명|  
|---------------|--------------------|-----------------|  
|**onLoad**|**customUI**|응용 프로그램에서 리본 메뉴를 로드할 때 호출되는 메서드를 식별합니다.|  
|**idMso**|**탭**|리본 메뉴에 표시할 기본 제공 탭을 식별합니다.|  
|**id**|**group**|그룹을 식별합니다.|  
|**레이블**|**group**|그룹에 나타나는 텍스트를 지정합니다.|  
  
 리본 XML 파일의 기본 요소와 특성은 사용할 수 있는 요소 및 특성의 일부에 불과합니다. 사용 가능한 요소 및 특성의 전체 목록은 기술 문서 [개발자용 Office(2007) 리본 사용자 인터페이스 사용자 지정(2/3부)](http://msdn.microsoft.com/en-us/6b904f55-525f-4520-9b81-a017db65657b)를 참조하세요.  
  
##  <a name="RibbonExtensionClass"></a> 리본 클래스 참조  
 Visual Studio는 리본 코드 파일에 리본 클래스를 생성합니다. 이 클래스에 리본 메뉴의 컨트롤에 대한 콜백 메서드를 추가합니다. 이 클래스는 <xref:Microsoft.Office.Core.IRibbonExtensibility> 인터페이스를 구현합니다.  
  
 다음 표에서는 이 클래스의 기본 메서드를 설명합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|`GetCustomUI`|리본 XML 파일의 내용을 반환합니다. Microsoft Office 응용 프로그램은 이 메서드를 호출하여 사용자 지정 리본 메뉴의 사용자 인터페이스를 정의하는 XML 문자열을 가져옵니다. 이 메서드는 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> 메서드를 구현합니다. **참고:** `GetCustomUI` 는 리본 XML 파일의 내용만 반환 하도록 구현 해야 VSTO 추가 기능에 대 한 초기화를 사용 해야 합니다.   특히, `GetCustomUI` 구현에서 대화 상자 또는 다른 창을 표시하려고 하면 안 됩니다. 그렇지 않으면 사용자 지정 리본 메뉴가 올바르게 동작하지 않을 수 있습니다. VSTO 추가 기능을 초기화하는 코드를 실행해야 하는 경우 `ThisAddIn_Startup` 이벤트 처리기에 코드를 추가합니다.|  
|`OnLoad`|<xref:Microsoft.Office.Core.IRibbonControl> 필드에 `ribbon` 매개 변수를 할당합니다. 사용자 지정 리본 메뉴를 로드하는 경우 Microsoft Office 응용 프로그램에서 이 메서드를 호출합니다. 이 필드를 사용하여 사용자 지정 리본 메뉴를 동적으로 업데이트할 수 있습니다. 자세한 내용은 기술 문서 [개발자용 Office(2007) 리본 사용자 인터페이스 사용자 지정(1/3부)](http://msdn.microsoft.com/en-us/a4fd6d18-d4a8-4e64-bd89-f437208573d3)를 참조하세요.|  
|`GetResourceText`|`GetCustomUI` 메서드에서 리본 XML 파일의 내용을 가져오기 위해 호출합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [연습: 리본 XML을 사용 하 여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)   
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)  
  
  