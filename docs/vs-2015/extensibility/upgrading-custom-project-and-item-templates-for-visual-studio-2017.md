---
title: Visual Studio "15"에 대 한 사용자 지정 프로젝트 및 항목 템플릿 업그레이드 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad02477b-e101-4f32-aeb7-292bf95d5c2f
caps.latest.revision: 4
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7e44ea1c267d9fe57c3f32ddad876b412f69ea24
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49221158"
---
# <a name="upgrading-custom-project-and-item-templates-for-visual-studio-15"></a>Visual Studio "15"에 대 한 사용자 지정 프로젝트 및 항목 템플릿 업그레이드
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio "15"에서 시작 하 여 Visual Studio Preview 4,.vsix 또는.msi 설치 된 프로젝트 및 항목 템플릿을 검색 하는 방법은 변경 됩니다. 사용자 지정 프로젝트 또는 항목 템플릿을 사용 하는 확장을 소유 하는 경우 확장을 업데이트 해야 합니다. 이 항목에서는 해야 할 사항을 설명 합니다.  
  
 이 변경은 Visual Studio "15"는 영향을 줍니다. 이전 버전의 Visual Studio에는 영향을 주지 않습니다.  
  
 VSIX 확장의 일부로 프로젝트 또는 항목 템플릿을 만들려는 경우 참조 [사용자 지정 프로젝트 및 항목 템플릿 만들기](../extensibility/creating-custom-project-and-item-templates.md)합니다.  
  
## <a name="template-scanning"></a>템플릿 검색  
 이전에 **devenv /setup** 하거나 **devenv /installvstemplates** 프로젝트 및 항목 템플릿을 찾으려면 로컬 디스크를 검색 합니다. Preview 4부터 검색 수행할 사용자 수준 위치에 대해서만 (**%USERPROFILE%\Documents\\< Visual Studio 버전\>\My Exported Templates\\**)에 사용 되는 생성 된 템플릿 합니다 **파일 / 내보내기 템플릿** 명령입니다.  
  
 기타 (비 사용자) 위치에 대 한 서식 파일의 다른 특성과 위치를 지정 하는 manifest(.vstman) 파일을 포함 해야 합니다. .Vstman 파일은 템플릿에 사용.vstemplate 파일과 함께 생성 됩니다. .Vsix를 사용 하 여 확장을 설치 하면 Visual Studio "15" Preview 2에서에서 확장을 다시 컴파일하여이 수행할 수 있습니다. 하지만.msi를 사용 하는 경우 수동으로 변경 해야 합니다. 이러한 변경을 수행 하기 위해 필요한 목록은 참조 하세요. **와 함께 설치 된 확장에 대 한 업그레이드를 합니다. MSI** 이 항목의에서 뒷부분에 있습니다.  
  
## <a name="how-to-update-a-vsix-extension-with-project-or-item-templates"></a>프로젝트 또는 항목 템플릿을 VSIX 확장을 업데이트 하는 방법  
 이 절차는 Visual Studio "15" Preview 2 업데이트를 기존 VSIX 확장을 설명 합니다.  
  
1.  Visual Studio "15" Preview 2에서에서 솔루션을 엽니다. 코드를 업그레이드 하 라는 메시지가 표시 됩니다. **확인**을 클릭합니다.  
  
2.  업그레이드를 완료 한 후에 설치 대상 버전을 변경 하는 것이 해야 합니다. VSIX 프로젝트에서 source.extension.vsixmanifest 파일을 열고 선택 합니다 **설치 대상** 탭 합니다. 경우는 **버전 범위** 필드가 **[14.0]**, 클릭 **편집** Visual Studio "15"를 포함 하도록 변경 합니다. 로를 설정 하는 예를 들어 **[14.0,15.0]** 또는 Visual Studio 2015 또는 Visual Studio "15" 확장을 설치 하려면 **[15.0]** 방금 Visual Studio "15"를 설치 합니다.  
  
3.  코드를 다시 컴파일해야 합니다.  
  
4.  Visual Studio를 닫습니다.  
  
5.  VSIX를 설치 합니다.  
  
6.  다음을 수행 하 여 업데이트를 테스트할 수 있습니다.  
  
    1.  파일 변경 검색 다음 레지스트리 키에 의해 활성화 됩니다.  
  
         **reg은 hklm\software\microsoft\visualstudio\15.0\VSTemplate /v DisableTemplateScanning /t REG_DWORD /d 1 /reg:32 추가**  
  
    2.  키를 추가한 후 실행할 **devenv /installvstemplates**합니다.  
  
    3.  Visual Studio를 다시 엽니다. 필요한 위치에 템플릿을 찾아야 합니다.  
  
    > [!NOTE]
    >  Visual Studio 확장성 프로젝트 템플릿 레지스트리 키가 존재 하는 경우 사용할 수 없는 경우 레지스트리 키를 삭제 해야 합니다 (다시 실행 하십시오 **devenv /installvstemplates**) 사용 합니다.  
  
