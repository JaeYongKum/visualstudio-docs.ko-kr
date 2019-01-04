---
title: '&lt;vstoRuntime&gt; 요소 (Visual Studio에서 Office 개발)'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <vstoRuntime> element
- <vstoRuntime> element
- vstoRuntime element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c5562bdfa8c9cce8e9490392ad81a7e2e697160c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53930702"
---
# <a name="ltvstoruntimegt-element-office-development-in-visual-studio"></a>&lt;vstoRuntime&gt; 요소 (Visual Studio에서 Office 개발)
  `vstoRuntime` 네임스페이스의 `vstav3` 요소에는 특정 Office 솔루션에 대해 지원되는 Visual Studio Tools for Office Runtime 버전이 포함됩니다.

## <a name="syntax"></a>구문

```xml
<vstoRuntime
    release
    version
    supportUrl />
```

## <a name="elements-and-attributes"></a>요소 및 특성
 `vstoRuntime` 요소는 필수이며 `vstav3` 네임스페이스에 있습니다. Office 솔루션이 Visual Studio Tools for Office Runtime의 두 가지 버전을 지원하는 경우 애플리케이션 매니페스트에는 두 개의 `vstoRuntime` 요소가 있습니다.

 `vstoRuntime` 요소에는 다음 특성이 있습니다.

|특성|설명|
|---------------|-----------------|
|`release`|필수 요소. Visual Studio Tools for Office Runtime의 릴리스 버전입니다.|
|`version`|필수 요소. Visual Studio Tools for Office Runtime 버전 번호입니다.|
|`supportUrl`|선택 사항입니다. Visual Studio Tools for Office Runtime의 설치 위치에 연결합니다.|

 `vstoRuntime` 에는 요소가 없습니다.

## <a name="example"></a>예제
 다음 코드 예제에서는 `vstoRuntime` 을 사용하여 배포된 Office 솔루션에 대한 애플리케이션 매니페스트의 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]요소를 보여 줍니다. 이 코드 예제는에서 제공 하는 더 큰 예제의 일부입니다 [Office 솔루션에 대 한 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)합니다.

```xml
<vstav3:vstoRuntime
    release="VSTOR40Beta1"
    version="10.0.20303"
    supportUrl="http://www.microsoft.com" />
```

## <a name="see-also"></a>참고 항목

- [Office 솔루션에 대 한 응용 프로그램 매니페스트](../vsto/application-manifests-for-office-solutions.md)
- [Office 솔루션의 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)
