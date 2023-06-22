---
title: 3단계 - 모바일 앱에 확장 등록
description: 이 부분에서는 UserProfile, Identity, Lifecycle 및 Signal 확장을 등록하기 위한 코드를 추가합니다.
feature: Push
jira: KT-4827
doc-type: tutorial
activity: use
team: TM
exl-id: d8c0d8c6-2e04-4c27-b27a-d0de79dd953b
source-git-commit: c84867ef59a10448a377a959d0b67ae71343a4aa
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 13%

---

# 3단계 - 모바일 앱에 확장 등록

이 부분에서는 사용자 프로필, ID, 라이프사이클 및 신호 확장을 등록하기 위한 코드를 추가합니다. 또한 아래 코드에 표시된 대로 Adobe Campaign Standard 확장을 등록해야 합니다.

에서 프로젝트를 엽니다. [!DNL Android] 스튜디오. MainApp에서 전체 코드 삭제 **패키지 문인 첫 번째 줄을 제외하고**.

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

32행 다음을 입력해야 합니다.[!UICONTROL  Launch] 속성의 환경 파일 ID. 다음에서 액세스할 수 있습니다. [!UICONTROL environment tab] / [!UICONTROL Launch] 속성.

![launch-id](assets/launch-id-property.PNG)
