---
title: UnInit | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cd4fc0b-974a-4e61-9ea8-0aaa1a0c52ea
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4cd66d7329fa4bfc288f3d60879e45cc86ded94e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47549663"
---
# <a name="uninit"></a>UnInit
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [UnInit](https://docs.microsoft.com/visualstudio/debugger/graphics/uninit)합니다.  
  
그래픽 로그 파일을 종료하고 닫고 앱이 그래픽 정보를 기록하는 동안 사용된 리소스를 확보합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void UnInit();  
```  
  
## <a name="remarks"></a>설명  
 `UnInit` 클래스의 인스턴스가 소멸될 때 `VsgDbg` 가 자동으로 호출됩니다. `VsgDbg` 인스턴스가 그래픽 정보를 기록하지 않는 경우 아무런 영향이 없습니다.  
  
 `UnInit` 클래스의 인스턴스에서 `VsgDbg`가 호출된 경우 `Init`를 호출하여 새 그래픽 로그 파일을 만들고 `UnInit`를 호출하여 종료할 수 있습니다. 동일한 `VsgDbg` 인스턴스를 사용하여 원하는 횟수만큼 이 작업을 반복하여 여러 독립 그래픽 로그 파일을 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Init](../debugger/init.md)



