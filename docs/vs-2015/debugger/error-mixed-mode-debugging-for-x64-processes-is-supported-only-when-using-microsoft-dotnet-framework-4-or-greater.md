---
title: '오류: 혼합 모드 디버깅 프로세스는 Microsoft.NET Framework 4를 사용 하는 경우에 지원 됩니다 x64 이상을 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: e4b0216c-7006-4832-883f-08e982ba8d3f
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5dfb5d43ef78e16a5280c7faff92a3ea7e791c43
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51805621"
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>오류: x64 프로세스용 혼합 모드 디버깅은 Microsoft .NET Framework 4 이상을 사용할 때만 지원됩니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

64비트 프로세스의 혼합 네이티브 및 관리 코드를 디버깅하려면 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 버전 4가 있어야 합니다. 4 이전 버전의 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]에서는 64비트 프로세스의 혼합 모드 디버깅이 지원되지 않습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   다음 단계 중 하나를 수행합니다.  
  
    -   [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]를 버전 4로 업그레이드합니다.  
  
    -   디버깅을 위해 32비트 버전의 응용 프로그램을 빌드합니다.  
  
## <a name="see-also"></a>참고 항목  
 [장치에서 원격 도구 설정](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)



