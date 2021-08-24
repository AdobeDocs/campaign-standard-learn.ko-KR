---
title: 4단계 - pushidentifier 설정
description: '**pushIdentifier**는 푸시 알림에 대한 장치 토큰이 포함된 문자열입니다. Firebase에서 전송되고 MobileCore.setPushIdentifier 메서드를 사용하여 SDK에 전달되는 것과 동일한 토큰입니다.'
feature: 푸시
kt: 4828
doc-type: tutorial
activity: use
team: TM
exl-id: 08387b84-edaa-45ee-ae66-53bcbd5c7c39
source-git-commit: 5a2f8c9a78bf5100b272f9b4461131545b3aeb8b
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---

# 4단계 - [!DNL pushidentifier] 설정

**[!DNL pushidentifier]**&#x200B;은 [!DNL Push] 알림에 대한 장치 토큰을 포함하는 문자열입니다. 이 토큰은 [!DNL Firebase]에서 전송되고 [!DNL MobileCore.setPushIdentifier] 메서드를 사용하여 SDK에 전달되는 것과 동일한 토큰입니다.

[!DNL Android™ ]Studio에서 프로젝트를 엽니다. [!DNL MainActivity] **에서 패키지 문**&#x200B;인 첫 번째 행을 제외한 전체 코드를 삭제합니다.

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

이제 앱을 테스트한 후에 다시 시도하세요.

* 녹색 화살표를 클릭하여 앱을 실행하거나 **[!DNL Run->Run'app']** 을 선택합니다.
* [!DNL Android™] 에뮬레이터를 시작해야 하며 [!DNL "Hello World" ] 텍스트로 앱을 실행하는 것이 보여야 합니다.
* [!DNL logcat] 창을 엽니다. &quot;[!DNL Got]&quot;을 검색합니다. 아래와 같이 로그에 [!DNL Firebase]에서 받은 토큰이 표시됩니다. &quot;[!DNL Got token]&quot; 뒤에 오는 긴 문자열은 Adobe Campaign에 전송되는 [!DNL pushidentifier ]입니다.

![logcat 토큰](assets/logcat-got-token.PNG)

### 모바일 애플리케이션 구독자 확인

Adobe Campaign Standard 인스턴스에 로그인합니다.
**[!UICONTROL Administration->Channels->Mobile App(Experience Platform SDK)]**&#x200B;으로 이동합니다. 적절한 모바일 애플리케이션을 엽니다. [!UICONTROL Mobile Application Subscribers] 탭으로 이동합니다. [!UICONTROL registration token ]이 나열되어 있어야 합니다.

![mobile-application-subscribers](assets/mobile-application-subscribers.PNG)

>[!NOTE]
>
>계속 진행하기 전에 [!UICONTROL Mobile Application Subscribers] 탭에 등록 토큰이 표시되지 않으면 여기에서 중지합니다.
