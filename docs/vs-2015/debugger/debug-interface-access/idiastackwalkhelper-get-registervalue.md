---
title: IDiaStackWalkHelper::get_registerValue | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::get_registerValue method
ms.assetid: 46ac5eee-73a3-44a1-8635-6c58ba193cb6
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 58876436a426a71df3f13df1e5857d9dbdace025
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47550876"
---
# <a name="idiastackwalkhelpergetregistervalue"></a>IDiaStackWalkHelper::get_registerValue
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [IDiaStackWalkHelper::get_registerValue](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkhelper-get-registervalue)합니다.  
  
레지스터의 값을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT get_registerValue (   
   DWORD      index,  
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `index`  
 [in] 값을 [CV_HREG_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md) 를에서 값을 얻기 위해 등록 하는 지정 하는 열거형입니다.  
  
 `pRetVal`  
 [out] 등록의 현재 값을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 크기에도 불구 하 고는 `pRetVal` 매개 변수를 구현만 무엇입니까 레지스터 일반적으로 보유 저장 해야 합니다. 예를 들어는 8 비트 레지스터만 가장 낮은 8-의 비트를 지정된 된 값을 보유합니다. 이 8 비트 값이 메서드에서 반환 하는 경우 64 비트로 확장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [CV_HREG_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md)


