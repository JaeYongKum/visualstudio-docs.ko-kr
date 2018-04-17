---
title: SetWefProcessId 메서드 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9dbd5a9ffb2ff9b3833dc8007fdfafb4b1a35857
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="setwefprocessid-method"></a>SetWefProcessId 메서드
  웹 확장 프레임 워크 (WEF) 콘텐츠를 실행 하는 프로세스 식별자를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetWefProcessId(  
    [in] DWORD dwProcessId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|*dwProcessId*|WEF 콘텐츠 실행을 위해 사용할 수 있는 프로세스 식별자입니다.|  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공적으로 완료되었는지 여부를 나타내는 HRESULT 값입니다.  
  
## <a name="remarks"></a>설명  
 WEF 콘텐츠 프로세스 생성 후 있지만 WEF 콘텐츠를 실행 하기 전에이 메서드를 호출 해야 합니다.  
  
 WEF 콘텐츠 프로세스에 디버거를 연결 하도록 개발 환경을 원하는 환경이 메서드의 구현에서이 작업을 수행 해야 합니다.  
  
  