---
title: IDebugCustomAttribute::GetAttributeBytes | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCustomAttribute::GetAttributeBytes
helpviewer_keywords:
- IDebugCustomAttribute::GetAttributeBytes
ms.assetid: cf34583b-6530-4dcc-89f8-eb27e4e8d594
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 41f1cb252b2537a49aa9542c39e7504a9b9940e0
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51763273"
---
# <a name="idebugcustomattributegetattributebytes"></a>IDebugCustomAttribute::GetAttributeBytes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

바이트의 blob으로 특성 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetAttributeBytes(   
   BYTE*  ppBlob,  
   DWORD* pdwLen  
);  
```  
  
```csharp  
int GetAttributeBytes(  
   ref byte[] ppBlob,   
   ref uint   pdwLen  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppBlob`  
 [out에서] 특성 (바이트)를 사용 하 여 입력은 배열입니다.  
  
 `pdwLen`  
 [out에서] 반환할 바이트의 최대 수를 지정 된 `ppBlob` 배열 및 배열에 실제로 기록 된 바이트 수를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 설정 된 `ppBlob` 매개 변수 개수를 반환 하려면 null 값에 사용할 수 있는 바이트 특성입니다. 그런 다음 배열을 할당 하 고 해당 배열에 전달 된 `ppBlob` 매개 변수입니다.  
  
 특성 바이트는 사용자 지정 특성의 원시 데이터를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)

