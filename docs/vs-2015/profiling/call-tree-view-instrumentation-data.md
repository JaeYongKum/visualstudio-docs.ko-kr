---
title: 호출 트리 뷰 - 계측 데이터 | Microsoft 문서
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Call Tree view
ms.assetid: 306bd176-0ce9-4a10-89ca-20b043d37d4e
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 385d12550692f5f27521afe4dea12e5bdb0aa9d8
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54782390"
---
# <a name="call-tree-view---instrumentation-data"></a>호출 트리 뷰 - 계측 데이터
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

호출 트리의 함수 값은 호출 트리의 부모 함수가 호출한 함수 인스턴스의 시간을 나타냅니다. 비율 값은 프로파일링 실행 시 모든 함수의 총 경과된 포괄 시간과 함수 인스턴스 값을 비교하여 계산됩니다.  
  
## <a name="general"></a>일반  
 일반 열에는 뷰 행의 함수가 표시됩니다.  
  
|열|설명|  
|------------|-----------------|  
|**함수 이름**|함수의 이름.|  
|**함수 주소**|함수의 주소입니다.|  
|**함수 줄 번호**|소스 파일에서 이 함수가 시작되는 줄 번호입니다.|  
|**호출 수**|이 함수에 대해 수행한 총 호출 수입니다.|  
|**소스 파일**|이 함수의 정의가 포함된 소스 파일입니다.|  
|**모듈 이름**|함수가 포함된 모듈의 이름입니다.|  
|**모듈 경로**|함수가 포함된 모듈의 경로입니다.|  
|**프로세스 ID**|프로파일링 실행의 PID(프로세스 ID)입니다.|  
|**프로세스 이름**|프로세스에 할당된 이름입니다.|  
|**시간 제외 프로브 오버헤드**|계측으로 인한 이 함수의 시간 오버헤드입니다. 모든 전용 시간에서 프로브 오버헤드를 뺀 값입니다.|  
|**시간 포괄 프로브 오버헤드**|계측으로 인한 이 함수와 해당 자식 함수의 시간 오버헤드입니다. 모든 포괄 시간에서 프로브 오버헤드를 뺀 값입니다.|  
|**수준**|호출 트리에서 함수의 깊이입니다. [VSPerfReport](../profiling/vsperfreport.md) 명령줄 보고서에서만 사용됩니다.|  
  
## <a name="elapsed-inclusive-values"></a>경과된 포괄 값  
 경과된 포괄 값은 호출 트리의 부모 함수가 호출한 함수 인스턴스의 호출 스택에 있는 시간을 나타냅니다. 시간에는 함수가 호출한 자식 함수에서 소요된 시간과 컨텍스트 전환, 입/출력 작업 등 운영 체제에 대한 호출에 소요된 시간이 포함됩니다.  
  
|열|설명|  
|------------|-----------------|  
|**경과된 포괄 시간**|이 컨텍스트에서 이 함수에 대한 모든 호출의 총 경과된 포괄 시간입니다.|  
|**경과된 포괄 시간 %**|이 컨텍스트에서 이 함수의 총 경과된 포괄 시간에서 소요된 프로파일링 실행의 총 경과된 포괄 시간 비율입니다.|  
|**경과된 평균 포괄 시간**|이 컨텍스트에서 이 함수에 대한 호출의 평균 경과된 포괄 시간입니다.|  
|**최대 경과된 포괄 시간**|이 컨텍스트에서 이 함수에 대한 호출의 최대 경과된 포괄 시간입니다.|  
|**최소 경과된 포괄 시간**|이 컨텍스트에서 이 함수에 대한 호출의 최소 경과된 포괄 시간입니다.|  
  
## <a name="elapsed-exclusive-values"></a>경과된 전용 값  
 경과된 전용 값은 호출 트리의 부모 함수가 호출한 함수 인스턴스에서 함수 본문의 코드를 실행하는 시간(즉, 함수가 호출 스택의 맨 위에 있을 때)을 나타냅니다. 시간에는 컨텍스트 전환, 입/출력 작업 등 운영 체제에 대한 호출의 시간이 포함됩니다. 그러나 이 시간에 함수가 호출한 자식 함수에서 소요된 시간은 포함되지 않습니다.  
  
