---
title: 솔루션이나 프로젝트 없이 Visual Studio에서 JavaScript 코드 작성
description: Visual Studio는 프로젝트 파일이나 솔루션 파일에 대한 종속성 없이 코드 작성을 지원
ms.custom: ''
ms.date: 06/06/2018
ms.technology: vs-nodejs
ms.topic: conceptual
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 7d56030b78abe57c80d816881991b9819ed6456b
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924743"
---
# <a name="develop-javascript-and-typescript-code-in-visual-studio-without-solutions-or-projects"></a>솔루션이나 프로젝트 없이 Visual Studio에서 JavaScript 및 TypeScript 코드 개발

Visual Studio 2017에는 [프로젝트 또는 솔루션 없이 코드를 개발](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)할 수 있는 기능이 도입되었습니다. 이 기능을 사용하면 코드의 폴더를 열고 IntelliSense, 검색, 리팩터링, 디버깅 등과 같은 다양한 편집기 지원 작업을 즉시 시작할 수 있습니다.
이러한 기능 외에도 Visual Studio용 Node.js 도구는 TypeScript 파일 작성, npm 패키지 관리 및 npm 스크립트를 실행하기 위한 지원이 추가되었습니다.

시작하려면 Visual Studio를 열 때 나타나는 시작 페이지에서 **폴더 열기**를 선택하거나 도구 모듬에서 **파일** > **열기** > **폴더**를 선택할 수 있습니다. 솔루션 탐색기는 폴더에 있는 모든 파일을 표시하며 파일을 열어 편집을 시작할 수 있습니다. 백그라운드에서 Visual Studio는 npm, 빌드 및 디버그 기능을 사용하도록 파일을 인덱싱합니다.

> [!IMPORTANT]
> npm 통합을 포함하여 이 문서에서 설명하는 많은 기능에는 Visual Studio 2017 버전 15.8 Preview 3이 필요합니다.

## <a name="npm-integration"></a>npm 통합

열린 폴더에 *package.json* 파일이 있는 경우 *package.json*을 마우스 오른쪽 단추로 클릭하여 npm에 해당하는 컨텍스트 메뉴(바로 가기 메뉴)를 표시할 수 있습니다. 

![솔루션 탐색기의 npm 메뉴](../javascript/media/solution-explorer-npm-ctx.png) 

바로 가기 메뉴에서 프로젝트 파일을 사용할 때 [npm 패키지 관리](npm-package-management.md)와 동일한 방법으로 npm으로 설치된 패키지를 관리할 수 있습니다.

또한 이 메뉴를 사용하면 *package.json*의 `scripts` 요소에 정의된 스크립트를 실행할 수도 있습니다. 이러한 스크립트는 `PATH` 환경 변수에서 사용할 수 있는 Node.js 버전을 사용합니다. 스크립트는 새 창에서 실행됩니다. 이는 빌드를 실행하거나 스크립트를 실행하는 좋은 방법입니다.

## <a name="build-and-debug"></a>빌드 및 디버그

### <a name="packagejson"></a>package.json
폴더의 *package.json*에 `main` 요소를 지정하는 경우 *package.json*의 오른쪽 클릭 바로 가기 메뉴에서 **디버그** 명령을 사용할 수 있습니다. 이를 클릭하면 *node.exe*가 지정된 스크립트를 인수로 시작합니다.

### <a name="javascript-files"></a>JavaScript 파일
파일을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **디버그**를 선택하여 JavaScript 파일을 디버깅할 수 있습니다. 그러면 *node.exe*가 해당 JavaScript 파일을 인수로 시작합니다.

### <a name="typescript-files-and-tsconfigjson"></a>TypeScript 파일 및 tsconfig.json
폴더에 *tsconfig.json*이 없으면 TypeScript 파일을 마우스 오른쪽 단추로 클릭하여 해당 파일을 빌드하고 디버깅할 수 있는 바로 가기 메뉴 명령을 볼 수 있습니다. 이러한 명령을 사용하면 *tsc.exe*를 기본 옵션으로 사용하여 빌드하거나 디버깅합니다. (디버그하려면 파일을 빌드해야 합니다.)

> [!NOTE]
> TypeScript 코드를 작성할 때 `C:\Program Files (x86)\Microsoft SDKs\TypeScript`에 설치된 최신 버전을 사용합니다.

폴더에 *tsconfig.json* 파일이 있으면 TypeScript 파일을 마우스 오른쪽 단추로 클릭하여 해당 TypeScript 파일을 디버깅할 수 있는 메뉴 명령을 볼 수 있습니다. 옵션은 *tsconfig.json*에 지정된 `outFile`이 없는 경우에만 나타납니다. `outFile`을 지정하면 *tsconfig.json*을 마우스 오른쪽 단추로 클릭하고 올바른 옵션을 선택하여 해당 파일을 디버깅할 수 있습니다. `tsconfig.json` 파일은 컴파일러 옵션을 지정할 수 있는 빌드 옵션도 제공합니다.

> [!NOTE]
> *tsconfig.json*에 대한 자세한 내용은 [tsconfig.json TypeScript Handbook 페이지](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)에서 찾을 수 있습니다.
