---
title: 5단계 - 알림 전파
description: 이 부분에서는 Android Notification Manager.Firebase를 사용하여 Adobe Campaign에서 받은 메시지를 전파합니다
feature: Push
kt: 4829
doc-type: tutorial
activity: use
team: TM
exl-id: b0e01224-4ddc-4999-b8c6-794e49245428
source-git-commit: ada0b029245190f53d58fa93c79c161719bfe9fd
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 1%

---

# 알림을 전송할 서비스 추가

이 부분에서는 [!DNL Android Notification Manager]. [!DNL Notification manager] 가 발생한 이벤트를 사용자에게 알리는 데 사용됩니다.
다음은 백그라운드에서 발생한 문제가 있음을 사용자에게 알려주는 방법입니다.

* Launch [!DNL Android Studio]
* 열기 *[!DNL ACSPushTutorial]* 프로젝트
* 프로젝트 구조를 확장합니다.
* 패키지 폴더([!DNL com.example.acspushtutorial]) 및 [!DNL New ->Java Class]
* 이 클래스의 이름을 지정합니다. *[!DNL MyService]* 확장 및 [!DNL FirebaseMessagingService]
* 만들기 *[!DNL sendNotification]* 이 클래스의 메서드입니다. 이 방법에서는 을 사용하여 알림의 콘텐츠와 채널을 설정해야 합니다 [!DNL NotificationCompat.Builder] 개체. 알림을 표시하려면 [!DNL NotificationManagerCompat.notify()], 알림 및 결과에 대한 고유 ID를 전달합니다 [!DNL NotificationCompat.Builder.build()].

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

## 수정 [!DNL AndroidManifest.xml]

생성된 서비스를 [!DNL AndroidManifest.xml]. 마지막 [!DNL AndroidManifest.xml] 는 아래와 같습니다.

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

를 클릭하여 앱을 실행합니다. **녹색 화살표** 도구 모음 또는 [!DNL Run] 메뉴 아래의 제품에서 사용할 수 있습니다.
