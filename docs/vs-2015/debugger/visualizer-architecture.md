---
title: 시각화 도우미 아키텍처 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 6aad395f-7170-4d9e-b2b8-a5faf453380e
caps.latest.revision: 20
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b7a3255b8e8b91f074308a0238719f26af6cf665
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51736156"
---
# <a name="visualizer-architecture"></a>시각화 도우미 아키텍처
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

디버거 시각화 도우미의 아키텍처는 두 부분으로 구성되어 있습니다.  
  
- 합니다 *디버거 쪽* Visual Studio 디버거 내에서 실행 됩니다. 디버거 쪽 코드에서는 시각화 도우미의 사용자 인터페이스를 만들고 표시합니다.  
  
- 합니다 *디버기 쪽* Visual Studio가 디버깅 하는 프로세스 내에서 실행 (합니다 *디버기*).  
  
  시각화 도우미는 디버거에서 표시할 수 있도록 하는 디버거 구성 요소 (*시각화*) 의미 있고 이해할 수 있는 형식에 데이터 개체의 콘텐츠입니다. 일부 시각화 도우미에서는 데이터 개체를 편집할 수도 있습니다. 사용자 지정 시각화 도우미를 작성하면 고유한 사용자 지정 데이터 형식을 처리하도록 디버거를 확장할 수 있습니다.  
  
  시각화할 데이터 개체는 디버깅할 프로세스 내에 상주 (합니다 *디버기* 프로세스). 데이터를 표시하는 사용자 인터페이스는 Visual Studio 디버거 프로세스 내에서 만들어집니다.  
  
|디버거 프로세스|디버기 프로세스|  
|----------------------|----------------------|  
|디버거 사용자 인터페이스(DataTip, 조사식 창, 간략한 조사식)|시각화할 데이터 개체|  
  
 디버거 인터페이스 내에서 데이터 개체를 시각화하려면 두 프로세스 사이에서 통신하는 코드가 필요합니다. 시각화 도우미 아키텍처 두 부분으로 이루어져 따라서: *디버거 쪽* 코드 및 *디버기 쪽* 코드입니다.  
  
 디버거 쪽 코드에서는 DataTip, 조사식 창, 간략한 조사식 등의 디버거 인터페이스에서 호출할 수 있는 자체 사용자 인터페이스를 만듭니다. 시각화 도우미 인터페이스는 <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer> 클래스와 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> 인터페이스를 사용하여 만들어집니다. 모든 시각화 도우미 API와 마찬가지로 DialogDebuggerVisualizer 및 IDialogVisualizerService는 <xref:Microsoft.VisualStudio.DebuggerVisualizers> 네임스페이스에 있습니다.  
  
|디버거 쪽|디버기 쪽|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer 클래스<br /><br /> IDialogVisualizerService 인터페이스|데이터 개체|  
  
 사용자 인터페이스를 통해 디버거 쪽에 있는 개체 공급자에서 시각화할 데이터를 가져옵니다.  
  
|디버거 쪽|디버기 쪽|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer 클래스<br /><br /> IDialogVisualizerService 인터페이스|데이터 개체|  
|개체 공급자(<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> 구현)||  
  
 디버기 쪽에는 개체 소스라는 해당 개체가 있습니다.  
  
|디버거 쪽|디버기 쪽|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer 클래스<br /><br /> IDialogVisualizerService 인터페이스|데이터 개체|  
|개체 공급자(<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> 구현)|개체 소스(<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>에서 파생)|  
  
 개체 공급자는 시각화 도우미 UI에 시각화할 개체 데이터를 제공합니다. 개체 공급자는 개체 소스에서 개체 데이터를 가져옵니다. 개체 공급자와 개체 소스는 디버거 쪽과 디버기 쪽 사이에 개체 데이터를 주고받는 API를 제공합니다.  
  
 모든 시각화 도우미는 시각화할 데이터 개체를 가져와야 합니다. 다음 표에서는 이러한 용도로 개체 공급자와 개체 소스에서 사용되는 해당 API를 보여 줍니다.  
  
|개체 공급자|개체 소스|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A><br /><br /> 또는<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A>|  
  
 개체 공급자는 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A> 또는 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A>를 사용할 수 있습니다. 두 가지 API 모두 개체 소스를 대상으로 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A>를 호출하게 됩니다. 에 대 한 호출 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A?displayProperty=fullName> [System.IO.Stream] 채웁니다 (<!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  -->), serialize 된 형태로 시각화 되 고 있는 개체를 나타내는입니다.  
  
 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A?displayProperty=fullName>는 데이터를 다시 개체 폼으로 deserialize합니다. 그런 다음 <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>를 사용하여 만든 UI에 이 개체 폼을 표시할 수 있습니다. <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName>는 사용자가 직접 deserialize해야 하는 원시 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  -->으로 데이터를 채웁니다. <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A?displayProperty=fullName>는 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName>를 호출하여 serialize된 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  -->을 가져온 다음 데이터를 deserialize하는 방식으로 작동합니다. .NET을 통해 개체를 serialize할 수 없고 사용자가 직접 serialize해야 하는 경우에는 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName>를 사용합니다. 이러한 경우 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.Serialize%2A?displayProperty=fullName> 메서드도 재정의해야 합니다.  
  
 읽기 전용 시각화 도우미를 만드는 경우에는 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A> 또는 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A>를 사용한 단방향 통신으로도 충분합니다. 데이터 개체 편집을 지원하는 시각화 도우미를 만드는 경우에는 더 많은 단계를 거쳐야 합니다. 이러한 경우 개체 공급자에서 개체 소스로 데이터 개체를 다시 전달할 수도 있어야 합니다. 다음 표에서는 이러한 용도로 사용되는 개체 공급자 및 개체 소스 API를 보여 줍니다.  
  
|개체 공급자|개체 소스|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A><br /><br /> 또는<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.CreateReplacementObject%2A>|  
  
 이 경우에도 개체 공급자에서 두 가지 API를 사용할 수 있습니다. 데이터는 항상 개체 공급자에서 개체 소스로 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  -->으로 전달되지만 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A>를 사용하는 경우 사용자가 개체를 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  -->으로 serialize해야 합니다.  
  
 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceObject%2A>는 사용자가 제공한 개체를 받아 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  -->으로 serialize한 다음 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A>를 호출하여 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  -->을 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.CreateReplacementObject%2A>에 전달합니다.  
  
 Replace 메서드 중 하나를 사용하면 디버기에서 시각화 대상 개체를 대체하는 새 데이터 개체가 만들어집니다. 원래 개체를 바꾸지 않고 내용을 변경하려는 경우에는 다음 표에 나와 있는 Transfer 메서드 중 하나를 사용합니다. 이들 API는 시각화 대상 개체를 바꾸지 않고 데이터를 양방향으로 동시에 전송합니다.  
  
|개체 공급자|개체 소스|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.TransferData%2A><br /><br /> 또는<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.TransferObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.TransferData%2A>|  
  
## <a name="see-also"></a>참고 항목  
 [방법: 시각화 도우미 작성](../debugger/how-to-write-a-visualizer.md)   
 [연습: C#에서 시각화 도우미 작성](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)   
 [연습: Visual Basic에서 시각화 도우미 작성](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)   
 [연습: Visual Basic에서 시각화 도우미 작성](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)   
 [시각화 도우미 보안 고려 사항](../debugger/visualizer-security-considerations.md)



