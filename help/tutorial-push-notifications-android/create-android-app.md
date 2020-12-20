---
title: 1단계 - Android 앱 만들기 및 Firebase 클라우드 메시지 사용을 위한 구성
description: 이 부분에서는 Adobe Campaign Standard에서 보낸 [!DNL Android] App to receive [!UICONTROL Push notifications] 을 만듭니다. 푸시 알림을 수신하려면 앱을 Google의 [!DNL Firebase Cloud Service]에 등록해야 합니다.
feature: Push
topics: Mobile
kt: 4825
doc-type: tutorial
activity: use
team: TM
translation-type: tm+mt
source-git-commit: cdd78e97f2769503d3d4f26933ccc7f35e9b20b9
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 2%

---


# 1단계 - [!DNL Android] 앱 만들기 및 [!DNL Firebase Cloud Messaging]을 사용하도록 구성

이 부분에서 Adobe Campaign Standard에서 보낸 [!UICONTROL Push notifications]을(를) 받을 [!DNL Android] 앱을 만듭니다. 푸시 알림을 수신하려면 앱을 Google의 [!DNL Firebase Cloud Service]에 등록해야 합니다.

1. [!DNL Firebase] 계정에 로그인합니다.

   [!DNL Firebase] 고품질의 앱을 신속하게 개발할 수 있는 Google의 모바일 플랫폼입니다. [!DNL Firebase] 계정이 없는 경우 여기에서 [을(를) 만드십시오.](https://firebase.google.com).

2. [!DNL Android Studio] 시작
3. **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL New Project]를 클릭합니다.**
4. **[!UICONTROL Empty Activity]**&#x200B;을(를) 선택하고 **[!UICONTROL Next]을(를) 클릭합니다 .**

   ![android-project](assets/android-project.PNG)

5. 프로젝트에 의미 있는 이름을 입력합니다.

   이 데모를 위해 프로젝트의 이름을 *[!DNL ACSPushTutorial]*&#x200B;으로 지정했습니다.

   ![android-project-configuration](assets/android-project-configuration.PNG)

6. 기본 패키지 이름을 적용하고 **[!DNL Finish]**&#x200B;을 클릭하여 프로젝트를 만듭니다.
7. 프로젝트 구조는 아래 스크린샷과 비슷해야 합니다.

   ![android-project-structure](assets/android-project-structure.PNG)

8. 클릭 **[!UICONTROL Tools]** > **[!UICONTROL Firebase].** (프로젝트를  [!DNL Firebase]
9. **[!UICONTROL Set up Firebase Cloud Messaging]을(를) 클릭합니다.**

   ![firebase 설정](assets/android-project-firebase-messaging.PNG)

10. **[!UICONTROL Connect to Firebase]을(를) 클릭합니다.**
11. 앱이 Firebase에 연결된 후 **[!UICONTROL Add FCM to your app].**
12. **[!UICONTROL Accept Changes]을(를) 클릭합니다.**

   앱에 FCM을 추가하는 경우 프로젝트를 변경하려면 마법사가 권한을 받아야 합니다.

   ![[!DNL add-fcm-to-your-app]](assets/firebase-add-fcm-to-app.PNG)

앱과 Firebase를 성공적으로 통합하려면 아래 표시된 메시지를 받게 됩니다.

![[!DNL fcm-successfull]](assets/android-firebase-success.PNG)

[프로젝트가 콘솔 내에 나열되는지  [!DNL Firebase ]확인합니다.](https://console.firebase.google.com/)

## [!UICONTROL Push Channel] 설정 구성

1. [!DNL Firebase] 콘솔에 로그인합니다.
2. **[!UICONTROL ACSPushTutorial]** 프로젝트를 엽니다.
3. **톱니바퀴 아이콘**&#x200B;을 클릭하고 프로젝트 설정을 엽니다

   ![project-settings](assets/firebase-project-settings.PNG)

4. **[!UICONTROL Cloud Messaging]** 탭으로 이동합니다.
5. 서버 키 복사

   ![서버 키](assets/firebase-server-key.PNG)

6. Adobe Campaign Standard 인스턴스에 로그인
7. **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile App]을 클릭합니다.**
8. 적절한 **[!UICONTROL Mobile Application Property]을 선택합니다.**
9. **[!UICONTROL Push Channel settings]** 섹션에서 **[!DNL Android]아이콘**&#x200B;을 클릭합니다.
10. 서버 키 필드에 서버 키를 붙여 넣습니다.

모든 것이 잘 진행되면 SUCCESS 메시지가 표시됩니다.

![push-channel-settings](assets/push-channel-settings.PNG)

요약하기 위해 [!DNL Android App]을(를) 만들고 [!DNL Android App]을(를) [!DNL Firebase]과(와) 연결했습니다. 그런 다음 [!DNL Android] 앱의 서버 키를 Adobe Campaign Standard의 모바일 앱에 붙여 넣어 Adobe Campaign의 모바일 앱을 [!DNL Android App]에 연결했습니다.
