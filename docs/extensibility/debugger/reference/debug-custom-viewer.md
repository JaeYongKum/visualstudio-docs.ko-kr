---
title: DEBUG_CUSTOM_VIEWER | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DEBUG_CUSTOM_VIEWER
helpviewer_keywords:
- DEBUG_CUSTOM_VIEWER structure
ms.assetid: 8e0ef3f0-0107-48e8-a037-6e52b4c4ed9d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe17c8747d5c678c14561a918ddd9d62bd658841
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315835"
---
# <a name="debugcustomviewer"></a>DEBUG_CUSTOM_VIEWER
사용자 지정 뷰어를 식별 하는 구조체 시각화 도우미를 입력 합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct tagDEBUG_CUSTOM_VIEWER {
    DWORD dwID;
    BSTR  bstrMenuName;
    BSTR  bstrDescription;
    GUID  guidLang;
    GUID  guidVendor;
    BSTR  bstrMetric;
} DEBUG_CUSTOM_VIEWER;
```

```csharp
public struct DEBUG_CUSTOM_VIEWER {
    public uint   dwID;
    public string bstrMenuName;
    public string bstrDescription;
    public Guid   guidLang;
    public Guid   guidVendor;
    public string bstrMetric;
};
```

## <a name="members"></a>멤버
dwID  
여러 뷰어 또는 하나에 의해 구현 되는 시각화 도우미를 구분 하기 위해 ID `GUID`합니다.

bstrMenuName  
드롭다운 메뉴에 나타나는 텍스트입니다.

bstrDescription  
사용자 지정 뷰어 또는 형식 시각화 도우미 (이어야 함 null 값을 사용 하지 않는 경우)의 설명입니다.

guidLang  
제공 하는 식 계산기의 언어입니다.

guidVendor  
제공 하는 식 계산기의 공급 업체입니다.

bstrMetric  
메트릭 사용자 지정 뷰어 또는 형식 시각화 도우미 `CLSID` 저장 됩니다.

## <a name="remarks"></a>설명
호출 하 여이 구조체의 목록이 반환 됩니다 합니다 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 메서드 (및 확장에 의해 합니다 [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) 메서드).

## <a name="requirements"></a>요구 사항
헤더: msdbg.h

네임스페이스: Microsoft.VisualStudio.Debugger.Interop

어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>참고 항목
[클래스 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)  
[GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)  
[GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)
