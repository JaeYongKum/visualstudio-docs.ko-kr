---
title: '방법: ClickOnce 신뢰 프롬프트 동작 구성 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, install without prompting
- deploying applications [ClickOnce], trust prompt
- ClickOnce applications, install without prompting
- ClickOnce applications, trust prompt
- ClickOnce deployment, trust prompt
ms.assetid: cc04fa75-012b-47c9-9347-f4216be23cf2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f2869e76b0b5fd70515701352d257530480f0920
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56618135"
---
# <a name="how-to-configure-the-clickonce-trust-prompt-behavior"></a>방법: ClickOnce 신뢰 프롬프트 동작 구성
최종 사용자가 Windows Forms 응용 프로그램, Windows Presentation Foundation 응용 프로그램, 콘솔 응용 프로그램, WPF 브라우저 등의 ClickOnce 응용 프로그램을 설치 하는 옵션이 제공 됩니다 컨트롤에 ClickOnce 신뢰 프롬프트를 구성할 수 있습니다. Office 솔루션 및 응용 프로그램입니다. 각 최종 사용자의 컴퓨터에서 레지스트리 키를 설정 하 여 신뢰 프롬프트를 구성 합니다.

 다음 표에서 각 영역 5 (인터넷, UntrustedSites, MyComputer, LocalIntranet, 및 TrustedSites)에 적용할 수 있는 구성 옵션을 보여 줍니다.

|옵션|레지스트리 설정 값|설명|
|------------|----------------------------|-----------------|
|신뢰 프롬프트를 사용 하도록 설정 합니다.|`Enabled`|ClickOnce 신뢰 프롬프트를 최종 사용자에 게 ClickOnce 응용 프로그램 신뢰를 부여할 수 있도록 표시 됩니다.|
|신뢰 프롬프트를 제한 합니다.|`AuthenticodeRequired`|ClickOnce 신뢰 프롬프트는 ClickOnce 응용 프로그램 게시자를 식별 하는 인증서를 사용 하 여 서명 된 경우에 표시 됩니다.|
|신뢰 프롬프트를 사용 하지 않도록 설정 합니다.|`Disabled`|ClickOnce 신뢰 프롬프트를 명시적으로 신뢰할 수 있는 인증서로 서명 되지 않은 ClickOnce 응용 프로그램에 대 한 표시 되지 않습니다.|

 다음 표에서 각 영역에 대 한 기본 동작을 보여 줍니다. 응용 프로그램 열 Windows Forms 응용 프로그램, Windows Presentation Foundation 응용 프로그램, WPF 브라우저 응용 프로그램 및 콘솔 응용 프로그램을 가리킵니다.

|영역|애플리케이션|Office 솔루션|
|----------|------------------|----------------------|
|`MyComputer`|`Enabled`|`Enabled`|
|`LocalIntranet`|`Enabled`|`Enabled`|
|`TrustedSites`|`Enabled`|`Enabled`|
|`Internet`|`Enabled`|`AuthenticodeRequired`|
|`UntrustedSites`|`Disabled`|`Disabled`|

 활성화, 제한, 또는 ClickOnce 신뢰 프롬프트를 사용 하지 않도록 설정 하 여 이러한 설정을 재정의할 수 있습니다.

## <a name="enable-the-clickonce-trust-prompt"></a>ClickOnce 신뢰 프롬프트를 사용 하도록 설정
 최종 사용자가 설치 하 고 해당 영역에서 제공 되는 ClickOnce 응용 프로그램을 실행 하는 옵션이 표시 하려는 경우 영역에 대 한 신뢰 프롬프트를 사용 하도록 설정 합니다.

#### <a name="to-enable-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>레지스트리 편집기를 사용 하 여 ClickOnce 신뢰 프롬프트를 사용 하도록 설정 하려면

1.  레지스트리 편집기를 엽니다.

    1.  **시작**을 클릭한 다음, **실행**을 클릭합니다.

    2.  에 **열기** 상자에 입력 `regedit`를 클릭 하 고 **확인**합니다.

2.  다음 레지스트리 키를 찾습니다.

     **\HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\.NETFramework\Security\TrustManager\PromptingLevel**

     키가 없으면 만듭니다.

