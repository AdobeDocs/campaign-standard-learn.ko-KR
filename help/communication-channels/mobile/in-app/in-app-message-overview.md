---
title: 인앱 메시지 소개
description: Adobe Campaign Standard(ACS) 인앱 메시지 채널을 사용하면 모바일 애플리케이션 내에서 고객의 실시간 행동에 대한 컨텍스트 기반의 인앱 메시지를 사용자에게 제공할 수 있습니다.
feature: In-App
topics: Mobile
kt: 1911
doc-type: feature video
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 82fb2d39dc61a55c0aa20ca1fa215f35a7dd9088
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 19%

---


# 메시지 [!UICONTROL In-App] 소개 {#introduction}

사용자가 모바일 응용 프로그램 내에서 활성 상태인 경우 이 [!UICONTROL In-App Messaging] 채널을 통해 메시지를 표시할 수 있습니다. 이 채널을 이용하려면 모바일 애플리케이션과 통합되어야 합니다 [!UICONTROL Adobe Experience Platform SDK].

이 자습서에서는 모바일 속성을 설정하는 데 필요한 단계, 채널에 대한 [!UICONTROL Launch] 확장 [!UICONTROL In-App Messaging] 및 Adobe Campaign Standard에서 [!UICONTROL In-App] 메시지를 준비, 사용자 정의 및 전송하는 방법에 대해 설명합니다. 이 링크를 클릭하면 강조 표시된 각 주제에 대한 비디오 자습서가 표시됩니다.

## 사전 요구 사항 {#prerequisites}

