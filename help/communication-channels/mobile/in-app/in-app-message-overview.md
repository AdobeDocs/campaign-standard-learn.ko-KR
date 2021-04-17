---
title: 인앱 메시지 소개
description: '"모바일 애플리케이션 내에서 고객의 실시간 행동에 대한 컨텍스트 내 관련 인앱 메시지를 사용자에게 전달하는 방법을 살펴볼 수 있습니다."'
feature: 앱 내
topics: Mobile
kt: 1911
doc-type: feature video
activity: use
team: TM
exl-id: c51716eb-7239-4fc0-9ccf-9f5f0a5fae65
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 07c2696cbdc72e24563c5d1442bf5c39b22d5a22
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 21%

---

# [!UICONTROL In-App] 메시지 소개 {#introduction}

[!UICONTROL In-App Messaging] 채널을 사용하면 사용자가 모바일 응용 프로그램 내에서 활성 상태일 때 메시지를 표시할 수 있습니다. 이 채널을 사용하려면 모바일 응용 프로그램을 [!UICONTROL Adobe Experience Platform SDK]과(와) 통합해야 합니다.

이 자습서에서는 모바일 속성을 설정하는 데 필요한 단계와 [!UICONTROL In-App Messaging] 채널의 [!UICONTROL Launch] 확장 단계와 Adobe Campaign Standard에서 [!UICONTROL In-App] 메시지를 준비, 사용자 정의 및 전송하는 방법에 대해 설명합니다. 링크를 클릭하면 강조 표시된 각 주제에 대한 비디오 자습서가 표시됩니다.

## 사전 요구 사항 {#prerequisites}