|열|설명|  
|------------|-----------------|  
|**경과된 전용 시간**|이 컨텍스트에서 이 함수에 대한 모든 호출의 총 경과된 전용 시간입니다.|  
|**경과된 전용 시간 비율(%)**|이 컨텍스트에서 이 함수의 총 경과된 전용 시간에서 소요된 프로파일링 실행의 총 경과된 전용 시간 비율입니다.|  
|**평균 경과된 전용 시간**|이 컨텍스트에서 이 함수에 대한 호출의 평균 경과된 전용 시간입니다.|  
|**최대 경과된 전용 시간**|이 컨텍스트에서 이 함수에 대한 호출의 최대 경과된 전용 시간입니다.|  
|**최소 경과된 전용 시간**|이 컨텍스트에서 이 함수에 대한 호출의 최소 경과된 전용 시간입니다.|  
  
## <a name="application-inclusive-values"></a>애플리케이션 포괄 값  
 애플리케이션 포괄 값은 호출 트리의 부모 함수가 호출한 함수 인스턴스가 호출 스택에 있는 시간을 나타냅니다. 시간에는 컨텍스트 전환, 입/출력 작업 등 운영 체제에 대한 호출에 소요된 시간이 포함되지 않습니다. 그러나 이 시간에 함수가 호출한 자식 함수에서 소요된 시간은 포함됩니다.  
  
|열|설명|  
|------------|-----------------|  
|**애플리케이션 포괄 시간**|이 컨텍스트에서 이 함수에 대한 모든 호출의 총 애플리케이션 포괄 시간입니다.|  
|**애플리케이션 포괄 시간 비율(%)**|이 컨텍스트에서 이 함수의 총 애플리케이션 포괄 시간에서 소요된 프로파일링 실행의 총 경과된 포괄 시간 비율입니다.|  
|**평균 애플리케이션 포괄 시간**|이 컨텍스트에서 이 함수에 대한 호출의 평균 애플리케이션 포괄 시간입니다.|  
|**최대 애플리케이션 포괄 시간**|이 컨텍스트에서 이 함수에 대한 호출의 최대 애플리케이션 포괄 시간입니다.|  
|**최소 애플리케이션 포괄 시간**|이 컨텍스트에서 이 함수에 대한 호출의 최소 애플리케이션 포괄 시간입니다.|  
  
## <a name="application-exclusive-values"></a>애플리케이션 전용 값  
 애플리케이션 전용 값은 호출 트리의 부모 함수가 호출한 함수 인스턴스에서 함수 본문의 코드를 직접 실행하는 시간(즉, 함수가 호출 스택의 맨 위에 있을 때)을 나타냅니다. 시간에는 컨텍스트 전환, 입/출력 작업 등 운영 체제에 대한 호출에 소요된 시간이 포함되지 않습니다. 또한 함수가 호출한 자식 함수에서 소요된 시간도 포함되지 않습니다.  
  
|열|설명|  
|------------|-----------------|  
|**애플리케이션 전용 시간**|이 컨텍스트에서 이 함수에 대한 모든 호출의 총 애플리케이션 전용 시간입니다.|  
|**애플리케이션 전용 시간 비율(%)**|이 컨텍스트에서 이 함수의 총 애플리케이션 전용 시간에서 소요된 프로파일링 실행의 총 경과된 전용 시간 비율입니다.|  
|**평균 애플리케이션 전용 시간**|이 컨텍스트에서 이 함수에 대한 호출의 평균 애플리케이션 전용 시간입니다.|  
|**최대 애플리케이션 전용 시간**|이 컨텍스트에서 이 함수에 대한 호출의 최대 애플리케이션 전용 시간입니다.|  
|**최소 애플리케이션 전용 시간**|이 컨텍스트에서 이 함수에 대한 호출의 최소 애플리케이션 전용 시간입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [방법: 보고서 뷰 열 사용자 지정](../profiling/how-to-customize-report-view-columns.md)   
 [호출 트리 뷰](../profiling/call-tree-view-sampling-data.md)   
 [호출 트리 뷰 - 계측](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)   
 [호출 트리 뷰 - 샘플링](../profiling/call-tree-view-dotnet-memory-sampling-data.md)
