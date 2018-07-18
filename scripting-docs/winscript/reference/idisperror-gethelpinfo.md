---
title: IDispError::GetHelpInfo | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetHelpInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetHelpInfo
ms.assetid: a146df13-eda4-4e56-8bf0-cf9886a2150f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 17098b4055bb61e9a2f639404edfe2214abc931e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24728013"
---
# <a name="idisperrorgethelpinfo"></a>IDispError::GetHelpInfo
도움말 파일의 경로 가능한 경우 오류를 설명 하는 항목의 컨텍스트 ID를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetHelpInfo(  
   BSTR*  pbstrFileName,  
   DWORD*  pdwContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrFileName`  
 [out] 도움말 파일의 정규화 된 경로 포함 하는 문자열입니다. 도움말 파일이 없는 또는 오류가 발생 하는 경우 반환 값은 NULL입니다.  
  
 `pdwContext`  
 [out] 오류에 대 한 도움말 컨텍스트 ID입니다. 도움말 파일이 없는 경우 (경우 `pbstrFileName` null),이 매개 변수는 의미가 없습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|공급자 관련 오류가 발생 했습니다.|  
|`E_INVALIDARG`|`pbstrFileName`또는 `pdwContext` null입니다.|  
|`E_OUTOFMEMORY`|공급자에서 도움말 파일 경로 반환 하는 충분 한 메모리를 할당할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 도움말 파일의 경로 가능한 경우 오류를 설명 하는 항목의 컨텍스트 ID를 반환 합니다.  
  
> [!NOTE]
>  이 메서드가 구현되지 않았습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDispError 인터페이스](../../winscript/reference/idisperror-interface.md)