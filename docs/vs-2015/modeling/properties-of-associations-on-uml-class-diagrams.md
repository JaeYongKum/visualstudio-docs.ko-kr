---
title: 클래스 다이어그램의 uml 연결 속성 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.teamarch.common.association.properties
helpviewer_keywords:
- UML, element properties
ms.assetid: f82bcd34-7903-4c00-8da1-613efa07d223
caps.latest.revision: 26
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: 96dc1d942a06e4030992889970fd3946d2e4d9d4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47541724"
---
# <a name="properties-of-associations-on-uml-class-diagrams"></a>UML 클래스 다이어그램 연결의 속성
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [UML 연결의 속성 클래스 다이어그램](https://docs.microsoft.com/visualstudio/modeling/properties-of-associations-on-uml-class-diagrams)합니다.  
  
UML 클래스 다이어그램에서 그릴 수 있습니다 *연결* 형식 쌍 사이입니다. 형식은 클래스, 인터페이스 또는 열거형입니다.  
  
 연결은 개발 중인 시스템이 연결된 형식의 인스턴스 간에 일종의 링크를 저장함을 나타냅니다. 일반적으로 링크 구현에 관한 어떤 것을 의미하지는 않습니다. 예를 들어 포인터, 테이블의 행, XML의 상호 참조된 이름 등이 될 수 있습니다.  
  
 연결은 특성 또는 특성 쌍을 다이어그램으로 표시하는 방법입니다. 예를 들어 메뉴 형식의 특성이 포함된 음식점 클래스를 정의한 경우 음식점과 메뉴 간에 연결을 그려서 같은 정의를 나타낼 수 있습니다.  
  
 연결을 그리려면, 클릭 **연결** 도구 상자에서 첫 번째 형식은 다음 두 번째를 클릭 합니다. 같은 형식을 두 번 클릭하여 인스턴스가 같은 형식의 다른 인스턴스와 연결될 수 있음을 표시할 수 있습니다.  
  
## <a name="properties"></a>속성  
 UML 클래스 다이어그램 연결의 속성입니다.  
  
 연결의 속성을 보려면 연결을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다. 속성은 속성 창에 나타납니다.  
  
 다음 그림과 같이 몇몇 속성은 다이어그램에도 표시됩니다.  
  
 ![연결의 속성](../modeling/media/uml-classprop.png "UML_ClassProp")  
  
|**Property**|설명|  
|------------------|-----------------|  
|**이름 (1)**|연결을 식별합니다. 다이어그램의 연결 중간점 근처에도 나타납니다.|  
|**정규화 된 이름**|연결을 고유하게 식별합니다. 연결의 첫 번째 역할이 포함된 패키지의 정규화된 이름이 접두사로 추가됩니다.|  
|**작업 항목**|이 연결에 연결된 작업 항목 수입니다. 작업 항목 링크를 참조 하세요 [모델 요소에 연결 하 고 작업 항목](../modeling/link-model-elements-and-work-items.md)합니다.|  
|**색**|연결선의 색입니다. 다른 속성과 달리 이 속성은 모델의 기본 관계에 대한 속성이 아니라 연결의 보기에 대한 속성입니다.|  
|**첫 번째 역할**<br /><br /> **두 번째 역할**|연결의 각 끝을 역할이라고 합니다. 각 역할은 연결의 반대쪽 끝에 있는 클래스의 해당 특성에 대한 속성을 설명합니다.<br /><br /> 예제 다이어그램에서 메뉴와 메뉴 항목 간 연결에는 메뉴 및 콘텐츠라는 역할이 포함됩니다.<br /><br /> 콘텐츠는 메뉴 클래스 특성의 이름입니다.|  
  
### <a name="properties-of-each-role"></a>각 역할의 속성  
 각 역할의 속성을 보려면 확장 합니다 **첫 번째 역할** 하거나 **두 번째 역할** 속성입니다.  
  
|**Property**|**기본**|설명|  
|------------------|-----------------|-----------------|  
|**역할 이름 (2)**|이 역할의 형식 이름|역할 이름입니다. 다이어그램에서 연결의 끝 근처에 나타납니다.|  
|**집계**|없음|**None** (4)-클래스의 인스턴스 간의 일반 관계를 나타냅니다.<br /><br /> **복합** (5)-이 역할에 있는 개체는 반대쪽 역할의 개체를 포함 합니다. 사용할 수는 **복합** 복합 집합체와의 연결을 만들려면 도구입니다.<br /><br /> **공유** (6)-이 역할에 다른 역할에 있는 개체에 대 한 참조가 포함 되어 있습니다. 사용할 수는 **집계** 공유 집합체와의 연결을 만들려면 도구입니다.<br /><br /> 로컬 규칙에 똑같은 해석이 적용될 수 있습니다.|  
|**파생 된**|False|True이면 이 링크 끝의 개체가 다른 특성 및 연결에서 계산됩니다. 예를 들어 MyWorkPlace는 MyEmployer.WorkPlace에서 계산됩니다. 설명 또는 연결된 주석에 세부 정보를 입력해야 합니다.|  
|**가 파생 Union**|False|True이면 역할은 파생된 형식 역할 집합의 합집합입니다.|  
|**탐색 가능**|True|연결을 이 방향으로 읽을 수 있습니다. 반대쪽 역할의 인스턴스가 제공되면 설명할 소프트웨어가 이 역할에서 연결된 인스턴스를 효율적으로 확인할 수 있습니다.<br /><br /> 한 역할이 탐색 가능하고 다른 역할이 그렇지 않으면 탐색 가능한 방향으로 연결에 화살표가 나타납니다(7).<br /><br /> 기본적으로 연결 도구는 한 방향으로 탐색 가능한 연결을 만듭니다. 양방향 연결으로 변환 하려면 연결을 선택, 클릭 하 고 표시 되는 작업 태그를 클릭 수 **양방향 만들기**합니다.|  
|**읽기 전용**|False|True이면 연결 인스턴스가 만들어진 후에는 연결 인스턴스를 변경할 수 없습니다. 링크는 항상 같은 개체에 연결됩니다.|  
|**복합성 (3)**|1|**1** -이 연결의 한이 end 항상 하나의 개체에 연결 합니다. 그림에서 모든 메뉴 항목에는 하나의 메뉴가 있습니다.<br /><br /> **0..1** -중 연결의이 끝이 한 개체에 연결 되거나 링크가 없습니다.<br /><br /> **\*** -연결의 반대쪽 끝에 있는 모든 개체가이 끝에 있는 개체의 컬렉션에 연결 되어 있고 컬렉션은 비어 있을 수 있습니다.<br /><br /> **1..\***  -연결의 반대쪽 끝에 있는 모든 개체가이 끝에 있는 하나 이상의 개체에 연결 됩니다. 그림에서 모든 메뉴에는 하나 이상의 메뉴 항목이 있습니다.<br /><br /> *n* **..** *m* -다른 끝에 있는 각 개체의 컬렉션을 포함 *n* 하 고 *m* 이 끝에 있는 개체에 대 한 링크입니다.|  
|**정렬**|False|True이면 반환된 컬렉션이 순차적 목록을 구성합니다. 복합성이 1보다 큰 경우입니다.|  
|**고유한**|False|True이면 반환된 컬렉션에 중복 값이 없습니다. 복합성이 1보다 큰 경우입니다.|  
|**표시 유형**|Public|Public - 전체적으로 표시됩니다.<br /><br /> Private - 소유하는 형식 외부에 표시되지 않습니다.<br /><br /> Protected - 소유자로부터 파생된 형식에 표시됩니다.<br /><br /> Package - 같은 패키지 내의 다른 형식에 표시됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [UML 클래스 다이어그램: 참조](../modeling/uml-class-diagrams-reference.md)   
 [UML 클래스 다이어그램 형식의 속성](../modeling/properties-of-types-on-uml-class-diagrams.md)   
 [UML 클래스 다이어그램 특성의 속성](../modeling/properties-of-attributes-on-uml-class-diagrams.md)   
 [UML 클래스 다이어그램 작업의 속성](../modeling/properties-of-operations-on-uml-class-diagrams.md)   
 [UML 클래스 다이어그램: 지침](../modeling/uml-class-diagrams-guidelines.md)


