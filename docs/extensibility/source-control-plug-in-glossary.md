---
title: 소스 제어 플러그 인 용어 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- glossary [Visual Studio SDK]
- source control plug-ins, glossary
ms.assetid: f224bbc9-38fc-4c80-ab09-51dcc8969f8e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ccfd4cbbbca86d3b6e93d9998410c5dea117328d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31139028"
---
# <a name="source-control-plug-in-glossary"></a>소스 제어 플러그 인 용어집
다음과 같은 유용한 용어 및 정의 소스 제어 플러그 인 SDK 설명서에 적용 됩니다.  
  
## <a name="definitions"></a>정의  
 체크 인  
 사용자 작업 복사본을 변경 하면 사용자는 중앙 원본 제어 리포지토리로 작업 복사본의 변경 내용을 전송 해야 합니다. 이렇게 하면 다른 사용자에 게 사용할 수 있는 파일의 새 수정 버전이 만들어집니다. 이 프로세스는 체크 인을 라고 합니다.  
  
 체크 아웃  
 수정 하려면 원래의 도와 리포지토리를 알리는 리포지토리에서 작업 복사본을 요청 하는 작업. 작업 복사본을 체크 아웃 하는 시점을 기준으로 프로젝트의 상태를 반영 합니다.  
  
 클라이언트  
 소스 코드 제어 시스템을 사용 하는 프로그램입니다. 이 문서에서는 Visual Studio IDE는 것입니다.  
  
 주석  
 소스 제어 작업을 수행할 때 사용자 수정에 첨부할 수 있는 변경 내용을 설명 하는 메시지입니다.  
  
 충돌  
 두 명의 사용자가 동일한 파일의 동일한 지역에 대 한 변경 내용을 체크 인할 때 상황. 일반적으로 병합이 수행 되어야 합니다.  
  
 디렉터리  
 클라이언트 쪽 로컬 폴더 디렉터리 라고 합니다. 이 사용자 변경 실제로 하면 복사본입니다. 지정된 된 프로젝트;의 작업 복사본 수 있을 수 있습니다. 일반적으로 각 개발자가 자신의 복사본을 있다고 가정 합니다.  
  
 가져오기  
 가져오기 작업 저장소 복사본과 최신 사용자의 작업 복사본을 제공합니다. 체크 아웃, 달리 사용자 하기만 하면 최신 사본을 하지만 변경 되지 않게 하려는 경우 get은 수행 합니다.  
  
 기록  
 이 일반적으로 간략하게 설명 모든 체크 아웃, 체크 인, 업데이트, 태그 및 릴리스 소스 제어 저장소에서 수행 합니다.  
  
 IDE  
 일반적으로 Visual Studio 통합 개발 환경을 나타냅니다. 그러나 소스 제어 플러그 인 API를 인식 하는 다른 클라이언트 환경을 참조할 수도 수 있습니다.  
  
 병합  
 프로세스 중 두 개 이상의 소스 코드 파일 결합 되어 이전 파일에서 모든 기능을 통합 하는 새 파일입니다. 이 개념은 여기서 두 개 이상의 개발자가 파일에 대해 동시 작업 버전 제어에서 중요 합니다.  
  
 프로젝트  
 소스 제어 폴더를 프로젝트 라고도 합니다. Visual Studio에서 프로젝트 또는 솔루션 관계를 않아도 됩니다.  
  
 플러그 인  
 소스 제어 플러그 인 API를 구현 하 여 소스 제어 기능을 제공 하는 DLL입니다.  
  
 리포지토리  
 마스터 복사본을 소스 제어 시스템에는 프로젝트의 전체 수정 기록을 저장 합니다. 각 프로젝트에는 정확히 하나의 저장소를 있습니다.  
  
 수정 버전  
 파일의 기록 또는 파일 집합에는 커밋된 변경 내용. 하나는 수정 버전은 지속적으로 변화 프로젝트에서 스냅숏 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)