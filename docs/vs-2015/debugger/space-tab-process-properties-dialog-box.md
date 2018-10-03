---
title: 프로세스 속성 대화 상자, 공간 탭 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: c4de1866-7447-48f7-aa88-28ad92c0b930
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 78f65edeec910bd0667bfc369ff1d4cbddb54813
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551892"
---
# <a name="space-tab-process-properties-dialog-box"></a>프로세스 속성 대화 상자, 공간 탭
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [프로세스 속성 대화 상자, 공간 탭](https://docs.microsoft.com/visualstudio/debugger/space-tab-process-properties-dialog-box)합니다.  
  
사용 된 **공간** 프로세스의 주소 공간을 검사 하는 탭 합니다. 표시할 합니다 [프로세스 속성 대화 상자](../debugger/process-properties-dialog-box.md), 포커스를 이동 하는 [프로세스 뷰에](../debugger/processes-view.md) 창입니다. 선택한 프로세스 노드 트리에서 선택 **속성** 에서 합니다 **보기** 메뉴.  
  
 다음 설정을 사용할 합니다 **공간** 탭:  
  
|입력|설명|  
|-----------|-----------------|  
|**으로 표시 된 공간 표시**|이 목록 상자를 사용 하 여 (이미지, 매핑, 예약 된 또는 할당 되지 않은) 공간의 범주를 선택 합니다.|  
|**실행 가능한 바이트**|선택한 범주에서이 프로세스를 사용 하는 주소 공간을 모두의 합계입니다. 실행 메모리는 메모리 프로그램을 실행할 수 있습니다 하지만 수 하지 읽거나 쓸입니다.|  
|**Exec 읽기 전용 바이트**|선택한 범주에서이 프로세스를 사용 하는 읽기 전용 속성 사용의 주소 공간을 모두의 합계입니다. Exec 읽기 전용 메모리는 메모리 될 수 있을 뿐만 아니라 읽기 수입니다.|  
|**Exec-읽기-쓰기 바이트 수**|선택한 범주에서이 프로세스를 사용 하는 읽기 / 쓰기 속성 사용의 주소 공간을 모두의 합계입니다. Exec-읽기-쓰기 메모리는 프로그램에서 뿐만 아니라 읽기 및 수정할 수 있는 메모리입니다.|  
|**Exec-쓰기 복사본 (바이트)**|선택한 범주에서 프로그램 실행 뿐만 아니라 읽기 및 쓰기 수 있는 모든 주소 공간의 합 합니다. 이 유형의 보호는 메모리에서 프로세스 간에 공유 해야 하는 경우에 사용 됩니다. 공유 프로세스 메모리를 읽기만 하는 경우는 모든 메모리를 사용 합니다는 동일한 합니다. 공유 프로세스 쓰기 액세스를 필요로 하는 경우 프로세스에 대 한이 메모리는 복사를 수행할 수는 있습니다.|  
|**액세스할 수 없는 바이트**|선택한 범주에서 프로세스를 사용 하는 것을 방지 하는 주소 공간을 모두의 합계입니다. 작성 하는 경우 액세스 위반이 생성 됩니다 또는 읽기를 시도 합니다.|  
|**읽기 전용 바이트**|선택한 범주에서 사용할 수 있을 뿐만 아니라 읽을 수 있는 주소 공간을 모두 합한 합니다.|  
|**읽기-쓰기 바이트 수**|선택한 범주에 대 한 읽기 및 쓰기를 허용 하는 주소 공간을 모두 합한 합니다.|  
|**쓰기 / 복사 바이트**|선택한 범주에 대 한 주소 공간을 모두 합한 있도록 쓰기 아니라 읽기에 대 한 메모리를 공유 합니다. 프로세스에서이 메모리를 읽는 경우에 동일한 메모리를 공유할 수 있습니다. 그러나 공유 프로세스에서이 공유 메모리에 대 한 읽기/쓰기 액세스할 수 있도록 하려는 경우 해당 메모리의 복사본 작성 하기 위한 이루어집니다.|


