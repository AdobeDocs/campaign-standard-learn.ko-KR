---
title: 이벤트 구성
description: 'Adobe Campaign Standard(ACS) 이벤트에서 인앱 메시지를 구성할 때 메시지가 표시되도록 트리거할 사용자 시작 작업을 정의합니다. '
feature: In-App
topics: Mobile
kt: 2548
doc-type: feature video
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 82fb2d39dc61a55c0aa20ca1fa215f35a7dd9088
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---


# 구성 [!UICONTROL Events] {#configuring-events}

메시지를 구성할 때 [!UICONTROL In-App] 표시할 메시지를 트리거하는 사용자 시작 작업을 정의해야 합니다. 이러한 작업을 호출합니다 [!UICONTROL events]. 세 가지 카테고리가 [!UICONTROL events] 있습니다. [!UICONTROL Mobile Application events], [!UICONTROL Life Cycle events]and [!UICONTROL Analytics events].

## [!UICONTROL Mobile Application Events] {#mobile-application-events}

[!UICONTROL Mobile Application events] 는 모바일 애플리케이션 [!UICONTROL custom events] 에 구현되어 있습니다.

예:

* 고객이 항목을 보았습니다.
* 고객이 장바구니에 품목을 추가합니다
* 장바구니 포기
* 고객이 제품을 구입했습니다.

Adobe Campaign [!UICONTROL events] 에서 구성해야 합니다. 다음 비디오에서는 이 작업을 수행하는 방법을 설명합니다.

>[!VIDEO](https://video.tv.adobe.com/v/26245?quality=12)

## [!UICONTROL Life Cycle events]  {#life-cycle-events}

[!UICONTROL Lifecycle events] 간편하게 사용할 수 있습니다 [!UICONTROL events]. 다음 [!UICONTROL events] 을 사용할 수 있습니다.

* [!UICONTROL launched]
* [!UICONTROL upgraded]
* [!UICONTROL crashed]

예를 들어 업그레이드 또는 이벤트 홍보 후에 새로운 기능을 소개하는 메시지가 될 수 있습니다.

>[!NOTE]
>
>모바일 응용 프로그램에서 [!UICONTROL Lifecycle module] 구성해야 합니다. 앱에 라이프사이클을 추가하는 [방법에 대한 자세한 내용은 여기를 참조하십시오.](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle)

## [!UICONTROL Analytics Events] {#analytics-events}

모바일 앱에서 구현된 항목에 따라 다음 세 가지 카테고리가 지원됩니다.

* Adobe Analytics
* [!UICONTROL Context data]
* [!UICONTROL View state]

>[!NOTE]
>
>[!UICONTROL Analytics events] Adobe Analytics 라이선스가 필요합니다. 구성된 [[!DNL Analytics] 확장](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#configure-analytics-extension-in-launch) 프로그램이 있고 [Analytics를 앱에](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-analytics#add-analytics-to-your-app)추가하면 ACS의 [!UICONTROL In-App] 구성에서 이러한 이벤트를 사용할 수 있게 됩니다.

## 추가 리소스

* [라이프사이클 지표 활성화(설명서)](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk#enable-lifecycle-metrics)
