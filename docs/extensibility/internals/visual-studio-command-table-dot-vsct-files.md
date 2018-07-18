---
title: Visual Studio 명령 테이블 (합니다. Vsct) 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, overview
- Visual Studio command table configuration files (VSCT), overview
ms.assetid: 1313adb4-add4-4e74-90e2-f4be522f5259
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3407c21f242cf45337ddad2ff19993d9e0130fbf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31140471"
---
# <a name="visual-studio-command-table-vsct-files"></a>Visual Studio 명령 테이블 (합니다. Vsct) 파일
명령 테이블 구성 파일은 VSPackage를 포함 하는 명령 집합을 설명 하는 텍스트 파일. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령 테이블 (VSCT) 컴파일러 binary 명령 테이블 (.cto) 출력 파일에 XML 기반 구성 파일 (.vsct 파일)를 컴파일합니다. 결과.cto 파일.ctc 구성 파일을 컴파일하는 데 명령 테이블 (CTC) 컴파일러를 사용 하 여 생성 하는 것과 동일 합니다. 그러나 XML 기반.vsct 파일에 XML 편집기 및 XML IntelliSense와 같은 몇 가지 이점이 있습니다.  
  
 구문 및.vsct 파일의 의미에 대 한 자세한 참조 [XML 명령 테이블 디자인 (합니다. Vsct) 파일](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
  
## <a name="in-this-section"></a>섹션 내용  
 [XML 명령 테이블(.Vsct) 파일 디자인](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
 .Vsct 파일을 디자인 하는 방법에 설명 합니다.  
  
 [방법: .Vsct 파일 만들기](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)  
 .Vsct 파일을 생성 하기 위한 메서드를 비교 합니다. 수동으로 새.vsct 파일을 만드는 과정을 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)  
 명령 테이블 XML 구성 파일의 각 섹션에 대 한 세부 정보를 제공합니다.  
  
 [테이블 구성 명령 (합니다. Ctc) 파일](http://msdn.microsoft.com/en-us/3413dda1-f372-4669-bcf0-c64d3463842c)  
 사용 되지 않는.ctc 파일 형식에 대 한 개요를 표시합니다.  
  
 [VSPackage에서 사용자 인터페이스 요소를 추가하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 명령 테이블 형식 지정에 설명합니다.  
  
 [VSPackage의 리소스](../../extensibility/internals/resources-in-vspackages.md)  
 관리 되는 Vspackage에서 관리 및 관리 되지 않는 리소스를 사용 하는 방법을 설명 합니다.  
  
 [명령, 메뉴 및 도구 모음](../../extensibility/internals/commands-menus-and-toolbars.md)  
 메뉴, 도구 모음 및 명령 콤보 상자를 포함하는 UI를 만드는 방법을 설명합니다.