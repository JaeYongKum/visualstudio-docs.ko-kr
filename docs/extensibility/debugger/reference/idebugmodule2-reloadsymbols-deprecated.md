---
title: IDebugModule2::ReloadSymbols_Deprecated | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugModule2::ReloadSymbols
helpviewer_keywords:
- IDebugModule2::ReloadSymbols method
ms.assetid: 0f9f0133-7d58-4cd9-a6ca-1141e095749d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 09f2e81699683ec49155faceb375da3d636ed4c4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49934043"
---
# <a name="idebugmodule2reloadsymbolsdeprecated"></a>IDebugModule2::ReloadSymbols_Deprecated
사용되지 않습니다. 사용 하지 마세요. 이 모듈의 기호를 다시 로드합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReloadSymbols(   
   LPCOLESTR pszUrlToSymbols,  
   BSTR*     pbstrDebugMessage  
);  
```  
  
```csharp  
int ReloadSymbols(   
   string     pszUrlToSymbols,  
   out string pbstrDebugMessage  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszUrlToSymbols`  
 [in] 기호 저장소에 대 한 경로입니다.  
  
 `pbstrDebugMessage`  
 [out] 모듈 창에서 모듈 이름 오른쪽에 표시 되는 상태 또는 오류 메시지와 같은 정보 메시지를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다. 디버그 엔진을 항상 반환 `E_FAIL`합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 더 이상 지원 합니다. 구현 된 [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md) 메서드 대신 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)