---
title: 그래픽 픽셀 기록 | Microsoft Docs
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
- vs.graphics.pixelhistory
ms.assetid: 0a2cbde5-1ad9-487e-857c-a3664158c268
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4b37dab129c5eb19825746177cb30a5e20493399
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47552504"
---
# <a name="graphics-pixel-history"></a>그래픽 픽셀 기록
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [그래픽 픽셀 기록](https://docs.microsoft.com/visualstudio/debugger/graphics/graphics-pixel-history)합니다.  
  
Visual Studio Graphics Analyzer의 그래픽 픽셀 기록 창을 사용하면 게임 또는 앱의 프레임 중에 발생하는 Direct3D 이벤트가 특정 픽셀에 어떻게 영향을 주는지를 파악할 수 있습니다.  
  
 다음은 픽셀 기록 창입니다.  
  
 ![기록에 세 가지 Direct3D 이벤트가 있는 픽셀입니다. ](../debugger/media/gfx-diag-demo-pixel-history-orientation.png "gfx_diag_demo_pixel_history_orientation")  
  
## <a name="understanding-the-pixel-history-window"></a>픽셀 기록 창 이해  
 픽셀 기록을 사용하면 프레임 중 Direct3D 이벤트가 렌더링 대상의 특정 픽셀에 어떻게 영향을 주는지를 분석할 수 있습니다. 후속 이벤트 또는 동일 이벤트의 후속 기본 형식이 픽셀의 최종 색 값을 계속해서 변경하더라도 특정 Direct3D 이벤트에 대한 렌더링 문제를 확인할 수 있습니다. 예를 들어 픽셀이 잘못 렌더링되어 다른 반투명 픽셀로 가려져서 해당 색이 프레임 버퍼에서 섞이는 현상이 발생할 수 있습니다. 렌더링 대상의 최종 내용만으로는 이러한 종류의 문제를 진단하기가 어렵습니다.  
  
 픽셀 기록 창에는 선택한 프레임이 재생되는 동안 픽셀의 전체 기록이 표시됩니다. 합니다 **최종 프레임 버퍼** 창의 맨 끝에서 제공 된 프레임 및 화면 같은 픽셀에 대 한 추가 정보와 함께 프레임의 프레임 버퍼에 기록 되는 색을 표시 좌표입니다. 이 영역도 포함 합니다 **알파 렌더링** 확인란 합니다. 이 확인란을 선택 합니다 **최종 프레임 버퍼** 색과 중간 색 값은 체크 무늬 패턴을 통해 투명도 사용 하 여 표시 됩니다. 확인란의 선택을 취소하면 색 값의 알파 채널을 무시합니다.  
  
 창의 아래 부분을 함께 픽셀의 색에 영향을 준 이벤트를 표시 합니다 **초기** 하 고 **최종** 의 초기 및 최종 색 값을 나타내는 의사 (pseudo) 이벤트 버퍼에서 섞이는 현상이 픽셀입니다. 초기 색상 값은 픽셀의 색상을 변경한 첫 번째 이벤트(일반적으로 `Clear` 이벤트)에 의해 결정됩니다. 다른 이벤트가 픽셀에 영향을 주지 않은 경우에도 픽셀의 기록에는 항상 이 두 의사(pseudo) 이벤트가 포함됩니다. 간에 표시 되는 다른 이벤트가 픽셀에 영향을 줄 수 있는 기회를 경우 합니다 **초기** 하 고 **최종** 이벤트입니다. 이벤트를 확장하여 세부 정보를 표시할 수 있습니다. 렌더링 대상을 지우는 이벤트와 같은 간단한 이벤트의 경우 이벤트의 영향은 단순한 색 값입니다. 반면 그리기 호출 등의 보다 복잡한 이벤트는 픽셀 값에 영향을 줄 수 있는 기본 형식을 하나 이상 생성합니다.  
  
 이벤트에 의해 그려진 기본 형식은 해당 형식과 인덱스 및 개체의 총 기본 형식 수로 식별할 수 있습니다. 예를 들어, 같은 식별자 **(6214)의 삼각형 1456/6214** 해당 기본 형식이 6214 개 삼각형으로 구성 된 개체의 1456 번째 삼각형에 해당 함을 의미 합니다. 각 기본 형식 식별자 왼쪽에는 해당 기본 형식이 픽셀에 준 영향을 요약하여 보여 주는 아이콘이 있습니다. 픽셀 색에 영향을 주는 기본 형식은 결과 색으로 채워진 모퉁이가 둥근 사각형으로 표시됩니다. 픽셀 색에 영향을 주지 않도록 제외된 기본 형식은 픽셀이 제외된 이유를 나타내는 아이콘으로 표시됩니다. 이러한 아이콘은 섹션에서 설명한 [기본 형식 제외](../debugger/graphics-pixel-history.md#exclusion) 이 문서의 뒷부분에 나오는.  
  
 각 기본 형식을 확장하면 픽셀 셰이더 출력이 기존 픽셀 색과 병합되어 결과 색을 생성한 방식을 점검할 수 있습니다. 또한 여기서 기본 형식과 연결된 픽셀 셰이더를 검사하거나 디버그할 수도 있으며 꼭짓점 셰이더 노드를 더 확장하여 꼭짓점 셰이더 입력을 검사할 수도 있습니다.  
  
###  <a name="exclusion"></a> 기본 형식 제외  
 여러 가지 이유로 인해 픽셀 색에 영향을 주지 않도록 기본 형식을 제외할 수 있습니다. 각 이유는 아래 테이블에서 설명하는 아이콘으로 나타냅니다.  
  
|아이콘|제외 이유|  
|----------|--------------------------|  
|![깊이 테스트 실패 아이콘. ](../debugger/media/vsg-hist-icon-failed-depth.png "vsg_hist_icon_failed_depth")|픽셀이 깊이 테스트를 통과하지 못해 제외되었습니다.|  
|![가 위 테스트 실패 아이콘입니다. ](../debugger/media/vsg-hist-icon-failed-scissor.png "vsg_hist_icon_failed_scissor")|픽셀이 가위 테스트를 통과하지 못해 제외되었습니다.|  
|![스텐실 테스트 실패 아이콘입니다. ](../debugger/media/vsg-hist-icon-failed-stencil.png "vsg_hist_icon_failed_stencil")|픽셀이 스텐실 테스트를 통과하지 못해 제외되었습니다.|  
  
### <a name="draw-call-exclusion"></a>그리기 호출 제외  
 그리기 호출의 모든 기본 형식이 테스트에 실패하여 영향을 미치는 렌더링 대상에서 제외되는 경우 그리기 호출을 확장할 수 없고 제외 이유에 해당하는 아이콘을 옆에 표시할 수 없습니다. 그리기 호출 예외가 발생하는 이유는 기본 형식 제외 원인과 유사하며 해당 아이콘도 마찬가지입니다.  
  
### <a name="viewing-and-debugging-shader-code"></a>셰이더 코드 보기 및 디버그  
 셰이더와 연관된 기본 형식 아래에 있는 컨트롤을 사용하여 꼭짓점, 헐, 도메인, 기하 도형 및 픽셀 셰이더에 대한 코드를 검사하고 디버그할 수 있습니다.  
  
##### <a name="to-view-a-shaders-source-code"></a>셰이더의 소스 코드를 보려면  
  
1.  에 **그래픽 픽셀 기록** 창 셰이더에 해당 하는 그리기 호출을 찾아 검토 하 고 확장 하려는 합니다.  
  
2.  방금 확장한 그리기 호출에서 관심 있는 문제를 보여 주는 기본 형식을 선택하고 확장합니다.  
  
3.  관심이 기본 형식에서 셰이더 제목 링크를 따라-예를 들어, 링크를 클릭 **꼭 짓 점 셰이더 obj:30** 꼭 짓 점 셰이더 소스 코드를 볼 수 있습니다.  
  
    > [!TIP]
    >  개체 번호 **obj:30**, 개체 테이블 및 파이프라인 단계 창 에서처럼 Graphics Analyzer 인터페이스 전체에서이 셰이더를 식별 합니다.  
  
##### <a name="to-debug-a-shader"></a>셰이더를 디버그하려면  
  
1.  에 **그래픽 픽셀 기록** 창 셰이더에 해당 하는 그리기 호출을 찾아 검토 하 고 확장 하려는 합니다.  
  
2.  그런 다음 방금 확장한 그리기 호출에서 관심 있는 문제를 보여 주는 기본 형식을 선택하고 확장합니다.  
  
3.  관심이 있다면 기본 선택 **디버깅 시작**합니다. HLSL 디버거의 이 진입점은 해당 기본 형식에 대한 셰이더의 첫 번째 호출 즉, 셰이더에서 처리되는 첫 번째 픽셀 또는 꼭짓점으로 기본 설정됩니다. 기본 형식에는 픽셀이 하나만 연결되어 있지만 선과 삼각형의 경우 둘 이상의 꼭짓점 셰이더 호출이 있습니다.  
  
     하는 특정 꼭 짓 점에 대해 꼭 짓 점 셰이더 호출을 디버그 하 고 VertexShader 제목 링크를 확장 하 고 관심이 꼭 짓 점 찾기, 선택한 **디버깅 시작** 옆에 있는 합니다.  
  
### <a name="links-to-graphics-objects"></a>그래픽 개체에 대한 링크  
 픽셀 기록에서 그래픽 이벤트를 파악하려면 이벤트 시작 시의 장치 상태에 대한 정보 또는 이벤트가 참조하는 Direct3D 개체에 대한 정보가 필요할 수 있습니다. 픽셀 기록에서 각 이벤트에 대 한 합니다 **그래픽 픽셀 기록** 상태와 관련 개체 당시 최신 장치에 대 한 링크를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 누락 된 장치 상태로 인해 개체](../debugger/walkthrough-missing-objects-due-to-device-state.md)   
 [연습: 음영으로 인한 렌더링 오류 디버그](../debugger/walkthrough-debugging-rendering-errors-due-to-shading.md)


