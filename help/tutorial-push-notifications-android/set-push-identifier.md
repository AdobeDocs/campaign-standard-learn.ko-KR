---
title: 4단계 - 푸시식별자 설정
description: '**pushIdentifier**는 푸시 알림의 장치 토큰을 포함하는 문자열입니다. Firebase가 전송한 것과 동일한 토큰이며 MobileCore.setPushIdentifier 메서드를 사용하여 SDK로 전달됩니다.'
feature: Push
topics: MOBILE
kt: 4828
doc-type: tutorial
activity: use
team: TM
translation-type: tm+mt
source-git-commit: c3ff1a137fb8ee9506a11f82e1a27d010bbd97e6
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# 4단계 - 설정 [!DNL pushidentifier]

이 **[!DNL pushidentifier]** 는 알림용 장치 토큰을 포함하는 [!DNL Push] 문자열입니다. 이 토큰은 보낸 토큰과 동일하며 이 방법 [!DNL Firebase] 을 사용하여 SDK로 [!DNL MobileCore.setPushIdentifier] 전달됩니다.

프로젝트에서 [!DNL Android ]스튜디오 열기 패키지 명령문의 첫 번째 줄을 [!DNL MainActivity] 제외한 전체 코드를 삭제합니다 ****.

다음 코드를 붙여넣습니다 [!DNL MainActivity].

```java
import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.util.Log;
import android.widget.Toast;

import com.adobe.marketing.mobile.MobileCore;
import com.google.android.gms.tasks.OnCompleteListener;
import com.google.android.gms.tasks.Task;
import com.google.firebase.iid.FirebaseInstanceId;
import com.google.firebase.iid.InstanceIdResult;

public class MainActivity extends AppCompatActivity {

@Override
protected void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_main);

registerToken();
}

void registerToken() {
FirebaseInstanceId.getInstance().getInstanceId()
    .addOnCompleteListener(new OnCompleteListener<InstanceIdResult>() {
        @Override
        public void onComplete(@NonNull Task<InstanceIdResult> task) {
            if (!task.isSuccessful()) {
                Log.w("Message App", "getInstanceId failed", task.getException());
                return;
            }

// Get new Instance ID token
String token = task.getResult().getToken();

Log.d("Got token", token);

MobileCore.setPushIdentifier(token);
}
});
}

@Override
public void onResume() {
super.onResume();
MobileCore.setApplication(getApplication());
MobileCore.lifecycleStart(null);
}

@Override
public void onPause() {
super.onPause();
MobileCore.lifecyclePause();
}
}
```

## 앱 테스트

이제 앱을 테스트한 후 더 이상 진행할 수 있습니다.

* 녹색 화살표를 클릭하여 앱을 실행하거나 선택합니다 **[!DNL Run->Run'app']**.
* 에뮬레이터가 [!DNL Android] 시작되어야 하며 [!DNL "Hello World" ]텍스트가 포함된 앱이 실행 중인 것을 볼 수 있습니다.
* 창을 [!DNL logcat] 엽니다. &quot;[!DNL Got]&quot;를 검색합니다. 아래와 같이 로그로 [!DNL Firebase] 보낸 토큰을 확인해야 합니다. &quot;[!DNL Got token]&quot; 다음에 오는 긴 문자열은 Adobe Campaign [!DNL pushidentifier ]로 전송되는 문자열입니다.

![logcat token](assets/logcat-got-token.PNG)

### 모바일 애플리케이션 구독자 확인

Adobe Campaign Standard 인스턴스에 로그인합니다.
탐색 **[!UICONTROL Administration->Channels->Mobile App(AEP SDK)]**. 해당 모바일 애플리케이션을 엽니다. Tab to the [!UICONTROL Mobile Application Subscribers] tab. 목록에 [!UICONTROL registration token ]표시됩니다.

![모바일 애플리케이션 구독자](assets/mobile-application-subscribers.PNG)

>[참고]
>더 이상 진행하기 전에 여기 STOP [!UICONTROL Mobile Application Subscribers] 탭에 등록 토큰이 표시되지 않는 경우
