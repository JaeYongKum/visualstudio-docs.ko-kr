---
title: "Visual Studio 템플릿 스키마 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".vstemplate 파일"
  - "Visual Studio 템플릿, 스키마"
  - "VSTEMPLATE 파일"
ms.assetid: 6f74a2d5-3811-43d6-8b10-eb5823ad8995
caps.latest.revision: 25
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 25
---
# Visual Studio 템플릿 스키마 참조
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 섹션에는 프로젝트 템플릿, 항목 템플릿 및 시작 키트에 대한 메타데이터를 저장하는 파일인 .vstemplate 파일의 XML 요소에 대한 정보가 포함되어 있습니다.  
  
 vstemplate.xsd를 사용하여 사용자 지정 .vstemplate 파일의 유효성을 검사할 수 있습니다.  이 파일은 ..\\*Visual Studio installation folder*\\Xml\\Schemas\\1033\\vstemplate.xsd 경로에 있습니다.  
  
|요소|자식 요소|특성|  
|--------|-----------|--------|  
|[AppliesTo](../extensibility/appliesto-element-visual-studio-templates.md)|없음|없음|  
|[Assembly\(템플릿\)](../extensibility/assembly-element-visual-studio-templates.md)|\-\-|\-\-|  
|[Assembly\(마법사 확장\)](../extensibility/assembly-element-visual-studio-template-wizard-extension.md)|\-\-|\-\-|  
|[BuildProjectOnload](../extensibility/buildprojectonload-element-visual-studio-templates.md)|\-\-|\-\-|  
|[CreateInPlace](../extensibility/createinplace-visual-studio-templates.md)|\-\-|\-\-|  
|[CreateNewFolder](../extensibility/createnewfolder-element-visual-studio-templates.md)|\-\-|\-\-|  
|[CustomDataSignature](../extensibility/customdatasignature-element-visual-studio-templates.md)|\-\-|\-\-|  
|[CustomParameter](../extensibility/customparameter-element-visual-studio-templates.md)|\-\-|Name<br /><br /> 값|  
|[CustomParameters](../extensibility/customparameters-element-visual-studio-templates.md)|CustomParameter|\-\-|  
|[DefaultName](../extensibility/defaultname-element-visual-studio-templates.md)|\-\-|\-\-|  
|[설명](../extensibility/description-element-visual-studio-templates.md)|\-\-|패키지<br /><br /> ID|  
|[EnableEditOfLocationField](../extensibility/enableeditoflocationfield-element-visual-studio-templates.md)|\-\-|\-\-|  
|[EnableLocationBrowseButton](../extensibility/enablelocationbrowsebutton-element-visual-studio-templates.md)|\-\-|\-\-|  
|[폴더](../extensibility/folder-element-visual-studio-project-templates.md)|ProjectItem<br /><br /> 폴더|Name|  
||\[사용되지 않음\]|\-\-|  
|[FullClassName](../extensibility/fullclassname-element-visual-studio-template-wizard-extension.md)|\-\-|\-\-|  
|[Hidden](../extensibility/hidden-element-visual-studio-templates.md)|\-\-|\-\-|  
|[아이콘](../extensibility/icon-element-visual-studio-templates.md)|\-\-|패키지<br /><br /> ID|  
|[LocationField](../extensibility/locationfield-element-visual-studio-project-templates.md)|\-\-|\-\-|  
|[LocationFieldMRUPrefix](../extensibility/locationfieldmruprefix-element-visual-studio-templates.md)|\-\-|\-\-|  
|[MaxFrameworkVersion](../extensibility/maxframeworkversion-element-visual-studio-templates.md)|\-\-|\-\-|  
|[Name](../extensibility/name-element-visual-studio-templates.md)|\-\-|패키지<br /><br /> ID|  
|[NumberOfParentCategoriesToRollUp](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)|\-\-|\-\-|  
|[PreviewImage](../extensibility/previewimage-element-visual-studio-templates.md)|\-\-|\-\-|  
|[프로젝트](../extensibility/project-element-visual-studio-templates.md)|폴더<br /><br /> ProjectItem|파일<br /><br /> TargetFileName<br /><br /> ReplaceParameters|  
|[ProjectCollection](../extensibility/projectcollection-element-visual-studio-templates.md)|ProjectTemplateLink<br /><br /> SolutionFolder|\-\-|  
|[ProjectItem\(항목 템플릿\)](../extensibility/projectitem-element-visual-studio-item-templates.md)|\-\-|하위 형식<br /><br /> CustomTool<br /><br /> ItemType<br /><br /> ReplaceParameters<br /><br /> TargetFileName|  
|[ProjectItem\(프로젝트 템플릿\)](../extensibility/projectitem-element-visual-studio-project-templates.md)|\-\-|TargetFileName<br /><br /> ReplaceParameters<br /><br /> OpenInEditor<br /><br /> OpenOrder<br /><br /> OpenInWebBrowser<br /><br /> OpenInHelpBrowser|  
|[ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md)|\-\-|\-\-|  
|[ProjectTemplateLink](../extensibility/projecttemplatelink-element-visual-studio-templates.md)|\-\-|ProjectName|  
|[ProjectType](../extensibility/projecttype-element-visual-studio-templates.md)|\-\-|\-\-|  
|[PromptForSaveOnCreation](../extensibility/promptforsaveoncreation-element-visual-studio-templates.md)|\-\-|\-\-|  
|[ProvideDefaultName](../extensibility/providedefaultname-element-visual-studio-templates.md)|\-\-|\-\-|  
|[참고 항목](../extensibility/reference-element-visual-studio-templates.md)|어셈블리|\-\-|  
|[참조](../extensibility/references-element-visual-studio-templates.md)|참고 항목|\-\-|  
|[RequiredFrameworkVersion](../extensibility/requiredframeworkversion-element-visual-studio-templates.md)|\-\-|\-\-|  
|[RequiredPlatformVersion](../extensibility/requiredplatformversion-element-visual-studio-templates.md)|\-\-|버전|  
|[SDKReference](72c8b352-0b7a-42b3-ba5d-2a2d1e90c3)|\-\-|패키지|  
|[ShowByDefault](../extensibility/showbydefault-visual-studio-templates.md)|\-\-|\-\-|  
|[SolutionFolder](../extensibility/solutionfolder-element-visual-studio-templates.md)|ProjectTemplateLink<br /><br /> SolutionFolder|Name|  
|[SortOrder](../extensibility/sortorder-element-visual-studio-templates.md)|\-\-|\-\-|  
|[SupportsCodeSeparation](../extensibility/supportscodeseparation-element-visual-studio-templates.md)|\-\-|\-\-|  
|[SupportsLanguageDropDown](../extensibility/supportslanguagedropdown-element-visual-studio-templates.md)|\-\-|\-\-|  
|[SupportsMasterPage](../extensibility/supportsmasterpage-element-visual-studio-templates.md)|\-\-|\-\-|  
|[TargetPlatformName](../extensibility/targetplatformname-element-visual-studio-templates.md)|RequiredPlatformVersion|\-\-|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|ProjectCollection<br /><br /> 프로젝트<br /><br /> 참조<br /><br /> ProjectItem<br /><br /> CustomParameters|[BuildOnLoad](../extensibility/buildprojectonload-visual-studio-templates.md)|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Name<br /><br /> 설명<br /><br /> 아이콘<br /><br /> PreviewImage<br /><br /> ProjectType<br /><br /> ProjectSubType<br /><br /> TemplateID<br /><br /> TemplateGroupID<br /><br /> SortOrder<br /><br /> CreateNewFolder<br /><br /> DefaultName<br /><br /> ProvideDefaultName<br /><br /> PromptForSaveOnCreation<br /><br /> EnableLocationBrowseButton<br /><br /> EnableEditOfLocationField<br /><br /> Hidden<br /><br /> DisplayInParentCategories<br /><br /> LocationFieldMRUPrefix<br /><br /> NumberOfParentCategoriesToRollUp<br /><br /> CreateInPlace<br /><br /> BuildOnLoad<br /><br /> BuildProjectOnload<br /><br /> ShowByDefault<br /><br /> LocationField<br /><br /> SupportsMasterPage<br /><br /> SupportsCodeSeparation<br /><br /> SupportsLanguageDropDown<br /><br /> RequiredFrameworkVersion<br /><br /> FrameworkVersion<br /><br /> MaxFrameworkVersion<br /><br /> CustomDataSignature<br /><br /> TargetPlatformName|\-\-|  
|[TemplateGroupID](../extensibility/templategroupid-element-visual-studio-templates.md)|\-\-|\-\-|  
|[TemplateID](../extensibility/templateid-element-visual-studio-templates.md)|\-\-|\-\-|  
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|TemplateData<br /><br /> TemplateContent<br /><br /> WizardExtension<br /><br /> WizardData|형식<br /><br /> 버전|  
|[WizardData](../extensibility/wizarddata-element-visual-studio-templates.md)|\-\-|Name|  
|[WizardExtension](../extensibility/wizardextension-element-visual-studio-templates.md)|어셈블리<br /><br /> FullClassName|\-\-|  
  
## 참고 항목  
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)   
 [방법: 시작 키트 만들기](../ide/how-to-create-starter-kits.md)