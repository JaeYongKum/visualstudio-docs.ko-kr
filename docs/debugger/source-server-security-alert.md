---
title: 소스 서버 보안 경고 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.enablewarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: af216023b1a157136f86f0ca8527a8b433b0a34b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719147"
---
# <a name="source-server-security-alert"></a>소스 서버 보안 경고
소스 서버를 사용할 경우 알 수 있고 신뢰할 수 있는 위치의 기호 파일만 사용합니다.

 이 경고는 소스 서버 지원을 사용하는 경우에 나타납니다. 소스 서버 명령은 디버그 기호 파일(**\*.pdb** 파일)에 포함되어 있습니다. PDB 파일의 출처를 확인해야 합니다.

> [!IMPORTANT]
>  소스 서버를 사용할 때는 잠재적인 보안 위협을 고려해야 합니다. 예를 들어, 임의의 명령이 응용 프로그램의 PDB 파일에 포함될 수 있으므로 실제로 실행하려는 명령만 srcsrv.ini 파일에 추가하도록 주의해야 합니다. srcsvr.ini 파일에 포함되지 않은 명령을 실행하려고 하면 확인 대화 상자가 나타납니다. 자세한 내용은 [Security Warning: Debugger Must Execute Untrusted Command](../debugger/security-warning-debugger-must-execute-untrusted-command.md)을 참조하세요. 명령 매개 변수에 대해서는 유효성 검사를 수행하지 않으므로 신뢰되는 명령에 대해 주의를 기울여야 합니다. 예를 들어 cmd.exe를 신뢰한 경우 악의적인 사용자가 이 명령을 위험하게 만드는 매개 변수를 지정할 수도 있습니다.

## <a name="see-also"></a>참고 항목
- [기호 파일(.pdb) 및 원본 파일 지정](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
- [디버거 보안](../debugger/debugger-security.md)
- [원본 서버](/windows/desktop/Debug/source-server-and-source-indexing)
