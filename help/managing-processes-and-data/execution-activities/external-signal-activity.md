---
title: 외부 신호 활동 - 매개 변수를 사용하여 워크플로우 호출
description: '"문제를 보다 효과적으로 모니터링하고 응답하면서 보다 복잡한 고객 여정을 지원하는 워크플로우를 다른 워크플로우에서 시작하는 방법을 살펴볼 수 있습니다."'
feature: Execution Activity
topics: Workflows
kt: 2750
thumbnail: 27249
doc-type: feature video
activity: use
team: TM
exl-id: d3996185-681c-4906-85f0-0543ab767519
role: Business Practitioner, Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 5d2bc8bd3a3a0fdb5e2f1ef75af2ab60b8f6abc8
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 9%

---

# [!UICONTROL External Signal activity ]- 매개 변수를 사용한 워크플로우 호출

[!UICONTROL External Signal activity]은 동일한 고객 여정의 일부인 다른 프로세스를 다른 워크플로우로 구성하고 조정하는 데 사용됩니다. 한 워크플로우를 다른 워크플로우에서 시작할 수 있게 하여 더 복잡한 고객 여정을 지원하는 동시에 문제가 발생하는 경우 보다 효과적으로 모니터링하고 대응할 수 있습니다.

ACS 19.2에서 [!UICONTROL External Signal activity]은 워크플로우를 호출할 수 있을 뿐만 아니라, 워크플로우에 매개 변수(타깃팅할 대상 이름, 가져올 파일 이름, 메시지 컨텐츠의 일부 등)를 전달할 수 있습니다. 다른 작업 과정 또는 외부 시스템과 통합하기 위한 REST API 호출의 작업 과정으로 이동합니다.

또한 이 기능에서 테스트를 실행할 수 있는 새로운 **Test** 활동이 포함됩니다.

다음 비디오에서는 다음에 필요한 구성 단계를 설명합니다.

1. **CRM(Content** Management System)과 같은 외부 시스템에서 외부 매개 변수를 받을 수 있습니다.

   * 외부 신호 활동에서 매개 변수를 선언합니다.
   * API 호출을 구성하여 매개 변수를 정의하고 워크플로 외부 신호 활동을 트리거합니다. API 호출을 구성하는 방법에 대한 자세한 내용은 [신호 활동 트리거](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity)를 참조하십시오.

1. **외부 매개 변수** (이벤트 변수)를 사용하여 워크플로우를 사용자 정의합니다.

   워크플로우가 트리거되면 매개 변수가 워크플로우의 이벤트 변수에 수집되어 워크플로우 내에서 사용할 수 있습니다. 이벤트 변수로 사용자 정의할 수 있는 모든 활동은 [설명서](https://helpx.adobe.com/campaign/standard/automating/using/calling-a-workflow-with-external-parameters.html)를 참조하십시오.

   * 테스트 활동 구성(19.2의 새로운 기능)
   * 읽기 대상자 및 이메일 배달 활동 구성

1. **외부 매개 변수** 로 작업 흐름을 호출하도록 종료 활동 구성

>[!VIDEO](https://video.tv.adobe.com/v/27249/?quality=12)

## 추가 리소스

* [외부 신호(설명서)](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/calling-workflow-external-parameters/calling-a-workflow-with-external-parameters.html)
