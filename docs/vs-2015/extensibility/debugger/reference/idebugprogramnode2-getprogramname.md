---
title: IDebugProgramNode2::GetProgramName | Microsoft Docs
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
- IDebugProgramNode2::GetProgramName
helpviewer_keywords:
- IDebugProgramNode2::GetProgramName
ms.assetid: 510c7f5d-48ff-4d9f-ad79-fbad9f15239d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0d2f516fb69c18e1a98bb0169f06ea3e063a4843
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51752254"
---
# <a name="idebugprogramnode2getprogramname"></a>IDebugProgramNode2::GetProgramName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

프로그램의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetProgramName (   
   BSTR* pbstrProgramName  
);  
```  
  
```csharp  
int GetProgramName (   
   out string pbstrProgramName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrProgramName`  
 [out] 프로그램의 이름을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 프로그램의 이름이 프로그램의 이름에는 이러한 경로에 속할 수 있지만 프로그램에 대 한 경로와 동일한 작업을 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 간단한에 대 한이 메서드를 구현 하는 방법을 보여 줍니다 `CProgram` 를 구현 하는 개체를 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스입니다. `MakeBstr` 함수 BSTR로 지정된 된 문자열의 복사본을 할당 합니다.  
  
```cpp#  
HRESULT CProgram::GetProgramName(BSTR* pbstrProgramName) {    
   if (!pbstrProgramName)    
      return E_INVALIDARG;    
  
   // Assign the member program name to the passed program name.    
   *pbstrProgramName = MakeBstr(m_pszProgramName);    
   return NOERROR;    
}    
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)