3.  다음 하위 키를 추가 **문자열 값**이미 없는, 연결 된 값이 다음 표에 표시 된 경우.

    |문자열 값의 하위 키|값|
    |-------------------------|-----------|
    |`Internet`|`Enabled`|
    |`UntrustedSites`|`Disabled`|
    |`MyComputer`|`Enabled`|
    |`LocalIntranet`|`Enabled`|
    |`TrustedSites`|`Enabled`|

     Office 솔루션에 대 한 `Internet` 는 기본값이 `AuthenticodeRequired` 하 고 `UntrustedSites` 값이 `Disabled`합니다. 나머지 모든 작업에 대 한 `Internet` 에 기본값이 `Enabled`합니다.

#### <a name="to-enable-the-clickonce-trust-prompt-programmatically"></a>프로그래밍 방식으로 ClickOnce 신뢰 프롬프트를 사용 하도록 설정 하려면

1.  Visual Basic 또는 시각적 개체 만들기 C# Visual Studio에서 응용 프로그램 콘솔.

2.  엽니다는 *Program.vb* 또는 *Program.cs* 편집에 대 한 파일을 다음 코드를 추가 합니다.

    ```vb
    Dim key As Microsoft.Win32.RegistryKey
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")
    key.SetValue("MyComputer", "Enabled")
    key.SetValue("LocalIntranet", "Enabled")
    key.SetValue("Internet", "Enabled")
    key.SetValue("TrustedSites", "Enabled")
    key.SetValue("UntrustedSites", "Disabled")
    key.Close()
    ```

    ```csharp
    Microsoft.Win32.RegistryKey key;
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");
    key.SetValue("MyComputer", "Enabled");
    key.SetValue("LocalIntranet", "Enabled");
    key.SetValue("Internet", "AuthenticodeRequired");
    key.SetValue("TrustedSites", "Enabled");
    key.SetValue("UntrustedSites", "Disabled");
    key.Close();
    ```

3.  애플리케이션을 빌드 및 실행합니다.

## <a name="restrict-the-clickonce-trust-prompt"></a>ClickOnce 신뢰 프롬프트를 제한 합니다.
 솔루션 사용자 신뢰 여부를 결정 하 라는 메시지가 표시 됩니다 전에 알려진 id가 있는 Authenticode 인증서로 서명 될 수 있도록 신뢰 프롬프트를 제한 합니다.

#### <a name="to-restrict-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>레지스트리 편집기를 사용 하 여 ClickOnce 신뢰 프롬프트를 제한 하려면

1.  레지스트리 편집기를 엽니다.

    1.  **시작**을 클릭한 다음, **실행**을 클릭합니다.

    2.  에 **열기** 상자에 입력 `regedit`를 클릭 하 고 **확인**합니다.

2.  다음 레지스트리 키를 찾습니다.

     **\HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\.NETFramework\Security\TrustManager\PromptingLevel**

     키가 없으면 만듭니다.

3.  다음 하위 키를 추가 **문자열 값**이미 없는, 연결 된 값이 다음 표에 표시 된 경우.

    |문자열 값의 하위 키|값|
    |-------------------------|-----------|
    |`UntrustedSites`|`Disabled`|
    |`Internet`|`AuthenticodeRequired`|
    |`MyComputer`|`AuthenticodeRequired`|
    |`LocalIntranet`|`AuthenticodeRequired`|
    |`TrustedSites`|`AuthenticodeRequired`|

#### <a name="to-restrict-the-clickonce-trust-prompt-programmatically"></a>ClickOnce 신뢰 프롬프트를 프로그래밍 방식으로 제한 하려면

1.  Visual Basic 또는 시각적 개체 만들기 C# Visual Studio에서 응용 프로그램 콘솔.

2.  엽니다는 *Program.vb* 또는 *Program.cs* 편집에 대 한 파일을 다음 코드를 추가 합니다.

    ```vb
    Dim key As Microsoft.Win32.RegistryKey
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")
    key.SetValue("MyComputer", "AuthenticodeRequired")
    key.SetValue("LocalIntranet", "AuthenticodeRequired")
    key.SetValue("Internet", "AuthenticodeRequired")
    key.SetValue("TrustedSites", "AuthenticodeRequired")
    key.SetValue("UntrustedSites", "Disabled")
    key.Close()
    ```

    ```csharp
    Microsoft.Win32.RegistryKey key;
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");
    key.SetValue("MyComputer", "AuthenticodeRequired");
    key.SetValue("LocalIntranet", "AuthenticodeRequired");
    key.SetValue("Internet", "AuthenticodeRequired");
    key.SetValue("TrustedSites", "AuthenticodeRequired");
    key.SetValue("UntrustedSites", "Disabled");
    key.Close();
    ```

