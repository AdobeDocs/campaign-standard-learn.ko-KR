---
title: 3단계 - 모바일 앱에 확장 등록
description: 이 부분에서는 UserProfile,Identity,Lifecycle 및 Signal 확장을 등록하는 코드를 추가합니다.
feature: Push
kt: 4827
doc-type: tutorial
activity: use
team: TM
exl-id: d8c0d8c6-2e04-4c27-b27a-d0de79dd953b
source-git-commit: ada0b029245190f53d58fa93c79c161719bfe9fd
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 11%

---

# 3단계 - 모바일 앱에 확장 등록

이 부분에서는 사용자 프로필, ID, 라이프사이클 및 신호 확장을 등록하는 코드를 추가합니다. 이러한 확장은 [[!UICONTROL Mobile Core Extensions]](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core). 또한 아래 코드에 표시된 대로 Adobe Campaign Standard 확장을 등록해야 합니다.

에서 프로젝트를 엽니다. [!DNL Android] 스튜디오. 기본 앱에서 전체 코드 삭제 **패키지 명령문인 첫 번째 줄 제외**.

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

32호선을 통해[!UICONTROL  Launch] 속성의 환경 파일 ID입니다. 다음 위치에서 액세스할 수 있습니다 [!UICONTROL environment tab] 당신의 [!UICONTROL Launch] 속성을 사용합니다.

![launch-id](assets/launch-id-property.PNG)
