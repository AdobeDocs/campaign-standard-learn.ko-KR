---
title: 3단계 - 모바일 앱에 익스텐션 등록
description: 이 부분에서는 UserProfile, Identity, Lifecycle 및 Signal 확장을 등록하는 코드를 추가합니다.
feature: Push
topics: Mobile
kt: 4827
doc-type: tutorial
activity: use
team: TM
translation-type: tm+mt
source-git-commit: c3ff1a137fb8ee9506a11f82e1a27d010bbd97e6
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 0%

---


# 3단계 - 모바일 앱에 익스텐션 등록

이 부분에서는 사용자 프로필, ID, 라이프사이클 및 신호 확장을 등록할 코드를 추가합니다. 이러한 익스텐션은 일부입니다 [[!UICONTROL Mobile Core Extensions]](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core). 또한 아래 코드와 같이 Adobe Campaign Standard 익스텐션을 등록해야 합니다.

스튜디오에서 프로젝트를 [!DNL Android] 엽니다. 패키지 명령문의 첫 번째 줄을 **제외한 MainApp의 전체 코드를 삭제합니다**.

MainApp에 다음 코드 붙여넣기

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

32행에서 속성의[!UICONTROL  Launch] 환경 파일 ID를 제공해야 합니다. 속성 [!UICONTROL environment tab] 에서 액세스할 수 [!UICONTROL Launch] 있습니다.

![launch-id](assets/launch-id-property.PNG)