## <a name="other-recommendations-for-deploying-project-and-item-templates"></a>프로젝트 및 항목 템플릿을 배포 하기 위한 기타 권장 사항  
  
-   압축 된 템플릿 파일을 사용 하지 마십시오. 템플릿 파일에 리소스와 콘텐츠를 검색 하기 위해 압축 된 필요한 압축 되므로 될 데 비용이 많이 들기 합니다. 대신 자신의 디렉터리 템플릿 초기화 속도를 개별 파일로 프로젝트 및 항목 템플릿을 배포 해야 합니다. VSIX 확장에 대 한 SDK 빌드 작업은 자동으로 압축을 풉니다 압축된 템플릿을 VSIX 파일을 만드는 동안.  
  
-   템플릿 검색 하는 동안 불필요 한 리소스 어셈블리 로드를 방지 하기 위해 템플릿 이름, 설명, 아이콘 또는 미리 보기에 대 한 패키지/리소스 ID 항목을 사용 하지 마십시오. 대신, 속성 또는 지역화 된 이름을 사용 하는 각 로캘에 대해 템플릿 항목을 만드는 지역화 된 매니페스트를 사용할 수 있습니다.  
  
-   템플릿을 있는 그대로 파일 항목을 포함 하는 경우 매니페스트 생성 얻지 못할 수도 있습니다 하면 예상된 된 결과가 있습니다. 이 경우 VSIX 프로젝트를 수동으로 생성 된 매니페스트를 추가 해야 합니다.  
  
## <a name="file-changes-in-project-and-item-templates"></a>프로젝트 및 항목 템플릿 파일 변경 내용  
 새 파일을 올바르게 작성할 수 있도록 템플릿 파일의 Visual Studio "15" 버전과 Visual Studio 2015 버전 간의 차이의 점을 보여줍니다.  
  
 Visual Studio 2015에서 만든 기본 프로젝트.vstemplate 파일은 다음과 같습니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Project" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:sdk="http://schemas.microsoft.com/developer/vstemplate-sdkextension/2010">  
  <TemplateData>  
    <Name>ProjectTemplate1</Name>  
    <Description>ProjectTemplate1</Description>  
    <Icon>ProjectTemplate1.ico</Icon>  
    <ProjectType>CSharp</ProjectType>  
    <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
    <SortOrder>1000</SortOrder>  
    <TemplateID>05b79cc9-2146-4716-a8e5-7e085cdd2221</TemplateID>  
    <CreateNewFolder>true</CreateNewFolder>  
    <DefaultName>ProjectTemplate1</DefaultName>  
    <ProvideDefaultName>true</ProvideDefaultName>  
  </TemplateData>  
  <TemplateContent>  
    <Project File="ProjectTemplate.csproj" ReplaceParameters="true">  
      <ProjectItem ReplaceParameters="true" TargetFileName="Properties\AssemblyInfo.cs">AssemblyInfo.cs</ProjectItem>  
      <ProjectItem ReplaceParameters="true" OpenInEditor="true">Class1.cs</ProjectItem>  
    </Project>  
  </TemplateContent>  
</VSTemplate>  
  
```  
  
 VSIX 프로젝트를 다시 작성에서 발생 시킨.vstman 파일 (찾을 수 있습니다 VSIX 프로젝트의 매니페스트 디렉터리)는 다음과 같습니다.  
  
```  
VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Project">  
    <RelativePathOnDisk>CSharp\1033\ProjectTemplate1</RelativePathOnDisk>  
    <TemplateFileName>ProjectTemplate1.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>ProjectTemplate1</Name>  
        <Description>ProjectTemplate1</Description>  
        <Icon>ProjectTemplate1.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <SortOrder>1000</SortOrder>  
        <TemplateID>05b79cc9-2146-4716-a8e5-7e085cdd2221</TemplateID>  
        <CreateNewFolder>true</CreateNewFolder>  
        <DefaultName>ProjectTemplate1</DefaultName>  
        <ProvideDefaultName>true</ProvideDefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```  
  
 제공한 정보는 [TemplateData](../extensibility/templatedata-element-visual-studio-templates.md) 요소 동일 하 게 유지 합니다. 합니다  **\<VSTemplateContainer >** 요소 관련 템플릿의.vstemplate 파일을 가리킵니다.  
  
 Visual Studio 2015에서 만든 기본 항목.vstemplate 파일은 다음과 같습니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:sdk="http://schemas.microsoft.com/developer/vstemplate-sdkextension/2010">  
  <TemplateData>  
    <Name>ItemTemplate1</Name>  
    <Description>ItemTemplate1</Description>  
    <Icon>ItemTemplate1.ico</Icon>  
    <TemplateID>bfeadf8e-a251-4109-b605-516b88e38c8d</TemplateID>  
    <ProjectType>CSharp</ProjectType>  
    <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
    <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
    <DefaultName>Class.cs</DefaultName>  
  </TemplateData>  
  <TemplateContent>  
    <References>  
      <Reference>  
        <Assembly>System</Assembly>  
      </Reference>  
    </References>  
    <ProjectItem ReplaceParameters="true">Class.cs</ProjectItem>  
  </TemplateContent>  
</VSTemplate>  
  
```  
  
 VSIX 프로젝트를 다시 작성에서 발생 시킨.vstman 파일 (찾을 수 있습니다 VSIX 프로젝트의 매니페스트 디렉터리)는 다음과 같습니다.  
  
