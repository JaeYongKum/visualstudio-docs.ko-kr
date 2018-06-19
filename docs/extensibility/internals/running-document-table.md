---
title: Document 테이블 실행 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- read locks
- running document table (RDT), IVsDocumentLockHolder interface
- running document table (RDT)
- running document table (RDT), edit locks
- document data objects, running document table
ms.assetid: bbec74f3-dd8e-48ad-99c1-2df503c15f5a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4a49a5267fcccbde60e194e3fc58b0f6b6ea7552
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134102"
---
# <a name="running-document-table"></a>실행 중인 문서 테이블
IDE에는 실행 중인 문서 테이블 (RDT) 라는 내부 구조에 현재 열려 있는 모든 문서 목록을 유지 관리 합니다. 이 목록은 이러한 문서 편집 현재는 여부에 관계 없이 메모리에 열려 있는 모든 문서를 포함 합니다. 문서는 프로젝트 또는 주 프로젝트 파일 (예를 들어.vcxproj 파일)에서 파일을 포함 하 여 유지 되는 모든 항목입니다.  
  
## <a name="elements-of-the-running-document-table"></a>실행 중인 문서 테이블의 요소  
 실행 중인 문서 테이블에는 다음 항목이 들어 있습니다.  
  
|요소|설명|  
|-------------|-----------------|  
|문서 모니커|문서 데이터 개체를 고유 하 게 식별 하는 문자열입니다. 이 절대 파일 경로 (예를 들어 C:\MyProject\MyFile) 파일을 관리 하는 프로젝트 시스템에 대 한 것입니다. 이 문자열은 이외의 데이터베이스에 저장된 프로시저와 같은 파일 시스템 저장소에 저장 하는 프로젝트에도 사용 됩니다. 이 경우 프로젝트 시스템에서 인식 하 고 문서를 저장 하는 방법을 결정 하기 위해 수 있는 구문 분석할 수 있는 고유 문자열로 서 만들 수 있습니다.|  
|계층 소유자|로 표현 되는 문서를 소유 하는 계층 개체는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 인터페이스입니다.|  
|항목 ID|계층 내에서 특정 항목에 대 한 항목 식별자입니다. 이 값은이 문서를 소유 하는 계층의 모든 문서 중에서 고유 하지만이 값은 서로 다른 계층 전체에서 고유 해야 아닙니다.|  
|문서 데이터 개체|이 최소한 한 `IUnknown`<br /><br /> 이름입니다. IDE는 특정 인터페이스 외 필요 하지 않습니다는 `IUnknown` 사용자 지정 편집기의 문서 데이터 개체에 대 한 인터페이스입니다. 그러나 표준 편집기에 대 한 편집기의 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> 프로젝트에서 파일 지 속성 호출을 처리 하려면 인터페이스가 필요 합니다. 자세한 내용은 참조 [저장 하는 표준 문서](../../extensibility/internals/saving-a-standard-document.md)합니다.|  
|플래그|RDT에 항목이 추가 될 때 읽기 또는 편집 잠금이 적용 되는지 여부를 문서를 저장 하는지 여부를 제어 하는 플래그 및 등을 지정할 수 있습니다. 자세한 내용은 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> 열거형을 참조하세요.|  
|잠금 수를 편집 합니다.|편집 잠금 수입니다. 편집 잠금 일부 편집기에 문서가 편집을 위해 열려 있는지를 나타냅니다. 편집 잠금 횟수를 0으로 바뀌면가 수정 된 경우 사용자 문서를 저장 하 라는 메시지가 됩니다. 예를 들어, 사용 하 여 편집기에서 문서를 열 때마다는 **새 창** 명령을 편집 잠금은 RDT에서 해당 문서에 대 한 추가 됩니다. 문서 순서로 설정 해야 하는 편집 잠금에 대 한 계층 구조를가지고 있거나 항목 id입니다.|  
|읽기 잠금 수|읽기 잠금을의 개수입니다. 읽기 잠금은 마법사와 같은 몇 가지 메커니즘을 통해 문서를 읽고 있는지를 나타냅니다. 읽기 잠금을 나타내는 문서를 편집할 수 없는 동안는 RDT에서 활성 문서를 포함 합니다. 문서 계층 구조가 하지 않거나 항목 id입니다. 경우에 읽기 잠금을 설정할 수 있습니다. 이 기능을 사용 하면 메모리에 문서를 열고 모든 계층에서 소유 하는 문서 없이 RDT에 입력할 수 있습니다. 이 기능은 거의 사용 되지 않습니다.|  
|잠금 소유자|인스턴스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> 인터페이스입니다. 잠금 소유자 열고 편집기 외부에서 문서를 편집 하는 마법사와 같은 기능을 통해 구현 됩니다. 잠금 소유자 기능을 편집 잠금으로 아직 편집 중인 동안 닫히는에서 문서를 방지 하기 위해 문서에 추가할 수 있습니다. 일반적으로 편집 잠금을 문서 창 (즉, 편집기)에 추가 합니다.|  
  
 RDT의 각 항목에 고유한 계층 또는 일반적으로 프로젝트의 한 노드에 해당 하는 항목 ID와 연결 합니다. 편집 하기 위해 사용할 수 있는 모든 문서는 일반적으로 계층에서 담당 합니다. 에 RDT 입력 제어는 프로젝트 또는-더 정확 하 게-계층 구조를 현재 소유 하 고 편집 중인 문서 데이터 개체입니다. 정보를 사용 하 여 RDT에, IDE를 한 번에 둘 이상의 프로젝트에 의해 열 문서를 방지할 수 있습니다.  
  
 계층 구조에서 또한 데이터의 지 속성을 제어 하 고는 RDT의 정보를 사용 하 여 업데이트 된 **저장** 및 **다른 이름으로 저장** 대화 상자. 사용자가 문서 수정 후 선택한 및는 **종료** 명령을 **파일** 메뉴 IDE 프롬프트를 사용 하 여는 **변경 내용 저장** 모든 프로젝트 개체를 표시 하려면 대화 상자 및 현재 수정 되는 프로젝트 항목을 추가 합니다. 따라서 사용자가 저장 하는 문서를 선택할 수 있습니다. 저장 하는 문서 목록 (즉, 포함 된 문서를 변경)은 RDT에서 생성 됩니다. 참조 되는 모든 항목은 **변경 내용 저장** 응용 프로그램을 종료할 때 대화 상자는 RDT에 레코드가 있어야 합니다. RDT 조정 되는 문서를 저장 하 고 사용자는에 게 메시지를 저장 하는 방법에 대 한 각 문서에 대 한 플래그 항목에 지정 된 값을 사용 하 여 작업 합니다. RDT 플래그에 대 한 자세한 내용은 참조는 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> 열거형입니다.  
  
