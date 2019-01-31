---
title: VCMessage 작업 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- vc.task.vcmessage
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- VCMessage task (MSBuild (Visual C++))
- MSBuild (Visual C++), VCMessage task
ms.assetid: 956675fd-05dc-40b4-856f-616145103498
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e1011ccfe1609376dc496dc6eb8e7f50795fab5c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54784501"
---
# <a name="vcmessage-task"></a>VCMessage 작업
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
빌드 중에 경고 및 오류 메시지를 로깅합니다.  
  
## <a name="remarks"></a>주의  
 이 작업은 Visual C++에 대한 MSBuild 구현을 도우며 사용자가 호출할 수 없습니다. 자세한 내용은 <xref:Microsoft.Build.Utilities.TaskLoggingHelper>을 참조하세요.  
  
## <a name="parameters"></a>매개 변수  
 다음 표에서는 **VCMessage** 작업의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|**인수**|선택적 **문자열** 매개 변수입니다.<br /><br /> 표시할 메시지의 세미콜론으로 구분된 목록입니다.|  
|**코드**|필수 **String** 매개 변수입니다.<br /><br /> 메시지를 정규화하는 오류 번호입니다.|  
|**Type**|선택적 **문자열** 매개 변수입니다.<br /><br /> 내보낼 메시지의 종류를 지정합니다. 경고 메시지를 내보낼 `"Warning"` 또는 오류 메시지를 내보낼 `"Error"`를 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [작업 참조](../msbuild/msbuild-task-reference.md)
