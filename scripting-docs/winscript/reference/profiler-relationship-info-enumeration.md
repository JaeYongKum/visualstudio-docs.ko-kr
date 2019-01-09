---
title: PROFILER_RELATIONSHIP_INFO 열거형 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fae69317-6224-4a6a-8e9e-ccaa6a330818
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e95b11537873d3bfe02bf3fa793b61ace10938aa
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095812"
---
# <a name="profilerrelationshipinfo-enumeration"></a>PROFILER_RELATIONSHIP_INFO 열거형
관계에서 개체에 대 한 정보를 나타냅니다. 레지스트리에 [PROFILER_HEAP_OBJECT_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
typedef [v1_enum] enum {    PROFILER_PROPERTY_TYPE_NUMBER = 0x01,    PROFILER_PROPERTY_TYPE_STRING = 0x02,    PROFILER_PROPERTY_TYPE_HEAP_OBJECT = 0x03,    PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT = 0x04,    PROFILER_PROPERTY_TYPE_BSTR = 0x05,} PROFILER_RELATIONSHIP_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|값|설명|  
|------------|-----------|-----------------|  
|PROFILER_PROPERTY_TYPE_NUMBER|0x01|개체에는 숫자입니다.|  
|PROFILER_PROPERTY_TYPE_STRING|0x02|개체는 문자열입니다.|  
|PROFILER_PROPERTY_TYPE_HEAP_OBJECT|0x03|개체 힙 개체가입니다.|  
|PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT|0x04|개체 외부, 즉, 아닌 경우 가비지 컬렉션 힙에|  
|PROFILER_PROPERTY_TYPE_BSTR|0x05|개체는 BSTR입니다.|  
|PROFILER_PROPERTY_TYPE_SUBSTRING|0x06|개체에는 부분 문자열입니다.|