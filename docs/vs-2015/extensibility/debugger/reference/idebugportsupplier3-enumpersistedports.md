---
title: IDebugPortSupplier3::EnumPersistedPorts | Microsoft Docs
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
- IDebugPortSupplier3::EnumPersistedPorts
helpviewer_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
ms.assetid: 1c3dead3-5d6c-4067-8418-4015f0b0dd07
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9c6378f6957bc61f2f370f137d8d095dbdc380da
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51809352"
---
# <a name="idebugportsupplier3enumpersistedports"></a>IDebugPortSupplier3::EnumPersistedPorts
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 메서드는 지속형된 포트 목록 열거를 허용 하는 개체를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumPersistedPorts(  
   BSTR_ARRAY         PortNames,  
   IEnumDebugPorts2** ppEnum  
);  
```  
  
```csharp  
int EnumPersistedPorts(  
   BSTR_ARRAY           PortNames,  
   out IEnumDebugPorts2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `PortNames`  
 [in] A [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md) 찾아 지속형된 포트 간의 반환 포트 이름의 목록을 포함 하는 구조입니다. 이러한 이름 가진 지속형된 포트만 반환 됩니다.  
  
 `ppEnum`  
 [out] 구현 하는 개체를 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md) 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 지속형된 포트는 포트 공급자가 인스턴스화되고 포트 공급자 소멸 되 면 저장 하는 경우 로드 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)   
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)   
 [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)

