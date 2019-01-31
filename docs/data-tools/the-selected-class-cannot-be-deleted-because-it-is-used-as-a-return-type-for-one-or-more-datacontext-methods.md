---
title: 선택한 클래스가 하나 이상의 DataContext 메서드의 반환 형식으로 사용되므로 해당 클래스를 삭제할 수 없습니다.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 00fc4ee0be84cc4937fddc083633324cc8ab41d3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55070866"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>선택한 클래스가 하나 이상의 DataContext 메서드의 반환 형식으로 사용되므로 해당 클래스를 삭제할 수 없습니다.

하나 이상의 <xref:System.Data.Linq.DataContext> 메서드 반환 형식은 선택한 엔터티 클래스입니다. 에 대 한 반환 형식으로 사용 되는 엔터티 클래스를 삭제 한 <xref:System.Data.Linq.DataContext> 메서드를 사용 하면 프로젝트를 컴파일하는 합니다. 선택한 엔터티 클래스를 삭제하려면 해당 엔터티 클래스를 사용하는 <xref:System.Data.Linq.DataContext> 메서드를 식별하고 해당 메서드의 반환 형식을 서로 다른 엔터티 클래스로 설정합니다.

<xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 원래 자동으로 생성된 형식으로 되돌리려면 우선 **메서드** 창에서 <xref:System.Data.Linq.DataContext> 메서드를 삭제한 다음, 개체를 **서버 탐색기**/**데이터베이스 탐색기**에서 **O/R 디자이너**로 다시 끌어 옵니다.

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. **메서드** 창에서 <xref:System.Data.Linq.DataContext> 메서드를 선택하고 **속성** 창에서 **반환 형식** 속성을 검사하여 엔터티 클래스를 반환 형식으로 사용하는 <xref:System.Data.Linq.DataContext> 메서드를 식별합니다.

2. **반환 형식**을 서로 다른 엔터티 클래스로 설정하거나 메서드 창에서 <xref:System.Data.Linq.DataContext> 메서드를 삭제합니다.

## <a name="see-also"></a>참고 항목

- [O/R 디자이너 메시지](../data-tools/o-r-designer-messages.md)
- [Visual Studio의 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)