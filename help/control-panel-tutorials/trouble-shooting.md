---
title: Campaign 컨트롤 패널의 문제 해결
description: Campaign 컨트롤 패널을 사용하면 인스턴스 및 허용 목록 IP 주소별로 SFTP 저장소를 모니터링하고 관리할 수 있습니다.
feature: Control Panel
topics: null
kt: 2938
doc-type: article
activity: use
team: PM
translation-type: tm+mt
source-git-commit: 747aa1610f29a9a9409091169c7b398523dd1f77
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 100%

---


# [!UICONTROL Control Panel] 문제 해결

Campaign 컨트롤 패널 사용 시 문제를 해결하는 방법을 배웁니다.

## 로그인 및 홈페이지

로그인 및 홈페이지에서 발생하는 문제

### 증상: Adobe Experience Cloud에 로그인 불가

**방법:**
사용자가 [!DNL IMS Org ID] (xxx)를 찾아야 합니다. 관리자는 관리할 각 인스턴스에 대해 사용자를 [!UICONTROL product profile] [!DNL “Campaign-xxx-Admins”]에 추가해야 합니다. 사용자가 모든 인스턴스의 관리자인 경우에도 사용자를 *[!UICONTROL user]*(으)로 추가해야 할 수 있습니다.

### 증상: [!UICONTROL Adobe Experience Cloud Home] (으)로 액세스하는 [!UICONTROL Control Panel] 에 있는 링크가 사용자에게 표시되지 않음

**원인:**
사용자는 [!UICONTROL product profile] `Campaign-xxx-Administrators/Admin`의 사용자로 추가되기 전에는 링크를 볼 수 없음

**방법:**
관리자는 관리할 각 인스턴스에 대해 사용자를 [!UICONTROL product profile] *[!DNL Campaign-xxx-Admins]*&#x200B;에 추가해야 합니다. 사용자가 모든 인스턴스의 관리자인 경우에도 사용자를 *[!UICONTROL user]*(으)로 추가해야 할 수 있습니다.

### 증상: 인스턴스가 [!UICONTROL Control Panel]에 나열되지 않음

**원인:**
누락된 인스턴스에 대해 *[!UICONTROL user]* 제품 프로필 `Campaign-xxx-Administrators/Admin`으로 사용자가 추가되어야 할 가능성이 높음

**방법:**
관리자는 관리할 각 인스턴스에 대해 사용자를 제품 프로필 `Campaign-xxx-Admins`에 추가해야 합니다. 사용자가 모든 인스턴스의 관리자인 경우에도 사용자를 *[!UICONTROL user]*(으)로 추가해야 할 수 있습니다.

### 유용한 비디오

>[!VIDEO](https://video.tv.adobe.com/v/27183?quality=12)

*확인 [!DNL IMS Org ID] (00:26)*

>[!VIDEO](https://video.tv.adobe.com/v/27147?quality=12)

*관리자를 사용할 수 있도록 [!UICONTROL product profile] [!DNL administrators]에 추가하는 방법[!UICONTROL Control Panel] (01:03분)*

### 유용한 설명서

* [[!UICONTROL Control Panel]를 검색](https://helpx.adobe.com/kr/campaign/kb/control-panel-overview.html)
* [[!UICONTROL Control Panel]에 대한 권한 관리](https://helpx.adobe.com/kr/campaign/kb/control-panel-access.html)

## SFTP 서버에 연결 설정(클라이언트 또는 API)

SFTP 서버에 연결하려면 다음이 필요합니다.

* [!UICONTROL allow listing] SFTP 서버에 연결할 IP 주소
* Adobe Campaign에 등록해야 하는 개인/공개 키 쌍
* SFTP 서버에 직접 연결하는 경우 SFTP 클라이언트 소프트웨어도 필요합니다

### 유용한 설명서

* [SFTP 서버에 로그인](https://docs.adobe.com/content/help/ko-KR/control-panel/using/control-panel-home.html#LoggingintoyourSFTPserver)

