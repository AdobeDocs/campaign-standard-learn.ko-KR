---
title: 이벤트 구성
description: '"이벤트는 표시되는 인앱 메시지를 트리거할 사용자 시작 작업을 정의하는 방법을 이해합니다. "'
feature: In App
kt: 2548
thumbnail: 26245.jpg
doc-type: feature video
activity: use
team: TM
exl-id: 2c7937f4-b0da-46e5-934e-c660012c2c6f
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 2be2719ddd84490b796d9abc6300376fa896ff0c
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---

# 구성 [!UICONTROL Events] {#configuring-events}

구성 시 [!UICONTROL In-App] 메시지가 표시되면 표시할 메시지를 트리거하는 사용자 시작 작업을 정의해야 합니다. 이러한 작업을 라고 합니다 [!UICONTROL events]. 세 가지 범주 [!UICONTROL events] 사용할 수 있습니다. [!UICONTROL Mobile Application events], [!UICONTROL Life Cycle events], 및 [!UICONTROL Analytics events].

## [!UICONTROL Mobile Application Events] {#mobile-application-events}

[!UICONTROL Mobile Application events] is [!UICONTROL custom events] 모바일 애플리케이션에서 구현됩니다.

예:

* 고객이 항목을 보았습니다
* 고객이 장바구니에 항목을 추가합니다
* 장바구니 포기
* 고객이 물건을 구입했습니다

이러한 구성 요소를 구성해야 합니다 [!UICONTROL events] Adobe Campaign. 다음 비디오에서는 이 작업을 수행하는 방법을 설명합니다.

>[!VIDEO](https://video.tv.adobe.com/v/26245?quality=12)

## [!UICONTROL Life Cycle events] {#life-cycle-events}

[!UICONTROL Lifecycle events] 즉시 사용 가능 [!UICONTROL events]. 다음 [!UICONTROL events] 사용할 수 있습니다.

* [!UICONTROL launched]
* [!UICONTROL upgraded]
* [!UICONTROL crashed]

예제 사용 사례는 업그레이드 후 새로운 기능을 소개하는 메시지 또는 이벤트 프로모션일 수 있습니다.

>[!NOTE]
>
>다음 [!UICONTROL Lifecycle module] 모바일 애플리케이션에서 를 구성해야 합니다. 자세한 내용은 여기 를 참조하십시오 [앱에 라이프사이클을 추가하는 방법](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle)

## [!UICONTROL Analytics Events] {#analytics-events}

모바일 앱에서 구현된 항목에 따라 다음 세 가지 카테고리가 지원됩니다.

* Adobe Analytics
* [!UICONTROL Context data]
* [!UICONTROL View state]

>[!NOTE]
>
>[!UICONTROL Analytics events] Adobe Analytics 라이센스가 필요합니다. 일단 이 [[!DNL Analytics] 확장 구성](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#configure-analytics-extension-in-launch) 및 이 추가됨 [앱에 분석](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#add-analytics-to-your-app)에서 이러한 이벤트를 사용할 수 있습니다. [!UICONTROL In-App] 구성입니다.

## 추가 리소스

* [라이프사이클 지표 활성화(설명서)](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk#enable-lifecycle-metrics)
