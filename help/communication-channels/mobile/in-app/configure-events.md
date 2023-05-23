---
title: 이벤트 구성
description: "이벤트에서 표시할 인앱 메시지를 트리거하는 사용자 시작 작업을 정의하는 방법을 이해합니다. "
feature: In App
kt: 2548
thumbnail: 26245.jpg
doc-type: feature video
activity: use
team: TM
exl-id: 2c7937f4-b0da-46e5-934e-c660012c2c6f
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 89df23d00913d36b93d3be03b62c74320524f9c7
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 2%

---

# 구성 [!UICONTROL Events] {#configuring-events}

구성 시 [!UICONTROL In-App] 메시지를 표시하려면 사용자가 시작한 작업을 정의하여 메시지를 표시해야 합니다. 이러한 작업을 라고 합니다. [!UICONTROL events]. 다음의 세 가지 범주 [!UICONTROL events] 사용 가능: [!UICONTROL Mobile Application events], [!UICONTROL Life Cycle events], 및 [!UICONTROL Analytics events].

## [!UICONTROL Mobile Application Events] {#mobile-application-events}

[!UICONTROL Mobile Application events] 은(는) [!UICONTROL custom events] 모바일 애플리케이션에서 구현됩니다.

예:

* 고객이 항목을 조회함
* 고객이 장바구니에 품목을 추가합니다.
* 장바구니 포기
* 고객이 구매한 항목

다음을 구성해야 합니다. [!UICONTROL events] Adobe Campaign. 다음 비디오에서는 이 작업을 수행하는 방법에 대해 설명합니다.

>[!VIDEO](https://video.tv.adobe.com/v/26245?quality=12&learn=on)

## [!UICONTROL Life Cycle events] {#life-cycle-events}

[!UICONTROL Lifecycle events] 기본 제공 [!UICONTROL events]. 다음 [!UICONTROL events] 사용 가능:

* [!UICONTROL launched]
* [!UICONTROL upgraded]
* [!UICONTROL crashed]

업그레이드 후 새로운 기능을 소개하는 메시지나 이벤트 프로모션이 사용 사례의 예입니다.

>[!NOTE]
>
>다음 [!UICONTROL Lifecycle module] 모바일 애플리케이션에서 구성해야 합니다. 자세한 내용은 여기 를 참조하십시오. [앱에 라이프사이클을 추가하는 방법](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle)

## [!UICONTROL Analytics Events] {#analytics-events}

모바일 앱에서 구현된 항목에 따라 다음 세 가지 카테고리가 지원됩니다.

* Adobe Analytics
* [!UICONTROL Context data]
* [!UICONTROL View state]

>[!NOTE]
>
>[!UICONTROL Analytics events] Adobe Analytics 라이선스가 필요합니다. 를 가져오면 [[!DNL Analytics] 확장 구성됨](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#configure-analytics-extension-in-launch) 및 이(가) 을(를) 추가함 [앱에 대한 분석](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#add-analytics-to-your-app), 이러한 이벤트는에서 사용할 수 있습니다. [!UICONTROL In-App] acs에서 구성
