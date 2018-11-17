---
title: WinCounter | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff319ffc-f249-4c3f-9eb2-06e392e3ae80
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33a0e13869c46a9e2998252e819442bd61480b4c
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51809298"
---
# <a name="wincounter"></a>WinCounter
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**WinCounter** 옵션은 Windows 또는 응용 프로그램 성능 카운터를 지정하여 프로파일링 실행 동안 설정한 간격에 따라 수집합니다. Windows 및 응용 프로그램 성능 카운터는 프로파일링 데이터 파일에 표시로 나열됩니다. 여러 성능 카운터를 지정하여 별도 옵션에 수집할 수 있습니다.  
  
 기본적으로 카운터는 500밀리초마다 수집됩니다. **AutoMark** 옵션을 사용하여 다른 수집 간격을 지정합니다.  
  
 오직 하나의 **AutoMark** 옵션만 사용됩니다. 여러 **AutoMark** 옵션이 지정된 경우 마지막 옵션이 사용됩니다.  
  
 **WinCounter** 옵션은 **Start** 옵션에만 사용할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
VSPerfCmd.exe /Start:Method /Wincounter:Path [/WinCounter:Path] [AutoMark:Milliseconds] [Options]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Path`  
 Windows 성능 카운터는 PDH 카운터 경로 형식입니다.  
  
## <a name="required-options"></a>필수 옵션  
 **WinCounter** 옵션은 **Start** 옵션에만 사용할 수 있습니다.  
  
 **Start:** `Method`  
 **Start** 옵션은 지정된 프로파일링 방법으로 프로파일러를 초기화합니다.  
  
## <a name="exclusive-options"></a>전용 옵션  
 **AutoMark** 옵션은 **WinCounter** 옵션에만 사용할 수 있습니다.  
  
 **AutoMark:** `Milliseconds`  
 Windows 성능 카운터 데이터 수집 사이에 경과하는 시간(밀리초)을 지정합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 Windows 성능 카운터가 1000밀리초 간격마다 수집되도록 지정됩니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WinCounter:"\Processor(0)\% Processor Time" /WinCounter:"\System\Context Switches/sec" /AutoMark:1000  
```  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)



