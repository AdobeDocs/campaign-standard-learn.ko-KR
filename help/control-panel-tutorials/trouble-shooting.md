---
title: Campaign 컨트롤 패널의 문제 해결
description: Campaign 컨트롤 패널을 사용하면 인스턴스 및 IP 주소별로 SFTP 저장소를 모니터링하고 관리할 허용 목록에 추가하다 수 있습니다.
feature: Control Panel
kt: 2938
doc-type: article
activity: use
team: PM
exl-id: f546f791-a69b-4586-abfa-3e626b8feb17
source-git-commit: 481cbdcc9ac7446cc36fbff6e3d6e43fe333d30b
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 47%

---

# [!UICONTROL Control Panel] 문제 해결

Campaign 컨트롤 패널 사용 시 문제를 해결하는 방법을 배웁니다.

## 로그인 및 홈페이지

로그인 및 홈페이지에서 발생하는 문제

### 증상: Adobe Experience Cloud에 로그인할 수 없습니다.

**방법:**
사용자가 해당 [!DNL IMS Org ID] (xxx) 관리자는 사용자를 [!UICONTROL product profile] [!DNL “Campaign-xxx-Admins”] 관리할 각 인스턴스에 대해 을 설정합니다. 사용자가 모든 인스턴스의 관리자인 경우 자신을 *[!UICONTROL user]*.

### 증상: [!UICONTROL Adobe Experience Cloud Home] (으)로 액세스하는 [!UICONTROL Control Panel] 에 있는 링크가 사용자에게 표시되지 않음

**원인:**
사용자는 [!UICONTROL product profile] `Campaign-xxx-Administrators/Admin`의 사용자로 추가되기 전에는 링크를 볼 수 없음

**방법:**
관리자는 사용자를 [!UICONTROL product profile] *[!DNL Campaign-xxx-Admins]* 관리할 각 인스턴스에 대해 을 설정합니다. 사용자가 모든 인스턴스의 관리자인 경우 자신을 *[!UICONTROL user]*.

### 증상: 인스턴스가 [!UICONTROL Control Panel]에 나열되지 않음

**원인:**
사용자는 *[!UICONTROL user]* 제품 프로필 `Campaign-xxx-Administrators/Admin` 누락된 인스턴스에 대해

**방법:**
관리자는 사용자를 제품 프로필에 추가해야 합니다 `Campaign-xxx-Admins` 관리할 각 인스턴스에 대해 을 설정합니다. 사용자가 모든 인스턴스의 관리자인 경우 자신을 *[!UICONTROL user]*.

### 유용한 비디오

>[!VIDEO](https://video.tv.adobe.com/v/27183?quality=12)

*확인 [!DNL IMS Org ID] (00:26)*

>[!VIDEO](https://video.tv.adobe.com/v/27147?quality=12)

*관리자를 사용할 수 있도록 [!UICONTROL product profile] [!DNL administrators]에 추가하는 방법[!UICONTROL Control Panel] (01:03분)*

### 유용한 설명서

* [[!UICONTROL Control Panel]를 검색](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ko)
* [[!UICONTROL Control Panel]에 대한 권한 관리](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=en)

## SFTP 서버에 연결 설정(클라이언트 또는 API)

SFTP 서버에 연결하려면 다음이 필요합니다.

* [!UICONTROL allow listing] SFTP 서버에 연결할 IP 주소
* Adobe Campaign에 등록해야 하는 개인/공개 키 쌍
* SFTP 서버에 직접 연결하는 경우 SFTP 클라이언트 소프트웨어가 필요합니다

### 유용한 설명서 {#helpful-docs}

* [SFTP 서버에 로그인](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=en)
