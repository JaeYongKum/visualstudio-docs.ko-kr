---
title: SccDirQueryInfo 함수 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccDirQueryInfo
helpviewer_keywords:
- SccDirQueryInfo function
ms.assetid: 459e2d99-573d-47c4-b834-6d82c5e14162
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cc42301901c6642a54dcb6b84de52a4acc198b4a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56720421"
---
# <a name="sccdirqueryinfo-function"></a>SccDirQueryInfo 함수
이 함수는 현재 상태에 대 한 정규화 된 디렉터리의 목록을 검사합니다.

## <a name="syntax"></a>구문

```cpp
SCCRTN SccDirQueryInfo(
LPVOID  pContext,
LONG    nDirs,
LPCSTR* lpDirNames,
LPLONG  lpStatus
);
```

### <a name="parameters"></a>매개 변수
 pContext

[in] 원본 제어 플러그 인 상황에 맞는 구조입니다.

 nDirs

[in] 쿼리할 선택한 디렉터리의 수입니다.

 lpDirNames

[in] 배열 쿼리할 디렉터리의 정규화 된 경로입니다.

 lpStatus

[out에서] 소스 제어 상태 플래그를 반환 하는 플러그 인에 대 한 배열 구조 (참조 [디렉터리 상태 코드](../extensibility/directory-status-code-enumerator.md) 세부 정보에 대 한).

## <a name="return-value"></a>반환 값
 원본 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환 하:

|값|설명|
|-----------|-----------------|
|SCC_OK|쿼리 성공 했습니다.|
|SCC_E_OPNOTSUPPORTED|소스 코드 제어 시스템에서이 작업을 지원 하지 않습니다.|
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제로 인해 액세스 문제가 있습니다. 재시도 사용 하는 것이 좋습니다.|
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|

## <a name="remarks"></a>설명
 함수에서 비트의 비트 마스크를 사용 하 여 반환 배열을 채웁니다 합니다 `SCC_DIRSTATUS` 제품군 (참조 [디렉터리 상태 코드](../extensibility/directory-status-code-enumerator.md)), 지정 된 각 디렉터리에 대해 하나의 항목입니다. 에서는 상태 배열은 호출자가 할당 됩니다.

 IDE는 해당 프로젝트에 있는지를 쿼리하여 디렉터리는 소스 제어 하는지 여부를 확인 하려면 디렉터리 이름이 전에이 함수를 사용 합니다. 소스 제어에서 디렉터리가 없는 경우 IDE는 사용자에 게 적절 한 경고를 제공할 수 있습니다.

> [!NOTE]
>  소스 제어 플러그 인을 하나 이상 상태 값은 구현 하지 하기로 구현 되지 않은 비트를 0으로 설정 되어야 합니다.

## <a name="see-also"></a>참고자료
- [원본 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)
- [디렉터리 상태 코드](../extensibility/directory-status-code-enumerator.md)