---
title: "Office 문서의 암호 보호 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- passwords [Office development in Visual Studio], document protections
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
ms.assetid: 9cee99c8-73c6-4f89-9d5e-7912c876ff96
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 45f350fed3c806a9ac8f79178a50ef22aa0a800e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="password-protection-on-office-documents"></a>Office 문서의 암호 보호
  암호를 아는 하지 않는 사용자가 열 수 없습니다 있도록 Microsoft Office Word 문서 및 Microsoft Office Excel 통합 문서에 대 한 암호를 설정 하는 것이 불가능 합니다. 이 옵션을 라고 **열기 암호**합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 기존 문서 및 통합 문서는를 사용 하 여 문서 수준 프로젝트를 만들 수 있습니다 **열기 암호** 사용 하도록 설정 합니다. Visual Studio에서 동작은 Word 및 Excel 문서에 대해 다른 **열기 암호** 사용 하도록 설정 합니다.  
  
 사용 하도록 설정 하는 방법에 대 한 내용은 **열기 암호**, Word 또는 Excel에서 도움말을 참조 하세요.  
  
## <a name="behavior-of-excel-and-word"></a>Excel 및 Word의 동작  
 가 있는 Visual Studio의 Excel 통합 문서를 열 때마다 **열기 암호** 활성화 Excel 묻는 암호입니다. 솔루션을 빌드할 때 메시지가 표시 됩니다는 암호에 대 한 다시 빌드 시 문서를 열 때문에 있습니다.  
  
 가 있는 Visual Studio의 Word 문서를 열고 처음 **열기 암호** 활성화 저장할지 확인 암호에 대 한 합니다. 성공적으로 암호를 입력 한 후 **열기 암호** 문서에서 제거 하 고 문서를 열어 암호를 더 이상 필요 합니다. 솔루션의 문서를 사용 하려는 경우 전에 암호를 요구 하도록 열 수, 사용 하도록 설정 해야 **열기 암호** 최종 빌드 및 솔루션을 배포 하기 전에.  
  
## <a name="see-also"></a>참고 항목  
 [문서 수준 솔루션의 문서 보호](../vsto/document-protection-in-document-level-solutions.md)   
 [정보 권한 관리 및 관리 코드 확장 개요](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [방법: 코드 권한이 제한 된 문서 뒤 실행 허용](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)  
  
  