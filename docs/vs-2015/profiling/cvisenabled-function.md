---
title: CvIsEnabled 함수 | Microsoft 문서
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkers/CvIsEnabledEx
- cvmarkers/CvIsEnabled
helpviewer_keywords:
- CvIsEnabled method
- CvIsEnabledEx method
ms.assetid: 2e4fea6d-758d-4150-8744-6102a1d58c1c
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 91a8a0a27456299a914b2919aaf169fa72edf540
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51723889"
---
# <a name="cvisenabled-function"></a>CvIsEnabled 함수
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

세션에서 지정된 ETW 공급자를 사용하도록 설정했는지 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CvIsEnabled(  
   _In_ PCV_PROVIDER pProvider  
);  
HRESULT CvIsEnabledEx(  
   _In_ PCV_PROVIDER pProvider,  
   _In_ CV_IMPORTANCE level,  
   _In_ int category  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `category`  
 범주입니다.  
  
 `level`  
 중요도 수준입니다.  
  
 `pProvider`  
 올바른 공급자 개체입니다. NULL일 수 없습니다.  
  
## <a name="return-value"></a>반환 값  
 현재 공급자를 사용할 수 있는 경우 S_OK입니다. 현재 공급자를 사용할 수 없는 경우 S_FALSE입니다. 오류가 발생한 경우 오류 코드입니다. FAILED 매크로를 사용하여 오류 조건을 확인한 후 S_OK/S_FALSE를 확인할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** cvmarkers.h  
  
## <a name="see-also"></a>참고 항목  
 [C++ 라이브러리 참조](../profiling/cpp-library-reference.md)



