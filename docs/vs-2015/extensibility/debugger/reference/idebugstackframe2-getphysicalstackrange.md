---
title: IDebugStackFrame2::GetPhysicalStackRange | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
helpviewer_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
ms.assetid: 2f6992e2-ac1c-433f-83b7-a7f83a4ce63d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8c48943ba68bf4090fd6d2b65b3ffba1f5018af2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47554863"
---
# <a name="idebugstackframe2getphysicalstackrange"></a>IDebugStackFrame2::GetPhysicalStackRange
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugStackFrame2::GetPhysicalStackRange](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugstackframe2-getphysicalstackrange)합니다.  
  
스택 프레임과 연결 된 물리적 주소 범위의 컴퓨터 종속 표현을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetPhysicalStackRange (   
   UINT64* paddrMin,  
   UINT64* paddrMax  
);  
```  
  
```csharp  
int GetPhysicalStackRange (   
   out ulong paddrMin,  
   out ulong paddrMax  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `paddrMin`  
 [out] 이 스택 프레임과 연결 된 가장 낮은 물리적 주소를 반환 합니다.  
  
 `paddrMax`  
 [out] 이 스택 프레임과 연결 된 가장 높은 물리적 주소를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드에서 반환 되는 정보는 스택 프레임을 정렬 하려면 세션 디버그 관리자 SDM ()가 사용 됩니다.  
  
 호출 스택, 즉 증가, 점점 더 낮은 메모리 주소를 새 스택 프레임 추가 되어 있는지 간주 됩니다. 런타임 아키텍처는이 가정을 일치 하는 실제 스택에 범위를 제공 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)