1. **[!UICONTROL In-App]** 채널에 액세스할 수 있는지 확인합니다. 이 채널에 액세스할 수 없는 경우 계정 팀에 문의하십시오.
1. **사용자**&#x200B;에 Adobe Campaign Standard 및 [!UICONTROL Launch]에 필요한 **권한**&#x200B;이 있는지 확인합니다.

   1. Adobe Campaign Standard에서 IMS 사용자가 [!UICONTROL Standard User] 및 [!UICONTROL Administrator] 그룹의 일부인지 확인합니다.\
      이 단계에서는 사용자가 Adobe Campaign Standard에 로그인하고 Experience Platform SDK 모바일 앱 페이지로 이동하여 [!UICONTROL Launch]에서 만든 모바일 앱 속성을 볼 수 있습니다.
   1. [!UICONTROL Launch]에서 IMS 사용자가 [!UICONTROL Launch] 제품 프로필에 속하는지 확인합니다.\
      이 단계에서는 사용자가 [!UICONTROL Launch]에 로그인하여 속성을 만들고 볼 수 있습니다. [!UICONTROL Launch]의 제품 프로파일에 대한 자세한 내용은 [제품 프로필 만들기](https://docs.adobelaunch.com/launch-reference/administration/user-permissions#3-create-your-product-profile)를 참조하십시오. 제품 프로필에는 회사 또는 속성에 설정된 권한이 없지만 사용자는 계속 로그인할 수 있어야 합니다.

1. Adobe Experience Platform Launch:

   1. 모바일 속성을 만들고 Experience Platform SDK로 모바일 앱을 계측하여 모바일 응용 프로그램을 만듭니다.
   1. 모바일 응용 프로그램용 **Adobe Campaign Standard** 확장을 설치합니다.

익스텐션에 대한 자세한 내용은 [!UICONTROL Adobe Launch ]설명서에서 [Adobe 시작](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)에서 Campaign Standard 확장 구성을 참조하십시오.

## [!UICONTROL In-App] 메시지 {#steps-to-set-up}를 설정하는 절차

1. [Adobe Experience Platform SDK를 사용하여 모바일 애플리케이션 구성](/help/communication-channels/mobile/configure-mobile-apps-using-aep-sdk.md).

1. [이벤트를 구성합니다](/help/communication-channels/mobile/in-app/configure-events.md).

## [!UICONTROL In-App] 배달 {#create-manage-publish} 만들기, 관리 및 게시

홈 페이지 또는 [!UICONTROL Marketing Activities]에서 **[!UICONTROL Create an In-App Message]** 카드를 클릭하여 인앱 배달을 한 번 만들거나 워크플로우](/help/communication-channels/mobile/in-app/in-app-activity.md)에서 [인앱 배달을 만들 수 있습니다.

배달을 설정할 때 다른 배달 템플릿에서 선택하여 사용자를 타깃팅하는 3가지 옵션이 있습니다.

1. [**모바일 앱의 모든**](/help/communication-channels/mobile/in-app/broadcast-in-app-message.md) 사용자를 타깃팅하기 위해 인앱 메시지를 브로드캐스트합니다.

   이 메시지 유형을 사용하면 Adobe Campaign에 기존 프로필이 없더라도 모바일 애플리케이션의 모든 사용자(현재 또는 미래)에게 메시지를 보낼 수 있습니다. 따라서 사용자 프로필이 Adobe Campaign에 반드시 존재하지 않으므로 메시지를 사용자 정의할 때는 개인화를 사용할 수 없습니다.

1. 모바일 앱 프로필을 기반으로 모든 사용자를 Target으로 공유합니다.

   이 메시지 유형을 사용하면 Adobe Campaign에 모바일 프로필이 있는 모바일 앱의 알려진 모든 사용자 또는 익명의 사용자를 타겟팅할 수 있습니다. 이 메시지 유형은 개인적이지 않고 민감하지 않은 속성만 사용하여 개인화할 수 있으며 Mobile SDK와 Adobe Campaign의 인앱 메시지 서비스 간에 안전한 핸드셰이크가 필요하지 않습니다. 따라서 개인화 전략은 디바이스와의 상호 작용에서 사용자에 대해 수집한 정보를 바탕으로 합니다. 예: 지난 1주 동안 앱을 5회 이상 실행한 모든 사용자를 타깃팅합니다.

1. [**Campaign 프로필 기반 대상 사용자**](/help/communication-channels/mobile/in-app/target-users-based-on-campaign-profile.md).

   이 메시지 유형을 사용하면 모바일 애플리케이션을 구독한 Adobe Campaign 프로필(CRM 프로필)을 타겟팅할 수 있습니다. 메시지는 Adobe Campaign에서 사용 가능한 모든 프로필 속성을 사용하여 개인화할 수 있지만, 개인 및 민감한 정보가 포함된 메시지를 인증된 사용자만 사용할 수 있도록 Mobile SDK와 Campaign의 인앱 메시징 서비스 간의 안전한 핸드셰이크가 필요합니다.

이 템플릿은 이메일 또는 푸시와 같은 다른 채널에서 사용자를 이미 타깃팅하고 응답을 기반으로 하는 크로스 채널 오케스트레이션 사용 사례를 지원하는 데 유용합니다.

## 인앱 게재 보고서 {#report}

배달이 게시되면 인앱 배달](/help/communication-channels/mobile/in-app/in-app-reporting.md)에 대해 [보고할 수 있습니다.

## 추가 리소스

* [인앱 보고서](https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/list-of-reports/in-app-report.html)
* [모바일 속성 설정](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* [Adobe Experience Platform SDK를 사용한 모바일 애플리케이션 구성](https://helpx.adobe.com/kr/campaign/kb/configuring-app-sdk.html)
* [인앱 메시지 준비 및 보내기](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/in-app-messaging/preparing-and-sending-an-in-app-message.html)
* [인앱 메시지 사용자 지정](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/in-app-messaging/customizing-an-in-app-message.html)
* [워크플로우 내에서 인앱 메시지 보내기](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/channel-activities/in-app-delivery.html)
* [라이프사이클 지표 활성화](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk#enable-lifecycle-metrics)
