---
title: '방법: LINQ to SQL 클래스 (O-r 디자이너) 사이 연결 (관계) 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56133e65-81f3-44c3-bc28-ffdd0671a0d2
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5c739fcf11cec7eb841b99e58b01ada32cfdfd49
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49209367"
---
# <a name="how-to-create-an-association-relationship-between-linq-to-sql-classes-or-designer"></a>방법: LINQ to SQL 클래스 (O/R 디자이너) 사이 연결 (관계) 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
[!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)]에서 엔터티 클래스 간의 연결은 데이터베이스 테이블 간의 관계와 비슷합니다. 사용 하 여 엔터티 클래스 간의 연결을 만들 수 있습니다 합니다 **연결 편집기** 대화 상자.  
  
 사용 하는 경우 부모 클래스와 자식 클래스를 선택 해야 합니다 **연결 편집기** 연결을 만들려면 대화 상자. 부모 클래스는 기본 키가 있는 엔터티 클래스이고, 자식 클래스는 외래 키가 있는 엔터티 클래스입니다. 예를 들어 Northwind Customers 및 Orders 테이블에 매핑되는 엔터티 클래스를 만들면 Customer 클래스는 부모 클래스가 되고 Order 클래스는 자식 클래스가 됩니다.  
  
> [!NOTE]
>  테이블을 끌어 오면 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)] ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]), 연결은 기존에 따라 자동으로 만들어집니다 데이터베이스의 외래 키 관계입니다.  
  
 O/R 디자이너에서 연결을 선택 하면 연결을 만든 후 몇 가지 구성 가능한 속성이에 **속성** 창입니다. 연결은 관련 클래스 간의 선입니다. 다음 표에서는 연결 속성을 설명합니다.  
  
|속성|설명|  
|--------------|-----------------|  
|**카디널리티**|연결이 일대다 연결인지 또는 일대일 연결인지를 제어합니다.|  
|**자식 속성**|연결의 외래 키 쪽에서 자식 레코드의 컬렉션이거나 자식 레코드에 대한 참조인 부모 속성을 만들지 여부를 지정합니다. Customer와 Order 간의 연결에서 예를 들어 경우는 **자식 속성** 로 설정 된 **True**, Orders 라는 속성이 부모 클래스에 만들어집니다.|  
|**부모 속성**|연결된 부모 클래스를 참조하는 자식 클래스의 속성입니다. 예를 들어 Customer와 Order 간의 연결에서 연결된 주문 고객을 참조하는 Customer라는 속성이 Order 클래스에 만들어집니다.|  
|**참여 속성**|연결 속성을 표시 하 고 제공을 **줄임표** 다시 열리는 (...) 단추를 **연결 편집기** 대화 상자.|  
|**고유**|외래 대상 열에 고유성 제약 조건이 있는지 여부를 지정합니다.|  
  
### <a name="to-create-an-association-between-entity-classes"></a>엔터티 클래스 간에 연결을 만들려면  
  
1.  연결에서 부모 클래스를 나타내는 엔터티 클래스를 마우스 오른쪽 **추가**를 클릭 하 고 **연결**합니다.  
  
2.  확인 하는 올바른 **부모 클래스** 가 선택 합니다 **연결 편집기** 대화 상자.  
  
3.  선택 된 **자식 클래스** 콤보 상자에서.  
  
4.  선택 된 **연결 속성** 클래스가 관련 된 합니다. 일반적으로 이는 데이터베이스에 정의된 외래 키 관계에 매핑됩니다. 예를 들어, Customers 및 Orders 연결에서에서의 **연결 속성** 각 클래스에 대 한 CustomerID 됩니다.  
  
5.  클릭 **확인** 연결을 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [연습: LINQ to SQL 클래스 (O-r 디자이너) 만들기](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)   
 [방법: 기본 키 표현](http://msdn.microsoft.com/library/63c65289-6539-42b2-8493-891c232018fa)

