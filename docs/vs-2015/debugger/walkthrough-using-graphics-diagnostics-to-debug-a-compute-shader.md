---
title: '연습: 그래픽 진단을 사용 하 여 계산 셰이더 디버깅 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69287456-644b-4aff-bd03-b1bbb2abb82a
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 55f0b9de879011110d8df46c0e4d738265b0fa34
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51730649"
---
# <a name="walkthrough-using-graphics-diagnostics-to-debug-a-compute-shader"></a>연습: 그래픽 진단을 사용하여 컴퓨팅 셰이더 디버깅
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 연습에서는 Visual Studio 그래픽 진단 도구를 사용하여 잘못된 결과를 생성하는 컴퓨팅 셰이더를 조사하는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 설명합니다.  
  
-   **그래픽 이벤트 목록** 을 사용하여 문제의 잠재적인 원인을 찾습니다.  
  
-   사용 하는 **그래픽 이벤트 호출 스택** 셰이더 DirectCompute에서 실행 되는 계산을 확인 하려면 `Dispatch` 이벤트입니다.  
  
-   사용 하는 **그래픽 파이프라인 단계** 창과 HLSL 디버거를 문제의 원인이 되는 계산 셰이더를 검사 합니다.  
  
## <a name="scenario"></a>시나리오  
 이 시나리오에서는 DirectCompute를 사용하여 시뮬레이션 업데이트에서 컴퓨팅 성능이 가장 많이 필요한 부분을 수행하는 유체 역학 시뮬레이션을 작성했습니다. 앱이 실행되면 데이터 집합 및 UI가 제대로 렌더링되는 것으로 보이지만 시뮬레이션은 예상대로 작동하지 않습니다. 그래픽 진단을 사용하여 앱을 디버그할 수 있도록 그래픽 로그 문제를 포착할 수 있습니다. 이 문제는 앱에서 다음과 같이 보입니다.  
  
 ![시뮬레이트된 fluid 올바르게 작동 합니다. ](../debugger/media/gfx-diag-demo-compute-shader-fluid-problem.png "gfx_diag_demo_compute_shader_fluid_problem")  
  
 그래픽 로그의 그래픽 문제를 포착하는 방법에 대한 자세한 내용은 [Capturing Graphics Information](../debugger/capturing-graphics-information.md)를 참조하세요.  
  
## <a name="investigation"></a>조사  
 그래픽 진단 도구를 사용하여 캡처된 프레임을 검사할 수 있도록 그래픽 로그 파일을 로드할 수 있습니다.  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>그래픽 로그에서 프레임을 검사하려면  
  
1. Visual Studio에서 잘못된 시뮬레이션 결과를 보이는 프레임이 포함된 그래픽 로그를 로드합니다. Visual Studio에 새 그래픽 진단 탭이 나타납니다. 이 탭의 맨 윗부분에 선택한 프레임의 렌더링 대상 출력이 있습니다. 맨 아래에는 **프레임 목록**는 캡처된 각 프레임의 축소판 그림을 표시 합니다.  
  
2. 에 **프레임 목록**, 잘못 된 시뮬레이션 동작을 보여 주는 프레임을 선택 합니다. 렌더링 코드가 아니라 시뮬레이션 코드에 오류가 있는 것으로 보이더라도, DirectCompute 이벤트는 Direct3D 이벤트와 함께 프레임별로 캡처되므로 프레임을 선택해야 합니다. 이 시나리오에서 그래픽 로그 탭은 다음과 같습니다.  
  
    ![그래픽 로그 문서를 Visual Studio에서 사용 합니다. ](../debugger/media/gfx-diag-demo-compute-shader-fluid-step-1.png "gfx_diag_demo_compute_shader_fluid_step_1")  
  
   문제를 보이는 프레임을 선택한 후에 **그래픽 이벤트 목록** 을 사용하여 프레임을 진단할 수 있습니다. **그래픽 이벤트 목록** 모든 DirectCompute 호출 및 활성 프레임 중에 만들어진 Direct3D API 호출에 대 한 이벤트를 포함 합니다.-예를 들어 API 호출 GPU에서 계산을 실행 하거나 데이터 집합 또는 UI를 렌더링 하 합니다. 이 시나리오에서 우리는 GPU에서 실행하는 시뮬레이션의 일부를 나타내는 `Dispatch` 이벤트에 집중하겠습니다.  
  
