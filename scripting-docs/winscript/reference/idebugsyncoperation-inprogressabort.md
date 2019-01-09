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
ms.openlocfilehash: cab8bae7f131d24c1a2c7272dc8d1178e12bf0e6
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095526"
---
# <a name="idebugsyncoperationinprogressabort"></a>IDebugSyncOperation::InProgressAbort
다른 스레드에서 진행 중인 작업을 취소합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT InProgressAbort();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수 없이 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|작업을 취소할 수 없습니다.|  
|`E_ABORT`|작업을 완료할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 프로세스 디버그 관리자는 다른 스레드에서 진행 중인 작업을 취소할 디버거 스레드 내에서이 메서드를 호출 합니다.  
  
 경우는 `InProgressAbort` 반환 메서드 작업을 완료할 수 없습니다, `E_ABORT` 최대한 빨리 합니다. 이 메서드가 반환할 수 `E_NOTIMPL` 경우 작업을 취소할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSyncOperation 인터페이스](../../winscript/reference/idebugsyncoperation-interface.md)