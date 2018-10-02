---
title: 편집기 및 언어 서비스 확장 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK]
ms.assetid: 5653bac9-724f-4948-a820-68ce6aa96365
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e464b46185339bd1a22b433e4784154dbdb818c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564322"
---
# <a name="editor-and-language-service-extensions"></a>편집기 및 언어 서비스 확장
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [편집기 및 언어 서비스 확장](https://docs.microsoft.com/visualstudio/extensibility/editor-and-language-service-extensions)합니다.  
  
Visual Studio 코드 편집기의 대부분의 기능을 확장할 수 있습니다. 편집기는 Windows Presentation Foundation (WPF)에 기반 하 고 관리 코드에 기록 됩니다. 이전 버전의 Visual Studio의 디자인에서이 디자인 다른 하지만 같은 기능을 대부분을 제공 합니다. 편집기를 확장 하는 프레임 워크 MEF (Managed Extensibility)를 사용 합니다.  
  
 Visual Studio SDK 라고도 하는 어댑터를 제공 *shim* 이전 버전용으로 작성 된 Vspackage를 지원 하도록 합니다. 그럼에도 불구 하 고는 기존 VSPackage가 더 나은 성능 및 안정성을 가져올 새 기술 업데이트 하는 것이 좋습니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[편집기 항목 템플릿을 사용하여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)|편집기 항목 템플릿을 사용 하 여 소개 합니다.|  
|[편집기 및 언어 서비스 확장](../extensibility/extending-the-editor-and-language-services.md)|디자인 및 핵심 편집기의 기능을 소개 하 고 확장 하는 방법을 보여 주는 문서에 연결 합니다.|  
|[편집기의 레거시 인터페이스](../extensibility/legacy-interfaces-in-the-editor.md)|기존 코드에서 핵심 편집기에 액세스 하는 방법에 설명 하는 문서에 연결 합니다.|  
|[사용자 지정 편집기 및 디자이너 만들기](../extensibility/creating-custom-editors-and-designers.md)|사용자 지정 편집기를 만드는 방법에 설명 하는 문서에 연결 합니다.|  
|[레거시 언어 서비스 확장성](../extensibility/internals/legacy-language-service-extensibility.md)|Visual Studio 프로그래밍 언어를 통합 하는 방법에 설명 하는 문서에 연결 합니다.|  
|[MEF(Managed Extensibility Framework)](http://msdn.microsoft.com/library/6c61b4ec-c6df-4651-80f1-4854f8b14dde)|Managed Extensibility Framework (MEF)를 소개합니다.|  
|[Windows Presentation Foundation](http://msdn.microsoft.com/library/f667bd15-2134-41e9-b4af-5ced6fafab5d)|Windows Presentation Foundation (WPF)를 소개합니다.|
