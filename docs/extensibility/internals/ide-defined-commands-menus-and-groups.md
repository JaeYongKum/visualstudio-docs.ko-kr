---
title: IDE 정의 명령, 메뉴 및 그룹 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, environment-defined
- .vsct files, environment-defined constants
- command groups, environment-defined
ms.assetid: 86b3af13-7163-48c6-986b-7beeedbc26cc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b65266ad3367df5cebeabc251bc8bceb6cda7075
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129391"
---
# <a name="ide-defined-commands-menus-and-groups"></a>IDE 정의 명령, 메뉴 및 그룹
여러 메뉴, 명령 및 명령 그룹에서 사용 하기 위해 이미 정의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. 확장 하는 경우 이러한 명령을 사용 하기 위해 사용할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="finding-environment-defined-commands"></a>명령 환경 정의 찾기  
 환경 명령 4 개의.vsct 파일의 집합에 정의 됩니다.  
  
-   SharedCmdDef.vsct  
  
-   SharedCmdPlace.vsct  
  
-   ShellCmdDef.vsct  
  
-   ShellCmdPlace.vsct  
  
 이러한 파일은 %programfiles%\microsoft  *\<Visual Studio SDK 설치 경로 >* \VisualStudioIntegration\Common\Inc\\합니다. 이러한 파일은 정 및 메뉴 및 메뉴, 그룹와 명령에 대 한 컨테이너로 VSPackage의 명령 테이블 (.vsct) 구성 파일에서 사용할 수 있는 그룹의 Guid를 제공 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [Visual Studio 메뉴의 GUID 및 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)  
 Visual Studio 메뉴 모음에서 메뉴 및 포함 그룹의 GUID 및 ID 값을 제공 합니다.  
  
 [Visual Studio 도구 모음의 GUID 및 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)  
 Visual Studio IDE에서 도구 모음 및 포함 그룹의 GUID 및 ID 값을 제공 합니다.  
  
 [Visual Studio 명령의 GUID 및 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)  
 Visual Studio IDE에 의해 정의 된 명령의 GUID 및 ID 값을 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령 테이블 (합니다. Vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [프로젝트 시스템을 확장 하기 위한 명령을 IDE 정의](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)   
 [VSPackage에서 사용자 인터페이스 요소를 추가하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)