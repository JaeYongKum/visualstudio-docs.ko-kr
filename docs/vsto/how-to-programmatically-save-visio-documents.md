---
title: '방법: 프로그래밍 방식으로 Visio 문서 저장'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], saving Visio documents
- Visio [Office development in Visual Studio], saving Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4171f0237b7735748da567bd9482856c013759bc
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35675107"
---
# <a name="how-to-programmatically-save-visio-documents"></a>방법: 프로그래밍 방식으로 Visio 문서 저장
  여러 가지 방법을 사용하여 Microsoft Office Visio 문서를 저장할 수 있습니다.  
  
-   변경 내용을 기존 문서에 저장합니다.  
  
-   새 문서를 저장하거나 새 이름으로 문서를 저장합니다.  
  
-   지정된 인수와 함께 문서를 저장합니다.  
  
 자세한 내용은 VBA 참조 설명서에서 [Microsoft.Office.Interop.Visio.Document.Save](https://msdn.microsoft.com/library/office/ff766478.aspx) 메서드, [Microsoft.Office.Interop.Visio.Document.SaveAs](https://msdn.microsoft.com/library/office/ff765824.aspx) 메서드 및 [Microsoft.Office.Interop.Visio.Document.SaveAsEx](https://msdn.microsoft.com/library/office/ff768149.aspx) 메서드를 참조하세요.  
  
## <a name="save-an-existing-document"></a>기존 문서 저장  
  
### <a name="to-save-a-document"></a>문서를 저장하려면  
  
-   호출을 `Microsoft.Office.Interop.Visio.Document.Save` 메서드는 `Microsoft.Office.Tools.Visio.Document` 클래스에서 이전에 저장 된 문서입니다.  
  
     이 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
    > [!NOTE]  
    >  `Microsoft.Office.Interop.Visio.Document.Save` 메서드는 새 Visio 문서 아직 저장 되지 않은 경우 예외를 throw 합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#11](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#11)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#11](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#11)]  
  
## <a name="save-a-document-with-a-new-name"></a>새 이름으로 문서를 저장 합니다.  
 사용 된 `Microsoft.Office.Interop.Visio.Document.SaveAs` 새 문서 또는 새 이름이 있는 문서를 저장 하는 방법입니다. 이 메서드를 사용하려면 새 파일 이름을 지정해야 합니다.  
  
### <a name="to-save-the-active-visio-document-with-a-new-name"></a>활성 Visio 문서를 새 이름으로 저장하려면  
  
-   호출을 `Microsoft.Office.Interop.Visio.Document.SaveAs` 메서드의 `Microsoft.Office.Tools.Visio.Document` 파일 이름을 포함 한 정규화 된 경로 사용 하 여 저장 되도록 합니다. 해당 이름의 파일이 폴더에 이미 있으면 자동으로 덮어씁니다.  
  
     이 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#10](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#10)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#10](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#10)]  
  
## <a name="save-a-document-with-a-new-name-and-specified-arguments"></a>새 이름 및 지정 된 인수를 사용 하 여 문서를 저장 합니다.  
 사용 된 `Microsoft.Office.Interop.Visio.Document.SaveAsEx` 메서드를 새 이름으로 문서를 저장 하 고 문서에 적용할 인수를 지정 합니다.  
  
### <a name="to-save-document-with-a-new-name-and-specified-arguments"></a>새 이름 및 지정된 인수를 사용하여 문서를 저장하려면  
  
-   호출을 `Microsoft.Office.Interop.Visio.Document.SaveAsEx` 메서드의 `Microsoft.Office.Tools.Visio.Document` 파일 이름을 포함 한 정규화 된 경로 사용 하 여 저장 되도록 합니다. 해당 이름의 파일이 폴더에 이미 있으면 예외가 throw됩니다.  
  
     다음 코드 예제에서는 활성 문서를 새 이름으로 저장하고 문서를 읽기 전용으로 표시하며 가장 최근에 사용됨 문서 목록에 문서를 표시합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#12](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#12)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#12](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#12)]  
  
## <a name="compile-the-code"></a>코드 컴파일  
 이 코드 예제에는 다음이 필요합니다.  
  
-   디렉터리에 명명 된 새 이름이 있는 문서를 저장 하려면 `Test` 에 있어야 합니다 *내 문서* 폴더 (Windows XP 및 이전) 또는 *문서* 폴더 (Windows Vista).  
  
## <a name="see-also"></a>참고자료  
 [Visio 솔루션](../vsto/visio-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 새 Visio 문서 만들기](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 열기](../vsto/how-to-programmatically-open-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 닫기](../vsto/how-to-programmatically-close-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 인쇄](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  