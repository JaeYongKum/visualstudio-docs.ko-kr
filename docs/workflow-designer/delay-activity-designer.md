---
title: 워크플로 디자이너-Delay 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Delay.UI
ms.assetid: f51742a8-2c9a-47d1-8a23-18459d03ae19
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e22c80712bcb0c792fb929ae85b84912122a0bc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31971656"
---
# <a name="delay-activity-designer"></a>Delay 활동 디자이너

**지연** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.Delay> 활동입니다.

## <a name="the-delay-activity"></a>Delay 활동

<xref:System.Activities.Statements.Delay> 활동은 지정된 시간 동안 워크플로 실행을 지연시킵니다.

### <a name="using-the-delay-activity-designer"></a>Delay 활동 디자이너 사용

**지연** 활동 디자이너에서 확인할 수 있습니다는 **기본 형식** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**워크플로 디자이너의 탭 (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)

**지연** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 활동은 일반적으로, 등 배치 때마다 워크플로 디자이너 화면에 끌어 놓 및는 <xref:System.Activities.Statements.Sequence>합니다. 그러면 기본 <xref:System.Activities.Statements.Delay>인 Delay라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수는 **지연** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.

### <a name="the-delay-properties"></a>Delay 속성

다음 표에서는 <xref:System.Activities.Statements.Delay> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표에서 편집할 수 있습니다 및 워크플로 Designerdesigner 화면에서 편집할 수 일부 그 중입니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Delay> 활동의 이름입니다. 기본값은 Delay입니다. <xref:System.Activities.Activity.DisplayName%2A> 값은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.Delay.Duration%2A>|True|워크플로를 지연할 시간입니다. 이 속성은 속성 표에서 설정합니다. 리터럴 <xref:System.TimeSpan>을 00:00:00 형식으로 입력하거나 Visual Basic 식을 입력하여 시간을 지정합니다.|

## <a name="see-also"></a>참고자료

- [Primitives](../workflow-designer/primitives-activity-designers.md)
- [할당](../workflow-designer/assign-activity-designer.md)
- [Delay 활동 디자이너](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)