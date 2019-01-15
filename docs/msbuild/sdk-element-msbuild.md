---
title: SDK 요소(MSBuild) | Microsoft Docs
ms.date: 01/25/2018
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Project
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Sdk element [MSBuild]
- <Sdk> element [MSBuild]
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6e42714a44ebaee4d7e72d3997537491195d504f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53938979"
---
# <a name="sdk-element-msbuild"></a>Sdk 요소(MSBuild)
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 SDK를 참조합니다.  

 \<Project>  
 \<Sdk>  


## <a name="syntax"></a>구문  

```xml  
<Sdk Name="My.Custom.Sdk"
     Version="1.0.0" />  
```  

## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  

### <a name="attributes"></a>특성  

|특성|설명|  
|---------------|-----------------|  
|`Name`|필수 특성입니다.<br /><br /> 프로젝트 SDK의 이름입니다.|  
|`Version`|선택적 특성입니다.<br /><br /> 프로젝트 SDK의 버전입니다.|  

### <a name="child-elements"></a>자식 요소  
 없음

### <a name="parent-elements"></a>부모 요소  

| 요소 | 설명 |
| - | - |
| [프로젝트](../msbuild/project-element-msbuild.md) | [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트 파일의 필수 루트 요소입니다. |

## <a name="see-also"></a>참고 항목  
 [방법: MSBuild 프로젝트 SDK 참조](../msbuild/how-to-use-project-sdk.md)   
 [프로젝트 파일 스키마 참조](../msbuild/msbuild-project-file-schema-reference.md)   
 [MSBuild](../msbuild/msbuild.md)
