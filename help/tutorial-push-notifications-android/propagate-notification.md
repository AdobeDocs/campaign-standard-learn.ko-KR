---
title: 5단계 - 알림 전파
description: 이 부분에서는 Android Notification Manager.Firebase를 사용하여 Adobe Campaign에서 받은 메시지를 전파합니다
feature: Push
jira: KT-4829
user: Admin
level: Experienced
doc-type: tutorial
activity: use
team: TM
exl-id: b0e01224-4ddc-4999-b8c6-794e49245428
source-git-commit: 200dcb4d6698c174f7fde508779609b11043d031
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 2%

---

# 알림을 전송할 서비스 추가

이 부분에서는 [!DNL Android Notification Manager]을(를) 사용하여 Adobe Campaign에서 받은 메시지를 전파합니다. [!DNL Notification manager]은(는) 발생하는 이벤트를 사용자에게 알리는 데 사용됩니다.
다음은 백그라운드에서 어떤 일이 발생했음을 사용자에게 알리는 방법입니다.

* [!DNL Android Studio] 시작
* *[!DNL ACSPushTutorial]* 프로젝트 열기
* 프로젝트 구조 확장
* 패키지 폴더([!DNL com.example.acspushtutorial])를 마우스 오른쪽 단추로 클릭하고 [!DNL New ->Java Class]
* 이 클래스의 이름을 *[!DNL MyService]*&#x200B;로 지정하고 [!DNL FirebaseMessagingService]을(를) 확장하는지 확인하십시오.
* 이 클래스에서 *[!DNL sendNotification]* 메서드를 만듭니다. 이 메서드에서는 [!DNL NotificationCompat.Builder] 개체를 사용하여 알림의 내용과 채널을 설정해야 합니다. 알림이 표시되도록 하려면 [!DNL NotificationManagerCompat.notify()]을(를) 호출하여 알림에 대한 고유 ID와 [!DNL NotificationCompat.Builder.build()]의 결과를 전달합니다.

<!--
Removed `{.line-numbers}` below
-->

```java
package com.example.pushmessaging;
import android.app.NotificationChannel;
import android.app.NotificationManager;
import android.app.PendingIntent;
import android.content.Context;
import android.content.Intent;
import android.media.RingtoneManager;
import android.net.Uri;
import android.os.Build;
import android.util.Log;

import androidx.core.app.NotificationCompat;

import com.google.firebase.messaging.FirebaseMessagingService;
import com.google.firebase.messaging.RemoteMessage;

import java.util.Map;

public class MyService extends FirebaseMessagingService {
@Override
public void onMessageReceived(RemoteMessage remoteMessage)
{
Map<String,String> data  = remoteMessage.getData();
Log.d("data payload: ", data.toString());
sendNotification(remoteMessage);
}


private void sendNotification(RemoteMessage message) {
Intent intent = new Intent(this, MainActivity.class);
intent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
PendingIntent pendingIntent = PendingIntent.getActivity(this, 0 /* Request code */, intent, PendingIntent.FLAG_ONE_SHOT);

String channelId = "0";
Uri defaultSoundUri = RingtoneManager.getDefaultUri(RingtoneManager.TYPE_NOTIFICATION);
NotificationCompat.Builder notificationBuilder =
        new NotificationCompat.Builder(this, channelId)
                .setSmallIcon(R.drawable.ic_launcher_background)
                .setContentTitle("Message from AEM")
                .setContentText(message.getData().get("body"))
                .setAutoCancel(true)
                .setSound(defaultSoundUri)
                .setContentIntent(pendingIntent);

NotificationManager notificationManager =
        (NotificationManager) getSystemService(Context.NOTIFICATION_SERVICE);

// Since android Oreo notification channel is needed.
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
    NotificationChannel channel = new NotificationChannel(channelId,
            "Channel human readable title",
            NotificationManager.IMPORTANCE_DEFAULT);
    notificationManager.createNotificationChannel(channel);
}

notificationManager.notify(0 /* ID of notification */, notificationBuilder.build());
}
}
```

## [!DNL AndroidManifest.xml] 수정

만든 서비스를 [!DNL AndroidManifest.xml]에 추가합니다. 최종 [!DNL AndroidManifest.xml]은(는) 다음과 같아야 합니다.

<!--
Removed `{.line-numbers}` below
-->

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.pushmessaging">

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
        <service
            android:name=".MyService"
            android:exported="false">
            <intent-filter>
                <action android:name="com.google.firebase.MESSAGING_EVENT" />
            </intent-filter>
        </service>

        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

## 앱 실행

도구 모음 또는 [!DNL Run] 메뉴에서 **녹색 화살표**&#x200B;를 클릭하여 앱을 실행하십시오.
