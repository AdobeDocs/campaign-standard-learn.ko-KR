---
title: 이벤트 구성
description: '"이벤트가 사용자가 시작한 작업을 통해 인앱 메시지가 표시되는 것을 트리거하는 방법을 이해합니다. "'
feature: 앱 내
kt: 2548
thumbnail: 26245.jpg
doc-type: feature video
activity: use
team: TM
exl-id: 2c7937f4-b0da-46e5-934e-c660012c2c6f
role: Business Practitioner, Developer
level: Beginner, Intermediate
translation-type: tm+mt
source-git-commit: ada0b029245190f53d58fa93c79c161719bfe9fd
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 2%

---

# [!UICONTROL Events] {#configuring-events} 구성

[!UICONTROL In-App] 메시지를 구성할 때 표시할 메시지를 트리거하는 사용자 시작 작업을 정의해야 합니다. 이러한 작업을 [!UICONTROL events]이라고 합니다. [!UICONTROL events]의 세 가지 카테고리를 사용할 수 있습니다.[!UICONTROL Mobile Application events], [!UICONTROL Life Cycle events] 및 [!UICONTROL Analytics events].

## [!UICONTROL Mobile Application Events] {#mobile-application-events}

[!UICONTROL Mobile Application events] 모바일 애플리케이션 [!UICONTROL custom events] 에 구현된 이미지입니다.

예:

* 고객이 항목을 보았습니다.
* 고객이 장바구니에 항목을 추가합니다.
* 장바구니 포기
* 고객이 어떤 것을 구입했습니다.

Adobe Campaign에서 이러한 [!UICONTROL events]을 구성해야 합니다. 다음 비디오에서는 이 방법을 설명합니다.

>[!VIDEO](https://video.tv.adobe.com/v/26245?quality=12)

## [!UICONTROL Life Cycle events]  {#life-cycle-events}

[!UICONTROL Lifecycle events] 간편하게 사용할 수 있습니다 [!UICONTROL events]. 다음 [!UICONTROL events]을(를) 사용할 수 있습니다.

* [!UICONTROL launched]
* [!UICONTROL upgraded]
* [!UICONTROL crashed]

예를 들어 업그레이드 후 새로운 기능을 소개하고 이벤트 프로모션을 제공하는 메시지가 될 수 있습니다.

>[!NOTE]
>
>모바일 응용 프로그램에서 [!UICONTROL Lifecycle module]을(를) 구성해야 합니다. [앱에 라이프사이클을 추가하는 방법에 대한 자세한 내용은 여기를 참조하십시오](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle)

## [!UICONTROL Analytics Events] {#analytics-events}

모바일 앱에서 구현된 항목에 따라 다음 3가지 카테고리가 지원됩니다.

* Adobe Analytics
* [!UICONTROL Context data]
* [!UICONTROL View state]

>[!NOTE]
>
>[!UICONTROL Analytics events] Adobe Analytics 라이선스가 필요합니다. [[!DNL Analytics] 확장이 ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#configure-analytics-extension-in-launch)으로 구성되고 [Analytics를 앱](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#add-analytics-to-your-app)에 추가하면 ACS의 [!UICONTROL In-App] 구성에서 이러한 이벤트를 사용할 수 있게 됩니다.

## 추가 리소스

* [라이프사이클 지표 활성화(설명서)](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk#enable-lifecycle-metrics)
