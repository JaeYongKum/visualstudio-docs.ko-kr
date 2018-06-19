---
title: Visual Studio 복구할 수 없는 프로세스 오류
ms.date: 02/23/2017
ms.topic: troubleshooting
helpviewer_keywords:
- editor
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 1db7f2729ded01eedda6fff6d18ca1b2ee3607b6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31942223"
---
# Visual Studio 복구할 수 없는 프로세스 오류

Visual Studio 2017에서는 여러 out-of-proc 프로세스를 사용하여 필요한 백그라운드 작업을 실행합니다(예: Live Unit Testing, 코드 분석기 등). Visual Studio에서 이러한 out-of-proc 프로세스를 실행하면 성능상 이점이 있습니다. 예를 들어 리소스를 많이 사용하는 장기 실행 작업을 실행할 때 더 빠르게 응답합니다. 또한 Visual Studio는 32비트 프로세스이므로 out-of-proc 프로세스를 실행하면 메모리 집약적인 작업을 수행할 때 더 많은 메모리 공간이 확보됩니다.

어떤 이유로 인해 필수 프로세스가 종료될 경우 팝업 알림 표시줄에 다음과 같은 메시지가 나타납니다.

"Visual Studio에서 사용하는 프로세스에서 복원할 수 없는 오류가 발생했습니다. 작업을 저장하고, Visual Studio를 종료한 후 다시 시작하시는 것을 권장해 드립니다."

이 메시지가 표시되는 경우 즉시 작업을 저장하고 Visual Studio를 종료한 후 다시 시작해야 합니다. 그러지 않으면 Visual Studio의 작동이 중단될 수 있습니다.

## 프로세스 목록

다음은 Visual Studio를 제대로 작동하기 위해 실행해야 하는 Visual Studio에서 사용되는 out-of-proc 프로세스 목록입니다.

- Microsoft.Alm.Shared.Remoting.RemoteContainer.dll
- Microsoft.CodeAnalysis.LiveUnitTesting.EntryPoint
- PerfWatson2.exe
- ServiceHub.Host.Node.x86.exe
- ServiceHub.IdentityHost.exe
- ServiceHub.VSDetouredHost.exe
- ServiceHub.SettingsHost.exe
- ServiceHub.Host.CLR.x86.exe
- ServiceHub.RoslynCodeAnalysisService32.exe
- ServiceHub.RoslynCodeAnalysisService.exe
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe
- WaAppAgent.exe