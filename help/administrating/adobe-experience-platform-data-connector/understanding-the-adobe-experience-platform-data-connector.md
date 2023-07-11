---
title: Adobe Experience Platform 데이터 커넥터 이해
description: Adobe Experience Platform Data Connector는 XTK 데이터(Campaign에서 수집된 데이터)를 Adobe Experience Platform의 XDM(Experience Data Model) 데이터에 매핑하여 기존 고객이 Adobe Experience Platform에서 데이터를 사용할 수 있도록 지원합니다.
feature: People Core Service Integration
jira: KT-2826
thumbnail: 27304.jpg
role: User
level: Experienced
doc-type: feature video
activity: understand
team: TM
exl-id: 686961f9-5374-4cc6-8b36-7ee0584ea720
source-git-commit: d46e4c84a7d162085016722005cca4aadb4feb3c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 4%

---

# Adobe Experience Platform 이해 [!UICONTROL Data Connector]

>[!NOTE]
>
>이 기능은 베타 버전이며 예고 없이 자주 업데이트 및 수정될 수 있습니다.
>
>에게 문의하십시오. [!UICONTROL Adobe Customer Support] 이 기능을 구현할 계획이라면

## 개요

Adobe Experience Platform [!UICONTROL Data Connector] 는 XTK 데이터(Adobe Campaign에서 수집된 데이터)를 매핑하여 기존 고객이 Adobe Experience Platform에서 데이터를 사용할 수 있도록 지원합니다. [!DNL Experience Data Model] Adobe Experience Platform의 (XDM) 데이터.

커넥터는 단방향이며 데이터를 Adobe Campaign Standard에서 Adobe Experience Platform으로 전송합니다. 데이터는 Adobe Experience Platform에서 Adobe Campaign Standard으로 전송되지 않습니다.

Adobe Experience Platform [!UICONTROL Data Connector] Adobe Campaign Standard을 이해하는 데이터 엔지니어를 위한 것입니다 [!UICONTROL custom resources] 고객의 전체 데이터 스키마가 Adobe Experience Platform 내부에 어떻게 있어야 하는지 이해할 수 있습니다.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&learn=on)

*이 비디오는 Adobe Experience Platform에 대한 개요를 제공합니다 [!UICONTROL Data Connector] (09:35분)*

>[!NOTE]
>
>의 기본 전송 [!UICONTROL subscription events] 은(는) 지원되지 않습니다. 전송하려면 [!UICONTROL subscription events], Adobe Experience Platform에서 해당 XDM 및 데이터 세트를 만든 다음 이러한 데이터에 대한 사용자 지정 데이터 매핑을 구성할 수 있습니다.
>
>기존 항목 [!UICONTROL experience events] Adobe Experience Platform에 수집할 수 없지만 계속 생성됩니다. [!UICONTROL experience events] Adobe Experience Platform으로 스트리밍됩니다.

## 데이터 매핑을 수행하는 주요 단계

다음 자습서에서는 Campaign Standard과 Adobe Experience Platform 간에 데이터 매핑을 수행하는 주요 단계를 설명합니다.

1. [사용자 지정 리소스 매핑](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [Experience 이벤트 매핑](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [시드 테이블 데이터 매핑](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [데이터 매핑 수정](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [데이터 수집 작업 상태 확인](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

