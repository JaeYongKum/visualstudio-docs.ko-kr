---
title: 실행 취소 하 고 레거시 API를 사용 하 여 다시 실행 관리 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ab655c4822f7f5186cbcd18d451cfa3bb0aa656e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51764170"
---
# <a name="managing-undo-and-redo-by-using-the-legacy-api"></a>관리 실행 취소 및 레거시 API를 사용 하 여 다시 실행
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

편집기는 코드를 수정 하는 경우 최근 변경 내용이 되돌릴 수 있도록 하는 실행 취소 작업을 지원 해야 합니다. 대부분의 편집기에서 구현 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 하며 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 통합된 개발 환경 (IDE)에서 자동으로 제공 하는 실행 취소 기능을 가질 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md)  
 단일 또는 여러 뷰를 사용 하 여 편집기에 대 한 실행 취소 기능을 제공합니다.  
  
 [방법: 실행 취소 스택 정리](../extensibility/how-to-clear-the-undo-stack.md)  
 실행 취소 스택에 선택을 취소 하는 방법에 설명 합니다.  
  
 [방법: 연결된 실행 취소 관리 사용](../extensibility/how-to-use-linked-undo-management.md)  
 편집기에 연결 된 실행 취소 관리를 통합 합니다.  
  
## <a name="reference"></a>참조  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>  
 여러 뷰를 지 원하는 편집기에 대 한 실행 취소 관리를 제공 합니다.  
  
## <a name="related-sections"></a>관련 단원

