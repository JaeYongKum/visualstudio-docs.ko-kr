---
title: 보안 및 지역화된 위성 어셈블리
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- key pairs for strong-named assemblies
- strong-named assemblies, security considerations
- satellite assemblies, localized
- code signing, assemblies
- security [Visual Studio], assemblies
- strong-named assemblies, localized
- assemblies [Visual Studio], security
- localization, satellite assemblies
ms.assetid: 6d953840-b301-47d5-8d34-30c1b29b5071
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b7eb391f01bc5a709aeaf0002ac647c358355e5f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31943750"
---
# <a name="security-and-localized-satellite-assemblies"></a>보안 및 지역화된 위성 어셈블리

주 어셈블리에 강력한 이름 지정이 사용될 경우 주 어셈블리와 같은 개인 키를 사용하여 위성 어셈블리에 서명해야 합니다. 주 어셈블리와 위성 어셈블리 간에 공개/개인 키 쌍이 일치하지 않으면 리소스가 로드되지 않습니다. 어셈블리 서명에 대한 자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name)을 참조하세요.

 일반적으로 조직의 서명 그룹 또는 외부 서명 조직이 개인 키로 서명하도록 해야 할 수 있습니다. 이는 액세스가 보통 몇몇 개인으로 제한된다는 개인 키의 민감한 특성 때문입니다. 개발 중에 지연된 서명을 사용할 수 있습니다. 자세한 내용은 [어셈블리 서명 연기](/dotnet/framework/app-domains/delay-sign-assembly)를 참조하십시오.

## <a name="see-also"></a>참고 항목

- [어셈블리 보안 고려 사항](/dotnet/framework/app-domains/assembly-security-considerations)  - [주요 보안 개념](/dotnet/standard/security/key-security-concepts)
- [.NET Framework 기반의 국가별 응용 프로그램 소개](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)
- [응용 프로그램 지역화](../ide/localizing-applications.md)
- [응용 프로그램 전역화 및 지역화](../ide/globalizing-and-localizing-applications.md)