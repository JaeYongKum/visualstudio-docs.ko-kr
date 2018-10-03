---
title: 'DA0506: 프로파일링 중인 프로세스에 할당되는 최대 전용 바이트 | Microsoft 문서'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.rules.DA0506
- vs.performance.DA0506
- vs.performance.506
ms.assetid: e9c43554-9a85-4d98-9fa4-3b19986e7b62
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e2475c0c5c8755b89e790a0e10330c9832e7474d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47556151"
---
# <a name="da0506-maximum-private-bytes-allocated-for-the-process-being-profiled"></a>DA0506: 프로파일링 중인 프로세스에 할당되는 최대 전용 바이트
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [DA0506: 프로 파일링 중인 프로세스에 할당 된 최대 전용 바이트](https://docs.microsoft.com/visualstudio/profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled)합니다.  
  
규칙 Id | DA0506 |  
| 범주 | 리소스 모니터링 |  
| 프로 파일링 방법을 | 모든 |  
| 메시지 | 이 정보는 참고용 으로만 수집 되었습니다. Process Private Bytes 카운터는 프로파일링하고 있는 프로세스에 의해 할당된 가상 메모리를 측정합니다. 값은 모든 측정 간격에 걸쳐 관찰 된 최대값을 보고 합니다. |  
| 규칙 유형 | 정보 |  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링할 경우 이 규칙을 트리거하려면 10개 이상의 샘플을 수집해야 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 메시지는 프로세스가 현재 할당한 가상 메모리의 최대 크기(바이트)를 보고합니다(전용 바이트). 전용 바이트는 프로세스 내에서 실행되는 스레드만 액세스할 수 있는, 프로세스에 의해 할당된 가상 메모리 위치를 나타냅니다.  
  
 32비트 컴퓨터에서 실행되는 32비트 프로세스의 경우 프로세스 중 전용 부분의 상한은 2GB입니다. 32비트 프로세스는 [/3GB](http://go.microsoft.com/fwlink/?LinkId=177831) Boot.ini 스위치를 사용해서 최대 3GB의 가상 메모리를 얻을 수 있습니다. 64비트 컴퓨터에서 실행되는 32비트 프로세스는 전용 가상 메모리를 4GB까지 확보할 수 있습니다.  
  
 64비트 컴퓨터에서 실행되는 64비트 프로세스는 전용 가상 메모리를 8TB까지 확보할 수 있습니다.  
  
 보고된 값은 프로파일링되는 프로세스가 활성 상태였던 모든 측정 간격에 대한 최대값입니다.  
  
 프로세스 주소 공간에 대한 자세한 내용은 Windows 메모리 관리 설명서에서 [Virtual Address Space](http://go.microsoft.com/fwlink/?LinkId=177832)(가상 주소 공간)를 참조하세요.  
  
## <a name="how-to-use-rule-data"></a>규칙 데이터를 사용하는 방법  
 보고된 값을 사용하여 프로그램의 여러 가지 버전이나 빌드에 대한 성능을 비교하거나 여러 가지 프로파일링 시나리오에서 응용 프로그램의 성능을 파악합니다.  
  
 프로세스 전용 바이트의 최대값이 프로세스 주소 공간의 최대 확장값을 구조적으로 제한한 크기에 근접할 경우 메모리 예외가 발생할 수 있습니다. 자세한 내용은 MSDN Magazine에서 [Investigating Memory Issues](http://go.microsoft.com/fwlink/?LinkID=177833)(메모리 문제 검사)를 참조하세요.


