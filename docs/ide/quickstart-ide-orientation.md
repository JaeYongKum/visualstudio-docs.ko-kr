---
title: Visual Studio IDE 둘러보기
ms.date: 07/12/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 89689df19e5002c4c757d5a84c9263f8c40a10e7
ms.sourcegitcommit: b544e2157ac20866baf158eef9cfed3e3f1d68b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39388191"
---
# <a name="quickstart-first-look-at-the-visual-studio-ide"></a>빠른 시작: 먼저 Visual Studio IDE 살펴보기

이 5~10분이 걸리는 Visual Studio IDE(통합 개발 환경) 소개 내용에서는 창, 메뉴 및 기타 UI 기능 일부를 살펴보겠습니다.

아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 페이지로 이동하여 체험용으로 설치합니다.

## <a name="start-page"></a>시작 페이지

Visual Studio를 시작한 후 처음으로 보게 되는 것은 **시작 페이지**일 것입니다. **시작 페이지**는 필요한 명령과 프로젝트 파일을 빠르게 찾아볼 수 있는 “허브”로 디자인되었습니다. **최근 항목** 섹션에는 최근에 작업한 프로젝트 및 폴더가 표시됩니다. **새 프로젝트**에서 링크를 클릭하여 **새 프로젝트** 대화 상자를 표시하거나, **열기**에서 기존 코드 프로젝트 또는 폴더를 열 수 있습니다. 오른쪽에는 최신 개발자 뉴스 피드가 있습니다.

![Visual Studio의 시작 페이지](media/start-page.png)

**시작 페이지**를 닫았다가 다시 보려면 **파일** 메뉴에서 다시 열 수 있습니다.

![Visual Studio의 파일 메뉴](media/quickstart-IDE-file-menu-large.png)

## <a name="create-a-project"></a>프로젝트 만들기

Visual Studio의 기능을 계속 탐색하기 위해 새 프로젝트를 만들어 보겠습니다.

1. **시작 페이지**의 **새 프로젝트**에 있는 검색 상자에 **console**을 입력하여 프로젝트 형식 목록을 이름에 “console”이 포함된 항목으로 필터링합니다.

   ![Visual Studio 시작 페이지에서 프로젝트 템플릿 검색](media/start-page-search-templates.png)

   Visual Studio에서는 신속하게 코딩을 시작하는 데 도움이 되는 다양한 종류의 프로젝트 템플릿을 제공합니다. C# **콘솔 앱(.NET Framework)** 프로젝트 템플릿을 선택합니다. (또는 Visual Basic, C++, Javascript나 기타 언어 개발자인 경우 해당 언어 중 하나로 프로젝트를 만들 수 있습니다. 표시되는 UI는 모든 프로그래밍 언어에서 비슷합니다.)

1. 표시되는 **새 프로젝트** 대화 상자에서 기본 프로젝트 이름을 그대로 사용하고 **확인**을 선택합니다.

   프로젝트가 만들어지고 **편집기** 창에 *Program.cs*라는 파일이 열립니다. **편집기**에는 파일 내용이 표시되며, 여기서 Visual Studio에서 하는 코딩 작업 대부분을 수행합니다.

   ![Visual Studio의 편집기](media/editor.png)

## <a name="solution-explorer"></a>솔루션 탐색기

일반적으로 Visual Studio의 오른쪽에 있는 **솔루션 탐색기**에는 프로젝트, 솔루션 또는 코드 폴더에 있는 파일 및 폴더의 계층 구조가 그래픽으로 표시됩니다. **솔루션 탐색기**에서 계층 구조를 탐색하고 파일로 이동할 수 있습니다.

![Visual Studio의 솔루션 탐색기](media/quickstart-IDE-solution-explorer.png)

## <a name="menus"></a>메뉴

Visual Studio의 위쪽에 있는 메뉴 모음은 명령을 범주로 그룹화합니다. 예를 들어 **프로젝트** 메뉴에는 작업 중인 프로젝트와 관련된 명령이 포함되어 있습니다. **도구** 메뉴에서 **옵션**을 선택하여 Visual Studio 동작 방법을 사용자 지정하거나, **도구 및 기능 가져오기**를 선택하여 설치에 기능을 추가할 수 있습니다.

![Visual Studio의 메뉴 모음](media/quickstart-IDE-menu-bar.png)