#### <a name="to-find-the-dispatch-event-for-the-simulation-update"></a>시뮬레이션 업데이트에 대한 디스패치 이벤트를 찾으려면  
  
1. 에 **그래픽 진단** 도구 모음 선택 **이벤트 목록** 열려는 합니다 **그래픽 이벤트 목록** 창.  
  
2. 검사는 **그래픽 이벤트 목록** 데이터 집합을 렌더링 하는 그리기 이벤트입니다. 쉽게 하려면 입력 `Draw` 에 **검색** 의 오른쪽 위 모퉁이 있는 상자는 **그래픽 이벤트 목록** 창입니다. 그러면 목록이 필터링되어 제목에 "그리기"가 포함된 이벤트만 나타납니다. 이 시나리오에서는 다음과 같은 그리기 이벤트가 발생한 것이 확인됩니다.  
  
    ![이벤트 목록 &#40;EL&#41; 이벤트를 그리는 보여 줍니다. ](../debugger/media/gfx-diag-demo-compute-shader-fluid-step-2.png "gfx_diag_demo_compute_shader_fluid_step_2")  
  
3. 각 그리기 이벤트 간에 이동하면서 그래픽 로그 문서 탭에서 렌더링 대상을 살펴봅니다.  
  
4. 렌더링 대상에 렌더링된 데이터 집합이 처음으로 표시되면 중지합니다. 이 시나리오에서는 첫 번째 그리기 이벤트에서 데이터 집합이 렌더링됩니다. 시뮬레이션에서 오류가 표시됩니다.  
  
    ![이 그리기 이벤트 렌더링 시뮬레이션 데이터 집합입니다. ](../debugger/media/gfx-diag-demo-compute-shader-fluid-step-3.png "gfx_diag_demo_compute_shader_fluid_step_3")  
  
5. 이제 검사 합니다 **그래픽 이벤트 목록** 에 대 한는 `Dispatch` 시뮬레이션을 업데이트 하는 이벤트입니다. 시뮬레이션이 렌더링되기 전에 업데이트될 가능성이 있기 때문에 먼저, 결과를 렌더링하는 그리기 이벤트 이전에 발생하는 `Dispatch` 이벤트에 집중할 수 있습니다. 쉽게 하려면 수정 된 **검색** 상자를 `Draw;Dispatch;CSSetShader(`입니다. 그러면 그리기 이벤트 외에 `Dispatch` 및 `CSSetShader` 이벤트도 포함되도록 목록이 필터링됩니다. 이 시나리오에서는 그리기 이벤트 전에 다수의 `Dispatch` 이벤트가 발생한 것을 확인할 수 있습니다.  
  
    ![EL은 그리기, 디스패치 및 CSSetShader 이벤트](../debugger/media/gfx-diag-demo-compute-shader-fluid-step-4.png "gfx_diag_demo_compute_shader_fluid_step_4")  
  
   여러 개의 가능한 `Dispatch` 이벤트 중 문제에 해당하는 일부 이벤트를 알게 되었으므로 이제 이들 일부 이벤트에 대해 자세히 살펴볼 수 있습니다.  
  
#### <a name="to-determine-which-compute-shader-a-dispatch-call-executes"></a>디스패치 호출이 어떤 셰이더 컴퓨팅을 실행 여부를 확인하려면  
  
1. 에 **그래픽 진단** 도구 모음 선택 **이벤트 호출 스택** 열려는 합니다 **그래픽 이벤트 호출 스택** 창.  
  
2. 시뮬레이션 결과를 렌더링하는 그리기 이벤트부터 시작하여 각 이전 `CSSetShader` 이벤트 사이를 역방향으로 이동합니다. 그런 다음 합니다 **그래픽 이벤트 호출 스택** 창, 호출 사이트로 이동 하는 최상위 함수를 선택 합니다. 호출 사이트의 첫 번째 매개 변수를 사용할 수는 [CSSetShader](http://msdn.microsoft.com/library/ff476402.aspx) 셰이더 다음 실행 되는 계산을 확인 하기 위해 호출한 함수 `Dispatch` 이벤트입니다.  
  
   이 시나리오에는 각 프레임에 `CSSetShader` 및 `Dispatch` 이벤트가 세 쌍 있습니다. 역방향으로 살펴보면, 세 번째 쌍은 통합 단계를 나타내고(유체 입자가 실제로 이동함), 두 번째 쌍은 힘 계산 단계를 나타내고(각 입자에 영향을 주는 힘이 계산됨), 첫 번째 쌍은 밀도 계산 단계를 나타냅니다.  
  
#### <a name="to-debug-the-compute-shader"></a>컴퓨팅 셰이더를 디버깅하려면  
  
1. 에 **그래픽 진단** 도구 모음 선택 **파이프라인 단계** 열려는 합니다 **그래픽 파이프라인 단계** 창.  
  
2. 세 번째 `Dispatch` 이벤트 (그리기 이벤트 바로 앞에 하나)를 선택한 후 합니다 **그래픽 파이프라인 단계** 창 아래에 있는 합니다 **계산 셰이더** 단계를 선택  **디버깅을 시작할**합니다.  
  
    ![EL.에서 세 번째 디스패치 이벤트를 선택](../debugger/media/gfx-diag-demo-compute-shader-fluid-step-6.png "gfx_diag_demo_compute_shader_fluid_step_6")  
  
    HLSL 디버거는 통합 단계를 수행하는 셰이더에서 시작됩니다.  
  
3. 계산 셰이더 소스 코드에서 통합 단계를 검토하여 오류의 원인을 찾습니다. 그래픽 진단을 HLSL 계산 셰이더 코드를 디버그할 때는 코드를 단계별로 실행하고 조사식 창과 같은 다른 익숙한 디버깅 도구를 사용할 수 있습니다. 이 시나리오에서는 통합 단계를 수행하는 컴퓨팅 셰이더에 오류가 나타나지 않는지 확인합니다.  
  
    ![IntegrateCS 계산 셰이더를 디버깅 합니다. ](../debugger/media/gfx-diag-demo-compute-shader-fluid-step-7.png "gfx_diag_demo_compute_shader_fluid_step_7")  
  
4. 계산 셰이더 디버깅을 중지 하는 **디버그** 도구 모음 선택 **디버깅 중지** (키보드: shift+f5).  
  
5. 그 다음, 두 번째 `Dispatch` 이벤트를 선택하고 이전 단계에서와 마찬가지로 컴퓨팅 셰이더 디버깅을 시작합니다.  
  
    ![EL.에서 두 번째 디스패치 이벤트를 선택](../debugger/media/gfx-diag-demo-compute-shader-fluid-step-8.png "gfx_diag_demo_compute_shader_fluid_step_8")  
  
    HLSL 디버거는 각 유체 입자에 작용하는 힘을 계산하는 셰이더에서 시작됩니다.  
  
6. 힘 컴퓨팅 단계의 컴퓨팅 셰이더 소스 코드를 검사합니다. 이 시나리오에서는 여기가 오류의 원인이라는 것이 확인됩니다.  
  
    ![ForceCS 디버깅&#95;간단한 셰이더를 계산 합니다. ](../debugger/media/gfx-diag-demo-compute-shader-fluid-step-9.png "gfx_diag_demo_compute_shader_fluid_step_9")  
  
   오류의 위치를 확인한 후에는 디버깅을 중지하고 상호 작용하는 입자 간의 거리를 올바르게 계산하도록 계산 셰이더 소스 코드를 수정할 수 있습니다. 이 시나리오에서는 줄 `float2 diff = N_position + P_position;`을 `float2 diff = N_position - P_position;`으로 변경하면 됩니다.  
  
   ![수정 된 계산&#45;셰이더 코드입니다. ](../debugger/media/gfx-diag-demo-compute-shader-fluid-step-10.png "gfx_diag_demo_compute_shader_fluid_step_10")  
  
   이 시나리오에서는 컴퓨팅 셰이더가 런타임에 컴파일되므로 시뮬레이션에 미치는 영향을 관찰하기 위해 변경을 적용한 후 애플리케이션을 다시 시작하면 됩니다. 앱을 다시 빌드할 필요가 없습니다. 앱을 실행하면 이제 시뮬레이션이 올바르게 동작하는 것이 확인됩니다.  
  
   ![시뮬레이트된 fluid가 올바르게 작동 합니다. ](../debugger/media/gfx-diag-demo-compute-shader-fluid-resolution.png "gfx_diag_demo_compute_shader_fluid_resolution")



