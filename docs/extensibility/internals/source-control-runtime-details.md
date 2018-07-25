---
title: 소스 제어 런타임 세부 정보 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], runtime details
ms.assetid: 1acd30e0-f98c-4bde-b9cd-4076845887df
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b972218258ded1ebf2f9f606927ba351e77afa01
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130314"
---
# <a name="source-control-runtime-details"></a>소스 제어에 대 한 런타임 세부 정보
사용자는 마법사와 같은 자동화 컨트롤러를 통해 또는 소스 제어에 파일을 프로젝트에 추가 하는 경우 프로젝트를 소스 제어에 추가 됩니다. 프로젝트를 지정 하지 않습니다 자체에 대 한 소스 제어; 인지 이 원본 제어를 지원 하지만 수동으로에 추가 해야 합니다.  
  
## <a name="registering-with-a-source-control-package"></a>소스 제어 패키지 등록  
 프로젝트의 파일은 소스 제어에 추가 되 면 환경 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A> 쿠키와 소스 제어 시스템에서 사용 되는 4 개의 불투명 문자열을 제공 하기. 프로젝트 파일의 이러한 문자열을 저장 합니다. 이러한 문자열에 전달 되어야 (Visual Studio 구성 요소 소스 제어 패키지를 관리 하는) 소스 제어 스텁 프로젝트 형식을 시작할 때 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>합니다. 이 로드 적절 한 원본 제어 패키지 및 해당 구현에 대 한 호출을 전달 `IVsSccManager2::RegisterSccProject`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>   
 [소스 제어 지원](../../extensibility/internals/supporting-source-control.md)