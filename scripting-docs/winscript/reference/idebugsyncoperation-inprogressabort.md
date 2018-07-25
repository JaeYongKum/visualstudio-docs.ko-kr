---
title: IDebugSyncOperation::InProgressAbort | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugSyncOperation.InProgressAbort
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugSyncOperation::InProgressAbort
ms.assetid: bfd0889c-b627-4843-b1c6-b6b918f42d61
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1df0b0ca1d775d4d99e1da5f88a207bd4f78f99b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24728263"
---
# <a name="idebugsyncoperationinprogressabort"></a>IDebugSyncOperation::InProgressAbort
다른 스레드에서 진행 중인 작업을 취소합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT InProgressAbort();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수가 없습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|작업을 취소할 수 없습니다.|  
|`E_ABORT`|작업을 완료할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 프로세스 디버깅 관리자에서 다른 스레드에서 진행 중인 작업을 취소할 디버거 스레드 내에서이 메서드를 호출 합니다.  
  
 경우는 `InProgressAbort` 반환 메서드 작업을 완료할 수 없습니다, `E_ABORT` 최대한 빨리 합니다. 이 메서드가 반환할 수 `E_NOTIMPL` 경우 작업을 취소할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSyncOperation 인터페이스](../../winscript/reference/idebugsyncoperation-interface.md)