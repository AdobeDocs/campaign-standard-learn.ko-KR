---
title: 4단계 - pushidentifier 설정
description: '**pushIdentifier**는 푸시 알림에 대한 장치 토큰이 포함된 문자열입니다. Firebase에서 전송되고 MobileCore.setPushIdentifier 메서드를 사용하여 SDK에 전달되는 것과 동일한 토큰입니다.'
feature: Push
kt: 4828
doc-type: tutorial
activity: use
team: TM
exl-id: 08387b84-edaa-45ee-ae66-53bcbd5c7c39
source-git-commit: 5a2f8c9a78bf5100b272f9b4461131545b3aeb8b
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# 4단계 - 설정 [!DNL pushidentifier]

다음 **[!DNL pushidentifier]** 는 [!DNL Push] 알림. 에 의해 전송된 것과 동일한 토큰 [!DNL Firebase] 를 사용하여 SDK에 전달됩니다. [!DNL MobileCore.setPushIdentifier] 메서드를 사용합니다.

에서 프로젝트를 엽니다. [!DNL Android™ ]스튜디오. 에서 전체 코드를 삭제합니다. [!DNL MainActivity] **패키지 명령문인 첫 번째 줄 제외**.

다음 코드를 [!DNL MainActivity]:

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

이제 앱을 테스트한 후에 다시 시도하세요.

* 녹색 화살표를 클릭하여 앱을 실행하거나 을 선택합니다 **[!DNL Run->Run'app']**.
* 다음 [!DNL Android™] 에뮬레이터를 시작해야 하며 앱이 [!DNL "Hello World" ]텍스트.
* 를 엽니다. [!DNL logcat] 창을 엽니다. &quot; 검색[!DNL Got]&quot;. 에서 받은 토큰이 표시됩니다 [!DNL Firebase] 아래와 같이 로그에 기록됩니다. &quot; 다음에 오는 긴 문자열[!DNL Got token]&quot; [!DNL pushidentifier ]Adobe Campaign으로 전송됩니다.

![logcat 토큰](assets/logcat-got-token.PNG)

### 모바일 애플리케이션 구독자 확인

Adobe Campaign Standard 인스턴스에 로그인합니다.
탐색 **[!UICONTROL Administration->Channels->Mobile App(Experience Platform SDK)]**. 적절한 모바일 애플리케이션을 엽니다. Tab 키를 눌러 [!UICONTROL Mobile Application Subscribers] 탭. 다음 항목이 표시됩니다. [!UICONTROL registration token ]나열됨.

![mobile-application-subscribers](assets/mobile-application-subscribers.PNG)

>[!NOTE]
>
>에 등록 토큰이 표시되지 않으면 [!UICONTROL Mobile Application Subscribers] 탭 계속 진행하기 전에 여기서 중지합니다.
