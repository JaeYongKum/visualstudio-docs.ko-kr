---
title: IDebugDocumentContext2::EnumCodeContexts | Microsoft Docs
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
- IDebugDocumentContext2::EnumCodeContexts
helpviewer_keywords:
- IDebugDocumentContext2::EnumCodeContexts
ms.assetid: 627af69c-5cce-4e1d-8233-5f4d8dbc62e5
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c98df184441568be62a7caf6ab999ea8adf0955e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51791386"
---
# <a name="idebugdocumentcontext2enumcodecontexts"></a>IDebugDocumentContext2::EnumCodeContexts
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

이 문서 컨텍스트와 연결 된 모든 코드 컨텍스트 목록을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT EnumCodeContexts(   
   IEnumDebugCodeContexts2** ppEnumCodeCxts  
);  
```  
  
```csharp  
int EnumCodeContexts(   
   out IEnumDebugCodeContexts2 ppEnumCodeCxts  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppEnumCodeCxts`  
 [out] 반환 된 [IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md) 코드 컨텍스트의 목록을 포함 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 단일 문서 컨텍스트를 문서에는 템플릿을 사용 하는 경우 여러 코드 컨텍스트를 생성 하거나 파일을 포함할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 간단한에 대 한이 메서드를 구현 하는 방법을 보여 줍니다 `CDebugContext` 노출 하는 개체를 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 인터페이스입니다.  
  
```cpp#  
HRESULT CDebugContext::EnumCodeContexts(IEnumDebugCodeContexts2 **ppEnumCodeCxts)    
{    
   HRESULT hr;    
  
   // Check for a valid IEnumDebugCodeContexts2 interface pointer.    
   if (ppEnumCodeCxts)    
   {    
      *ppEnumCodeCxts = NULL;    
  
      // Create a CEnumDebugCodeContexts object.    
      CComObject<CEnumDebugCodeContexts>* pEnum;    
      hr = CComObject<CEnumDebugCodeContexts>::CreateInstance(&pEnum);    
      assert(hr == S_OK);    
      if (hr == S_OK)    
      {    
         // Get an IID_IDebugCodeContext2 interface.    
         CComPtr<IDebugCodeContext2> spCodeCxt;    
         hr = QueryInterface(IID_IDebugCodeContext2,  
                             (void**)&spCodeCxt);  
         assert(hr == S_OK);    
         if (hr == S_OK)    
         {    
            // Initialize the code context enumerator with the    
            // IDebugCodeContext2 information.  
            IDebugCodeContext2* rgpCodeContext[] = { spCodeCxt.p };    
            hr = pEnum->Init(rgpCodeContext,  
                             &(rgpCodeContext[1]),  
                             NULL,  
                             AtlFlagCopy);  
            assert(hr == S_OK);    
            if (hr == S_OK)    
            {    
               // Set the passed IEnumDebugCodeContexts2 pointer equal to the pointer  
               // value of the created CEnumDebugCodeContexts object.  
               hr = pEnum->QueryInterface(ppEnumCodeCxts);    
               assert(hr == S_OK);    
            }    
         }    
  
         // Otherwise, delete the CEnumDebugCodeContexts object.    
         if (FAILED(hr))    
         {    
            delete pEnum;    
         }    
      }    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)

