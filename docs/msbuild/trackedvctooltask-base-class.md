---
title: TrackedVCToolTask 클래스 | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 92d12e08f374efd306589d9d50f840a8d36f5b5a
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070515"
---
# <a name="trackedvctooltask-base-class"></a>TrackedVCToolTask 기본 클래스

다양한 작업은 궁극적으로 <xref:Microsoft.Build.Utilities.Task> 클래스 및 [ToolTask](/dotnet/api/microsoft.build.utilities.tooltask) 클래스에서 상속됩니다. 이 클래스는 [VCToolTask](../msbuild/vctooltask-base-class.md)에서 파생되는 작업에 여러 매개 변수를 추가합니다. 이러한 매개 변수가 이 문서에 나열되어 있습니다.

## <a name="parameters"></a>매개 변수

다음 표에서는 **TrackedVCToolTask** 기본 클래스의 매개 변수에 대해 설명합니다.

|매개 변수|설명|
|---------------|-----------------|
|**DeleteOutputOnExecute**|선택적 **bool** 매개 변수입니다.|
|**EnableExecuteTool**|선택적 **bool** 매개 변수입니다.|
|**ExcludedInputPaths**|선택적 **ITaskItem[]** 매개 변수입니다.|
|**MinimalRebuildFromTracking**|선택적 **bool** 매개 변수입니다.|
|**PathOverride**|선택적 **string** 매개 변수입니다.|
|**PostBuildTrackingCleanup**|선택적 **bool** 매개 변수입니다.|
|**RootSource**|선택적 **string** 매개 변수입니다.|
|**SkippedExecution**|선택적 **bool** 출력 매개 변수입니다.|
|**SourcesCompiled**|선택적 **ITaskItem** 출력 매개 변수입니다.|
|**TLogCommandFile**|선택적 **ITaskItem** 매개 변수입니다.|
|**TLogReadFiles**|선택적 **ITaskItem[]** 매개 변수입니다.|
|**TLogWriteFiles**|선택적 **ITaskItem[]** 매개 변수입니다.|
|**ToolArchitecture**|선택적 **string** 매개 변수입니다.|
|**TrackCommandLines**|선택적 **bool** 매개 변수입니다.|
|**TrackFileAccess**|선택적 **bool** 매개 변수입니다.|
|**TrackedInputFilesToIgnore**|선택적 **ITaskItem[]** 매개 변수입니다.|
|**TrackedOutputFilesToIgnore**|선택적 **ITaskItem[]** 매개 변수입니다.|
|**TrackerFrameworkPath**|선택적 **string** 매개 변수입니다.|
|**TrackerSdkPath**|선택적 **string** 매개 변수입니다.|

## <a name="see-also"></a>참고 항목

[작업 참조](../msbuild/msbuild-task-reference.md)<br/>
[작업](../msbuild/msbuild-tasks.md)