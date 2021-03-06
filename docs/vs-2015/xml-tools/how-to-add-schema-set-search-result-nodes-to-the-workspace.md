---
title: '방법: 작업 영역에 스키마 집합 검색 결과 노드 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 75f254a8f64c3750a3c89e10016a0520d3760847
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49210368"
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>방법: 작업 영역에 스키마 집합 검색 결과 노드 추가
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
이 항목에서는 작업 영역에서 키워드 검색을 수행한 결과로 XML 스키마 탐색기에서 강조 표시되는 노드를 추가하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  전역 노드만 추가할 수는 [작업 영역](../xml-tools/xml-schema-designer-workspace.md)합니다.  
  
 이 예제에서는 샘플 [구매 주문 스키마](../xml-tools/sample-xsd-file-purchase-order-schema.md)합니다.  
  
### <a name="to-add-schema-set-result-nodes"></a>스키마 집합 결과 노드를 추가하려면  
  
1.  단계를 따릅니다 [방법:는 XSD 스키마 파일 만들기 및 편집](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)합니다.  
  
2.  검색 텍스트 상자에 "purchaseOrder"를 입력 합니다 [XML 탐색기](../xml-tools/xml-schema-explorer.md) 도구 모음 및 검색 단추를 클릭 합니다.  
  
     ![XML 스키마 탐색기 키워드 검색](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")  
  
     또한 검색 결과가 XML 스키마 탐색기에서 강조 표시되고 세로 스크롤 막대의 눈금 표시로 나타납니다.  
  
3.  검색 결과 클릭 하 여 작업 영역에 추가 합니다 **작업 영역에 선택한 노드 추가** 요약 결과 창에서 단추입니다.  
  
     ![XML 스키마 탐색기 검색 결과](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")  
  
     합니다 `purchaseOrder` 노드 및 `PurchaseOrderType` 의 디자인 화면에 나란히 표시 하는 노드를 [그래프 뷰](../xml-tools/graph-view.md)합니다. 이 두 노드는 서로 관련되어 있으므로(`purchaseOrder` 요소가 `PurchaseOrderType` 형식임) 두 노드 사이에 화살표가 그려집니다.



