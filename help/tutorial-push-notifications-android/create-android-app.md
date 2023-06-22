---
title: 1단계 - Android 앱 만들기 및 Firebase Cloud Messaging 사용을 위한 구성
description: 이 부분에서는 [!DNL Android] 받을 앱 [!UICONTROL Push notifications] Adobe Campaign Standard에서 보냈습니다. 푸시 알림을 받으려면 앱을 Google에 등록해야 합니다. [!DNL Firebase Cloud Service].
feature: Push
jira: KT-4825
doc-type: tutorial
activity: use
team: TM
recommendations: noDisplay
exl-id: f087d9f2-cce9-4903-977f-3c5b47522c06
source-git-commit: c84867ef59a10448a377a959d0b67ae71343a4aa
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 3%

---

# 1단계 - 만들기 [!DNL Android] 앱 및 사용할 구성 [!DNL Firebase Cloud Messaging]

이 부분에서 다음을 생성합니다. [!DNL Android] 받을 앱 [!UICONTROL Push notifications] Adobe Campaign Standard에서 보냈습니다. 푸시 알림을 받으려면 앱을 Google에 등록해야 합니다. [!DNL Firebase Cloud Service].

1. 에 로그인 [!DNL Firebase] 계정입니다.

   [!DNL Firebase] 는 고품질 앱을 신속하게 개발할 수 있도록 도와주는 Google의 모바일 플랫폼입니다. 이(가) 없는 경우 [!DNL Firebase] 계정을 만드십시오. [여기에서](https://firebase.google.com).

2. 시작 [!DNL Android Studio]
3. 클릭 **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL New Project].**
4. **[!UICONTROL Empty Activity]**&#x200B;을(를) 선택하고 **[!UICONTROL Next]을(를) 클릭합니다 .**

   ![android-project](assets/android-project.PNG)

5. 프로젝트에 의미 있는 이름을 제공하십시오.

   이 데모에서는 프로젝트 이름을 로 지정했습니다. *[!DNL ACSPushTutorial]*

   ![android-project-configuration](assets/android-project-configuration.PNG)

6. 기본 패키지 이름을 적용하고 **[!DNL Finish]** 프로젝트를 만듭니다.
7. 프로젝트 구조는 아래 스크린샷과 유사해야 합니다.

   ![android-project-structure](assets/android-project-structure.PNG)

8. 클릭 **[!UICONTROL Tools]** > **[!UICONTROL Firebase].** (이에 프로젝트가 추가됩니다.) [!DNL Firebase])
9. **[!UICONTROL Set up Firebase Cloud Messaging]를 클릭합니다.**

   ![firebase 설정](assets/android-project-firebase-messaging.PNG)

10. **[!UICONTROL Connect to Firebase]를 클릭합니다.**
11. 앱이 Firebase에 연결되면 **[!UICONTROL Add FCM to your app].**
12. **[!UICONTROL Accept Changes]를 클릭합니다.**

   앱에 FCM을 추가하는 경우 마법사에서 프로젝트를 변경할 수 있는 권한이 필요합니다.

   ![[!DNL add-fcm-to-your-app]](assets/firebase-add-fcm-to-app.PNG)

Firebase와 앱을 성공적으로 통합하면 아래 표시된 것과 같은 메시지가 표시됩니다.

![[!DNL fcm-successfull]](assets/android-firebase-success.PNG)

[프로젝트가에 나열되어 있는지 확인합니다. [!DNL Firebase ]콘솔](https://console.firebase.google.com/)

## 구성 [!UICONTROL Push Channel] 설정

1. 다음으로 로그인 [!DNL Firebase] 콘솔
2. 를 엽니다. **[!UICONTROL ACSPushTutorial]** 프로젝트.
3. 다음을 클릭합니다. **톱니바퀴 아이콘** 프로젝트 설정을 엽니다.

   ![프로젝트 설정](assets/firebase-project-settings.PNG)

4. 탭 **[!UICONTROL Cloud Messaging]** 탭.
5. 서버 키 복사

   ![server-key](assets/firebase-server-key.PNG)

6. Adobe Campaign Standard 인스턴스에 로그인
7. 클릭 **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile App].**
8. 적절한 항목 선택 **[!UICONTROL Mobile Application Property].**
9. 다음을 클릭합니다. **[!DNL Android]아이콘** 다음에서 **[!UICONTROL Push Channel settings]** 섹션.
10. 서버 키를 서버 키 필드에 붙여넣습니다.

모든 것이 잘 작동하면 성공 메시지가 표시됩니다.

![푸시 채널 설정](assets/push-channel-settings.PNG)

요약하자면, 다음 항목을 만들었습니다. [!DNL Android App] 및 연결됨 [!DNL Android App] 포함 [!DNL Firebase]. 그런 다음 Adobe Campaign의 모바일 앱을 [!DNL Android App] 을(를) 붙여 넣어 [!DNL Android] Adobe Campaign Standard의 모바일 앱에 대한 앱의 서버 키입니다.
