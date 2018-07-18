---
title: 워크플로 디자이너-CompensableActivity 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.CompensableActivity.UI
ms.assetid: e0340d89-d39e-4a52-8557-13e27040d7b5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d723b50fe0267939119239861c5ae951e01cd445
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758295"
---
# <a name="compensableactivity-activity-designer"></a>CompensableActivity 활동 디자이너

합니다 **CompensableActivity** 활동 디자이너는 만들기 및 구성 하는 데 사용 되는 <xref:System.Activities.Statements.CompensableActivity> 활동입니다.

## <a name="the-compensableactivity-activity"></a>CompensableActivity 활동
 <xref:System.Activities.Statements.CompensableActivity>는 성공적으로 완료한 후 확인 또는 보정할 수 있는 작업 단위를 정의합니다.

### <a name="using-the-compensableactivity-activity-designer"></a>CompensableActivity 활동 디자이너 사용
 합니다 **CompensableActivity** 활동 디자이너에서 찾을 수 있습니다 합니다 **트랜잭션** 범주의 **도구 상자**합니다. 열려는 **도구 상자**를 선택 합니다 **도구 상자** 워크플로 디자이너의 왼쪽에 탭 합니다. 또는 선택할 **도구 상자** 에서 합니다 **뷰** 메뉴 또는 키를 눌러 **Ctrl**+**Alt** + **X**합니다.

 합니다 **CompensableActivity** 활동 디자이너에서 끌 수 있습니다 **도구 상자** 워크플로 디자이너 화면에 끌어 놓 및 합니다. 활동 디자이너 내부를 삭제할 수는 <xref:System.Activities.Statements.Sequence>합니다. Activity designer 만들어집니다를 <xref:System.Activities.Statements.CompensableActivity> 기본값을 사용 하 여 작업 <xref:System.Activities.Activity.DisplayName%2A> CompensableActivity입니다. 편집 합니다 <xref:System.Activities.Activity.DisplayName%2A> 헤더의 값을 **CompensableActivity** 활동 디자이너입니다. 편집할 수도 있습니다는 **DisplayName** 속성 그리드의 상자입니다.

### <a name="the-compensableactivity-properties"></a>CompensableActivity 속성
 다음 표에서는 <xref:System.Activities.Statements.CompensableActivity> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 합니다 <xref:System.Activities.Activity.DisplayName%2A> 고 <xref:System.Activities.Activity%601.Result%2A> 속성 속성 표에서 편집할 수 있지만 다른 속성을 워크플로 디자이너 화면에서 편집 해야 합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.CompensableActivity> 활동의 선택적 이름입니다. 기본값은 CompensableActivity입니다.|
|<xref:System.Activities.Activity%601.Result%2A>|False|<xref:System.Activities.Statements.CompensableActivity>의 반환 값을 지정합니다. 이 속성은 속성 표에서 편집해야 합니다.|
|<xref:System.Activities.Statements.CompensableActivity.Body%2A>|True|보정, 취소 및 확인 논리를 제공할 활동을 지정합니다. 추가할 합니다 <xref:System.Activities.Statements.CompensableActivity.Body%2A> 활동에서 활동 **도구 상자** 에 **본문** 상자에 **CompensableActivity** 활동 디자이너입니다. 여기에 작업 놓기"힌트 텍스트를 추가 합니다.|
|<xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>|False|취소가 없을 때 실행 되는 작업을 지정 합니다. 활동을 추가 하려면 해당 디자이너에서 삭제할 **도구 상자** 에 **CancellationHandler** 상자에 **CompensableActivity** 활동 디자이너입니다. 여기에 작업 놓기 "힌트 텍스트를 추가 합니다.|
|<xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>|False|<xref:System.Activities.Statements.CompensableActivity.Body%2A> 활동을 보정할 때 실행할 활동을 지정합니다. <xref:System.Activities.Statements.Compensate> 활동을 사용하여 이 처리기를 명시적으로 호출할 수 있습니다.<br /><br /> 활동을 추가 하려면 해당 활동 디자이너에서 삭제할 **도구 상자** 에 **CompensationHandler** 상자에 **CompensableActivity** 활동 디자이너. 여기에 작업 놓기 "힌트 텍스트를 추가 합니다.|
|<xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>|False|<xref:System.Activities.Statements.CompensableActivity.Body%2A> 활동을 확인할 때 실행할 활동을 지정합니다. <xref:System.Activities.Statements.Confirm> 활동을 사용하여 이 처리기를 명시적으로 호출할 수 있습니다.<br /><br /> 활동을 추가 하려면 해당 활동 디자이너에서 삭제할 **도구 상자** 에 **ConfirmationHandler** 상자에 **CompensableActivity** 활동 디자이너. 여기에 작업 놓기 "힌트 텍스트를 추가 합니다.|

## <a name="see-also"></a>참고자료

- [트랜잭션](../workflow-designer/transaction-activity-designers.md)
- [CancellationScope](../workflow-designer/cancellationscope-activity-designer.md)
- [보정](../workflow-designer/compensate-activity-designer.md)
- [확인](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)