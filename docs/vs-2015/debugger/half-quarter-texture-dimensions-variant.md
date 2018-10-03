---
title: 절반 / 분기 텍스처 크기 변형 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 282e9bbb-51aa-4cd0-8e5c-0901268c29e5
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f42a6786fc378379ca446b704ac8159b8979bf08
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564560"
---
# <a name="halfquarter-texture-dimensions-variant"></a>절반/분기 텍스처 크기 변형
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목의 최신 버전에서 찾을 수 있습니다 [절반 / 분기 텍스처 크기 변형](https://docs.microsoft.com/visualstudio/debugger/graphics/half-quarter-texture-dimensions-variant)합니다.  
  
렌더링 대상이 아닌 질감의 질감 크기를 줄입니다.  
  
## <a name="interpretation"></a>해석  
 질감이 적을수록 차지하는 메모리도 줄어들기 때문에 메모리 대역폭도 더 적게 사용하고 GPU의 질감 캐시에 대한 부담도 줄어듭니다. 그러나 상세한 정도가 떨어지면, 특히 3-D 장면에서 가깝게 보거나 확대한 상태에서 보게 되는 경우 이미지 품질이 저하될 수 있습니다.  
  
 이러한 변형이 성능을 크게 개선하면 앱에서 메모리 대역폭을 너무 많이 사용하거나, 질감 캐시를 비효율적으로 사용하거나 또는 둘 다일 수 있음을 나타냅니다. 또한 질감이 사용 가능한 것보다 더 많은 GPU 메모리를 차지하고 있음을 나타낼 수도 있습니다. 이런 경우 질감은 시스템 메모리로 페이징됩니다.  
  
 앱에서 메모리 대역폭을 너무 많이 사용하거나 질감 캐시를 비효율적으로 사용하는 경우 적절한 질감에 Mip 맵을 사용할 것을 고려한 후에만 질감 크기를 줄일 것을 고려하세요. 더 많은 GPU 메모리를 차지함에도 불구하고 Mip 맵 질감은 더 작은 질감과 마찬가지로 메모리 대역폭을 더 적게 사용하고 캐시 사용률을 높이지만 질감 세부 정보는 줄이지 않습니다. 메모리 사용이 증가하더라도 질감이 시스템 메모리로 페이징되지 않는 경우에는 항상 Mip 맵을 사용하는 것이 좋습니다.  
  
 질감이 사용 가능한 것보다 더 많은 GPU 메모리를 차지하는 경우에는 적절한 질감 압축을 고려한 후에만 질감의 크기를 줄일 것을 고려하세요. 더 작은 질감과 마찬가지로 압축된 질감은 더 적은 메모리를 차지하고 시스템 메모리로 페이징할 필요가 줄어듭니다. 그러나 이러한 질감의 색상 충실도는 떨어집니다. 질감의 콘텐츠에 따라 일부 질감(예: 작은 영역에 색상 변형이 상당한 질감)의 경우 압축이 적절하지 않습니다. 그러만 많은 질감이 압축을 하면 크기를 줄인 것보다 전체적으로 더 나은 이미지 품질을 유지할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 원본 질감을 만드는 `ID3D11Device::CreateTexture2D`를 호출할 때마다 질감 크기가 줄어듭니다. `pDesc`에서 전달되는 D3D11_TEXTURE2D_DESC 개체가 렌더링 시 사용된 질감을 설명하는 경우 특히 질감 크기가 줄어듭니다. 즉, 다음과 같은 경우입니다.  
  
-   BindFlags 멤버에 D3D11_BIND_SHADER_RESOURCE 플래그 집합만 있는 경우  
  
-   MiscFlags 멤버에 D3D11_RESOURCE_MISC_TILE_POOL 플래그 또는 D3D11_RESOURCE_MISC_TILED 플래그 집합이 없는 경우(타일식 리소스의 크기가 조정되지 않음)  
  
-   D3D11_FORMAT_SUPPORT_RENDER_TARGET(질감 크기를 줄이는 데 필요)에 따라 결정된 대로 질감 형식이 렌더링 대상으로 지원되는 경우 렌더링 대상으로 지원되지는 않지만 BC1, BC2 및 BC3 형식도 지원됩니다.  
  
 응용 프로그램에서 초기 데이터를 제공하는 경우 이 변형은 질감 데이터를 질감을 만들기 전에 해당하는 크기로 조절합니다. BC1, BC2 또는 BC3와 같은 블록 압축 형식으로 초기 데이터가 제공되는 경우 초기 데이터는 더 작은 질감을 만드는 데 사용되기 전에 디코딩 및 비율 크기 조정 후 다시 인코딩됩니다. 블록 기반 압축의 특성은 추가 디코딩-비율 크기 조정-인코딩 프로세스는 이전에 인코딩되지 않은 질감의 비율 크기 조정된 버전에서 블록 압축 질감이 생성되는 경우보다 거의 항상 이미지 품질이 낮습니다.  
  
 질감에 Mip 맵을 사용하는 경우 변형은 Mip 수준의 수를 적절하게 줄입니다. 절반 크기로 조정하는 경우 한 수준 낮게, 4분의 1 크기로 조정하는 경우에는 두 수준 낮게 줄입니다.  
  
## <a name="example"></a>예제  
 이러한 변형은 `CreateTexture2D` 호출 전 런타임에 질감의 크기를 조정합니다. 전체 크기 질감은 더 많은 디스크 공간을 사용하고 인코딩에 상당한 계산 리소스가 필요한 압축된 질감의 경우, 특히 추가 단계에서 앱에서의 로드 시간이 길어질 수 있기 때문에 프로덕션 코드에는 이러한 접근 방식을 사용하는 것이 좋습니다. 대신 빌드 파이프라인의 일부인 이미지 편집기 또는 이미지 프로세서를 사용하여 질감의 크기를 오프라인으로 조정하는 것이 좋습니다. 이러한 접근 방식은 디스크 공간 요구 사항을 줄이고 앱에서 런타임 오버헤드를 없애며 더 긴 처리 시간을 허용하므로 최상의 이미지 품질을 유지하면서 동시에 질감을 축소 또는 압축할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Mip 맵 생성 변형](../debugger/mip-map-generation-variant.md)   
 [BC 텍스처 압축 변형](../debugger/bc-texture-compression-variant.md)


