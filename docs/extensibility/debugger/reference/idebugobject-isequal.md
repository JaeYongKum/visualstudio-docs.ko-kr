---
title: IDebugObject::IsEqual | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugObject::IsEqual
helpviewer_keywords:
- IDebugObject::IsEqual method
ms.assetid: 4b76e663-ef2e-41ff-9be1-bf26d666a34a
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 9780a18ff72058a90739c421061fabd9ce8520e1
ms.contentlocale: ko-kr
ms.lasthandoff: 08/28/2017

---
# <a name="idebugobjectisequal"></a>IDebugObject::IsEqual
Compares an object with this object.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsEqual(   
   IDebugObject* pObject,  
   BOOL*         pfIsEqual  
);  
```  
  
```csharp  
int IsEqual(  
   IDebugObject pObject,  
   out int      pfIsEqual  
);  
```  
  
#### <a name="parameters"></a>Parameters  
 `pObject`  
 [in] An [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) object representing the object to compare to.  
  
 `pfIsEqual`  
 [out] Returns non-zero (`TRUE`) if the values of the objects are equal; otherwise, returns zero (`FALSE`).  
  
## <a name="return-value"></a>Return Value  
 If successful, returns S_OK; otherwise, returns an error code.  
  
## <a name="remarks"></a>Remarks  
 Typically, this method can compare the addresses of the values represented by the `pObject` parameter and this [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) object; if the addresses are equal, then the objects can be considered equal.  
  
## <a name="see-also"></a>See Also  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
