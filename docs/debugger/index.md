---
layout: LandingPage
title: 앱 디버깅 | Microsoft Docs
description: Visual Studio 2017을 사용하여 플랫폼 및 장치에 대해 선택한 언어로 애플리케이션, 서비스 및 도구를 디버그하는 방법에 대해 알아봅니다.
ms.custom: seodec18
ms.topic: landing-page
ms.technology: vs-ide-debug
ms.author: mikejo
author: mikejo5000
manager: douge
ms.openlocfilehash: 2ee721d3febc070435419f2750b52bd4daf533b1
ms.sourcegitcommit: 35bebf794f528d73d82602e096fd97d7b8f82c25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/18/2018
ms.locfileid: "53560715"
---
# <a name="debugging-in-visual-studio"></a>Visual Studio의 디버깅

Visual Studio 디버거를 사용하여 프로그램의 런타임 동작을 관찰하고 문제를 찾아낼 수 있습니다. 디버거는 모든 Visual Studio 프로그래밍 언어 및 관련 라이브러리와 함께 작동합니다. 디버거를 사용하면 프로그램 실행을 중단하여 코드 검사, 변수 검사 및 편집, 레지스터 보기, 소스 코드로부터 만들어진 명령 보기, 애플리케이션에 사용된 메모리 공간 확인 등을 수행할 수 있습니다.

<ul class="panelContent cardsFTitle">
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/what-is-debugging">
            <div class="cardSize">
                <div class="cardPadding">
                    <div class="card">
                        <div class="cardImageOuter">
                            <div class="cardImage">
                                <img src="https://docs.microsoft.com/media/common/i_categorize.svg" alt="What is debugging?">
                            </div>
                        </div>
                        <div class="cardText">
                            <h3>디버깅이란 무엇인가요?</h3>
                        </div>
                    </div>
                </div>
            </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/write-better-code-with-visual-studio">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/common/i_code-quality.svg" alt="Write better code">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>버그를 줄이면서 C# 코드를 작성해 보세요.</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugger-Feature-tour-of-Visual-studio-2017-sqwiwLD6D_1111787171">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/common/i_video.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>디버거 사용에 대한 비디오 보기</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
</ul>

<h2>디버거 시작</h2>

<ul class="panelContent cardsFTitle">
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/debugger-feature-tour">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/common/i_road-map.svg" alt="Road map">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>디버거로 수행할 수 있는 작업 보기</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/debugging-absolute-beginners">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/common/i_get-started.svg" alt="Absolute beginners">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>완전 초보자 가이드</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/get-started/csharp/tutorial-debugger?toc=/visualstudio/debugger/toc.json">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/logos/logo_csharp.svg" alt="C#">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>C++ 앱 디버그</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/getting-started-with-the-debugger-cpp">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/logos/logo_Cplusplus.svg" alt="C++">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>C++ 앱 디버그</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/get-started/visual-basic/tutorial-debugger?toc=/visualstudio/debugger/toc.json">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/logos/logo_vb.svg" alt="VB">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Visual Basic 앱 디버그</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
</ul>

<h2>디버거에 대한 자세한 정보</h2>

<ul class="panelContent cardsFTitle">
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/using-breakpoints">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/common/i_investigate.svg" alt="Use breakpoints">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>중단점에 대한 자세한 정보</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/debugger-tips-and-tricks">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/common/i_debug.svg" alt="Tips and tricks">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>디버거 팁과 요령</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/view-historical-application-state">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/common/i_investigate.svg" alt="View historical app state">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>이전 앱 상태 검사(Visual Studio Enterprise)</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/debug-live-azure-applications">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/logos/logo_azure.svg" alt="Azure">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>라이브 Azure App Service 애플리케이션 디버그</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
</ul>

<hr>
<h2>참조</h2>

<ul class="panelContent cardsW">
    <li>
        <a href="/visualstudio/debugger/api-reference-for-intellitrace-extensibility">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>IntelliTrace 참조</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>디버그 인터페이스 액세스 SDK</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/spy-increment-help">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Spy++</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/mac/debugging">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>디버깅(Mac용 Visual Studio)</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
</ul>

---
