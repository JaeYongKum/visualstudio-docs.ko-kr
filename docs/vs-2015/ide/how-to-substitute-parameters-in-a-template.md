---
title: '방법: 템플릿 매개 변수 대체 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- template parameters, substituting
- Visual Studio templates, using parameters
ms.assetid: a62924a7-4ba0-413d-b606-fdbe1fcf2807
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 97a8a99e160e4d488e44cc9e084789fe3a005eb1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54780293"
---
# <a name="how-to-substitute-parameters-in-a-template"></a>방법: 템플릿 매개 변수 대체
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

템플릿을 기반으로 하는 파일을 만들 때 클래스 이름 및 네임스페이스와 같은 템플릿 매개 변수를 바꿀 수 있습니다. 템플릿 매개 변수의 전체 목록은 [템플릿 매개 변수](../ide/template-parameters.md)를 참조하세요.  
  
## <a name="procedure"></a>프로시저  
 템플릿을 기반으로 하는 프로젝트를 만들 때마다 템플릿의 파일에 있는 매개 변수를 바꿀 수 있습니다. 이 절차에서는 템플릿을 사용하여 새 프로젝트를 만들 때 네임스페이스 이름을 안전한 프로젝트 이름으로 바꾸는 템플릿을 만드는 방법을 설명합니다.  
  
#### <a name="to-use-a-parameter-to-replace-namespace-name-with-the-project-name"></a>매개 변수를 사용하여 네임스페이스 이름을 프로젝트 이름으로 바꾸려면  
  
1.  템플릿의 하나 이상 코드 파일에 매개 변수를 삽입합니다. 예:  
  
    ```  
    namespace $safeprojectname$  
    ```  
  
    > [!NOTE]
    >  템플릿 매개 변수는 $*parameter*$ 형식으로 작성됩니다.  
  
2.  템플릿에 대한 .vstemplate 파일에서 이 파일을 포함하는 `ProjectItem` 요소를 찾습니다.  
  
3.  `ProjectItem` 요소에 대해 `ReplaceParameters` 특성을 `true`로 설정합니다. 예:  
  
    ```  
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)   
 [템플릿 매개 변수](../ide/template-parameters.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [ProjectItem 요소(Visual Studio 항목 템플릿)](../extensibility/projectitem-element-visual-studio-item-templates.md)
