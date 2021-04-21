---
title: 4단계 - 푸시 식별자 설정
description: '**pushIdentifier**는 푸시 알림에 대한 장치 토큰이 포함된 문자열입니다. Firebase에서 전송되고 MobileCore.setPushIdentifier 메서드를 사용하여 SDK로 전달되는 토큰과 동일합니다.'
feature: 푸시
topic: 모바일
kt: 4828
doc-type: tutorial
activity: use
team: TM
exl-id: 08387b84-edaa-45ee-ae66-53bcbd5c7c39
translation-type: tm+mt
source-git-commit: ddbb0843ea45a83d9ab5bfa0877287f6ba7d6210
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---

# 4단계 - [!DNL pushidentifier] 설정

**[!DNL pushidentifier]**&#x200B;은 [!DNL Push] 알림에 대한 장치 토큰이 포함된 문자열입니다. 이 토큰은 [!DNL Firebase]에 의해 전송되고 [!DNL MobileCore.setPushIdentifier] 메서드를 사용하여 SDK에 전달되는 토큰과 동일합니다.

[!DNL Android ]studio에서 프로젝트를 엽니다. 패키지 문&#x200B;**의 첫 번째 행을 제외한 [!DNL MainActivity]**&#x200B;의 전체 코드를 삭제합니다.

다음 코드를 [!DNL MainActivity]에 붙여 넣습니다.

<!--
Removed `{.line-numbers}` below
-->

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

이제 앱을 테스트한 후 더 이상 진행하십시오.

* 녹색 화살표를 클릭하여 앱을 실행하거나 **[!DNL Run->Run'app']**&#x200B;을 선택합니다.
* [!DNL Android] 에뮬레이터는 시작해야 하며 [!DNL "Hello World" ] 텍스트로 실행 중인 앱이 표시됩니다.
* [!DNL logcat] 창을 엽니다. &quot;[!DNL Got]&quot;을 검색합니다. 아래 표시된 것처럼 [!DNL Firebase]에서 받은 토큰이 로그에 기록되어 있어야 합니다. &quot;[!DNL Got token]&quot; 뒤에 오는 긴 문자열은 Adobe Campaign으로 전송되는 [!DNL pushidentifier ]입니다.

![logcat token](assets/logcat-got-token.PNG)

### 모바일 애플리케이션 구독자 확인

Adobe Campaign Standard 인스턴스에 로그인합니다.
**[!UICONTROL Administration->Channels->Mobile App(AEP SDK)]**&#x200B;으로 이동합니다. 해당 모바일 애플리케이션을 엽니다. [!UICONTROL Mobile Application Subscribers] 탭으로 이동합니다. [!UICONTROL registration token ]이(가) 나열되어야 합니다.

![모바일 애플리케이션 구독자](assets/mobile-application-subscribers.PNG)

>[!NOTE]
>
>더 이상 진행하기 전에 [!UICONTROL Mobile Application Subscribers] 탭 STOP에 등록 토큰이 표시되지 않는 경우 여기를 클릭하십시오.
