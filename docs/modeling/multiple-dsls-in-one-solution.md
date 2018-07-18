---
title: 하나의 솔루션에 여러 DSL 포함
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: b0719e4397fed7b850454140462c6e0ed4148da9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31949568"
---
# <a name="multiple-dsls-in-one-solution"></a>하나의 솔루션에 여러 DSL 포함
여러 DSL이 함께 설치되도록 단일 솔루션의 일부분으로 패키지할 수 있습니다.

 다양한 기술을 통해 여러 DSL을 통합할 수 있습니다. 자세한 내용은 참조 [Visual Studio Modelbus를 사용 하 여 모델 통합](../modeling/integrating-models-by-using-visual-studio-modelbus.md) 및 [하는 방법: 끌어서 놓기 처리기를 추가](../modeling/how-to-add-a-drag-and-drop-handler.md) 및 [복사 동작을 사용자 지정](../modeling/customizing-copy-behavior.md)합니다.

### <a name="to-build-more-than-one-dsl-in-the-same-solution"></a>같은 솔루션에서 둘 이상의 DSL을 작성하려면

1.  둘 이상의 DSL 솔루션과 VSIX 프로젝트를 만든 다음 모든 프로젝트를 단일 솔루션에 추가합니다.

    -   새 VSIX 프로젝트를 만들려면:에서 **새 프로젝트** 대화 상자에서 **Visual C#**, **확장성**, **VSIX 프로젝트**합니다.

    -   VSIX 솔루션 디렉터리에 둘 이상의 DSL 솔루션을 만듭니다.

         각 DSL에 대해 새 Visual Studio 인스턴스를 엽니다. 새 DSL을 만들고 VSIX 솔루션과 같은 솔루션 폴더를 지정합니다.

         각 DSL을 서로 다른 파일 확장명으로 만들어야 합니다.

    -   이름을 변경 하는 **Dsl** 및 **DslPackage** 되므로 모두 다른 프로젝트. 예: `Dsl1`, `DslPackage1`, `Dsl2`, `DslPackage2`.

    -   각 **DslPackage\*\source.extension.tt**, 올바른 Dsl 프로젝트 이름으로이 줄을 업데이트 합니다.

         `string dslProjectName = "Dsl2";`

    -   VSIX 솔루션에서 Dsl * 및 DslPackage 추가\* 프로젝트.

         각 쌍을 자체 솔루션 폴더에 배치할 수 있습니다.

2.  DSL의 VSIX 매니페스트를 결합합니다.

    1.  열기 * YourVsixProject ***\source.extension.manifest**합니다.

    2.  각 DSL 선택 **콘텐츠 추가** 추가:

        -   `Dsl*` 프로젝트로 **MEF 구성 요소**

        -   `DslPackage*` 프로젝트로 **MEF 구성 요소**

        -   `DslPackage*` 프로젝트로 **VS 패키지**

3.  솔루션을 빌드합니다.

 그러면 생성되는 VSIX가 두 DSL을 모두 설치합니다. F5 키를 사용 하 여이 테스트 하거나 배포 수 * YourVsixProject ***\bin\Debug\\\*.vsix**합니다.

## <a name="see-also"></a>참고 항목

- [Visual Studio Modelbus를 사용하여 모델 통합](../modeling/integrating-models-by-using-visual-studio-modelbus.md)
- [방법: 끌어서 놓기 처리기 추가](../modeling/how-to-add-a-drag-and-drop-handler.md)
- [복사 동작 사용자 지정](../modeling/customizing-copy-behavior.md)