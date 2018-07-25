---
title: UWP 앱에서 프리페치된 콘텐츠를 사용 하 여 디버그 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 458b320b971cbb3c4db74d6f2202455332ca5465
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056327"
---
# <a name="debug-uwp-apps-using-prefetched-content-in-visual-studio"></a>프리페치된 콘텐츠를 사용 하 여 Visual Studio에서 UWP 앱 디버그
  
 UWP 앱 응답 속도를 높이려면, 웹 페이지 또는 이미지 같은 일부 웹 콘텐츠를 앱의 미리 로드 하려면 Windows를 요청할 수 있습니다 [WinINet](/windows/desktop/WinInet/about-wininet) 캐시 합니다. 이 기능을 프리페치라고 합니다. 시작 시 사용 되는 콘텐츠에 특히 효과적 이지만 너무 자주 사용 되는 기타 콘텐츠를 사전 인출할 수 있습니다. 메서드를 [Windows.Networking.BackgroundTransfer.ContentPrefetcher](/uwp/api/Windows.Networking.BackgroundTransfer.ContentPrefetcher) 클래스를 사용 하면 미리 로드 하려는 콘텐츠의 Uri를 지정할 수 있습니다. Windows SDK를 참조 하세요 [콘텐츠 프리페치 샘플](http://code.msdn.microsoft.com/windowsapps/ContentPrefetcher-Sample-432c8309) 앱에 ContentPrefetcher 기능을 추가 하는 방법의 예입니다.  
  
 Windows는 휴리스틱을 사용하여 프리페치를 수행하는 시기와 필요성 및 어떤 리소스를 다운로드할지 결정합니다. 휴리스틱은 시스템 네트워크 및 전력 조건, 사용자 응용 프로그램 사용 내용, 이전 프리페치 시도 결과를 고려합니다. Visual Studio에서 사용할 수 있습니다 합니다 **Windows 스토어 응용 프로그램 프리페치 트리거** Windows ContentPrefetcher 휴리스틱 무시 및 지정된 된 웹 콘텐츠 미리 로드 하도록 명령 합니다. 이것은 알려진 상태(로드 여부와 관계없음)로 프리페치할 콘텐츠로 응용 프로그램의 동작 또는 성능을 테스트할 때 유용할 수 있습니다.  
  
## <a name="to-force-preloading-of-contentprefetcher-specified-resources"></a>ContentPrefetcher 지정 리소스를 강제로 미리 로드하려면  
 이 절차는 이미 ContentPrefetcher 기능을 설정하고 응용 프로그램 프로젝트에서 미리 로드할 콘텐츠 URI를 지정했다는 가정 하에 진행됩니다. 시작 하 고 선택 하기 전에 앱을 중지 해야 지정된 리소스가 새롭거나 수정 된 경우 콘텐츠를 미리 로드 하도록 합니다 **Windows 스토어 응용 프로그램 프리페치 트리거** 명령입니다. 먼저 응용 프로그램을 실행하여 URI를 등록합니다. **Windows 스토어 응용 프로그램 프리페치 트리거** 명령이 ContentPrefetcher의 콘텐츠를 다운로드 및 캐시에 추가 강제로 수행 합니다. 후속 응용 프로그램 실행 시 콘텐츠가 미리 로드되었다고 가정할 수 있습니다.  
  
1.  응용 프로그램을 시작하여 프리페치 콘텐츠 URI를 앱과 함께 등록합니다. 에 **디버그** 메뉴 선택 **디버깅 시작** (바로 가기 키: F5).  
  
2.  에 **디버그** 메뉴 선택 **디버깅 중지** (바로 가기 키: Shift + F5).  
  
3.  에 **디버그** 메뉴 선택 **기타 디버그 대상** 를 선택한 후 **Windows 스토어 응용 프로그램 프리페치 트리거**합니다.  
  
 이제 프리페치된 웹 리소스로 응용 프로그램을 디버그, 테스트 또는 분석할 수 있습니다.  
  
> [!NOTE]
>  지정된 웹 콘텐츠를 추가 또는 수정할 때마다 이러한 단계를 반복합니다.  
  
## <a name="see-also"></a>참고 항목  
 [블로그 게시물:에 대 한 Windows 스토어 앱 프리페치 트리거 Visual Studio 2013 업데이트 2](http://blogs.msdn.com/b/visualstudioalm/archive/2014/02/06/triggering-prefetch-for-windows-store-apps-in-visual-studio-2013-update-2.aspx)