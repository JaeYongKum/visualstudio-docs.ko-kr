---
title: '방법: 찾기 구현 및 메커니즘을 바꾸기 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - find and replace
ms.assetid: bbd348db-3d19-42eb-99a2-3e808528c0ca
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: eaae77979fc15954b4480a038c791a15bd95ab65
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47543436"
---
# <a name="how-to-implement-the-find-and-replace-mechanism"></a>방법: 구현 찾기 및 바꾸기 메커니즘
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [방법: 찾기 및 바꾸기 메커니즘을 구현](https://docs.microsoft.com/visualstudio/extensibility/how-to-implement-the-find-and-replace-mechanism)합니다.  
  
Visual Studio 찾기/바꾸기를 구현 하는 두 가지를 제공 합니다. 한 가지 방법은 셸에 텍스트 이미지를 전달 하 고 검색, 강조 표시 및 대체 텍스트를 처리 하도록 하는 것입니다. 이 여러 텍스트 범위를 지정할 수가 있습니다. 또는 VSPackage는 자체에서 이러한 기능을 제어할 수 있습니다. 두 경우 모두 현재 대상 및 열려 있는 모든 문서에 대 한 대상에 대 한 shell에 알려야 합니다.  
  
### <a name="to-implement-findreplace"></a>찾기/바꾸기 구현 하려면  
  
1.  구현 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget> 프레임 속성에서 반환한 개체 중 하나에서 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>합니다. 사용자 지정 편집기를 만드는 경우 사용자 지정 편집기 클래스의 일부로이 인터페이스를 구현 해야 합니다.  
  
2.  사용 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetCapabilities%2A> 메서드 편집기를 지 원하는 옵션을 지정 하 고 텍스트 이미지 검색를 구현 하는지 여부를 나타냅니다.  
  
     편집기 텍스트 이미지 검색을 지 원하는 경우 구현 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>합니다.  
  
     그렇지 않으면 구현 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> 고 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>입니다.  
  
3.  구현 하는 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> 하 고 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A> 메서드를 호출 하 여 검색 작업을 간소화할 수 있습니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper> 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>
