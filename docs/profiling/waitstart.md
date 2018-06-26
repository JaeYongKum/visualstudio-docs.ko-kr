---
title: WaitStart | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 059f05d25f1882cd857dd1e39ea40a58a7c5e1d3
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34571372"
---
# <a name="waitstart"></a>WaitStart
WaitStart 옵션을 사용하면 *VSPerfCmd.exe* Start 하위 명령이 프로파일러가 초기화되었거나 지정된 시간(초)이 경과되었을 때만 결과를 반환합니다. 기본적으로 Start 명령은 즉시 결과를 반환합니다. 프로파일러를 초기화하지 않고 Start 하위 명령이 반환되면 오류가 반환됩니다. 시간(초)을 지정하지 않으면 Start 명령은 무기한 대기합니다.  
  
 WaitStart 옵션은 프로파일러가 초기화되었는지 보장하기 위한 배치 파일에서 유용합니다.  
  
## <a name="syntax"></a>구문  
  
```cmd  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Seconds`  
 Start 하위 명령에서 반환되기 전에 대기할 시간(초)입니다.  
  
## <a name="required-options"></a>필수 옵션  
 WaitStart 옵션은 Start 하위 명령과만 함께 사용할 수 있습니다.  
  
 **Output:** `filename`  
 출력 파일 이름을 지정합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예  
 이 배치 파일 예제에서 Start 명령은 프로파일러가 초기화될 때까지 5초 동안 대기합니다.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5  
if not %errorlevel% 0 goto :error_tag  
VSPerfCmd.exe /Launch:TestApp.exe  
goto :end  
:error_tag  
@echo Could not start Profiler!  
@echo Error %errorlevel%  
:end  
```