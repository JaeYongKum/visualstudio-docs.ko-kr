---
title: 작업 항목 링크 처리기 정의 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML API
ms.assetid: d52e0bbf-0166-4bb4-a2e3-cefed6188875
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 7ce74627d1d2d48ab02e0b124fbc38949f1f76f9
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51733061"
---
# <a name="define-a-work-item-link-handler"></a>작업 항목 링크 처리기 정의
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

사용자가 UML 모델 요소와 작업 항목 간에 링크를 만들거나 삭제할 때 응답하는 Visual Studio Integration Extension을 만들 수 있습니다. 예를 들어 사용자가 새 작업 항목을 모델 요소에 연결하도록 선택하면 코드에서는 모델의 값으로부터 작업 항목 필드를 초기화합니다.  
  
## <a name="set-up-a-uml-extension-solution"></a>UML 확장 솔루션  
 이를 통해 처리기를 개발하고 다른 사용자에게 배포할 수 있습니다. 다음 두 Visual Studio 프로젝트를 설정해야 합니다.  
  
-   링크 처리기 코드가 포함된 클래스 라이브러리 프로젝트.  
  
-   명령을 설치할 컨테이너로 사용되는 VSIX 프로젝트. 필요하면 같은 VSIX에 다른 구성 요소를 포함할 수 있습니다.  
  
#### <a name="to-set-up-the-visual-studio-solution"></a>Visual Studio 솔루션을 설정하려면  
  
1.  클래스 라이브러리 프로젝트를 만들어 기존 VSIX 솔루션에 추가하거나 새 솔루션을 만듭니다.  
  
    1.  **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
    2.  아래 **설치 된 템플릿**, 확장 **Visual C#** 또는 **Visual Basic**, 가운데 열에서 클릭 **클래스 라이브러리**합니다.  
  
    3.  **솔루션** 을 설정하여 새 솔루션을 만들지 또는 열려 있는 VSIX 솔루션에 구성 요소를 추가할지를 나타냅니다.  
  
    4.  프로젝트 이름 및 위치를 설정하고 확인을 클릭합니다.  
  
2.  솔루션에 포함되어 있지 않으면 VSIX 프로젝트를 만듭니다.  
  
    1.  **솔루션 탐색기**의 솔루션 바로 가기 메뉴에서 **추가**, **새 프로젝트**를 선택합니다.  
  
    2.  **설치된 템플릿**에서 **Visual C#** 또는 **Visual Basic**을 확장한 다음 **확장성**을 선택합니다. 가운데 열에서 **VSIX 프로젝트**를 선택합니다.  
  
3.  VSIX 프로젝트를 솔루션의 시작 프로젝트로 설정합니다.  
  
    -   솔루션 탐색기의 VSIX 프로젝트 바로 가기 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.  
  
4.  **source.extension.vsixmanifest**아래에 있는 **콘텐츠**, 클래스 라이브러리 프로젝트를 MEF 구성 요소로 추가 합니다.  
  
    1.  **메타데이터** 탭에서 VSIX 이름을 설정합니다.  
  
    2.  **설치 대상** 탭에서 Visual Studio 버전을 대상으로 설정합니다.  
  
    3.  **자산** 탭에서 **새로 만들기**를 선택하고 대화 상자에서 다음을 설정합니다.  
  
         **형식** = **MEF 구성 요소**  
  
         **소스** = **현재 솔루션의 프로젝트**  
  
         **프로젝트** = *클래스 라이브러리 프로젝트*  
  
## <a name="defining-the-work-item-link-handler"></a>작업 항목 링크 처리기 정의  
 클래스 라이브러리 프로젝트에서 다음 작업을 모두 수행합니다.  
  
