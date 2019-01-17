---
title: IActiveScriptSiteDebug 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSiteDebug interface
ms.assetid: 2557ee09-688b-4c03-a821-180c24dfa0e6
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 339325686d2a98e34c6e9f96056612769a9e110e
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348310"
---
# <a name="iactivescriptsitedebug-interface"></a>IActiveScriptSiteDebug 인터페이스
스마트 호스트를 구현 하는 `IActiveScriptSiteDebug` 문서 관리를 수행 하 고 디버깅에 참여 하는 인터페이스입니다. 합니다 `IActiveScriptSite` 개체에는 일반적으로의 구현을 제공 합니다 `IActiveScriptSiteDebug` 인터페이스입니다. 이 작업을 호출 합니다 `IActiveScriptSite::QueryInterface` 메서드를 `IActiveScriptSiteDebug` 인터페이스입니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IActiveScriptSiteDebug` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptSiteDebug::GetDocumentContextFromPosition](../../winscript/reference/iactivescriptsitedebug-getdocumentcontextfromposition.md)|언어 엔진에서 사용 하 여 위임할 `IDebugCodeContext::GetSourceContext`합니다.|  
|[IActiveScriptSiteDebug::GetApplication](../../winscript/reference/iactivescriptsitedebug-getapplication.md)|이 스크립트 사이트와 연결 된 디버그 응용 프로그램 개체를 반환 합니다.|  
|[IActiveScriptSiteDebug::GetRootApplicationNode](../../winscript/reference/iactivescriptsitedebug-getrootapplicationnode.md)|스크립트는 아래 문서를 추가할 응용 프로그램 노드를 가져옵니다.|  
|[IActiveScriptSiteDebug::OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md)|스마트 호스트를 런타임 오류를 처리 하는 방법을 결정할 수 있습니다.|