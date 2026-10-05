---
title: 3단계 - 모바일 앱에 확장 등록
description: 이 부분에서는 UserProfile, Identity, Lifecycle 및 Signal 확장을 등록하기 위한 코드를 추가합니다.
feature: Push
user: Admin
level: Experienced
jira: KT-4827
doc-type: tutorial
activity: use
team: TM
exl-id: d8c0d8c6-2e04-4c27-b27a-d0de79dd953b
TQID: 'https://experienceleague.adobe.com/WjKV0qe9zi7cV37Wn54BJdI91n92i302t4k-yMIenZ4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: a4657621-810c-498b-8a27-7ced9c176dda
    internal-label: Push notifications
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 508c3590ce956401ccfba3a256000cbc5849a684
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 14%
---
# 3단계 - 모바일 앱에 확장 등록

이 부분에서는 사용자 프로필, ID, 라이프사이클 및 신호 확장을 등록하기 위한 코드를 추가합니다. 또한 아래 코드에 표시된 대로 Adobe Campaign Standard 확장을 등록해야 합니다.

[!DNL Android] 스튜디오에서 프로젝트를 엽니다. MainApp **에서 패키지 문인 첫 번째 줄을 제외한 전체 코드를 삭제합니다**.

다음 코드를 MainApp에 붙여넣기

<!--
Removed `{.line-numbers}` below
-->

```java
import [!DNL android].app.Application;
import android.util.Log;

import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.Campaign;
import com.adobe.marketing.mobile.Identity;
import com.adobe.marketing.mobile.InvalidInitException;
import com.adobe.marketing.mobile.Lifecycle;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;
import com.adobe.marketing.mobile.Signal;
import com.adobe.marketing.mobile.UserProfile;

public class MainApp extends Application {

@Override
public void onCreate() {
super.onCreate();

MobileCore.setApplication(this);
MobileCore.setLogLevel(LoggingMode.DEBUG);

try{
    Campaign.registerExtension();
    UserProfile.registerExtension();
    Identity.registerExtension();
    Lifecycle.registerExtension();
    Signal.registerExtension();
    MobileCore.start(new AdobeCallback () {
        @Override
        public void call(Object o) {
            MobileCore.configureWithAppID("copy your launch property id here");
        }
    });
} catch (InvalidInitException e) {
    Log.d("ACS Exception", "exception");
}
}
}
```

32행 [!UICONTROL  Launch] 속성의 환경 파일 ID를 제공해야 합니다. [!UICONTROL Launch] 속성의 [!UICONTROL environment tab]에서 액세스할 수 있습니다.

![launch-id](assets/launch-id-property.PNG)
