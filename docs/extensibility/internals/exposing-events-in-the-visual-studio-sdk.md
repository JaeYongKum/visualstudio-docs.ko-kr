---
title: Visual Studio SDK에에서는 이벤트를 노출 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- events [Visual Studio], exposing
- automation [Visual Studio SDK], exposing events
ms.assetid: 70bbc258-c221-44f8-b0d7-94087d83b8fe
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 02ddcf0c2321f6f4c07170117c6474b993c340f4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132236"
---
# <a name="exposing-events-in-the-visual-studio-sdk"></a>Visual Studio SDK에에서는 이벤트를 노출
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 있습니다 자동화를 사용 하 여 이벤트 소스입니다. 프로젝트 및 프로젝트 항목에 대 한 이벤트 소스는 것이 좋습니다.  
  
 이벤트에서 자동화 소비자가 검색 되는 <xref:EnvDTE.DTEClass.Events%2A> 개체 또는 <xref:EnvDTE.DTEClass.GetObject%2A> ("EventObjectName"). 환경 `IDispatch::Invoke` 를 사용 하 여는 `DISPATCH_METHOD` 또는 `DISPATCH_PROPERTYGET` 이벤트를 반환 하는 플래그입니다.  
  
 다음 프로세스에서는 VSPackage 관련 이벤트 반환 되는 방법을 설명 합니다.  
  
1.  환경을 시작합니다.  
  
2.  레지스트리에서 모든 Vspackage, 자동화, AutomationEvents 및 AutomationProperties 키 아래의 모든 값 이름이 읽고 이러한 이름을 테이블에 저장 합니다.  
  
3.  이 예제에서는 자동화 소비자 호출 `DTE.Events.AutomationProjectsEvents` 또는 `DTE.Events.AutomationProjectItemsEvents`합니다.  
  
4.  환경은 테이블에 문자열 매개 변수를 찾아서 해당 VSPackage를 로드 합니다.  
  
5.  환경에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> 메서드 이름을 사용 하 여이 예제에서는 AutomationProjectsEvents 또는 AutomationProjectItemsEvents; 호출에 전달 합니다.  
  
6.  VSPackage에 메서드가 같은 루트 개체를 만듭니다 `get_AutomationProjectsEvents` 및 `get_AutomationProjectItemEvents` 을 다음 개체를 IDispatch 포인터를 반환 합니다.  
  
7.  환경 자동화 호출에 전달 된 이름을 기반으로 적절 한 메서드를 호출 합니다.  
  
8.  `get_` 메서드 둘 다 구현 하는 다른 IDispatch 기반 이벤트 개체를 만듭니다.는 `IConnectionPointContainer` 인터페이스 및 `IConnectionPoint` 인터페이스를 개체에는 IDispatchpointer를 반환 합니다.  
  
 자동화를 사용 하 여 이벤트를 노출 하려면에 응답 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> 감시할을 레지스트리에 추가 하는 문자열입니다. 기본적인 Project 예제에는 문자열은 "BscProjectsEvents" 및 "BscProjectItemsEvents"입니다.  
  
## <a name="registry-entries-from-the-basic-project-sample"></a>기본 프로젝트 샘플에서 레지스트리 항목  
 이 섹션에서는 레지스트리에 자동화 이벤트 값을 추가 하는 위치를 보여 줍니다.  
  
 [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Packages\\< PkgGUID\>\AutomationEvents]  
  
 "AutomationProjectEvents 개체를 반환 AutomationProjectEvents"=""  
  
 "AutomationProjectItemsEvents 개체를 반환 AutomationProjectItemEvents"=""  
  
