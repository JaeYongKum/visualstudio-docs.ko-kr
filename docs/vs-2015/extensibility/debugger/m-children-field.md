---
title: m_children 필드 | Microsoft Docs
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
- m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f044c2dae278a0656f1f9e4c41a3940d87658a64
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51731038"
---
# <a name="mchildren-field"></a>m_children 필드
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

이 작업을 사용 하 여 등록 된 자식 작업의 목록입니다.  
  
 **네임스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** mscorlib (mscorlib.dll)  
  
 .NET Framework에서이 내부 멤버에 액세스할 수 없는 때문에 다음 구문은 공통 중간 언어 (CIL) 제공 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children  
```  
  
## <a name="remarks"></a>설명  
 작업이 실행 되는 동안 작업을 실행 하는 스레드만이 배열을 액세스 해야 합니다.  
  
 작업이 완료 되는 경우에 다른 스레드가에 아무것도 추가 하거나 제거할 아무 것도 하지 않는 있다면이 필드에 액세스할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ContingentProperties 클래스](../../extensibility/debugger/contingentproperties-class-internal-members.md)

