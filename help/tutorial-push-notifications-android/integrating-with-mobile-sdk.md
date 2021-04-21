---
title: 2단계 - Mobile SDK 통합
description: 이 부분에서 Android 앱을 Mobile SDK와 통합합니다. Android 앱과 모바일 SDK 통합
feature: 푸시
kt: 4826
doc-type: tutorial
activity: use
team: TM
exl-id: 0fa53536-8330-4e96-be2f-afc078609bcd
translation-type: tm+mt
source-git-commit: ada0b029245190f53d58fa93c79c161719bfe9fd
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 3%

---

# 2단계 - Android 앱과 [!UICONTROL Mobile SDK] 통합

이 부분에서는 [!DNL Android] 앱을 [!UICONTROL Mobile SDK]과 통합합니다. [!UICONTROL mobile SDK]을(를) [!DNL Android] 앱과 통합하려면 다음 단계를 따르십시오.

* [!DNL Android Studio]에서 *ACSPushTutorial* 프로젝트를 엽니다.
* [!DNL android.app.Application]을(를) 확장하는 *MainApp*&#x200B;이라는 새 java 클래스를 만듭니다.
* 이 시점에서 프로젝트 구조는 다음과 같아야 합니다.

![기본 앱](assets/android-main-app.PNG)

* [!DNL Gradle Scripts] 폴더를 확장합니다. 모듈의 [!DNL build.gradle]을 두 번 클릭합니다. 다음 종속성을 [!DNL build.gradle] 파일의 종속성 섹션에 붙여 넣습니다. 이제 [!DNL build.gradle] 파일이 다음과 같아야 합니다.

<!--
Removed `{.line-numbers}` below
-->

```java
implementation 'com.adobe.marketing.mobile:campaign:1.+'
implementation 'com.adobe.marketing.mobile:userprofile:1.+'
implementation 'com.adobe.marketing.mobile:sdk-core:1.+'
```

![module-grade](assets/module-build-gradle.PNG)

* 지금 동기화 버튼을 클릭하여 [!DNL Android] 프로젝트를 동기화하여 프로젝트를 동기화합니다.

## [!DNL AndroidManifest.xml]{#modify-android-manifest} 수정

*AndroidManifest.xml*&#x200B;을 열고 매니페스트 요소 뒤에 응용 프로그램 요소 앞에 다음 2행을 붙여 넣습니다. 이를 통해 앱이 외부 세계와 통신할 수 있습니다

<!--
Removed `{.line-numbers}` below
-->

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

애플리케이션 요소에 다음 줄 복사
[!DNL android:name=".MainApp"]
[!DNL AndroidManifest.xml] 저장
[!DNL AndroidManifest.xml]은(는) 다음과 같아야 합니다.

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