1. 채널에 액세스할 수 있는지 **[!UICONTROL In-App]** 확인합니다. 이 채널에 액세스할 수 없는 경우 계정 팀에 문의하십시오.
1. Verify that your **user** has the necessary **permissions** in Adobe Campaign Standard and [!UICONTROL Launch].

   1. Adobe Campaign Standard에서 IMS 사용자가 [!UICONTROL Standard User] 및 [!UICONTROL Administrator] 그룹에 속하는지 확인합니다.\
      이 단계에서는 사용자가 Adobe Campaign Standard에 로그인하여 Experience Platform SDK 모바일 앱 페이지로 이동하고 사용자가 만든 모바일 앱 속성을 볼 수 있습니다 [!UICONTROL Launch].
   1. 에서 [!UICONTROL Launch]IMS 사용자가 [!UICONTROL Launch] 제품 프로필에 포함되어 있는지 확인합니다.\
      이 단계에서는 사용자가 로그인하여 속성을 만들고 볼 [!UICONTROL Launch] 수 있습니다. 제품 프로필에 대한 자세한 내용 [!UICONTROL Launch]은 제품 프로필 [만들기를 참조하십시오](https://docs.adobelaunch.com/launch-reference/administration/user-permissions#3-create-your-product-profile). 제품 프로필에는 회사 또는 속성에 설정된 권한이 없어야 하지만 사용자는 계속 로그인할 수 있어야 합니다.

1. Adobe Experience Platform Launch:

   1. 모바일 속성을 만들고 Experience Platform SDK로 모바일 앱을 계측하여 모바일 응용 프로그램을 만듭니다.
   1. 모바일 애플리케이션용 **Adobe Campaign Standard** 익스텐션을 설치합니다.

익스텐션에 대한 자세한 내용은 [설명서의 Adobe 론치에서 Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) 확장 [!UICONTROL Adobe Launch ]구성을 참조하십시오.

## 메시지 설정 [!UICONTROL In-App] 단계 {#steps-to-set-up}

1. [Adobe Experience Platform SDK를 사용하여 모바일 애플리케이션을 구성합니다](/help/communication-channels/mobile/configure-mobile-apps-using-aep-sdk.md).

1. [이벤트를 구성합니다](/help/communication-channels/mobile/in-app/configure-events.md).

## 배달 만들기, 관리 및 [!UICONTROL In-App] 게시 {#create-manage-publish}

홈 페이지나 브라우저에서 **[!UICONTROL Create an In-App Message]** 카드를 클릭하여 인앱 게재를 한 번 만들거나 워크플로우 [!UICONTROL Marketing Activities]내에서 인앱 배달 [](/help/communication-channels/mobile/in-app/in-app-activity.md)을 만들 수 있습니다.

배달을 설정할 때 다른 배달 템플릿 중에서 선택하여 사용자를 타게팅하는 세 가지 옵션이 있습니다.

1. [**모바일 앱의 모든 사용자를 타깃팅하기 위해 인앱 메시지를&#x200B;**](/help/communication-channels/mobile/in-app/broadcast-in-app-message.md)브로드캐스트합니다.

   이 메시지 유형을 사용하면 Adobe Campaign에 기존 프로필이 없더라도 모바일 애플리케이션의 모든 사용자(현재 또는 미래)에게 메시지를 보낼 수 있습니다. 따라서 사용자 프로필은 Adobe Campaign에 반드시 존재하지 않으므로 메시지를 사용자 지정할 때는 개인화를 수행할 수 없습니다.

1. 모든 사용자를 모바일 앱 프로필에 따라 Target으로 지정합니다.

   이 메시지 유형을 사용하면 Adobe Campaign에 모바일 프로필이 있는 모바일 앱의 알려진 모든 사용자 또는 익명의 사용자를 타겟팅할 수 있습니다. 이 메시지 유형은 개인적이지 않고 민감하지 않은 속성만 사용하여 개인화할 수 있으며 Mobile SDK와 Adobe Campaign의 인앱 메시지 서비스 간에 안전한 핸드셰이크가 필요하지 않습니다. 따라서 개인화 전략은 디바이스와의 상호 작용에서 사용자에 대해 수집한 정보를 기반으로 합니다. 예: 지난 1주 동안 앱을 5회 이상 실행한 모든 사용자를 타깃팅합니다.

1. [**캠페인 프로필을 기반으로 한 Target 사용자&#x200B;**](/help/communication-channels/mobile/in-app/target-users-based-on-campaign-profile.md)

   이 메시지 유형을 사용하면 모바일 애플리케이션을 구독한 Adobe Campaign 프로필(CRM 프로필)을 타겟팅할 수 있습니다. 이 메시지는 Adobe Campaign에서 사용 가능한 모든 프로필 속성을 사용하여 개인화할 수 있지만, 개인 및 민감한 정보가 있는 메시지가 인증된 사용자만 사용하도록 보장하기 위해 Mobile SDK와 Campaign의 인앱 메시지 서비스 간의 안전한 핸드셰이크가 필요합니다.

이 템플릿은 이메일 또는 푸시와 같은 다른 채널에서 사용자를 이미 타깃팅한 크로스채널 오케스트레이션 사용 사례를 지원하고 인앱 메시지로 사용자를 타깃팅하려는 경우에 유용합니다.

## 인앱 게재 보고서 {#report}

게재가 게시되면 인앱 배달에 [대해 보고할 수 있습니다](/help/communication-channels/mobile/in-app/in-app-reporting.md).

## 추가 자료

* [인앱 보고서](https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/list-of-reports/in-app-report.html)
* [모바일 속성 설정](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* [Adobe Experience Platform SDK를 사용한 모바일 애플리케이션 구성](https://helpx.adobe.com/kr/campaign/kb/configuring-app-sdk.html)
* [인앱 메시지 준비 및 보내기](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/in-app-messaging/preparing-and-sending-an-in-app-message.html)
* [인앱 메시지 사용자 지정](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/in-app-messaging/customizing-an-in-app-message.html)
* [워크플로우 내에서 인앱 메시지 보내기](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/channel-activities/in-app-delivery.html)
* [라이프사이클 지표 활성화](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk#enable-lifecycle-metrics)
