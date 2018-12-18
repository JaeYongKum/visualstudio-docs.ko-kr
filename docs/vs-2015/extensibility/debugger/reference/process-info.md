---
title: PROCESS_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PROCESS_INFO
helpviewer_keywords:
- PROCESS_INFO structure
ms.assetid: 260c33cc-a05e-4645-84b6-536d0b3b0537
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b7d99110511f9d126c2545ae2917c67afffb361f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51767123"
---
# <a name="processinfo"></a>PROCESS_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

프로세스에 대 한 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
typedef struct tagPROCESS_INFO {   
   PROCESS_INFO_FIELDS Fields;  
   BSTR                bstrFileName;  
   BSTR                bstrBaseName;  
   BSTR                bstrTitle;  
   AD_PROCESS_ID       ProcessId;  
   DWORD               dwSessionId;  
   BSTR                bstrAttachedSessionName;  
   FILETIME            CreationTime;  
   PROCESS_INFO_FLAGS  Flags;  
} PROCESS_INFO;  
```  
  
```csharp  
public struct PROCESS_INFO {   
   public uint          Fields;  
   public string        bstrFileName;  
   public string        bstrBaseName;  
   public string        bstrTitle;  
   public AD_PROCESS_ID ProcessId;  
   public uint          dwSessionId;  
   public string        bstrAttachedSessionName;  
   public FILETIME      CreationTime;  
   public uint          Flags;  
};  
```  
  
## <a name="members"></a>멤버  
 필드  
 플래그의 조합 된 [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md) 채워진 필드를 지정 하는 열거형입니다.  
  
 bstrFileName  
 프로세스의 전체 경로 이름입니다. 호출에 해당 하는 [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) 매개 변수를 사용 하 여 메서드 `GN_FILENAME`합니다.  
  
 bstrBaseName  
 파일 이름 및 프로세스의 확장입니다. 호출에 해당 하는 `IDebugProcess2::Getname` 매개 변수를 사용 하 여 메서드 `GN_BASENAME`합니다.  
  
 bstrTitle  
 있는 경우 프로세스의 제목입니다. 호출에 해당 하는 `IDebugProcess2::Getname` 매개 변수를 사용 하 여 메서드 `GN_TITLE`합니다.  
  
 ProcessId  
 합니다 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) 프로세스 식별 하는 구조입니다. 호출에 해당 하는 [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md) 메서드.  
  
 dwSessionId  
 이 프로세스에서 실행 되는 디버그 세션의 식별자입니다.  
  
 bstrAttachedSessionName  
 연결 된 세션 이름입니다. 호출에 해당 하는 [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md) 메서드.  
  
 CreationTime  
 프로세스 만든 시간입니다.  
  
 플래그  
 플래그의 조합 된 [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md) 프로세스의 속성을 지정 하는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 이 구조에 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) 메서드 위치에서 채워집니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)   
 [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md)   
 [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)   
 [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)   
 [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)