**보기** 메뉴를 선택한 다음, **오류 목록**을 선택하여 **오류 목록** 창을 열어 보겠습니다.

## <a name="error-list"></a>오류 목록

**오류 목록**에는 오류, 경고 및 코드의 현재 상태에 대한 메시지가 표시됩니다. 파일 또는 프로젝트 어딘가에 오류(예: 괄호 또는 세미콜론 누락)가 있는 경우 여기에 나열됩니다.

![Visual Studio의 오류 목록](media/quickstart-IDE-error-list.png)

## <a name="output-window"></a>출력 창

**출력** 창에는 프로젝트 및 원본 제어 공급자에서 빌드한 출력 메시지가 표시됩니다.

프로젝트를 빌드하여 일부 빌드 출력을 확인하겠습니다. **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다. **출력** 창에는 자동으로 포커스가 표시되고 빌드 성공 메시지가 표시됩니다.

![Visual Studio의 출력 창](media/build-output-minimal.png)

## <a name="quick-launch"></a>빠른 실행

**빠른 실행** 상자는 Visual Studio에서 거의 대부분 작업을 빠르고 손쉽게 수행할 수 있게 해줍니다. 수행하려는 작업과 관련된 일부 텍스트를 입력하면 해당 텍스트와 관련된 옵션 목록이 표시됩니다. 예를 들어 빌드가 정확하게 수행하는 작업에 대한 추가 세부 정보를 표시하기 위해 빌드 출력의 세부 정보 표시를 증가시킨다고 가정해 보겠습니다. 수행할 수 있는 방법은 다음과 같습니다.

1. **세부 정보 표시**를 **빠른 실행** 상자에 입력합니다. 표시된 결과에서 **옵션** 범주에 있는 **프로젝트 및 솔루션 -> 빌드 및 실행**을 선택합니다.

   ![Visual Studio의 빠른 실행 상자](media/quickstart-IDE-quick-launch.png)

   **옵션** 대화 상자가 열려 **빌드 및 실행** 옵션 페이지가 표시됩니다.

1. **MSBuild 프로젝트 빌드 출력의 자세한 정도** 아래에서 **보통**을 선택한 다음 **확인**을 클릭합니다.

1. **솔루션 탐색기**에서 **ConsoleApp1** 프로젝트를 마우스 오른쪽 단추로 클릭하고 팝업 메뉴에서 **다시 빌드**를 선택하여 프로젝트를 다시 빌드합니다.

   이번에는 **출력** 창에 어떤 파일이 어디에 복사되었는지를 비롯하여 빌드 프로세스의 더 자세한 정보 로깅이 표시됩니다.

   ![Visual Studio의 세부 정보 표시 빌드 출력](media/build-output-verbose.png)

## <a name="send-feedback-menu"></a>사용자 의견 보내기 메뉴

Visual Studio를 사용하는 동안 문제가 발생하거나 제품을 개선하는 방법에 대한 제안이 있는 경우 Visual Studio 창의 위쪽에서 **빠른 실행** 상자 옆에 있는 **사용자 의견 보내기** 메뉴를 사용할 수 있습니다.

![Visual Studio의 사용자 의견 보내기 메뉴](media/quickstart-IDE-send-feedback.png)

## <a name="next-steps"></a>다음 단계

사용자 인터페이스에 익숙해지도록 Visual Studio의 몇 가지 기능에 대해 살펴보았습니다. 더 살펴보려면:

- [Visual Studio IDE 개요](../ide/visual-studio-ide.md)에서 Visual Studio를 더 자세히 살펴봅니다(약간의 디버깅도 가능).

- [오류 목록](../ide/reference/error-list-window.md), [출력 창](../ide/reference/output-window.md), [속성 창](../ide/reference/properties-window.md) 및 [옵션 대화 상자](../ide/reference/options-dialog-box-visual-studio.md)와 같은 창에 대한 자세한 내용이 들어 있는 VS 설명서의 **일반 사용자 인터페이스 요소** 섹션을 살펴봅니다.

## <a name="see-also"></a>참고 항목

- [빠른 시작: IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)
- [빠른 시작: 편집기에서 코드 작성](../ide/quickstart-editor.md)
- [빠른 시작: 프로젝트 및 솔루션](../ide/quickstart-projects-solutions.md)