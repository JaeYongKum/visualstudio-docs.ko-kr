---
title: IDebugCodeContext3 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8cbbec576b4e7b17f1a87e9d60ed1857fb3157b5
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51733266"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

확장 된 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 모듈 및 프로세스 인터페이스를 검색할 수 있도록 하는 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugCodeContext3 : IDebugCodeContext2  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진에서 구현 하 여 사용 하 여 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 디버그 패키지 합니다.  
  
## <a name="methods"></a>메서드  
 메서드 외에도 `IDebugCodeContext2` 인터페이스에서이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|디버그 모듈의 인터페이스에 대 한 참조를 검색합니다.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|디버그 프로세스의 인터페이스에 대 한 참조를 검색합니다.|  
  
## <a name="remarks"></a>설명  
 일반적으로 구현 하지 않아도 되는 선택적 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

