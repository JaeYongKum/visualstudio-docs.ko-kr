---
title: IDebugPortPicker | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugPortPicker interface
ms.assetid: 8b7f6685-a3c5-4355-b706-c1b574f6ff84
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 486efef813d3657b3a1b76ff5f64834f3b84a628
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51800993"
---
# <a name="idebugportpicker"></a>IDebugPortPicker
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

포트를 선택 하기 위한 사용자 지정된 UI를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPortPicker : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 인터페이스는 포트 공급자가 구현 됩니다. 포트 공급자 없거나 CLSID로 노출 하 고 가리키는 하 여 해당 포트 선택을 정의 `metricPortPickerCLSID` 노출 된 CLSID에 메트릭.  
  
## <a name="methods"></a>메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugPortPicker`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[DisplayPortPicker](../../../extensibility/debugger/reference/idebugportpicker-displayportpicker.md)|사용자가 포트를 선택할 수 있도록 지정 된 대화 상자가 표시 됩니다.|  
|[SetSite](../../../extensibility/debugger/reference/idebugportpicker-setsite.md)|서비스 공급자를 설정합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

