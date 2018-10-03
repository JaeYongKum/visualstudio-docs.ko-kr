---
title: GPU 작업(이 프로세스) | Microsoft 문서
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
- vs.cv.threads.timeline.gpuexecution
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 0956edbf-9bcd-4afe-9287-fda628648ca0
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc7741e46d9b7ae3bf7e53e6a07f5601e7dbbd83
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564357"
---
# <a name="gpu-activity-this-process"></a>GPU 작업(이 프로세스)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [GPU 작업 (이 프로세스)](https://docs.microsoft.com/visualstudio/profiling/gpu-activity-this-process)합니다.  
  
동시성 시각화 도우미의 스레드 뷰에 있는 **GPU 작업(이 프로세스)** 세그먼트는 GPU가 현재 프로세스를 대신하여 요청을 처리 중이던 시간을 나타냅니다. 이러한 요청은 DMA(직접 메모리 액세스) 패킷으로 GPU에 전송됩니다. 세그먼트 길이는 GPU가 현재 프로세스를 대신하여 DMA 패킷을 처리 중이던 시간을 나타냅니다.  
  
 GPU 작업 세그먼트를 선택할 때 **현재** 탭의 보고서에 처리된 DMA 패킷에 대한 정보가 표시됩니다. 이 정보에는 DirectX 엔진과 연관된 하드웨어 큐에서 패킷이 대기하는 데 걸린 시간, 패킷을 전송한 프로세스, 패킷을 처리하는 데 필요한 시간이 포함됩니다. 현재 프로세스가 아닌 프로세스가 DMA 패킷을 GPU에 실제로 제출했을 수 있습니다. 동시성 시각화 도우미는 다른 프로세스가 현재 프로세스를 대신하여 GPU로 작업을 제출했을 때를 감지할 수 있습니다.