```  
VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Item">  
    <RelativePathOnDisk>CSharp\1033\ItemTemplate1</RelativePathOnDisk>  
    <TemplateFileName>ItemTemplate1.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>ItemTemplate1</Name>  
        <Description>ItemTemplate1</Description>  
        <Icon>ItemTemplate1.ico</Icon>  
        <TemplateID>bfeadf8e-a251-4109-b605-516b88e38c8d</TemplateID>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <DefaultName>Class.cs</DefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```  
  
 제공한 정보는  **\<TemplateData >** 요소 동일 하 게 유지 합니다. 합니다  **\<VSTemplateContainer >** 요소 관련 템플릿의.vstemplate 파일을 가리킵니다.  
  
 .Vstman 파일의 다양 한 요소에 대 한 자세한 내용은 참조 하세요. [Visual Studio 템플릿 매니페스트 스키마 참조](../extensibility/visual-studio-template-manifest-schema-reference.md)합니다.  
  
## <a name="upgrades-for-extensions-installed-with-an-msi"></a>와 함께 설치 된 확장에 대 한 업그레이드를 합니다. MSI  
 다음과 같은 일반적인 템플릿 위치에 템플릿을 배포 하는 일부 MSI 기반 확장 합니다.  
  
-   **\<Visual Studio 설치 디렉터리 > \Common7\IDE\\< ProjectTemplates/Itemtemplate >**  
  
-   **\<Visual Studio 설치 디렉터리 > \Common7\IDE\Extensions\\< ExtensionName\>\\< 프로젝트/Itemtemplate >**  
  
 MSI 기반 배포를 수행 하는 확장 프로그램을 하는 경우 템플릿 매니페스트를 수동으로 생성 및 확장 설치에 포함 되어 있는지 확인 해야 합니다. 위에 나열 된.vstman 예제 비교 해야 하며 [Visual Studio 템플릿 매니페스트 스키마 참조](../extensibility/visual-studio-template-manifest-schema-reference.md)합니다. 포함 해야 하는 항목을 보려면  
  
 프로젝트 및 항목 템플릿에 대 한 별도 매니페스트를 만들어야 하 고 루트 템플릿 지정 된 대로 위의 디렉터리를 가리키도록 해야 합니다. 확장 및 로캘 당 하나의 매니페스트를 만들어야 합니다.  
  
## <a name="troubleshooting-template-installation"></a>문제 해결 템플릿 설치  
 프로젝트 또는 항목 템플릿을 배포 하는 문제에 봉착 한 경우에 진단 로깅을 활성화할 수 있습니다.  
  
1.  로깅을 사용 하도록 설정 하는 레지스트리 키를 설정 하려면 다음 명령을 실행 합니다.  
  
     **reg은 HKCU\software\microsoft\visualstudio\15.0_Config\VSTemplate /v EnableTemplateDiscoveryLog /t REG_DWORD /d 1 추가**  
  
2.  Visual Studio를 시작 하 고 새 프로젝트를 새 항목 대화 상자 템플릿 양쪽 트리에 모두 초기화를 시작 합니다. 서식 파일 로그에 나타납니다 **%LOCALAPPDATA%\Microsoft\VisualStudio\15.0\VsTemplateDiagnosticsList.csv**합니다. 이 로그에 항목을 추가 하는 각 템플릿 트리 초기화 합니다.  
  
 로그 파일에는 다음 열을 포함 합니다.  
  
-   **FullPathToTemplate**에 다음 값입니다.  
  
    -   매니페스트 기반 배포에 대 한 1  
  
    -   디스크 기반 배포에 대 한 0  
  
-   **TemplateFileName**  
  
-   다른 템플릿 속성