## <a name="edit-locks-and-read-locks"></a>편집 잠금과 읽기 잠금  
 편집 잠금과 읽기 잠금은 RDT에 있어야 합니다. 문서 창 증가분과 감소 분 편집이 잠급니다. 따라서 사용자가 열 때 새 문서 창 하나씩 편집 잠금 수가 증가 합니다. 편집 잠금 수가 0에 도달 하면 계층 신호를 받는를 유지 하거나 연결된 된 문서에 대 한 데이터를 저장 합니다. 계층 데이터 파일 또는 저장소에 있는 항목으로 유지 하는 포함 하 여 어떤 방식으로 지속 합니다. 사용할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.LockDocument%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> 편집 잠금을 추가 및 읽기 잠금을, 인터페이스 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnlockDocument%2A> 이러한 잠금을 제거 하는 메서드.  
  
 일반적으로 편집기에 대 한 문서 창을 인스턴스화할 때 창 프레임의 문서에 대 한 편집 잠금을 RDT에 자동으로 추가 합니다. 그러나 문서의 사용자 지정 보기를 만드는 경우 사용 하지 않는 표준 문서 창 (구현 하지 않는, 즉는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 인터페이스)를 직접 편집 잠금을 설정 해야 합니다. 예를 들어 마법사, 편집기에서 열리지 않고 문서 편집 됩니다. 마법사와 비슷한 엔터티도 열리도록 문서 잠금에 대 한 순서로 이러한 엔터티를 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> 인터페이스입니다. 문서 잠금 소유자를 등록 하려면 호출는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.RegisterDocumentLockHolder%2A> 메서드와 전달 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> 구현 합니다. 그러면 문서 잠금 소유자는 RDT 추가 합니다. 문서 잠금 소유자를 구현 하기 위한 또 다른 시나리오는 특수 도구 창을 통해 문서를 열 경우. 이 인스턴스에서 도구 창이 문서를 닫을 수 없는 합니다. 그러나 문서 잠금 표시자 RDT는에서를 등록 하면 IDE를 호출할 수의 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder.CloseDocumentHolder%2A> 문서 닫기 메시지를 표시 하는 메서드.  
  
## <a name="other-uses-of-the-running-document-table"></a>실행 중인 문서 테이블의 다른 곳에 사용  
 IDE에서 다른 엔터티는 RDT를 사용 하 여 문서에 대 한 정보를 가져옵니다. 예를 들어 소스 제어 관리자를 사용 하 여는 RDT 파일의 최신 버전을 가져온 후에 편집기에서 문서를 다시 로드 하려면 시스템이 설명 합니다. 이 수행 하려면 소스 제어 관리자는 그 중 어느 열려 있는지 확인 하기 위해 RDT에 있는 파일을 찾습니다. 인 경우 원본 제어 관리자 먼저 확인 하는 계층 구조를 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> 메서드. 프로젝트를 구현 하지 않는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> 메서드를 다음 소스 제어의 구현에 대 한 관리자 검사는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> 문서 데이터 개체를 직접에서 메서드.  
  
 IDE를 사용 하 여는 RDT resurface (앞으로 가져오기) 사용자는 해당 문서를 요청 하는 경우 열려 있는 문서. 자세한 내용은 참조 [파일 열기 명령을 사용 하 여 표시 파일](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)합니다. RDT에서 열려 있는 파일 인지를 확인 하려면 다음을 수행할 하나.  
  
-   항목이 열려 인지 알아보려면 문서 모니커 (즉, 전체 문서 경로)에 대 한 쿼리.  
  
-   계층 또는 항목 ID를 사용 하 여 전체 문서 경로 대 한 프로젝트 시스템을 주고 다음 항목에서에서 조회할는 RDT 받을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [RDT_ReadLock 사용](../../extensibility/internals/rdt-readlock-usage.md)   
 [지속성 및 실행 중인 문서 테이블](../../extensibility/internals/persistence-and-the-running-document-table.md)