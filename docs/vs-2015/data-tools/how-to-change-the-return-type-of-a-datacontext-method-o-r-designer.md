---
title: '방법: DataContext 메서드 (O-r 디자이너)의 반환 형식을 변경 | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5b66bff-6dbb-43c0-bffa-317133ca5b9e
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e4999c9fd273b78ff740e53c25bbe5a4b0a3017f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49211746"
---
# <a name="how-to-change-the-return-type-of-a-datacontext-method-or-designer"></a>방법: DataContext 메서드 (O/R 디자이너)의 반환 형식 변경
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
저장 프로시저 또는 함수를 기반으로 만들어진 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식은 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]에서 저장 프로시저 또는 함수를 놓는 위치에 따라 달라집니다. 저장 프로시저 또는 함수에서 반환된 데이터의 스키마가 엔터티 클래스의 모양과 일치하는 경우 항목을 기존 엔터티 클래스에 직접 놓으면 엔터티 클래스의 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다. 항목을 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]의 빈 영역에 놓으면 자동으로 생성된 형식을 반환하는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다. 메서드 창에 추가한 후 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 변경할 수 있습니다. 반환 형식을 검사 하거나 변경 하는 <xref:System.Data.Linq.DataContext> 메서드를 선택 하 고 클릭 합니다 **반환 형식** 속성에는 **속성** 창.  
  
> [!NOTE]
>  되돌릴 수 없습니다 <xref:System.Data.Linq.DataContext> 반환 형식을 엔터티 클래스를 사용 하 여 자동으로 생성 된 형식을 반환 하도록 설정 하는 메서드를 **속성** 창입니다. 자동으로 생성된 형식을 반환하도록 <xref:System.Data.Linq.DataContext> 메서드를 되돌리려면 원래 데이터베이스 개체를 O/R 디자이너로 끌어 와야 합니다.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-change-the-return-type-of-a-datacontext-method-from-the-auto-generated-type-to-an-entity-class"></a>DataContext 메서드의 반환 형식을 자동으로 생성된 형식에서 엔터티 클래스로 변경하려면  
  
1.  메서드 창에서 <xref:System.Data.Linq.DataContext> 메서드를 선택합니다.  
  
2.  선택 **반환 형식** 에 **속성** 창을 선택한 다음 사용 가능한 엔터티 클래스를 **반환 형식** 목록입니다. 추가 하거나에서 만들어 원하는 엔터티 클래스가 목록에 없는 경우는 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] 목록에 추가 합니다.  
  
3.  .dbml 파일을 저장합니다.  
  
### <a name="to-change-the-return-type-of-a-datacontext-method-from-an-entity-class-back-to-the-auto-generated-type"></a>DataContext 메서드의 반환 형식을 엔터티 클래스에서 자동으로 생성된 형식으로 다시 변경하려면  
  
1.  메서드 창에서 <xref:System.Data.Linq.DataContext> 메서드를 선택한 다음 삭제합니다.  
  
2.  데이터베이스 개체를 끌어서 **서버 탐색기**/**데이터베이스 탐색기** O/R 디자이너의 빈 영역에 놓으면 됩니다.  
  
3.  .dbml 파일을 저장합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)   
 [방법: 저장 프로시저 및 함수에 매핑된 DataContext 메서드 만들기(O/R 디자이너)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)

