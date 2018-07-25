---
title: 문자열 시각화 도우미에서 문자열을 보기 | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2017
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.stringviewer
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- string visualizer
- visualizers, string
ms.assetid: 080fd8f1-72b0-461f-8451-3c84d5dc51df
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca6e4519a85659b36e5cf6baebaadd1d1c626f1a
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151037"
---
# <a name="view-strings-in-a-string-visualizer-in-visual-studio"></a>Visual Studio에서 문자열 시각화 도우미에서 문자열 보기
디버깅 하는 동안 문자열 시각화 도우미 데이터 팁 또는 디버거 창에서 보려는 너무 긴 문자열 보기를 열 수 있습니다. 대부분의 시나리오에서 잘못 된 형식의 문자열을 식별 하는 시각화 도우미 도움이 됩니다.

표준 기본 제공 문자열 시각화 도우미는 일반 텍스트, XML, HTML 및 JSON을 포함 합니다. 디버거에 표시 되는 WPF 개체와 같은 몇 가지 windows 같은 합니다 **자동** 창에서 시각화 도우미를 열 수도 있습니다.

## <a name="open-a-string-visualizer"></a>문자열 시각화 도우미를 열려면

일반 텍스트, XML, HTML 또는 JSON 문자열을 보려면 돋보기 아이콘을 클릭 ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "시각화 아이콘") 문자열 값을 포함 하는 변수를 가리킬 때. 돋보기 아이콘을 확인 하려면 디버거에서 일시 중지 해야 합니다.

![문자열 시각화 도우미를 열려면](../debugger/media/dbg-tips-string-visualizers.png "OpenStringVisualizer")

## <a name="view-string-data"></a>문자열 데이터 보기

합니다 **식** 문자열 시각화 도우미에서 필드는 현재 변수 또는 식 위로 가져갈 디버거에서 보여 줍니다.

합니다 **값** 필드는 문자열 값을 보여 줍니다. 텍스트 시각화 도우미에서는 일반 텍스트를 보여 줍니다.

Blank **값** 특정 시각화 도우미를 문자열 형식을 인식할 수 없습니다 나타냅니다. XML 시각화 도우미는 빈 값을 표시 하는 예를 들어 **값** 간단한 텍스트 문자열 (XML 태그 없음) 또는 JSON 형식 문자열에 대 한 합니다. 시각화 도우미에서 인식할 수 없는 문자열을 확인 해야 할 경우 텍스트 시각화 도우미를 사용 합니다.

### <a name="view-json-string-data"></a>JSON 문자열 데이터 보기

올바른 형식의 JSON 문자열은 JSON 시각화 도우미에서 다음 그림과 같이 표시 됩니다. 잘못 된 형식의 JSON 오류 아이콘 (또는 빈 인식할 수 없는 경우)에 표시 될 수 있습니다. 오류 아이콘이 나타나면 복사와 같은 JSON linting 도구에 JSON 문자열을 붙여 넣습니다 [JSLint](https://www.jslint.com/) JSON 오류를 식별 합니다.

![JSON 문자열 시각화 도우미](../debugger/media/dbg-tips-string-visualizer-json.png "JSON 문자열 시각화 도우미")

### <a name="view-xml-string-data"></a>XML 문자열 데이터 보기

올바른 형식의 XML 문자열로 XML 시각화 도우미에서 다음 그림과 같이 표시 됩니다. 잘못 된 XML은 XML 태그 (또는 빈 인식할 수 없는 경우) 없이 표시할 수 있습니다.

![XML 문자열 시각화 도우미](../debugger/media/dbg-string-visualizers-xml.png "XML 문자열 시각화 도우미")

### <a name="view-html-string-data"></a>문자열 데이터를 HTML 보기

올바른 형식의 HTML 문자열로 표시 되는 문자열 브라우저에서 렌더링 되는 경우 다음 그림과에서 같이 보기와 유사 합니다. 잘못 된 HTML은 일반 텍스트로 표시할 수 있습니다.

![HTML 문자열 시각화 도우미](../debugger/media/dbg-string-visualizers-html.png "HTML 문자열 시각화 도우미")

## <a name="see-also"></a>참고 항목  
 [사용자 지정 시각화 도우미 (C#, Visual Basic) 만들기](../debugger/create-custom-visualizers-of-data.md)