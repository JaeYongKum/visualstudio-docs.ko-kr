---
title: IDebugCoreServer2::GetMachineUtilities_V7 | Microsoft Docs
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
- IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 217118d96fbcf50f267570bcd1c26abd5d8128c3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549712"
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDebugCoreServer2::GetMachineUtilities_V7](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcoreserver2-getmachineutilities-v7)합니다.  
  
이 메서드는 서버에 대 한 시스템 유틸리티를 가져옵니다.  
  
> [!NOTE]
>  이 메서드는 사용 되지 않는: 사용 하지 마세요 ([!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 항상 반환 `E_NOTIMPL` 이 메서드를 호출 하는 경우). 기록을 위해 보존 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetMachineUtilities_V7(  
   IDebugMDMUtil2_V7** ppUtil  
);  
```  
  
```csharp  
int GetMachineUtilities_V7(  
   out IDebugMDMUtil2_V7 ppUtil  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppUtil`  
 [out] 반환 된 `IDebugMDMUtil2_V7` 머신 유틸리티 정보를 나타내는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 항상 반환 `E_NOTIMPL`, 메서드가 구현 되지 않았음을 나타내는입니다.  
  
## <a name="remarks"></a>설명  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 항상 반환 `E_NOTIMPL` 이 메서드를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)
