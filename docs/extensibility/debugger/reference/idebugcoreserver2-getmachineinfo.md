---
title: IDebugCoreServer2::GetMachineInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCoreServer2::GetInfo
helpviewer_keywords:
- IDebugCoreServer2::GetInfo
ms.assetid: 8fa1a1d3-9fcb-4fb3-bf4e-e7172ac08d77
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: cabb1f6ccd241e905b032d79e9cdcb74d11bd77b
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="idebugcoreserver2getmachineinfo"></a>IDebugCoreServer2::GetMachineInfo
핵심 서버에서 실행 중인 컴퓨터에 대 한 설명을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetInfo(   
   MACHINE_INFO_FIELDS Fields,  
   MACHINE_INFO*       pMachineInfo  
);  
```  
  
```csharp  
int GetInfo(   
   enum_ MACHINE_INFO_FIELDS  Fields,  
   MACHINE_INFO[]             pMachineInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Fields`  
 [in] 플래그의 조합 된 [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md) 의 필드를 지정 하는 열거형 `pMachineInfo` 작성 됩니다.  
  
 `pMachineInfo`  
 [out에서] A [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md) 는 컴퓨터에 대 한 설명을 포함 하는 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md)   
 [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md)