### <a name="project-references"></a>프로젝트 참조  
 다음 [!INCLUDE[TLA2#tla_net](../includes/tla2sharptla-net-md.md)] 어셈블리를 프로젝트 참조에 추가합니다.  
  
 `Microsoft.TeamFoundation.WorkItemTracking.Client.dll`  
  
 `Microsoft.VisualStudio.TeamFoundation.WorkItemTracking.dll Microsoft.VisualStudio.Modeling.Sdk.[version]`  
  
 `Microsoft.VisualStudio.ArchitectureTools.Extensibility.Uml`  
  
 `Microsoft.VisualStudio.Uml.Interfaces`  
  
 `System.ComponentModel.Composition`  
  
 `System.Drawing` -샘플 코드 사용  
  
 이러한 참조 중 하나를 찾을 수 없는 경우는 **.NET** 탭의 **참조 추가** 대화 상자에서 찾아보기 탭을 사용 하 여 Visual Studio [version] \Common7\IDE\ \Program Files\Microsoft에서에서 찾을 PrivateAssemblies\\합니다.  
  
### <a name="import-the-work-item-namespace"></a>작업 항목 네임스페이스 가져오기  
 사용자 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 프로젝트 **참조**, 다음 어셈블리에 대 한 참조를 추가 합니다.  
  
- Microsoft.TeamFoundation.WorkItemTracking.Client.dll  
  
- Microsoft.VisualStudio.TeamFoundation.WorkItemTracking.dll  
  
  프로그램 코드에서 다음 네임스페이스를 가져옵니다.  
  
```  
using System.ComponentModel.Composition;  
using Microsoft.VisualStudio.Uml.Classes;  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Uml;  
using Microsoft.VisualStudio.TeamFoundation.WorkItemTracking;  
using System.Linq;  
```  
  
### <a name="define-the-linked-work-item-event-handler"></a>연결된 작업 항목 이벤트 처리기 정의  
 클래스 라이브러리 프로젝트에 클래스 파일을 추가하고 해당 콘텐츠를 다음과 같이 설정합니다. 네임스페이스 및 클래스 이름을 원하는 대로 변경합니다.  
  
```  
using System.ComponentModel.Composition;  
using Microsoft.VisualStudio.Uml.Classes;  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Uml;  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation;  
using Microsoft.VisualStudio.TeamFoundation.WorkItemTracking;  
using System.Linq;  
  
namespace WorkItems  
{  
  [Export(typeof(ILinkedWorkItemExtension))]  
  public class MyWorkItemExtension : ILinkedWorkItemExtension  
  {  
    // Called before a new work item is edited by the user.  
    // Use this to initialize work item fields from the model element.  
    public void OnWorkItemCreated(System.Collections.Generic.IEnumerable<IElement> elementsToBeLinked, IWorkItemDocument workItemDocument)  
    {  
      INamedElement namedElement =  
            elementsToBeLinked.First() as INamedElement;  
      if (namedElement != null)  
        workItemDocument.Item.Title = namedElement.Name;  
  
    }  
  
    // Called when any work item is linked to a model element.  
    public void OnWorkItemLinked(System.Collections.Generic.IEnumerable<IElement> elements, string serverUri, int workItemId)  
    {  
      foreach (IElement element in elements)  
        foreach (IShape shape in element.Shapes())  
          shape.Color = System.Drawing.Color.Red;  
    }  
  
    // Called when a work item is unlinked from a model element.  
    public void OnWorkItemRemoved(IElement element, string serverUri, int workItemId)  
    {  
      foreach (IShape shape in element.Shapes())  
        shape.Color = System.Drawing.Color.White;  
    }  
  }  
}  
```  
  
## <a name="testing-the-link-handler"></a>링크 처리기 테스트  
 테스트를 위해 디버그 모드에서 링크 처리기를 실행합니다.  
  
> [!WARNING]
>  작업 항목을 만들거나 작업 항목에 연결하려면 TFS SCC(소스 코드 제어)에 이미 연결되어 있어야 합니다. 다른 TFS SCC에 대한 연결을 열려고 하면 Visual Studio가 자동으로 현재 솔루션을 닫습니다. 작업 항목을 만들거나 작업 항목에 연결하기 전에 적절한 SCC에 이미 연결되어 있는지 확인합니다. Visual Studio의 이후 릴리스에서는 SCC에 연결되어 있지 않으면 메뉴 명령을 사용할 수 없습니다.  
  
#### <a name="to-test-the-link-handler"></a>링크 처리기를 테스트하려면  
  
1.  **F5**키를 누르거나, **디버그** 메뉴에서 **디버깅 시작**을 선택합니다.  
  
     [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 의 실험적 인스턴스가 시작됩니다.  
  
     **문제 해결**: 새 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 시작, VSIX 프로젝트가 솔루션의 시작 프로젝트로 설정 되어 있는지 확인 하지 않습니다.  
  
2.  실험적 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 모델링 프로젝트를 열거나 만들고 모델링 다이어그램을 열거나 만듭니다.  
  
3.  UML 클래스와 같은 모델 요소를 만들고 해당 이름을 설정합니다.  
  
4.  요소를 마우스 오른쪽 단추로 누른 **작업 항목 만들기**합니다.  
  
    -   하위 메뉴에 표시 하는 경우 **Team Foundation Server 연결 열기**, 프로젝트를 닫습니다, 적절 한 TFS에 연결한 후이 절차를 다시 시작 해야 합니다.  
  
    -   하위 메뉴에 작업 항목 형식 목록이 표시되면 작업 항목을 클릭합니다.  
  
         새 작업 항목 양식이 열립니다.  
  
5.  이전 섹션의 샘플 코드를 사용했으면 작업 항목 제목이 모델 요소와 같은지 확인합니다. 이는 `OnWorkItemCreated()`가 작동했음을 보여 줍니다.  
  
6.  양식을 작성하고 작업 항목을 저장하고 닫습니다.  
  
7.  현재 작업 항목이 빨간색으로 표시되는지 확인합니다. 이는 샘플 코드의 `OnWorkItemLinked()`를 보여 줍니다.  
  
     **문제 해결**: 처리기 메서드를 실행 하지 않은 경우에 있는지 확인 합니다.  
  
    -   클래스 라이브러리 프로젝트를 MEF 구성 요소로 나열 됩니다는 **콘텐츠** 목록의 **source.extensions.manifest** VSIX 프로젝트에서.  
  
    -   올바른 `Export` 특성이 처리기 클래스에 연결되고 해당 클래스가 `ILinkedWorkItemExtension`을 구현합니다.  
  
    -   모든 `Import` 및 `Export` 특성의 매개 변수가 유효합니다.  
  
## <a name="about-the-work-item-handler-code"></a>작업 항목 처리기 코드 정보  
  
### <a name="listening-for-new-work-items"></a>새 작업 항목 수신 대기  
 `OnWorkItemCreated`는 사용자가 모델 요소에 연결할 새 작업 항목을 만들도록 선택하면 호출됩니다. 코드에서 작업 항목 필드가 초기화됩니다. 작업 항목이 필드를 업데이트하고 작업 항목을 저장할 수 있는 사용자에게 제공됩니다. 작업 항목이 성공적으로 저장될 때까지 모델 요소 링크가 만들어지지 않습니다.  
  
```  
public void OnWorkItemCreated(  
    IEnumerable<IElement> elementsToBeLinked,  
    IWorkItemDocument workItem)  
{  
  INamedElement namedElement =   
         elementsToBeLinked.First() as INamedElement;  
  if (namedElement != null)  
      workItem.Item.Title = namedElement.Name;  
}  
```  
  
### <a name="listening-for-link-creation"></a>링크 만들기 수신 대기  
 `OnWorkItemLinked`는 링크가 만들어진 후에만 호출됩니다. 새 작업 항목 또는 기존 항목에 대한 링크인지와 관계없이 호출됩니다. 각 작업 항목에 대해 한 번 호출됩니다.  
  
```  
public void OnWorkItemLinked  
        (IEnumerable<IElement> elements,   
         string serverUri, // TFS server  
         int workItemId)  
{  
  foreach (IElement element in elements)  
    foreach (IShape shape in element.Shapes())  
         shape.Color = System.Drawing.Color.Red;  
}  
```  
  
> [!NOTE]
>  이 예제가 작동하려면 `System.Drawing.dll`에 프로젝트 참조를 추가하고 네임스페이스 `Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation`을 가져와야 합니다. 그러나 `OnWorkItemLinked`의 다른 구현에 대해서는 이러한 추가가 필요하지 않습니다.  
  
### <a name="listening-for-link-removal"></a>링크 제거 수신 대기  
 `OnWorkItemRemoved`는 삭제되는 각 작업 항목 링크 바로 앞에 한 번 호출됩니다. 모델 요소가 삭제되면 해당 링크가 모두 제거됩니다.  
  
```  
public void OnWorkItemRemoved  
         (IElement element, string serverUri, int workItemId)  
{...}  
```  
  
## <a name="updating-a-work-item"></a>작업 항목 업데이트  
 Team Foundation 네임스페이스를 사용하여 작업 항목을 조작할 수 있습니다.  
  
 다음 예제를 사용하려면 다음 .NET 어셈블리를 프로젝트 참조에 추가합니다.  
  
-   Microsoft.TeamFoundation.Client.dll  
  
-   Microsoft.TeamFoundation.WorkItemTracking.Client.dll  
  
```  
  
using Microsoft.TeamFoundation.Client;  
using Microsoft.TeamFoundation.WorkItemTracking.Client;  
...  
public void OnWorkItemLinked  
        (IEnumerable<IElement> elements,   
         string serverUri, // TFS server  
         int workItemId)  
{  
  TfsTeamProjectCollection tfs =  
        TfsTeamProjectCollectionFactory  
            .GetTeamProjectCollection(new Uri(serverUri));  
  WorkItemStore workItemStore = new WorkItemStore(tfs);  
  WorkItem item = workItemStore.GetWorkItem(workItemId);  
  item.Open();  
  item.Title = "something";  
  item.Save();  
}   
```  
  
## <a name="accessing-the-work-item-reference-links"></a>작업 항목 참조 링크에 액세스  
 다음과 같이 링크에 액세스할 수 있습니다.  
  
```  
//Get:  
string linkString = element.GetReference(ReferenceConstants.WorkItem);  
// Set:  
element.AddReference(ReferenceConstants.WorkItem, linkString, true);  
  
```  
  
 `linkString` 형식은 다음과 같습니다.  
  
 `string.Format(@"%{0}\{1}#{1}${2}", tfServer, projectCollection, RepositoryGuid, workItem.Id);`  
  
 다음은 각 문자에 대한 설명입니다.  
  
- 서버의 URI는 다음과 같습니다.  
  
   `http://tfServer:8080/tfs/projectCollection`  
  
   `projectCollection`에서는 사례가 중요합니다.  
  
- `RepositoryGuid`는 TFS 연결에서 가져올 수 있습니다.  
  
  ```csharp  
  TfsTeamProjectCollection tpc = TfsTeamProjectCollectionFactory...;  
  RepositoryGuid= tpc.InstanceId;  
  
  ```  
  
  참조에 대 한 자세한 내용은 참조 하세요. [UML에 참조 문자열 연결 모델 요소](../modeling/attach-reference-strings-to-uml-model-elements.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.TeamFoundation.WorkItemTracking.Client.WorkItemStore?displayProperty=fullName>   
 [모델 요소에 연결 하 고 작업 항목](../modeling/link-model-elements-and-work-items.md)   
 [UML 모델 요소에 참조 문자열 연결](../modeling/attach-reference-strings-to-uml-model-elements.md)   
 [모델링 확장 정의 및 설치](../modeling/define-and-install-a-modeling-extension.md)   
 [UML API를 사용한 프로그래밍](../modeling/programming-with-the-uml-api.md)



