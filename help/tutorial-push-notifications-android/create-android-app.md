---
title: 1단계 - Android 앱 만들기 및 Firebase Cloud Messaging 사용 구성
description: 이 부분에서는 Adobe Campaign Standard에서 보낸 [!UICONTROL Push notifications]을(를) 받을  [!DNL Android] 앱을 만듭니다. 푸시 알림을 받으려면 앱을 Google  [!DNL Firebase Cloud Service]에 등록해야 합니다.
feature: Push
user: Admin
level: Experienced
jira: KT-4825
doc-type: tutorial
activity: use
team: TM
recommendations: noDisplay
exl-id: f087d9f2-cce9-4903-977f-3c5b47522c06
source-git-commit: 0ad82fb0533ed8fc2a85c2a32c7e54deef14d05a
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# 1단계 - [!DNL Android] 앱 만들기 및 [!DNL Firebase Cloud Messaging] 사용 구성

이 부분에서는 Adobe Campaign Standard에서 보낸 [!UICONTROL Push notifications]을(를) 받을 [!DNL Android] 앱을 만듭니다. 푸시 알림을 받으려면 앱을 Google [!DNL Firebase Cloud Service]에 등록해야 합니다.

1. [!DNL Firebase] 계정에 로그인합니다.

   [!DNL Firebase]은(는) 고품질 앱을 빠르게 개발할 수 있도록 도와주는 Google의 모바일 플랫폼입니다. [!DNL Firebase] 계정이 없는 경우 여기에서 [개](https://firebase.google.com)를 만드십시오.

2. [!DNL Android Studio] 시작
3. **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL New Project].**&#x200B;을 클릭합니다.
4. **[!UICONTROL Empty Activity]**&#x200B;을(를) 선택하고 **[!UICONTROL Next].**&#x200B;을(를) 클릭합니다.

   ![android-project](assets/android-project.PNG)

5. 프로젝트에 의미 있는 이름을 제공하십시오.

   이 데모에서는 프로젝트 이름을 *[!DNL ACSPushTutorial]*(으)로 지정했습니다.

   ![android-project-configuration](assets/android-project-configuration.PNG)

6. 기본 패키지 이름을 수락하고 **[!DNL Finish]**&#x200B;을(를) 클릭하여 프로젝트를 만듭니다.
7. 프로젝트 구조는 아래 스크린샷과 유사해야 합니다.

   ![android-project-structure](assets/android-project-structure.PNG)

8. **[!UICONTROL Tools]** > **[!UICONTROL Firebase]을(를) 클릭합니다.**(프로젝트를 [!DNL Firebase]에 추가)
9. **[!UICONTROL Set up Firebase Cloud Messaging].** 클릭

   ![firebase 설정](assets/android-project-firebase-messaging.PNG)

10. **[!UICONTROL Connect to Firebase].** 클릭
11. 앱이 Firebase에 연결되면 **[!UICONTROL Add FCM to your app].**&#x200B;을(를) 클릭합니다.
12. **[!UICONTROL Accept Changes].** 클릭

   앱에 FCM을 추가하는 경우 마법사에서 프로젝트를 변경할 수 있는 권한이 필요합니다.

   ![[!DNL add-fcm-to-your-app]](assets/firebase-add-fcm-to-app.PNG)

Firebase와 앱을 성공적으로 통합하면 아래 표시된 것과 같은 메시지가 표시됩니다.

![[!DNL fcm-successfull]](assets/android-firebase-success.PNG)

[프로젝트가  [!DNL Firebase &#x200B;]콘솔](https://console.firebase.google.com/)에 나열되어 있는지 확인

## [!UICONTROL Push Channel] 설정 구성

1. [!DNL Firebase] 콘솔에 로그인
2. **[!UICONTROL ACSPushTutorial]** 프로젝트를 엽니다.
3. **톱니바퀴 아이콘**&#x200B;을 클릭하고 프로젝트 설정을 엽니다.

   ![프로젝트 설정](assets/firebase-project-settings.PNG)

4. **[!UICONTROL Cloud Messaging]** 탭으로 이동합니다.
5. 서버 키 복사

   ![서버 키](assets/firebase-server-key.PNG)

6. Adobe Campaign Standard 인스턴스에 로그인
7. **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile App]을(를) 클릭합니다.**
8. 적절한 **[!UICONTROL Mobile Application Property].** 선택
9. **[!UICONTROL Push Channel settings]** 섹션에서 **[!DNL Android]아이콘**&#x200B;을 클릭합니다.
10. 서버 키를 서버 키 필드에 붙여넣습니다.

모든 것이 잘 작동하면 성공 메시지가 표시됩니다.

![푸시 채널 설정](assets/push-channel-settings.PNG)

요약하면 [!DNL Android App]을(를) 만들고 [!DNL Android App]을(를) [!DNL Firebase]과(와) 연결했습니다. 그런 다음 Adobe Campaign의 모바일 앱에 [!DNL Android] 앱의 서버 키를 붙여 넣어 Adobe Campaign Standard의 모바일 앱을 [!DNL Android App]과(와) 연결했습니다.
