---
title: 4단계 - pushidentifier 설정
description: '**pushIdentifier**는 푸시 알림용 장치 토큰을 포함하는 문자열입니다. Firebase에서 전송하고 MobileCore.setPushIdentifier 메서드를 사용하여 SDK에 전달되는 토큰과 동일합니다.'
feature: Push
user: Admin
level: Experienced
jira: KT-4828
doc-type: tutorial
activity: use
team: TM
exl-id: 08387b84-edaa-45ee-ae66-53bcbd5c7c39
source-git-commit: 757afce50981b96b7820c987308d639a73746c0c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# 4단계 - 설정 [!DNL pushidentifier]

다음 **[!DNL pushidentifier]** 는 의 장치 토큰을 포함하는 문자열입니다. [!DNL Push] 알림입니다. 에 의해 전송된 것과 동일한 토큰입니다 [!DNL Firebase] 를 사용하여 SDK에 전달됩니다. [!DNL MobileCore.setPushIdentifier] 메서드를 사용합니다.

에서 프로젝트를 엽니다. [!DNL Android™]스튜디오. 에서 전체 코드 삭제 [!DNL MainActivity] **패키지 문인 첫 번째 줄을 제외하고**.

다음 코드를에 붙여 넣습니다. [!DNL MainActivity]:

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

이제 더 진행하기 전에 앱을 테스트해 보십시오.

* 녹색 화살표를 클릭하거나 을 선택하여 앱을 실행합니다. **[!DNL Run->Run'app']**.
* 다음 [!DNL Android™] 에뮬레이터가 시작되고 앱의 실행 상태가 표시되어야 합니다. [!DNL "Hello World"]텍스트를 입력하십시오.
* 를 엽니다. [!DNL logcat] 창. 검색 대상[!DNL Got]&quot;. 다음에서 받은 토큰이 표시됩니다. [!DNL Firebase] 아래와 같이 로그에 기록됩니다. 뒤에 오는 긴 문자열[!DNL Got token]&quot;은(는) [!DNL pushidentifier]Adobe Campaign으로 전송됩니다.

![logcat-토큰](assets/logcat-got-token.PNG)

### 모바일 애플리케이션 구독자 확인

Adobe Campaign Standard 인스턴스에 로그인.
탐색 **[!UICONTROL Administration->Channels->Mobile App(Experience Platform SDK)]**. 적절한 모바일 애플리케이션을 엽니다. 탭 [!UICONTROL Mobile Application Subscribers] 탭. 다음이 표시됩니다. [!UICONTROL registration token]나열됨.

![mobile-application-subscribers](assets/mobile-application-subscribers.PNG)

>[!NOTE]
>
>에 등록 토큰이 표시되지 않는 경우 [!UICONTROL Mobile Application Subscribers] 더 진행하기 전에 여기서 STOP 을 탭하십시오.
