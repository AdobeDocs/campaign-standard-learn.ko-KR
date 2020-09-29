---
title: 2단계 - Mobile SDK 통합
description: 이 부분에서는 Android 앱을 Mobile SDK와 통합합니다. Android 앱과 모바일 SDK 통합
feature: Push
topics: Mobile
kt: 4826
doc-type: tutorial
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 13b4f1d395dfe53f9fc5263e7b06be700e30b986
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 2단계 - Android 앱 [!UICONTROL Mobile SDK] 과 통합

이 부분에서는 [!DNL Android] [!UICONTROL Mobile SDK]앱을 앱 [!UICONTROL mobile SDK] 과 [!DNL Android] 통합하려면 다음 단계를 따르십시오.

* ACSPushTutorial *프로젝트* 열기 [!DNL Android Studio]
* MainApp이라는 새 java 클래스 *를 만들어* [!DNL android.app.Application]
* 이 시점에서 프로젝트 구조가 다음과 같아야 합니다.

![기본 앱](assets/android-main-app.PNG)

* 폴더를 [!DNL Gradle Scripts] 확장합니다. 모듈 [!DNL build.gradle] 을 두 번 클릭합니다. 파일의 종속성 섹션에 다음 종속성을 [!DNL build.gradle] 붙여 넣습니다. 이제 [!DNL build.gradle] 파일은 아래와 같습니다

<!--
Removed `{.line-numbers}` below
-->

```java
implementation 'com.adobe.marketing.mobile:campaign:1.+'
implementation 'com.adobe.marketing.mobile:userprofile:1.+'
implementation 'com.adobe.marketing.mobile:sdk-core:1.+'
```

![모듈 등급](assets/module-build-gradle.PNG)

* 지금 동기화 버튼을 클릭하여 [!DNL Android] 프로젝트를 동기화하면 프로젝트를 동기화할 수 있습니다

## 수정 [!DNL AndroidManifest.xml]{#modify-android-manifest}

AndroidManifest.xml *을* 열고 매니페스트 요소 뒤에 응용 프로그램 요소 앞에 다음 2줄을 붙여 넣습니다. 이를 통해 앱이 외부 세계와 통신할 수 있습니다

<!--
Removed `{.line-numbers}` below
-->

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

응용 프로그램 요소의 다음 줄[!DNL android:name=".MainApp"]을 복사사용자 [!DNL AndroidManifest.xml]저장 [!DNL AndroidManifest.xml] 은 다음과 같아야 합니다

<!--
Removed `{.line-numbers}` below
-->

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.acspushtutorial">
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

<application
    android:name=".MainApp"
    android:allowBackup="true"
    android:icon="@mipmap/ic_launcher"
    android:label="@string/app_name"
    android:roundIcon="@mipmap/ic_launcher_round"
    android:supportsRtl="true"
    android:theme="@style/AppTheme">

<activity android:name=".MainActivity">
<intent-filter>
    <action android:name="android.intent.action.MAIN" />
    <category android:name="android.intent.category.LAUNCHER" />
</intent-filter>
</activity>
</application>

</manifest>
```
