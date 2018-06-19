---
title: 상태 표시줄 확장 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- status bars, about status bars
- status bars, overview
ms.assetid: f955115c-4c5f-45ec-b41b-365868c5ec0c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a766e0c607d4d669fada794e1cf0779559f2346b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31130494"
---
# <a name="extending-the-status-bar"></a>상태 표시줄을 확장합니다.
IDE의 맨 아래에 정보를 표시 하려면 Visual Studio 상태 표시줄을 사용할 수 있습니다.  
  
 4 개 지역에서 정보 및 UI 상태 표시줄을 확장 하는 경우 표시할 수 있습니다: 피드백 영역, 진행률 표시줄, 애니메이션 영역 및 디자이너 영역입니다. 피드백 영역을 사용 하면 텍스트를 표시 하 고 표시 된 텍스트를 강조 표시할 수 있습니다. 진행률 표시줄에는 파일을 저장 하는 등 단기 실행 작업에 대 한 증분 진행률이 표시 됩니다. 애니메이션 영역 장기 실행 작업 또는 결정 되지 않은 길이, 솔루션의 여러 프로젝트를 만드는 등의 작업에 대해 계속 반복 애니메이션을 표시 합니다. 및 디자이너 영역 커서 위치의 줄 및 열 번호를 보여 줍니다.  
  
 상태 표시줄을 사용 하 여 가져올 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar> 인터페이스 (에서 <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> 서비스). 또한 창 프레임에 배치 하는 모든 개체를 구현 하 여 상태 표시줄 클라이언트 개체도 등록할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> 인터페이스입니다. Visual Studio에 대 한 해당 창에 배치 하는 개체를 쿼리 창이 활성화 될 때마다는 `IVsStatusbarUser` 인터페이스입니다. 발견 호출는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> 메서드 반환 되는 인터페이스와 개체를이 메서드 내에서 상태 표시줄에서 업데이트할 수 있습니다. 예를 들어 windows, 문서, 사용할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> 활성화 될 때 디자이너 영역에 대 한 정보를 업데이트 하는 메서드.  
  
 다음 절차는 VSIX 프로젝트를 만들고 사용자 지정 메뉴 명령을 추가 하는 방법을 알고 가정 합니다. 자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
## <a name="modifying-the-status-bar"></a>상태 표시줄을 수정합니다.  
 이 절차에서는 설정 하 고 텍스트를 정적 텍스트를 표시 하는 상태 표시줄의 피드백 영역에 표시 된 텍스트를 강조 표시 하는 방법을 보여 줍니다.  
  
#### <a name="reading-and-writing-to-the-status-bar"></a>읽기 및 쓰기를 상태 표시줄  
  
1.  라는 VSIX 프로젝트를 **TestStatusBarExtension** 라는 메뉴 명령을 추가 하 고 **TestStatusBarCommand**합니다.  
  
