---
title: VSG_DEFAULT_RUN_FILENAME | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ea549d2f-c857-458c-93c7-bc5a2d11d15d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 303bce554ff6345a37719a8d2f529f3c1ffe02e2
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31472026"
---
# <a name="vsgdefaultrunfilename"></a>VSG_DEFAULT_RUN_FILENAME
그래픽 로그 파일의 기본 파일 이름을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
#define VSG_DEFAULT_FILENAME filename  
```  
  
#### <a name="parameters"></a>매개 변수  
 `filename`  
 그래픽 정보를 프로그래밍 방식으로 캡처할 때 그래픽 로그 파일에 대해 기본적으로 제공되는 파일 이름입니다.  
  
## <a name="value"></a>값  
 그래픽 로그 파일의 파일 이름을 나타내는 문자열 리터럴입니다. 기본적으로 L"default.vsglog"입니다.  
  
```C++  
#define VSG_DEFAULT_FILENAME L"default.vsglog"  
```  
  
## <a name="remarks"></a>설명  
 전처리기 기호 `DONT_SAVE_VSGLOG_TO_TEMP`가 정의된 경우 파일 이름이 캡처된 앱의 현재 디렉터리에 상대적이거나 절대 경로입니다. 그렇지 않으면 사용자의 임시 파일 디렉터리에 상대적이고 절대 경로일 수 없습니다.  
  
 정의 된 파일 이름을 변경 하려면 다시 정의 해야 것 포함 하기 전에 `vsgcapture.h` 프로그램에서 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 캡처 파일의 기본 파일 이름을 변경하는 방법을 보여줍니다.  
  
```C++  
// Redefine the default capture filename before including vsgcapture.h  
#define VSG_DEFAULT_FILENAME L"capture.vsglog"  
  
#include <vsgcapture.h>  
```  
  
## <a name="see-also"></a>참고 항목  
 [DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)