---
title: 매개 변수 요소 | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
- xml
helpviewer_keywords:
- Parameter element [MSBuild]
- <Parameter> element [MSBuild]
ms.assetid: b273afff-b500-4e97-8cfd-31f39fa64a51
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d4778923bf6c9e521a7ee26546510466fcfefc83
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49894263"
---
# <a name="parameter-element"></a>매개 변수 요소
`UsingTask` `TaskFactory`에 의해 생성되는 작업에 대한 특정 매개 변수 정보를 포함합니다.  요소의 이름은 매개 변수의 이름입니다.  자세한 내용은 [UsingTask 요소(MSBuild)](../msbuild/usingtask-element-msbuild.md)를 참조하세요.  

 \<Project>  
 \<UsingTask>  
 \<ParameterGroup>  
 \<Parameter>  

## <a name="syntax"></a>구문  

```xml  
<ParameterGroup ParameterType="SystemType"  
    Output="true/false"  
    Required="true/false" />  
```  

## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  

### <a name="attributes"></a>특성  

|특성|설명|  
|---------------|-----------------|  
|`ParameterType`|선택적 특성입니다.<br /><br /> 매개 변수의 .NET 형식(예: `System.String`)입니다.|  
|`Output`|선택적 부울 특성입니다.<br /><br /> `true`인 경우 매개 변수는 태스크의 출력 매개 변수입니다. 기본적으로 이 값은 `false`입니다.|  
|`Required`|선택적 부울 특성입니다.<br /><br /> `true`인 경우 이 매개 변수는 작업의 필수 매개 변수입니다. 기본적으로 이 값은 `false`입니다.|  

### <a name="child-elements"></a>자식 요소  
 없음  

### <a name="parent-elements"></a>부모 요소  

|요소|설명|  
|-------------|-----------------|  
|[ParameterGroup](../msbuild/parametergroup-element.md)|`UsingTask` `TaskFactory`에 의해 생성된 작업에 존재할 매개 변수의 선택적 목록을 포함합니다.|  

## <a name="example"></a>예  
 다음 예제에서는 `Parameter` 요소를 사용하는 방법을 보여 줍니다.  

```xml  
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">  
       <ParameterGroup>  
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>  
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>  
             ...  
</ParameterGroup>  
       <TaskBody Evaluate="true">  
      ... Task factory-specific data ...  
       </TaskBody>  
</UsingTask>  
```  

## <a name="see-also"></a>참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)   
 [프로젝트 파일 스키마 참조](../msbuild/msbuild-project-file-schema-reference.md)
