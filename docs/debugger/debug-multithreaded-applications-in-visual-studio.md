---
title: Visual Studio에서 다중 스레드 응용 프로그램 디버그 | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.gputthreads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], high-performance computing
- debugging [Visual Studio], multithreaded
- multithreaded debugging
- high-performance debugging
ms.assetid: 9d175bc2-1d95-4c47-9bc3-9755af968a9c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 46f165896947f541a7f7be2c48658b83dfd3d102
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35675244"
---
# <a name="debug-multithreaded-applications-in-visual-studio"></a>Visual Studio에서 다중 스레드 응용 프로그램 디버깅
스레드는 운영 체제에서 프로세서 시간을 할당받는 명령 시퀀스입니다. 운영 체제에서 실행되는 모든 프로세스는 최소한 하나의 스레드로 구성됩니다. 프로세스에 스레드가 둘 이상인 경우를 다중 스레드라고 합니다.  
  
다중 프로세서, 다중 코어 프로세서 또는 하이퍼스레드 프로세스를 갖춘 컴퓨터는 여러 스레드를 동시에 실행할 수 있습니다. 여러 스레드를 병렬 처리하면 프로그램 성능이 크게 향상되지만, 여러 스레드를 추적해야 하므로 디버깅이 어려워질 수도 있습니다.  
  
또한 다중 스레드로 인해 새로운 종류의 버그가 생길 수 있습니다. 예를 들어 둘 이상의 스레드에서 같은 리소스에 액세스해야 하지만 한 번에 스레드 중 하나만 리소스에 안전하게 액세스할 수 있는 경우가 많습니다. 한 번에 한 스레드만 리소스에 액세스할 수 있게 하려면 특정한 형태의 상호 제외가 필요합니다. 상호 제외가 올바르게 수행 되는 경우 만들 수는 *교착 상태* 스레드가 실행 될 수 있는 조건이 있습니다. 교착 상태 문제는 특히 디버깅하기 어려울 수 있습니다.

Visual Studio는 다중 스레드 응용된 프로그램 디버깅에 사용할 다양 한 도구를 제공 합니다.

- 스레드를 스레드 디버깅을 위한 기본 도구는 합니다 **스레드** 창, 소스 창의 스레드 마커 **병렬 스택** 창 **병렬 조사식** 창 및 합니다 **디버그 위치** 도구 모음입니다. 에 대해 자세히 알아보려면 합니다 **스레드** 창 및 **디버그 위치** 도구 모음에서 참조 [연습: 스레드 창을 사용 하 여 디버그](../debugger/how-to-use-the-threads-window.md)합니다. 사용 하는 방법을 알아보려면 합니다 **병렬 스택** 및 **병렬 조사식** windows 참조 [다중 스레드 응용 프로그램 디버깅 시작](../debugger/get-started-debugging-multithreaded-apps.md)합니다. 두 항목에는 스레드 마커를 사용 하는 방법을 보여 줍니다.
  
- 사용 하는 코드에 대 한 합니다 [TPL 작업 병렬 라이브러리 ()](/dotnet/standard/parallel-programming/task-parallel-library-tpl) 또는 [동시성 런타임](/cpp/parallel/concrt/concurrency-runtime/), 디버깅을 위한 기본 도구를 **병렬 스택** 창, 합니다 **병렬 조사식** 창 및 **태스크** 창 (합니다 **작업** 창에는 또한 JavaScript 지원). 시작을 참조 하세요 [연습: 병렬 응용 프로그램 디버깅](../debugger/walkthrough-debugging-a-parallel-application.md) 하 고 [연습: c + + AMP 응용 프로그램 디버깅](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application). 

- GPU 스레드 디버깅을 위한 기본 도구는 합니다 **GPU 스레드** 창입니다. 참조 [방법: GPU 스레드 창 사용](../debugger/how-to-use-the-gpu-threads-window.md)합니다.  

- 기본 도구는 프로세스에 대 한 합니다 **프로세스에 연결** 대화 상자를 **프로세스** 창 및 **디버그 위치** 도구 모음입니다.  
  
Visual Studio에서 제공하는 강력한 중단점 및 추적점은 다중 스레드 응용 프로그램을 디버깅할 때 매우 유용할 수 있습니다. 개별 스레드에 중단점을 설정 하려면 중단점 조건 및 필터를 사용할 수 있습니다. 참조 [중단점을 사용 하 여](../debugger/using-breakpoints.md)입니다. 
  
