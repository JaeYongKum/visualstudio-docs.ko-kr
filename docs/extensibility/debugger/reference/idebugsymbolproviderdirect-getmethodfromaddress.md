---
title: IDebugSymbolProviderDirect::GetMethodFromAddress | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugSymbolProviderDirect::GetMethodFromAddress
- GetMethodFromAddress
ms.assetid: 33ffd197-1221-41bc-a9f6-f133ebdcb783
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2b164e7e317da54f6ea22131e923c55901acec49
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31122641"
---
# <a name="idebugsymbolproviderdirectgetmethodfromaddress"></a>IDebugSymbolProviderDirect::GetMethodFromAddress
지정 된 디버그 주소에서 메서드에 대 한 정보를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMethodFromAddress(  
   IDebugAddress* pAddress,  
   GUID*          pGuid,  
   DWORD*         pAppID,  
   _mdToken*      pTokenClass,  
   _mdToken*      pTokenMethod,  
   DWORD*         pdwOffset,  
   DWORD*         pdwVersion  
);  
```  
  
```csharp  
int GetMethodFromAddress(  
   IDebugAddress pAddress,  
   out Guid      pGuid,  
   out uint      pAppID,  
   out uint      pTokenClass,  
   out uint      pTokenMethod,  
   out uint      pdwOffset,  
   out uint      pdwVersion  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAddress`  
 [in] 디버그 하 여 표시 되는 주소는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
 `pGuid`  
 [out] 모듈의 고유 식별자입니다.  
  
 `pAppID`  
 [out] 응용 프로그램 도메인의 식별자입니다.  
  
 `pTokenClass`  
 [out] 토큰 나타내는 포함 하는 클래스입니다.  
  
 `pTokenMethod`  
 [out] 토큰을 나타내는 모듈입니다.  
  
 `pdwOffset`  
 [out] 바이트의 시작 부분부터 오프셋은 `pAddress` 매개 변수입니다.  
  
 `pdwVersion`  
 [out] 메서드의 버전 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)