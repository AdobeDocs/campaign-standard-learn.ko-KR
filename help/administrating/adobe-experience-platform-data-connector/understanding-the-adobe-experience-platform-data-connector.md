---
title: Adobe Experience Platform 데이터 커넥터 이해
description: Adobe Experience Platform 데이터 커넥터를 사용하면 기존 고객이 Adobe Experience Platform의 XDM(Experience Data Model) 데이터에 XTK 데이터(Campaign에서 인제스트된 데이터)를 매핑하여 Adobe Experience Platform에서 데이터를 이용할 수 있도록 할 수 있습니다.
feature: Adobe Experience Platform Data Connector
topics: ACoP
kt: 2826
thumbnail: 27304.jpg
doc-type: feature video
activity: understand
team: TM
translation-type: tm+mt
source-git-commit: 11263e247184ddc6a8e3df6a8ed0899907fbb366
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 10%

---


# Adobe Experience Platform 이해 [!UICONTROL Data Connector]

>[!NOTE]
>
>이 기능은 현재 베타 버전이며 예고 없이 자주 업데이트되고 수정될 수 있습니다.
>
>이 기능을 구현하려는 [!UICONTROL Adobe Customer Support] 경우 연락하십시오.

## 개요

Adobe Experience Platform [!UICONTROL Data Connector] 는 기존 고객이 Adobe Experience Platform의 XTK 데이터(Adobe Campaign에서 데이터 수집)를 [!DNL Experience Data Model] (XDM) 데이터에 매핑하여 Adobe Experience Platform에서 데이터를 사용할 수 있도록 지원합니다.

커넥터는 단방향이며 Adobe Campaign Standard에서 Adobe Experience Platform으로 데이터를 보냅니다. 그 데이터는 Adobe Experience Platform에서 Adobe Campaign Standard으로 절대로 보내지지 않는다.

Adobe Experience Platform [!UICONTROL Data Connector] 는 Adobe Campaign Standard을 이해하고 고객의 전체 데이터 스키마가 Adobe Experience Platform 내에 있어야 하는 방법을 알고 있는 데이터 엔지니어 [!UICONTROL custom resources] 를 대상으로 합니다.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12)

*이 비디오에서는 Adobe Experience Platform에 대한 개요를 제공합니다 [!UICONTROL Data Connector] (09분 35초).*

>[!NOTE]
>
>기본적으로 전송되지 [!UICONTROL subscription events] 않습니다. 전송하려면 Adobe Experience Platform [!UICONTROL subscription events]에서 해당 XDM 및 데이터 세트를 만든 다음 이러한 데이터에 대한 사용자 지정 데이터 매핑을 구성할 수 있습니다.
>
>기존 것을 Adobe Experience Platform으로 인제스트할 [!UICONTROL experience events] 수는 없지만 현재 생성된 것을 Adobe Experience Platform [!UICONTROL experience events] 로 스트리밍할 예정이다.

## 데이터 매핑을 수행하는 주요 단계

다음 자습서에서는 Campaign Standard과 Adobe Experience Platform 간의 데이터 매핑을 수행하는 주요 단계를 설명합니다.

1. [사용자 지정 리소스 매핑](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [Experience 이벤트 매핑](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [시드 테이블 데이터 매핑](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [데이터 매핑 수정](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [데이터 수집 작업 상태 확인](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

## 추가 리소스

* [Adobe Experience Platform 데이터 커넥터 정보](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-about-data-connector.html)
* [경험 데이터 모델 개요](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-data-model-overview.html)
* [매핑 정의](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-mapping-definition.html)
* [매핑 활성화](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-mapping-activation.html)
* [API를 통한 데이터 수집 트리거](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-triggering-data-ingestion.html)
