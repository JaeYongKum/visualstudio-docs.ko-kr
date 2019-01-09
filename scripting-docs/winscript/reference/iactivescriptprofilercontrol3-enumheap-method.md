---
title: IActiveScriptProfilerControl3::EnumHeap 메서드 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 2799d06d-20dd-4c12-9646-554c0ea3606e
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 25e81a4aa631c142d4444c0578742f68001a108d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097021"
---
# <a name="iactivescriptprofilercontrol3enumheap-method"></a>IActiveScriptProfilerControl3::EnumHeap 메서드
인터페이스를 반환 합니다 ([IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)) 연관된 된 스크립트 엔진의 컨텍스트에서 GC 힙 개체에서 반복을 사용할 수 있는 합니다.  
  
 디버그에서이 메서드를 호출 하거나 릴리스 모드 수 있습니다. UI 스레드가 유휴 상태일 때이 메서드를 호출 해야 합니다. 제외 하 고 스크립트 엔진에 대 한 없는 작업을 수행 하는 메서드를 호출한 후 [iactivescriptprofilerheapenum:: Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md) 때까지 [iactivescriptprofilerheapenum:: Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)S_FALSE를 반환 합니다. 또는 [IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md) 인터페이스 포인터가 릴리스될 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT EnumHeap([out] IActiveScriptProfilerHeapEnum** ppEnum);  
```  
  
#### <a name="parameters"></a>매개 변수  
 ppEnum  
 [out] 반환 된 [IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 HRESULT입니다.