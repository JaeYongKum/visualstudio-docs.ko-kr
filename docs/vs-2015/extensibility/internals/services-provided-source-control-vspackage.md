---
title: 서비스 제공 (소스 제어 VSPackage) | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- services, source control packages
- source control packages, services
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ee980b74415d906a5c48cfd5ad1e20e7b5544320
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49273379"
---
# <a name="services-provided-source-control-vspackage"></a>제공된 서비스(소스 제어 VSPackage)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

서비스는 있는 기능 및 Visual Studio 통합된 개발 환경 (IDE)와 해당 설치 Vspackage Vspackage 간에 공유 되는 기본 메커니즘입니다. 서비스 및 Visual Studio IDE에서 중요도의 자세한 설명을 참조 하세요[사용 및 제공 서비스](../../extensibility/using-and-providing-services.md)합니다.  
  
## <a name="the-source-control-service"></a>소스 제어 서비스  
 Visual Studio 서비스, IDE 수준 서비스 및 패키지 수준 서비스의 두 계층을 제공합니다. Visual Studio IDE는 고유 하 게 IDE 수준 서비스를 제공합니다. 소스 제어 패키지 이러한 서비스 중 일부를 사용 합니다. 소스 제어 VSPackage로 패키지 자체의 개인 원본 제어 서비스를 제공 하 여 해당 원본 제어 기능을 공유 합니다. 소스 제어 패키지는 Visual Studio IDE에서 사용할 수 있는 계약의 형식에 의해 구현 된 원본 제어와 관련 된 인터페이스 집합을 캡슐화 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디자인 요소](../../extensibility/internals/source-control-vspackage-design-elements.md)

