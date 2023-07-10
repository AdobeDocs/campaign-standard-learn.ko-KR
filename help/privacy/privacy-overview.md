---
title: ACS(Adobe Campaign Standard)를 통한 개인 정보 보호 요청 - 개요
description: 튜토리얼에서는 Adobe Campaign Standard 인터페이스를 통해 개인 정보 요청을 만드는 방법을 설명합니다.
feature: Privacy Tools
jira: KT-1480
doc-type: feature video
activity: use
team: TM
recommendations: noDisplay
exl-id: fb766403-694c-4a7b-b3d1-4a418df85891
source-git-commit: b7c0c39339ff89bab2c81a3d9fd31f67b8ee4d71
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 90%

---

# Adobe Campaign Standard 사용자 인터페이스를 통한 개인 정보 보호 요청

Adobe Campaign은 GDPR(일반 데이터 보호 규정) 및 CCPA(California Consumer Privacy Act)와 같은 개인 정보 보호 법률을 준수하여 개인 정보 보호 액세스를 수행하고 PII 데이터의 요청을 삭제하는 3가지 방법을 데이터 컨트롤러에게 제공합니다.

* **개인 정보 보호 핵심 서비스 통합을 통해:** 모든 Experience Cloud 솔루션 [!UICONTROL Privacy Service]으로 푸시된 개인 정보 보호 요청은 전용 워크플로우를 통해 Campaign에서 자동으로 처리됩니다. Privacy Core Service에서 개인 정보 요청을 만드는 방법에 대해 알아보려면 [Adobe Experience Platform Privacy Service](https://developer.adobe.com/apis/experienceplatform/gdpr.html)를 참조하십시오.

* **API를 통해:** Adobe Campaign은 REST를 사용하여 개인 정보 요청을 자동 프로세스로 만들 수 있는 API를 제공합니다.

* **Adobe Campaign 인터페이스를 통해:** 데이터 컨트롤러가 각 개인 정보 요청에 대해 Adobe Campaign에서 새로운 개인 정보 요청을 만듭니다.

>[!NOTE]
>
> **CHANGES WITH ACS 19.4:**
> 
> 다음 [Privacy Service 통합](https://developer.adobe.com/apis/experienceplatform/gdpr.html) 는 모든 액세스 및 삭제 요청에 사용해야 하는 메서드입니다. 19.4 릴리스부터 액세스 및 삭제 요청에 Campaign API 및 인터페이스는 더 이상 사용되지 않습니다. 사용 중단된 Campaign Standard 및 제거된 기능에 대한 자세한 내용은 [이 페이지](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=ko)를 참조하십시오.
>
>**개인 정보 판매 옵트아웃(CCPA)**
>
> Campaign 인터페이스 및 API에서는 CCPA 옵트아웃 필드를 기본적으로 제공합니다.
>
> 버전을 확인하려면 인터페이스 오른쪽 상단의 **?** 아이콘을 클릭하고 [정보]를 선택합니다.

## 비디오 튜토리얼

### 개인 정보 보호 요청을 위한 필수 구성 요소

1. [네임스페이스 만들기](/help/privacy/namespaces-for-privacy-requests.md)
1. [사용자 정의 리소스 수정](/help/privacy/custom-resources-for-privacy-requests.md)

### Adobe Campaign 사용자 인터페이스를 통해 개인 정보 요청을 만들고 추적 및 실행하기

* [Adobe Campaign 사용자 인터페이스를 통해 개인 정보 요청을 만들고 추적하기](/help/privacy/create-and-track-privacy-requests.md)
* [개인 정보 요청 실행](/help/privacy/execute-privacy-requests.md)

## 추가 리소스

* [Campaign에 대한 일반 개인 정보 보호 지침](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=ko#getting-started)
* [ACS용 CCPA](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=ko#privacy-requests)
* [Adobe Experience Platform Privacy Service](https://developer.adobe.com/apis/experienceplatform/gdpr.html)
* [Adobe Campaign Standard REST API 설명서](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#privacy-management)
