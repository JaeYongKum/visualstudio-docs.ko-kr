---
title: DEBUG_ADDRESS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_ADDRESS
helpviewer_keywords:
- DEBUG_ADDRESS structure
ms.assetid: 79f5e765-9aac-4b6e-82ef-bed88095e9ba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 07312208967aeccfbd81f44587f84a43dfebf4c0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101448"
---
# <a name="debugaddress"></a>DEBUG_ADDRESS
이 구조는 주소를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _tagDEBUG_ADDRESS {  
   ULONG32             ulAppDomainID;  
   GUID                guidModule;  
   _mdToken            tokClass;  
   DEBUG_ADDRESS_UNION addr;  
} DEBUG_ADDRESS;  
```  
  
```csharp  
public struct DEBUG_ADDRESS {  
   public uint                ulAppDomainID;  
   public Guid                guidModule;  
   public int                 tokClass;  
   public DEBUG_ADDRESS_UNION addr;  
}  
```  
  
## <a name="terms"></a>용어  
 ulAppDomainID  
 프로세스 id입니다.  
  
 guidModule  
 이 주소를 포함 하는 모듈의 GUID입니다.  
  
 tokClass  
 클래스 또는이 주소의 형식을 확인 하는 토큰입니다.  
  
> [!NOTE]
>  이 값은 기호 공급자 이며 따라서 클래스 형식에 대 한 식별자로 이외의 일반 의미가 없습니다.  
  
 Addr  
 A [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 개별 주소 형식을 설명 하는 구조체의 통합을 포함 하는 구조에 있습니다. 값 `addr`합니다.`dwKind` 제공 되는 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) 합집합을 해석 하는 방법을 설명 하는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 이 구조에 전달 되는 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) 메서드를 입력 합니다.  
  
 **경고 [c + + 전용]**  
  
 경우 `addr.dwKind` 은 `ADDRESS_KIND_METADATA_LOCAL` 쓰고 `addr.addr.addrLocal.pLocal` 값이 아닌 null을 호출 해야 합니다 `Release` 토큰 포인터에:  
  
```  
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL &&  addr.addr.addrLocal.pLocal != NULL)  
{  
    addr.addr.addrLocal.pLocal->Release();  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)