|이름|형식|범위|설명|  
|----------|----------|-----------|-----------------|  
|기본 (@)|REG_SZ|사용 하지 않는|사용되지 않습니다. 설명서에 대 한 데이터 필드를 사용할 수 있습니다.|  
|AutomationProjectsEvents|REG_SZ|이벤트 개체의 이름입니다.|키 이름에만 관련이 있습니다. 설명서에 대 한 데이터 필드를 사용할 수 있습니다.<br /><br /> 이 예제에서는 기본 프로젝트 샘플에서 제공 됩니다.|  
|AutomationProjectItemEvents|REG_SZ|이벤트 개체의 이름|키 이름에만 관련이 있습니다. 설명서에 대 한 데이터 필드를 사용할 수 있습니다.<br /><br /> 이 예제에서는 기본 프로젝트 샘플에서 제공 됩니다.|  
  
 이벤트 개체는 자동화 소비자에 의해 요청 된 경우에 VSPackage가 지 원하는 모든 이벤트에 대 한 메서드가 포함 루트 개체를 만듭니다. 환경에서 적절 한 호출 `get_` 이 개체에서 메서드. 예를 들어 경우 `DTE.Events.AutomationProjectsEvents` 호출 되는 `get_AutomationProjectsEvents` 루트 개체에서 메서드를 호출 합니다.  
  
 ![Visual Studio 프로젝트 이벤트](../../extensibility/internals/media/projectevents.gif "ProjectEvents")  
이벤트에 대 한 자동화 모델  
  
 클래스 `CProjectEventsContainer` BscProjectsEvents에 대 한 소스 개체를 나타내는 반면 `CProjectItemsEventsContainer` BscProjectItemsEvents에 대 한 원본 개체를 나타냅니다.  
  
 대부분의 경우 대부분의 이벤트 개체는 필터 개체를 사용 하기 때문에 모든 이벤트 요청에 대해 새 개체를 반환 해야 합니다. 이벤트를 발생 하는 경우 이벤트 처리기가 호출 되 고 있는지 확인 하려면이 필터를 확인 합니다.  
  
 AutomationEvents.h 및 AutomationEvents.cpp 선언 및 다음 표에 클래스의 구현을 포함 합니다.  
  
|클래스|설명|  
|-----------|-----------------|  
|`CAutomationEvents`|검색 하는 이벤트 루트 개체를 구현 하는 `DTE.Events` 개체입니다.|  
|`CProjectsEventsContainer` 및 `CProjectItemsEventsContainer`|해당 이벤트를 실행 하는 이벤트 소스 개체를 구현 합니다.|  
  
 다음 코드 예제에는 이벤트 개체에 대 한 요청에 응답 하는 방법을 보여 줍니다.  
  
```cpp  
STDMETHODIMP CVsPackage::GetAutomationObject(  
    /* [in]  */ LPCOLESTR       pszPropName,   
    /* [out] */ IDispatch **    ppIDispatch)  
{  
    ExpectedPtrRet(ppIDispatch);  
    *ppIDispatch = NULL;  
  
    if (_wcsicmp(pszPropName, g_wszAutomationProjects) == 0)   
        //Is the requested name our Projects object?  
    {  
        return GetAutomationProjects(ppIDispatch);  
        // Gets our Projects object.  
    }  
    else if (_wcsicmp(pszPropName, g_wszAutomationProjectsEvents) == 0)  
        //Is the requested name our ProjectsEvents object?  
    {  
        return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
          // Gets our ProjectEvents object.  
    }  
    else if (_wcsicmp(pszPropName, g_wszAutomationProjectItemsEvents) == 0)  //Is the requested name our ProjectsItemsEvents object?  
    {  
        return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
          // Gets our ProjectItemsEvents object.  
    }  
    return E_INVALIDARG;  
}  
```  
  
 위의 코드에서 `g_wszAutomationProjects` ("FigProjects"), 프로젝트 컬렉션의 이름 `g_wszAutomationProjectsEvents` ("FigProjectsEvents") 및 `g_wszAutomationProjectItemsEvents` ("FigProjectItemEvents")은 프로젝트 이벤트의 이름 및 프로젝트 항목에서 발생 한 이벤트를 프로그램 VSPackage 구현입니다.  
  
 이벤트 개체는 같은 중앙 위치에서 검색 되는 `DTE.Events` 개체입니다. 이러한 방식으로 모든 이벤트 개체 그룹화 되어 최종 사용자는 특정 이벤트를 찾으려면 전체 개체 모델을 검색 하지 않아도 되도록 있습니다. 이렇게 또한 하면 시스템 수준 이벤트에 대 한 사용자 고유의 코드를 구현 해야 하는 대신 특정 VSPackage 개체를 제공 합니다. 그러나 최종 사용자에 게 찾아야에 대 한 이벤트 프로그램 `ProjectItem` 인터페이스를 즉시가 확실 하지 않으면 해당 이벤트 개체가 검색 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>   
 [VSSDK 샘플](http://aka.ms/vs2015sdksamples)