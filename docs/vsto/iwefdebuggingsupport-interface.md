---
title: "IWefDebuggingSupport 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 7b132c51e12d553bcd6e722e87c8aeee96be5e5c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="iwefdebuggingsupport-interface"></a>IWefDebuggingSupport 인터페이스
  Office 용 앱의 디버깅을 용이 하 게 하려면 Visual Studio와 같은 디버깅 환경에서 구현 합니다. Word 또는 Excel과 같은 Office 응용 프로그램 Visual Studio에서이 인터페이스를 가져오고 디버깅 세션 중 특정 시점에서 인터페이스의 메서드를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[  
    uuid(ccaf1a90-ce1c-4199-9cd6-b40c5c57a671),  
    oleautomation  
]  
interface IWefDebuggingSupport : IUnknown  
{  
    HRESULT SetWefProcessId(  
        [in] DWORD dwProcessId);  
    HRESULT GetAutoInsertExtensions(  
        [out, retval] SAFEARRAY(BSTR)* psaExtensionNames);  
}  
```  
  
## <a name="methods"></a>메서드  
 다음 표에서 IWefDebuggingSupport 인터페이스를 정의 하는 메서드를 보여 줍니다.  
  
|name|설명|  
|----------|-----------------|  
|[GetAutoInsertExtensions 메서드](../vsto/getautoinsertextensions-method.md)|디버깅 하는 동안 자동으로 삽입 될 Office 용 앱에 대 한 정보를 가져옵니다.|  
|[SetWefProcessId 메서드](../vsto/setwefprocessid-method.md)|웹 확장 프레임 워크 (WEF) 콘텐츠를 실행 하는 프로세스 식별자를 제공 합니다.|  
  
  