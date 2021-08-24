---
title: Adobe Experience Platform 데이터 커넥터 이해
description: Adobe Experience Platform Data Connector는 기존 고객이 Adobe Experience Platform에서 XTK 데이터(Campaign에서 수집한 데이터)를 XDM(Experience Data Model) 데이터에 매핑하여 Adobe Experience Platform에서 데이터를 사용할 수 있도록 합니다.
feature: 사용자 핵심 서비스 통합
kt: 2826
thumbnail: 27304.jpg
doc-type: feature video
activity: understand
team: TM
exl-id: 686961f9-5374-4cc6-8b36-7ee0584ea720
source-git-commit: 344b8d8bb216489db586b030c71fd84d273968d9
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 8%

---

# Adobe Experience Platform [!UICONTROL Data Connector] 이해

>[!NOTE]
>
>이 기능은 현재 베타에 있으며, 예고 없이 자주 업데이트되고 수정될 수 있습니다.
>
>이 기능을 구현하려면 [!UICONTROL Adobe Customer Support]에 문의하십시오.

## 개요

Adobe Experience Platform [!UICONTROL Data Connector]은(는) 기존 고객이 Adobe Experience Platform의 XTK 데이터(Adobe Campaign에서 수집된 데이터)를 [!DNL Experience Data Model] (XDM) 데이터에 매핑하여 Adobe Experience Platform에서 데이터를 사용할 수 있도록 하는 데 도움이 됩니다.

커넥터는 일방향 및 Adobe Campaign Standard에서 Adobe Experience Platform으로 데이터를 전송합니다. 데이터는 Adobe Experience Platform에서 Adobe Campaign Standard으로 전송되지 않습니다.

Adobe Experience Platform [!UICONTROL Data Connector]은 Adobe Campaign Standard [!UICONTROL custom resources]을 이해하고 고객의 전체 데이터 스키마가 Adobe Experience Platform 내에 있어야 하는 방법을 알고 있는 데이터 엔지니어를 위한 것입니다.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12)

*이 비디오에서는 Adobe Experience Platform에 대한 개요를 제공합니다  [!UICONTROL Data Connector] (09:35)*

>[!NOTE]
>
>[!UICONTROL subscription events] 의 기본 전송이 지원되지 않습니다. [!UICONTROL subscription events]을 전송하려면 Adobe Experience Platform에서 해당 XDM 및 데이터 세트를 만든 다음, 이러한 데이터에 대한 사용자 지정 데이터 매핑을 구성할 수 있습니다.
>
>기존 [!UICONTROL experience events]을(를) Adobe Experience Platform에 수집할 수 없지만 생성된 [!UICONTROL experience events]이(가) Adobe Experience Platform으로 스트리밍됩니다.

## 데이터 매핑을 수행하는 주요 단계

다음 자습서에서는 Campaign Standard과 Adobe Experience Platform 간에 데이터 매핑을 수행하는 주요 단계를 설명합니다.

1. [사용자 지정 리소스 매핑](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [Experience 이벤트 매핑](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [시드 테이블 데이터 매핑](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [데이터 매핑 수정](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [데이터 수집 작업 상태 확인](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

## 추가 리소스

* [Adobe Experience Platform 데이터 커넥터 정보](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-about-data-connector.html)
* [경험 데이터 모델 개요](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/mapping-campaign-and-aep-data/aep-data-model-overview.html)
* [매핑 정의](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-mapping-definition.html)
* [매핑 활성화](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-mapping-activation.html)
* [API를 통한 데이터 수집 트리거](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-triggering-data-ingestion.html)
