---
title: 2단계 - Mobile SDK 통합
description: 이 부분에서는 Android 앱을 Mobile SDK와 통합합니다. 모바일 SDK를 Android 앱과 통합하려면
feature: Push
kt: 4826
doc-type: tutorial
activity: use
team: TM
recommendations: noDisplay
exl-id: 0fa53536-8330-4e96-be2f-afc078609bcd
source-git-commit: 57dbf456625d22cd2e4526d92e5a8c20a048d339
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 3%

---

# 2단계 - 통합 [!UICONTROL Mobile SDK] Android 앱 사용

이 부분에서는 [!DNL Android] 앱 사용 [!UICONTROL Mobile SDK]. 통합하려면 [!UICONTROL mobile SDK] (으)로 [!DNL Android] 앱에서 다음 단계를 따르십시오.

* 를 엽니다. *ACSPushTutorial* 의 프로젝트 [!DNL Android Studio]
* 라는 새 Java 클래스를 만듭니다. *MainApp* 확장됨 [!DNL android.app.Application]
* 이 시점의 프로젝트 구조는 다음과 같아야 합니다

![main-app](assets/android-main-app.PNG)

* 확장 [!DNL Gradle Scripts] 폴더를 삭제합니다. 를 두 번 클릭합니다. [!DNL build.gradle] 을 참조하십시오. 의 종속성 섹션에 다음 종속성을 붙여 넣습니다. [!DNL build.gradle] 파일. 사용자 [!DNL build.gradle] 이제 파일은 다음과 같아야 합니다

<!--
Removed `{.line-numbers}` below
-->

```java
implementation 'com.adobe.marketing.mobile:campaign:1.+'
implementation 'com.adobe.marketing.mobile:userprofile:1.+'
implementation 'com.adobe.marketing.mobile:sdk-core:1.+'
```

![모듈 그래들](assets/module-build-gradle.PNG)

* 동기화 [!DNL Android] 프로젝트를 동기화하기 위해 [지금 동기화] 단추 클릭

## 수정 [!DNL AndroidManifest.xml]{#modify-android-manifest}

열기 *AndroidManifest.xml* manifest 요소 뒤와 application 요소 앞에 다음 2줄을 붙여넣습니다. 이렇게 하면 앱이 외부 세계와 통신할 수 있습니다

<!--
Removed `{.line-numbers}` below
-->

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

응용 프로그램 요소에서 다음 줄을 복사합니다.
[!DNL android:name=".MainApp"]
저장 [!DNL AndroidManifest.xml]
사용자 [!DNL AndroidManifest.xml] 다음과 같아야 합니다.

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
