---
title: IDispError 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDispError interface
ms.assetid: 3dc7b55e-94ba-4669-b20a-1e011f2d07cf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b717ebfe740a9b356513bb0f15e90c629a14e147
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345840"
---
# <a name="idisperror-interface"></a>IDispError 인터페이스
자세한 상황별 오류 정보를 제공합니다.  
  
> [!NOTE]
>  이 인터페이스가 구현 되지 않았습니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDispError` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDispError::QueryErrorInfo](../../winscript/reference/idisperror-queryerrorinfo.md)|특정 유형의 오류 정보를 검색합니다.|  
|[IDispError::GetNext](../../winscript/reference/idisperror-getnext.md)|다음 검색 `IDispError` 개체입니다.|  
|[IDispError::GetHresult](../../winscript/reference/idisperror-gethresult.md)|오류 코드를 검색 합니다 `IDispError` 개체입니다.|  
|[IDispError::GetSource](../../winscript/reference/idisperror-getsource.md)|클래스 또는 오류를 발생 시킨 응용 프로그램에 대 한 프로그래밍 언어별 식별자를 반환 합니다.|  
|[IDispError::GetHelpInfo](../../winscript/reference/idisperror-gethelpinfo.md)|도움말 파일의 경로 가능한 경우 오류를 설명 하는 항목의 컨텍스트 ID를 반환 합니다.|  
|[IDispError::GetDescription](../../winscript/reference/idisperror-getdescription.md)|오류에 대 한 텍스트 설명을 반환합니다.|