---
title: 1x1 뷰포트 크기 변형 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 3dbc3247-00f5-4644-8ff9-72e9febcf09a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0c2f97793c838316d252aa56dcadd9fbb045decf
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31472060"
---
# <a name="1x1-viewport-size-variant"></a>1x1 뷰포트 크기 변형
모든 렌더링 대상의 뷰포트 크기를 1x1 픽셀로 줄입니다.  
  
## <a name="interpretation"></a>해석  
 뷰포트가 더 작으면 음영 처리해야 하는 픽셀 수가 줄어들지만 처리해야 하는 꼭짓점 수가 줄지는 않습니다. 뷰포트 크기를 1x1픽셀로 설정하면 앱에서 픽셀 음영이 효과적으로 제거됩니다.  
  
 이러한 변형으로 성능이 크게 향상되면 앱에서 채우기 속도를 너무 많이 사용함을 나타낼 수 있습니다. 이는 선택한 해상도가 대상 플랫폼에 비해 너무 높거나 앱에서 나중에 덮어쓰기(overdraw)한 픽셀을 음영 처리하는 데 상당한 시간이 소요됨을 나타낼 수 있습니다. 이 결과는 프레임 버퍼의 크기를 줄이거나 overdraw 양을 줄이면 앱의 성능이 향상된다는 것을 알려줍니다.  
  
## <a name="remarks"></a>설명  
 `ID3D11DeviceContext::OMSetRenderTargets` 또는 `ID3D11DeviceContext::RSSetViewports`를 호출한 후에는 항상 뷰포트 크기가 1x1로 다시 설정됩니다.  
  
## <a name="example"></a>예제  
 이 변형은 다음과 같은 코드를 사용하여 재현할 수 있습니다.  
  
```  
D3D11_VIEWPORT viewport;  
viewport.TopLeftX = 0;  
viewport.TopLeftY = 0;  
viewport.Width = 1;  
viewport.Height = 1;  
d3d_context->RSSetViewports(1, &viewport);  
```