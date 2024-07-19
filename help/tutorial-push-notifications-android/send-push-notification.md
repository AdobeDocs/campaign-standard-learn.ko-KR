---
title: 6부 - 푸시 알림 보내기 작업 테스트
description: 6부 - 푸시 알림 보내기 작업 테스트
feature: Push
jira: KT-4830
user: Admin
level: Experienced
doc-type: tutorial
activity: use
team: TM
exl-id: 10218e1f-6e85-490a-84d9-c5d42bd2321d
source-git-commit: f4712dcf6dec01867414057346f8501c6e1669ec
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 2%

---

# 6부 - [!UICONTROL Push Notification]을(를) 보내 작업 테스트

이제 Adobe Campaign을 사용하여 [!UICONTROL Push Notification]을(를) 만들고 보내야 합니다. 테스트 목적으로 간단한 푸시 알림을 만들려면 다음 단계를 따르십시오.

* Adobe Campaign Standard 인스턴스에 로그인합니다
* **[!UICONTROL Marketing Activities]->[!UICONTROL Create]->[!UICONTROL Push Notification]** 클릭
* **[!UICONTROL Send push to app subscribers(mobileApp)]**&#x200B;을(를) 선택하고 [다음]을 클릭하십시오.
* **[!UICONTROL Associate a Mobile App to a delivery]** 드롭다운 목록에서 적절한 모바일 앱을 선택하고 **[!UICONTROL Next]**&#x200B;을(를) 클릭합니다
* 카운트 레이블을 클릭하면 0보다 큰 값이 반환됩니다. **[!UICONTROL Next]** 클릭
* 의미 있는 [!UICONTROL Message title] 및 [!UICONTROL Message body]을(를) 입력하고 **[!UICONTROL Create]**&#x200B;을(를) 클릭합니다.
* **[!UICONTROL Prepare]**&#x200B;을(를) 클릭합니다. 준비가 완료되면 **[!UICONTROL Confirm]**&#x200B;을(를) 클릭하여 메시지를 보냅니다.

모든 것이 잘 작동하면 에뮬레이터에서 실행 중인 Android™ 앱에 알림이 표시됩니다

## 추가 리소스

* [푸시 알림에 대한 자세한 설명서](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/push-notifications/about-push-notifications.html?lang=en)
* [푸시 알림 만들기(비디오)](/help/communication-channels/mobile/push-notifications/creating-a-push-notification.md)