2.  TestStatusBarCommand.cs를에서 (MenuItemCallback) 명령 처리기 메서드 코드를 다음으로 바꿉니다.  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar = (IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
  
        // Make sure the status bar is not frozen  
        int frozen;  
  
        statusBar.IsFrozen(out frozen);  
  
        if (frozen != 0)   
        {  
            statusBar.FreezeOutput(0);  
        }  
  
        // Set the status bar text and make its display static.  
        statusBar.SetText("We just wrote to the status bar.");  
  
        // Freeze the status bar.  
        statusBar.FreezeOutput(1);  
  
        // Get the status bar text.   
        string text;  
        statusBar.GetText(out text);  
        System.Windows.Forms.MessageBox.Show(text);  
  
        // Clear the status bar text.  
        statusBar.FreezeOutput(0);  
        statusBar.Clear();  
    }  
    ```  
  
3.  코드를 컴파일하고 디버깅을 시작 합니다.  
  
4.  열기는 **도구** Visual Studio의 실험적 인스턴스에서 메뉴. 클릭는 **호출 TestStatusBarCommand** 단추입니다.  
  
     나타나야 하는 상태 표시줄 지금은 읽기에에서 텍스트 **"म 상태 표시줄 방금 작성 했습니다."** 및 표시 되는 메시지 상자에는 동일한 텍스트입니다.  
  
#### <a name="updating-the-progress-bar"></a>진행률 표시줄을 업데이트합니다.  
  
1.  이 절차에서는 초기화 하 고 진행률 표시줄을 업데이트 하는 방법을 보여줍니다.  
  
2.  TestStatusBarCommand.cs 파일을 열고 MenuItemCallback 메서드를 다음 코드로 바꿉니다.  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar = (IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
        uint cookie = 0;  
        string label = "Writing to the progress bar";  
  
        // Initialize the progress bar.  
        statusBar.Progress(ref cookie, 1, "", 0, 0);  
  
        for (uint i = 0, total = 20; i <= total; i++)  
        {  
            // Display progress every second.  
            statusBar.Progress(ref cookie, 1, label, i, total);  
            System.Threading.Thread.Sleep(1000);  
        }  
  
        // Clear the progress bar.  
        statusBar.Progress(ref cookie, 0, "", 0, 0);  
    }  
    ```  
  
3.  코드를 컴파일하고 디버깅을 시작 합니다.  
  
4.  열기는 **도구** Visual Studio의 실험적 인스턴스에서 메뉴. 클릭 **호출 TestStatusBarCommand** 단추입니다.  
  
     나타나야 하는 상태 표시줄 지금은 읽기에에서 텍스트 **"진행률 표시줄을 기록 합니다."** 또한 업데이트 되는 초당 20 초 동안 진행률 표시줄이 표시 됩니다. 그 후 상태 표시줄 및 진행률 표시줄 취소 됩니다.  
  
#### <a name="displaying-an-animation"></a>애니메이션을 표시합니다.  
  
1.  상태 표시줄 반복 애니메이션 하나를 의미할 수입니다 (예: 솔루션의 여러 프로젝트 빌드) 장기 실행 작업을 표시 합니다. 이 애니메이션을 표시 되지 않으면 올바른 했는지 확인 **도구 / 옵션** 설정:  
  
     이동 하 여 **도구/옵션 / 일반** 탭 및 선택 취소 **클라이언트 성능에 따른 시각적 효과 자동 조정**합니다. 다음 하위 옵션을 확인 **리치 클라이언트 시각적 효과 사용 하도록 설정**합니다. 이제 Visual Studio의 실험적 인스턴스에 프로젝트를 빌드할 때 애니메이션을 볼 수 있습니다.  
  
     이 절차에서는 프로젝트 또는 솔루션을 빌드를 나타내는 표준 Visual Studio 애니메이션을 표시 합니다.  
  
2.  TestStatusBarCommand.cs 파일을 열고 MenuItemCallback 메서드를 다음 코드로 바꿉니다.  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar =(IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
  
        // Use the standard Visual Studio icon for building.  
        object icon = (short)Microsoft.VisualStudio.Shell.Interop.Constants.SBAI_Build;  
  
        // Display the icon in the Animation region.  
        statusBar.Animation(1, ref icon);  
  
        // The message box pauses execution for you to look at the animation.  
        System.Windows.Forms.MessageBox.Show("showing?");  
  
        // Stop the animation.   
        statusBar.Animation(0, ref icon);  
    }  
    ```  
  
3.  코드를 컴파일하고 디버깅을 시작 합니다.  
  
4.  열기는 **도구** 메뉴를 클릭 하 고 Visual Studio의 실험적 인스턴스에서 **호출 TestStatusBarCommand**합니다.  
  
     메시지 상자를 보면 맨 오른쪽에 있는 상태 표시줄에 애니메이션을도 표시 됩니다. 메시지 상자를 닫고 애니메이션이 사라집니다.