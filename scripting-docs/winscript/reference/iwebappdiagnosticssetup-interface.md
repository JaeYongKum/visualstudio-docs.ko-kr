---
title: IWebAppDiagnosticsSetup 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsSetup Interface
ms.assetid: ec7359f2-633e-4d59-b64b-9cab0134dfd0
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fc29282ec9d00ff79131765d2bf294c54fa347c6
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344904"
---
# <a name="iwebappdiagnosticssetup-interface"></a>IWebAppDiagnosticsSetup 인터페이스
이 인터페이스는 PDM 디버그 응용 프로그램을 디버깅 중인 프로세스에 COM 개체를 만들 웹 진단을 사용 하도록 설정 하 여 구현 됩니다. PDM 디버깅 응용 프로그램 개체를 구현 하는 경우 [IObjectWithSite](http://go.microsoft.com/fwlink/?LinkId=232438)를 호출 하는 Internet Explorer [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439) 에 생성 된 후에 그에 대 한 참조가 전달 [IWebBrowser2](http://go.microsoft.com/fwlink/?LinkId=232449). WWA 응용 프로그램을 호출 [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439) IWebApplicationHost를 대신 인터페이스는 WWA 전달 합니다. 하는 경우 [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439) 는 NULL이 아닌 값을 사용 하 여 호출한 [IWebAppDiagnosticsSetup::DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md) true를 반환 합니다. 그렇지 않으면 false를 반환 하 고 호출 하는 경우 [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) 실패 합니다.  
  
> [!IMPORTANT]
>  `IWebAppDiagnosticsSetup` 여 PDM v11.0 이상 구현 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="methods"></a>메서드  
 이 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)|지정한 필터에 의해 숨겨진 텍스트 문서를 가져옵니다.|  
|[IWebAppDiagnosticsSetup::DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md)|지정된 된 문서가 노드의 자식 노드 중 하나에 속하는지 여부를 결정 합니다.|