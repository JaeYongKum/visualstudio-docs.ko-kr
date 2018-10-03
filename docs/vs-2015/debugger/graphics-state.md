---
title: 그래픽 상태 | Microsoft Docs
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
- vs.graphics.statewindow
ms.assetid: 97e7757e-c372-4626-8149-99a81367a0e1
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 00b53745cc7a166d32633897c65888f4018f6068
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47551408"
---
# <a name="graphics-state"></a>그래픽 상태
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [그래픽 상태](https://docs.microsoft.com/visualstudio/debugger/graphics/graphics-state)합니다.  
  
Visual Studio 그래픽 진단의 상태 창은 그리기 호출과 같은 현재 이벤트 시간에 활성화된 그래픽 상태를 이해하는 데 도움이 됩니다.  
  
## <a name="understanding-the-state-window"></a>상태 창 이해  
 상태 창은 렌더링에 영향을 주는 상태를 수집하고 한 장소에서 계층적으로 표시합니다. 앱이 사용하는 Direct3D 버전에 따라 상태 창에 표시되는 정보가 달라질 수도 있습니다.  
  
### <a name="state-views"></a>상태 보기  
 다양한 방법으로 상태 테이블을 볼 수 있습니다.  
  
|보기|설명|  
|----------|-----------------|  
|API 입력 상태 보기|이 보기는 상태를 구성하는 Direct3D 개체에 유사한 레이아웃으로 상태를 표시합니다.|  
|논리 입력 상태 보기|이 보기는 상태를 구성하는 Direct3D 개체의 레이아웃을 미러링하지 않는 논리 뷰로 상태를 표시합니다.|  
|고정된 상태 보기|고정된 상태 보기는 계층 구조 대신 정규화된 이름을 포함하는 플랫 목록에 고정된 상태 항목을 표시합니다. 이 보기를 통해 적은 수의 줄에서 다양한 상태 번들의 많은 상태 항목을 볼 수 있습니다.|  
  
##### <a name="to-change-the-state-view"></a>상태 보기를 변경하려면  
  
-   상태 창 왼쪽 위, 제목 표시줄 바로 아래에서 사용하려는 상태 보기 스타일에 해당하는 단추를 선택합니다.  
  
    -   **API 입력된 상태 보기 표시**  
  
    -   **논리 상태 보기 표시**  
  
    -   **고정 된 상태 보기 표시**  
  
> [!IMPORTANT]
>  상태를 고정 해야 합니다 **표시 API 입력 상태** 또는 **논리 상태 표시** 에 표시 하려면을 **표시 고정 된 상태 보기**.  
  
### <a name="state-table-format"></a>상태 테이블 형식  
 상태 창에는 여러 정보 열이 표시됩니다.  
  
|열|설명|  
|------------|-----------------|  
|이름|상태 항목의 이름입니다. 이 항목이 상태 번들을 나타내는 경우 항목을 확장하여 표시할 수 있습니다.<br /><br /> 에 **API 입력 상태 보기** 하 고 **논리 상태 보기** 상태, 상태 간의 계층 관계를 표시할 이름이 들여쓰기 됩니다.<br /><br /> 에 **고정 된 상태 보기** 상태, 정규화 된 이름이 플랫 목록에 표시 됩니다.|  
|값|상태 항목의 값입니다.|  
|형식|상태 항목의 형식입니다.|  
  
### <a name="changed-state"></a>변경된 상태  
 그래픽 상태는 일반적으로 후속 그리기 호출 간에 점진적으로 변경되며, 상태가 잘못 변경될 경우 많은 종류의 렌더링 문제가 발생합니다. 이전 그리기 호출 이후 변경된 상태를 찾기 쉽도록 변경된 상태는 별표로 표시되고 빨간색으로 나타납니다. 이는 상태 자체뿐 아니라 부모 상태 항목에도 적용되므로 가장 높은 수준에서 변경된 상태를 쉽게 파악한 후 세부 정보로 드릴다운할 수 있습니다.  
  
### <a name="pinning-state"></a>고정 상태  
 많은 앱은 유사한 개체를 순차적으로 렌더링하고 알려진 상태 집합을 변경하기 때문에 그리기 호출 간에 이동할 때 상태가 어떻게 변경되는지 확인할 수 있도록 변경 상태를 제자리에 고정하는 것이 유용한 경우가 있습니다.  
  
 이는 특정 상태의 변경이 문제의 원인으로 격리된 경우에도 유용할 수 있습니다.  
  
##### <a name="to-pin-state-in-place"></a>상태를 제자리에 고정하려면  
  
1.  상태 창에서 관심 있는 상태를 찾습니다. 관심 있는 세부 정보를 찾기 위해 상위 수준 상태를 확장해야 할 수도 있습니다.  
  
2.  관심 있는 상태 위에 커서를 놓습니다. 상태 항목의 왼쪽에 고정 아이콘이 나타납니다.  
  
3.  고정 아이콘을 선택하여 상태 항목을 제자리에 고정합니다.


