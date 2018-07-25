---
title: IDebugSymbolProvider::GetAddressesFromContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromContext
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromContext method
ms.assetid: a3124883-a255-4543-a5ec-e1c7a97beb69
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 09bc0d4fc0a723c259e2897b95abbd8611b10c7d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31119859"
---
# <a name="idebugsymbolprovidergetaddressesfromcontext"></a>IDebugSymbolProvider::GetAddressesFromContext
이 메서드는 디버그 주소 배열로 문서 컨텍스트를 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAddressesFromContext(   
   IDebugDocumentContext2* pDocContext,  
   BOOL                    fStatmentOnly,  
   IEnumDebugAddresses**   ppEnumBegAddresses,  
   IEnumDebugAddresses**   ppEnumEndAddresses  
);  
```  
  
```csharp  
int GetAddressesFromContext(  
   IDebugDocumentContext2  pDocContext,  
   bool                    fStatmentOnly,  
   out IEnumDebugAddresses ppEnumBegAddresses,  
   out IEnumDebugAddresses ppEnumEndAddresses  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pDocContext`  
 [in] 문서 컨텍스트에서 가져왔습니다.  
  
 `fStatmentOnly`  
 [in] True 인 경우, 단일 문으로 디버그 주소를 제한 합니다.  
  
 `ppEnumBegAddresses`  
 [out] 이 문 또는 줄와 관련 된 디버그 시작 주소에 대 한 열거자를 반환 합니다.  
  
 `ppEnumEndAddresses`  
 [out] 반환 된 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) 관련 된이 문 또는 줄 끝 디버그 주소에 대 한 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 문서 컨텍스트는 일반적으로 다양 한 소스 줄을 나타냅니다. 이 방법은 제공 시작 및 끝 주소 디버그가이 줄 합니다. 일부 언어에는 여러 줄 또는 둘 이상의 문을 포함 하는 줄에 걸쳐 있는 문을 허용 합니다. 이 메서드는 단일 문으로 디버그 주소를 제한 하는 플래그를 제공 합니다.  
  
 서식 파일의 경우 처럼 여러 디버그 주소 단일 문에 대 한 것 같습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)