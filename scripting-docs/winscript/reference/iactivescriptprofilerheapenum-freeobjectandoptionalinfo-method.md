---
title: 'Iactivescriptprofilerheapenum:: Freeobjectandoptionalinfo 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fdd5f7cc-be4e-4c13-a181-6320d26b44eb
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8dd2b827deba31af1958842cf0dacd2a85f4260d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095695"
---
# <a name="iactivescriptprofilerheapenumfreeobjectandoptionalinfo-method"></a>IActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo 메서드
지정 된 해제 [PROFILER_HEAP_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 구조 및 관련 [PROFILER_HEAP_OBJECT_OPTIONAL_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 요소입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT FreeObjectAndOptionalInfo (    [in] ULONG celt,    [in, size_is(celt)] PROFILER_HEAP_OBJECT** heapObjects);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 사용 가능한 개체의 수입니다.  
  
 `heapObjects`  
 배열을 [PROFILER_HEAP_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 HRESULT입니다.