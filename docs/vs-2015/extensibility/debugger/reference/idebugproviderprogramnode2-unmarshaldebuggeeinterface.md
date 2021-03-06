---
title: IDebugProviderProgramNode2::UnmarshalDebuggeeInterface | Microsoft Docs
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
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
helpviewer_keywords:
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
ms.assetid: 2e4653c5-10f1-493c-9973-f31d266c5d48
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 94b40ba62e079fbc70fa4f9c7f9560e79bcc0a29
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51771977"
---
# <a name="idebugproviderprogramnode2unmarshaldebuggeeinterface"></a>IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

프로세스 경계를 넘어 지정된 된 인터페이스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT UnmarshalDebuggeeInterface(  
   REFIID riid,  
   void** ppvObject  
);  
```  
  
```csharp  
int UnmarshalDebuggeeInterface(  
   ref Guid   riid,  
   out IntPtr ppvObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 [in] 가져올 인터페이스의 GUID입니다.  
  
 `ppvObject`  
 [out] 원하는 인터페이스를 구현 하는 개체를 반환 합니다. [C + +]이 원하는 인터페이스 형식에 직접 캐스팅 될 수 있습니다. [C#]를 사용 합니다 <xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> 원하는 인터페이스를 가져올 방법.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 디버그 엔진에서 실행 중인 경우이 메서드는 사용을 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 프로세스 공간을 디버깅 하는 프로그램 자체 프로세스 공간에서 실행 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProviderProgramNode2](../../../extensibility/debugger/reference/idebugproviderprogramnode2.md)

