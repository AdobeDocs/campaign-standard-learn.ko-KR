---
title: Adobe Campaign Standard(ACS)를 통한 개인정보 보호 요청 - 개요
description: 자습서에서는 ACS(Adobe Campaign Standard) 인터페이스를 통해 개인 정보 생성을 요청하는 방법을 설명합니다.
feature: GDPR, CCAP
topic: Privacy
kt: 1480
doc-type: feature video
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 556bff4c94e16d3a94561dee1ccb311bc003b631
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 20%

---


# Adobe Campaign Standard 사용자 인터페이스를 통한 개인 정보 요청

Adobe Campaign은 GDPR(General Data Protection Regulation) 및 CPPA(California Consumer Privacy Act)와 같은 개인 정보 보호 법률을 준수하여 개인 정보 액세스를 수행하고 PII 데이터의 요청을 삭제하는 3가지 방법을 데이터 관리자에게 제공합니다.

* **개인정보 보호 핵심 서비스 통합:** 모든 Experience Cloud 솔루션 [!UICONTROL Privacy Service] 으로 푸시된 개인정보 보호 요청은 전용 워크플로우를 통해 Campaign에서 자동으로 처리됩니다. 개인정보 보호 코어 서비스에서 개인정보 보호 요청을 만드는 방법에 대해 알려면 [Adobe Experience Platform Privacy Service](https://adobe.io/apis/cloudplatform/gdpr.html)을 참조하십시오.

* **API를 통해:** Adobe Campaign은 REST를 사용한 개인 정보 요청 자동 프로세스를 허용하는 API를 제공합니다

* **Adobe Campaign 인터페이스를 통해 각 개인 정보** 를 요청하는 경우 데이터 관리자는 Adobe Campaign에서 새로운 개인 정보 보호 요청을 만듭니다.

>[!NOTE]
>
> **ACS 19.4의 변경 사항:**
> 
> [Privacy Service 통합](https://adobe.io/apis/cloudplatform/gdpr.html)은 모든 액세스 및 삭제 요청에 사용해야 하는 방법입니다. 19.4부터 액세스 및 삭제 요청에 대한 캠페인 API 및 인터페이스 사용은 더 이상 사용되지 않습니다. 사용 중단된 Campaign Standard 및 제거된 기능에 대한 자세한 내용은 [이 페이지](https://helpx.adobe.com/kr/campaign/kb/acs-deprecated-and-removed-features.html)를 참조하십시오.
>
>**개인 정보 판매 옵트아웃 (CCPA)**
>
>19.4부터 CCPA 옵트아웃 필드가 Campaign 인터페이스 및 API에 기본적으로 제공됩니다. 19.3에서 이 정보를 활용하려면 Adobe Campaign Standard에서 이 필드를 만들어야 합니다. 자세한 내용은 [자세한 설명서](https://helpx.adobe.com/kr/campaign/kb/acs-privacy.html#ccpa)를 참조하십시오.
>
> 버전을 확인하려면 인터페이스 오른쪽 상단의 아이콘을 클릭하고 정보를 선택합니다.

## 비디오 Tutorials

### 개인 정보 요청을 위한 사전 요구 사항

1. [네임스페이스 만들기](/help/privacy/namespaces-for-privacy-requests.md)
1. [사용자 정의 리소스 수정](/help/privacy/custom-resources-for-privacy-requests.md)

### Adobe Campaign 사용자 인터페이스를 통해 개인 정보 요청 만들기, 추적 및 실행

* [Adobe Campaign 사용자 인터페이스를 통해 개인 정보 요청 만들기 및 추적](/help/privacy/create-and-track-privacy-requests.md)
* [개인 정보 요청 실행](/help/privacy/execute-privacy-requests.md)

## 추가 리소스

* [Campaign에 대한 일반 개인 정보 보호 지침](https://helpx.adobe.com/kr/campaign/kb/campaign-privacy-overview.html)
* [ACS용 CCPA](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)
* [Adobe Experience Platform Privacy Service](https://adobe.io/apis/cloudplatform/gdpr.html)
* [Adobe Campaign Standard REST API 설명서](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#privacy-management)
