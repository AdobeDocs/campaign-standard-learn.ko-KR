---
title: 컨트롤 패널 촬영 문제
description: 제어판에서는 SFTP 저장소를 인스턴스와 허용 목록 IP 주소별로 모니터링하고 관리할 수 있습니다.
feature: Control Panel
topics: null
kt: 2938
doc-type: article
activity: use
team: PM
translation-type: tm+mt
source-git-commit: cb5d5bc58137fd374eafe165c6ea13288a60d7db
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---


# [!UICONTROL Control Panel}을(를) 촬영하는 동안 문제가 발생했습니다.

제어판 사용 시 문제를 해결하는 방법을 알아봅니다.

## 로그인 및 홈 페이지

로그인 및 홈 페이지에서 발생하는 문제

### 증상: Adobe Experience Cloud에 로그인할 수 없습니다.

**방법:**
사용자가 [!DNL IMS Org ID] (xxx)을 찾아야 합니다. 관리자는 관리할 각 인스턴스에 [!UICONTROL product profile] 사용자를 추가해야 [!DNL “Campaign-xxx-Admins”] 합니다. 사용자가 모든 인스턴스의 관리자인 경우에도 사용자를 다른 이름으로 추가해야 할 수 있습니다 *[!UICONTROL user]*.

### 증상: 액세스할 수 [!UICONTROL Adobe Experience Cloud Home] 있는 링크 [!UICONTROL Control Panel] 는 사용자에게 표시되지 않습니다.

**원인:**
사용자는 [!UICONTROL product profile] `Campaign-xxx-Administrators/Admin`

**방법:**
관리자는 관리할 각 인스턴스에 [!UICONTROL product profile] 사용자를 추가해야 *[!DNL Campaign-xxx-Admins]* 합니다. 사용자가 모든 인스턴스의 관리자인 경우에도 사용자를 다른 이름으로 추가해야 할 수 있습니다 *[!UICONTROL user]*.

### 증상: 인스턴스가 [!UICONTROL Control Panel]

**원인:**
누락된 인스턴스에 대해 *[!UICONTROL user]* 제품 프로필 `!DNL Campaign-xxx-Administrators/Admin` 으로 사용자가 추가되어야 합니다.

**방법:**
관리자는 관리할 각 인스턴스에 대해 사용자 `Campaign-xxx-Admins` 를 제품 프로필에 추가해야 합니다. 사용자가 모든 인스턴스의 관리자인 경우에도 사용자를 다른 이름으로 추가해야 할 수 있습니다 *[!UICONTROL user]*.

### 유용한 비디오

>[!VIDEO](https://video.tv.adobe.com/v/27183?quality=12)
*확인[!DNL IMS Org ID](00:26분)*

>[!VIDEO](https://video.tv.adobe.com/v/27147?quality=12)
*관리자를 사용할 수 있도록[!UICONTROL product profile]관리자에게 추가하는 방법(*[!DNL administrators]*1분[!UICONTROL Control Panel]3초)*

### 유용한 설명서

* [[!UICONTROL 제어판]](https://helpx.adobe.com/campaign/kb/control-panel-overview.html)
* [[!UICONTROL 제어판]에 대한 권한 관리](https://helpx.adobe.com/campaign/kb/control-panel-access.html)

## SFTP 서버에 연결 설정(클라이언트 또는 API)

SFTP 서버에 연결하려면 다음이 필요합니다.

* [!UICONTROL Whitelisting] SFTP 서버에 연결하는 IP 주소
* Adobe Campaign에 등록해야 하는 개인/공개 키 쌍
* SFTP 서버에 직접 연결하는 경우 SFTP 클라이언트 소프트웨어도 필요합니다

### 유용한 설명서

* [SFTP 서버에 로그인](https://helpx.adobe.com/campaign/kb/control-panel-sftp.html#LoggingintoyourSFTPserver)

