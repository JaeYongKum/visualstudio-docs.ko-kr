---
title: Float64Array 개체 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 74c945dc-56ae-458c-b0aa-782f240e9b6c
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20544812d94c1234d85d714f6e469d0de4f4c5ab
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24637413"
---
# <a name="float64array-object"></a>Float64Array 개체
64비트 float 값에 대해 형식화된 배열입니다. 콘텐츠가 0으로 초기화됩니다. 요청된 바이트 수를 할당할 수 없으면 예외가 발생합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      float64Array = new Float64Array( length );  
float64Array = new Float64Array( array );  
float64Array = new Float64Array( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>매개 변수  
 `float64Array`  
 필수 요소. 변수 이름은 **Float64Array** 개체를 할당 합니다.  
  
 `length`  
 배열에 있는 요소의 수를 지정합니다.  
  
 `array`  
 이 배열에 포함된 배열(또는 형식화된 배열)입니다. 콘텐츠가 각 요소가 Float64 형식으로 변환된 주어진 배열 또는 형식화된 배열의 콘텐츠로 초기화됩니다.  
  
 `buffer`  
 Float64Array가 나타내는 ArrayBuffer입니다.  
  
 `byteOffset`  
 선택 사항입니다. 버퍼의 시작 지점에서 Float64Array를 시작할 오프셋(바이트)을 지정합니다.  
  
 `length`  
 배열의 요소 수입니다.  
  
## <a name="constants"></a>상수  
 다음 표에서는 `Float64Array` 개체의 상수를 보여줍니다.  
  
|상수|설명|  
|--------------|-----------------|  
|[BYTES_PER_ELEMENT 상수](../../javascript/reference/bytes-per-element-constant-float64array.md)|배열에서 각 요소의 크기(바이트)입니다.|  
  
## <a name="properties"></a>속성  
 다음 표에서는 `Float64Array` 개체의 상수를 보여줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[buffer 속성](../../javascript/reference/bytelength-property-float64array.md)|읽기 전용입니다. 이 배열에서 참조되는 ArrayBuffer를 가져옵니다.|  
|[byteLength 속성](../../javascript/reference/bytelength-property-float64array.md)|읽기 전용입니다. ArrayBuffer의 시작 부분부터 생성 시 고정된 이 배열의 길이(바이트)입니다.|  
|[byteOffset 속성](../../javascript/reference/length-property-float64array.md)|읽기 전용입니다. ArrayBuffer의 시작 부분부터 생성 시 고정된 이 배열의 오프셋(바이트)입니다.|  
|[length 속성](../../javascript/reference/length-property-float64array.md)|배열의 길이입니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `Float64Array` 개체의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[get 메서드](../../javascript/reference/get-method-float64array.md)|생략 가능. 지정한 인덱스에 있는 요소를 가져옵니다.|  
|[set 메서드(Float64Array)](../../javascript/reference/set-method-float64array.md)|값 또는 값의 배열을 설정합니다.|  
|[subarray 메서드(Float64Array)](../../javascript/reference/subarray-method-float64array.md)|이 배열에 대한 ArrayBuffer 저장소의 새 Float64Array 뷰를 가져옵니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 Float64Array 개체를 사용하여 XmlHttpRequest에서 가져온 이진 데이터를 처리하는 방법을 보여줍니다.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Float64Array(buffer.byteLength / 8);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getFloat64(i * 8);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]