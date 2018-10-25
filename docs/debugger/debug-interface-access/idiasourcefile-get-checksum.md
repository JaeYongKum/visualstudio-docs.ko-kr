---
title: 'Idiasourcefile:: Get_checksum | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_checksum method
ms.assetid: aad63a7e-4e22-44e4-8a5b-81b5174ced1e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3f0484fce6f5355361c0c5156cd3c7ad827775c2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49919431"
---
# <a name="idiasourcefilegetchecksum"></a>IDiaSourceFile::get_checksum
체크섬 바이트 수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_checksum (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cbData`  
 [in] 바이트의 데이터 버퍼의 크기입니다.  
  
 `pcbData`  
 [out] 체크섬 바이트 수를 반환합니다. 이 매개 변수 수 없습니다 `NULL`합니다.  
  
 `data`  
 [out에서] 채워진 체크섬 바이트 버퍼입니다. 이 매개 변수가 `NULL`, 다음 `pcbData` 필요한 바이트 수를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 유형의 체크섬 바이트를 생성 하는 데 사용 된 체크섬 알고리즘을 확인 하려면 호출을 [idiasourcefile:: Get_checksumtype](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md) 메서드.  
  
 체크섬은 체크섬 바이트에 대 한 변경 내용에서 소스 파일의 변경 내용이 반영 하므로 일반적으로 소스 파일의 이미지에서 생성 됩니다. 체크섬 바이트 일치 하지 않는 경우 파일을 고려해 야 하는 다음 파일의 로드 된 이미지에서 생성 된 체크섬을 손상 또는 변조입니다.  
  
 일반적인 체크섬 크기가 32 바이트 보다 되지 있지만 체크섬의 최대 크기를 가정 하지 마세요. 설정 된 `data` 매개 변수를 `NULL` 체크섬을 검색 하는 데 필요한 바이트 수를 가져오려고 합니다. 그런 다음 적절 한 크기의 버퍼를 할당 하 고 새 버퍼를 사용 하 여 한 번 더이 메서드를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)