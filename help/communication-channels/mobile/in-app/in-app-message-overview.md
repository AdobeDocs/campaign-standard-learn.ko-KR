---
title: 인앱 메시지 소개
description: 모바일 애플리케이션 내에서 고객의 실시간 행동에 반응하여 사용자에게 컨텍스트에 맞는 인앱 메시지를 표시하는 방법에 대해 알아봅니다.
feature: In App
kt: 1911
doc-type: feature video
activity: use
team: TM
exl-id: c51716eb-7239-4fc0-9ccf-9f5f0a5fae65
role: User
level: Beginner
source-git-commit: 57dbf456625d22cd2e4526d92e5a8c20a048d339
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 21%

---

# 소개 [!UICONTROL In-App] 메시지 {#introduction}

다음 [!UICONTROL In-App Messaging] 채널을 사용하면 사용자가 모바일 애플리케이션 내에서 활성 상태일 때 메시지를 표시할 수 있습니다. 이 채널을 사용하려면 모바일 애플리케이션을 [!UICONTROL Adobe Experience Platform SDK].

이 튜토리얼에서는 모바일 속성을 설정하는 데 필요한 단계인 [!UICONTROL Launch] 확장 프로그램 [!UICONTROL In-App Messaging] 채널 및 준비, 사용자 지정 및 전송 방법 [!UICONTROL In-App] Adobe Campaign Standard의 메시지. 이 링크를 클릭하면 강조 표시된 각 주제에 대한 비디오 튜토리얼이 표시됩니다.

## 전제 조건 {#prerequisites}

1. 다음에 액세스할 수 있는지 확인합니다. **[!UICONTROL In-App]** 채널. 이 채널에 액세스할 수 없는 경우 계정 팀에 문의하십시오.
1. 다음을 확인합니다. **사용자** 필요한 **권한** Adobe Campaign Standard 및 [!UICONTROL Launch].

   1. Adobe Campaign Standard에서 IMS 사용자가 [!UICONTROL Standard User] 및 [!UICONTROL Administrator] 그룹.

      이 단계에서는 사용자가 Adobe Campaign Standard에 로그인하고 Experience Platform SDK 모바일 앱 페이지로 이동한 다음, 만든 모바일 앱 속성을 볼 수 있습니다 [!UICONTROL Launch].

   1. 위치 [!UICONTROL Launch]: IMS 사용자가 [!UICONTROL Launch] 제품 프로필. 이 단계에서는 사용자가에 로그인할 수 있습니다. [!UICONTROL Launch] 속성을 만들고 봅니다. 제품 프로필에 회사 또는 속성에 대해 설정된 권한이 없어야 하지만 사용자는 계속 로그인할 수 있어야 합니다.

1. Adobe Experience Platform Launch:

   1. 모바일 속성을 생성하여 모바일 애플리케이션을 만들고 Experience Platform SDK를 사용하여 모바일 앱을 계측합니다.
   1. 설치 **Adobe Campaign Standard** 모바일 애플리케이션용 확장.

확장에 대한 자세한 내용은 [Adobe Launch에서 Campaign Standard 확장 구성](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) 설명서에서 참조하십시오.

## 설정 단계 [!UICONTROL In-App] 메시지 {#steps-to-set-up}

1. [Adobe Experience Platform SDK를 사용하여 모바일 애플리케이션 구성](/help/communication-channels/mobile/configure-mobile-apps-using-aep-sdk.md).
1. [이벤트 구성](/help/communication-channels/mobile/in-app/configure-events.md).

## 만들기, 관리 및 게시 [!UICONTROL In-App] 게재 {#create-manage-publish}

다음을 클릭하여 한 번의 인앱 게재를 만들 수 있습니다. **[!UICONTROL Create an In-App Message]** 홈페이지의 카드, [!UICONTROL Marketing Activities]또는 다음을 수행할 수 있습니다. [워크플로우 내에서 인앱 게재 만들기](/help/communication-channels/mobile/in-app/in-app-activity.md).

게재를 설정할 때 서로 다른 게재 템플릿에서 선택하여 사용자를 타깃팅하는 세 가지 옵션이 있습니다.

1. [**인앱 메시지 브로드캐스트**](/help/communication-channels/mobile/in-app/broadcast-in-app-message.md) 모바일 앱의 모든 사용자를 타깃팅할 수 있습니다.

   이 메시지 유형을 사용하면 Adobe Campaign에 기존 프로필이 없더라도 모바일 애플리케이션의 모든 사용자(현재 또는 미래)에게 메시지를 보낼 수 있습니다. 따라서 Adobe Campaign에 사용자 프로필이 반드시 존재하는 것은 아니므로 메시지를 사용자 정의할 때는 개인화를 수행할 수 없습니다.

1. 모바일 앱 프로필을 기반으로 모든 사용자 Target.

   이 메시지 유형을 사용하면 Adobe Campaign에 모바일 프로필이 있는 모바일 앱의 알려진 모든 사용자 또는 익명의 사용자를 타겟팅할 수 있습니다. 이 메시지 유형은 개인적이지 않고 민감하지 않은 속성만 사용하여 개인화할 수 있으며 Mobile SDK와 Adobe Campaign의 인앱 메시지 서비스 간에 안전한 핸드셰이크가 필요하지 않습니다. 따라서 개인화 전략은 디바이스와의 상호 작용에서 사용자에 대해 학습한 내용을 기반으로 합니다. 예를 들어 지난 1주 동안 앱을 5회 이상 시작한 모든 사용자를 타깃팅합니다.

1. [**Campaign 프로필 기반 대상 사용자**](/help/communication-channels/mobile/in-app/target-users-based-on-campaign-profile.md).

   이 메시지 유형을 사용하면 모바일 애플리케이션을 구독한 Adobe Campaign 프로필(CRM 프로필)을 타겟팅할 수 있습니다. Adobe Campaign에서 사용 가능한 모든 프로필 속성을 사용하여 메시지를 개인화할 수 있습니다. 개인 및 중요 정보가 포함된 메시지를 인증된 사용자만 사용할 수 있도록 하려면 Mobile SDK와 Campaign의 인앱 메시지 서비스 간의 안전한 핸드셰이크가 필요합니다.

이 템플릿은 이메일 또는 푸시와 같은 다른 채널의 사용자를 이미 타겟팅한 크로스 채널 오케스트레이션 사용 사례를 지원하는 데 유용합니다. 응답을 기반으로 인앱 메시지를 통해 참여시킬 수 있습니다.

## 인앱 게재 보고서 {#report}

게재가 게시되면 다음과 같은 작업을 수행할 수 있습니다. [인앱 게재 보고서](/help/communication-channels/mobile/in-app/in-app-reporting.md).