3.  애플리케이션을 빌드 및 실행합니다.

## <a name="disable-the-clickonce-trust-prompt"></a>ClickOnce 신뢰 프롬프트를 사용 하지 않도록 설정
 최종 사용자가 보안 정책에서 이미 신뢰 하지 않는 솔루션을 설치할 수 있는 옵션이 없습니다 있도록 신뢰 프롬프트를 비활성화할 수 있습니다.

#### <a name="to-disable-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>레지스트리 편집기를 사용 하 여 ClickOnce 신뢰 프롬프트를 사용 하지 않도록 설정

1.  레지스트리 편집기를 엽니다.

    1.  **시작**을 클릭한 다음, **실행**을 클릭합니다.

    2.  에 **열기** 상자에 입력 `regedit`를 클릭 하 고 **확인**합니다.

2.  다음 레지스트리 키를 찾습니다.

     **\HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\.NETFramework\Security\TrustManager\PromptingLevel**

     키가 없으면 만듭니다.

3.  다음 하위 키를 추가 **문자열 값**이미 없는, 연결 된 값이 다음 표에 표시 된 경우.

    |문자열 값의 하위 키|값|
    |-------------------------|-----------|
    |`UntrustedSites`|`Disabled`|
    |`Internet`|`Disabled`|
    |`MyComputer`|`Disabled`|
    |`LocalIntranet`|`Disabled`|
    |`TrustedSites`|`Disabled`|

#### <a name="to-disable-the-clickonce-trust-prompt-programmatically"></a>ClickOnce 신뢰 프롬프트를 프로그래밍 방식으로 사용 하지 않도록 설정

1.  Visual Basic 또는 시각적 개체 만들기 C# Visual Studio에서 응용 프로그램 콘솔.

2.  엽니다는 *Program.vb* 또는 *Program.cs* 편집에 대 한 파일을 다음 코드를 추가 합니다.

    ```vb
    Dim key As Microsoft.Win32.RegistryKey
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")
    key.SetValue("MyComputer", "Disabled")
    key.SetValue("LocalIntranet", "Disabled")
    key.SetValue("Internet", "Disabled")
    key.SetValue("TrustedSites", "Disabled")
    key.SetValue("UntrustedSites", "Disabled")
    key.Close()
    ```

    ```csharp
    Microsoft.Win32.RegistryKey key;
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");
    key.SetValue("MyComputer", "Disabled");
    key.SetValue("LocalIntranet", "Disabled");
    key.SetValue("Internet", "Disabled");
    key.SetValue("TrustedSites", "Disabled");
    key.SetValue("UntrustedSites", "Disabled");
    key.Close();

    ```

3.  애플리케이션을 빌드 및 실행합니다.

## <a name="see-also"></a>참고 항목
- [ClickOnce 애플리케이션 보안](../deployment/securing-clickonce-applications.md)
- [ClickOnce 애플리케이션의 코드 액세스 보안](../deployment/code-access-security-for-clickonce-applications.md)
- [ClickOnce 및 Authenticode](../deployment/clickonce-and-authenticode.md)
- [신뢰할 수 있는 애플리케이션 배포 개요](../deployment/trusted-application-deployment-overview.md)
- [방법: ClickOnce 보안 설정 사용](../deployment/how-to-enable-clickonce-security-settings.md)
- [방법: ClickOnce 애플리케이션의 보안 영역 설정](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)
- [방법: ClickOnce 애플리케이션의 사용자 지정 권한 설정](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)
- [방법: 제한된 사용 권한으로 ClickOnce 애플리케이션 디버그](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)
- [방법: ClickOnce 애플리케이션의 클라이언트 컴퓨터에 신뢰할 수 있는 게시자 추가](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)
- [방법: 애플리케이션 및 배포 매니페스트에 다시 서명](../deployment/how-to-re-sign-application-and-deployment-manifests.md)