사용자 인터페이스가 있는 다중 스레드 응용 프로그램은 특히 디버깅하기 어려울 수 있습니다. 이러한 경우 응용 프로그램을 다른 컴퓨터에서 실행하면서 원격 디버깅을 사용하는 것이 좋습니다. 정보를 참조 하세요 [원격 디버깅](../debugger/remote-debugging.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용
 [다중 스레드 응용 프로그램 디버깅 시작](../debugger/get-started-debugging-multithreaded-apps.md)합니다.  
 스레드 디버깅 기능에 초점을 맞추어 기능을 안내 하는 **병렬 스택** 창 및 **병렬 조사식** 창입니다.

 [스레드 및 프로세스 디버깅을 위한 도구](../debugger/debug-threads-and-processes.md)  
 스레드 및 프로세스 디버깅에 대 한 도구의 기능을 나열 합니다.  
  
 [여러 프로세스 디버그](../debugger/debug-multiple-processes.md)  
 여러 프로세스 디버깅 방법에 대해 설명합니다.

 [연습: 스레드 창을 사용 하 여 디버그](../debugger/how-to-use-the-threads-window.md)합니다.  
 사용 하는 방법을 보여 주는 연습 합니다 **스레드** 창 및 **디버그 위치** 도구 모음입니다. 

 [연습: 병렬 응용 프로그램 디버그](../debugger/walkthrough-debugging-a-parallel-application.md)  
 사용 하는 방법을 보여 주는 연습 합니다 **병렬 스택** 하 고 **작업** windows.  
  
 [방법: 디버그 중 다른 스레드로 전환](../debugger/how-to-switch-to-another-thread-while-debugging.md)  
 디버깅 컨텍스트를 다른 스레드로 전환하는 세 가지 방법을 보여 줍니다.  
  
 [방법: 스레드에 플래그 지정 및 스레드의 플래그 해제](../debugger/how-to-flag-and-unflag-threads.md)  
 디버깅 도중 특별히 주의하려는 스레드를 표시하거나 플래그를 지정합니다.    
  
 [방법: 고성능 클러스터에서 디버그](../debugger/how-to-debug-on-a-high-performance-cluster.md)  
 고성능 클러스터에서 실행되는 응용 프로그램을 디버깅하는 방법을 보여 줍니다.  

 [네이티브 코드의 스레드 디버깅 팁](../debugger/tips-for-debugging-threads-in-native-code.md)  
 네이티브 스레드를 디버깅하는 단순하지만 유용한 방법을 보여 줍니다. 

 [방법: 네이티브 코드에 스레드 이름 설정](../debugger/how-to-set-a-thread-name-in-native-code.md)  
 스레드에에서 볼 수 있는 이름을 지정 합니다 **스레드** 창입니다.  
  
 [방법: 관리 코드에 스레드 이름 설정](../debugger/how-to-set-a-thread-name-in-managed-code.md)  
 스레드에에서 볼 수 있는 이름을 지정 합니다 **스레드** 창입니다. 
  
## <a name="related-sections"></a>관련 단원  
 [중단점 사용](../debugger/using-breakpoints.md)

 - 개별 스레드를 디버깅할 때 중단점 조건 또는 필터를 사용 합니다.  
  
 - 추적점을 통해 프로그램 실행을 중단 없이 추적할 수 있습니다. 이 기능은 교착 상태와 같은 문제를 파악할 때 유용합니다.  
  
 [스레딩](/dotnet/standard/threading/index)  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 프로그래밍의 스레드 개념에 대해 설명하며, 예제 코드가 포함되어 있습니다.  
  
 [구성 요소에서 다중 스레딩](http://msdn.microsoft.com/Library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 구성 요소에서 다중 스레드를 사용하는 방법에 대해 설명합니다.  
  
 [이전 코드를 위한 다중 스레드 지원(Visual C++)](/cpp/parallel/multithreading-support-for-older-code-visual-cpp)  
 MFC를 사용하는 C++ 프로그래머를 위한 스레드 개념 및 예제 코드가 들어 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레드 및 프로세스 디버깅](../debugger/debug-threads-and-processes.md)   
 [원격 디버깅](../debugger/remote-debugging.md)