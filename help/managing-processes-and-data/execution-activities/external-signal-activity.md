---
title: 외부 신호 활동 - 매개 변수를 사용하여 워크플로우 호출
description: 외부 신호 활동은 동일한 고객 여정의 일부인 다른 프로세스를 다양한 워크플로우로 구성하고 조정하는 데 사용됩니다. 따라서 다른 워크플로우에서 워크플로우를 시작할 수 있으므로 복잡한 고객 여정을 지원할 수 있고 문제가 발생하는 경우 보다 효과적으로 모니터링하고 대응할 수 있습니다.
feature: External Signal Activity
topics: Workflows
kt: 2750
doc-type: feature video
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 556bff4c94e16d3a94561dee1ccb311bc003b631
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---


# [!UICONTROL External Signal activity ]- 매개 변수를 사용한 워크플로우 호출

이 [!UICONTROL External Signal activity] 는 동일한 고객 여정의 일부이며 다양한 워크플로우로 다른 프로세스를 구성하고 조정하는 데 사용됩니다. 따라서 다른 워크플로우에서 워크플로우를 시작할 수 있으므로 복잡한 고객 여정을 지원할 수 있고 문제가 발생하는 경우 보다 효과적으로 모니터링하고 대응할 수 있습니다.

ACS 19.2에서는 워크플로우를 [!UICONTROL External Signal activity] 호출할 수 있을 뿐만 아니라, 매개 변수를 워크플로우에 전달(타깃팅할 대상 이름, 가져올 파일 이름, 메시지 컨텐츠의 일부 등)할 수 있습니다. 외부 시스템과 통합하기 위한 다른 워크플로우 또는 REST API 호출의 워크플로우에 연결할 수 있습니다.

이 기능에서 테스트를 실행할 수 있는 새로운 **테스트** 활동이 포함됩니다.

다음 비디오에서는 필요한 구성 단계를 설명합니다.

1. **CRM(Content Management System)과 같은 외부 시스템에서 외부 매개** 변수를 받을 수 있습니다.
   * 외부 신호 활동에서 매개 변수 선언
   * 매개 변수를 정의하고 워크플로 외부 신호 활동을 트리거하도록 API 호출을 구성합니다. API 호출을 구성하는 방법에 대한 자세한 내용은 신호 활동 [트리거를 참조하십시오](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity).

1. **외부 매개 변수** (이벤트 변수)를 사용하여 워크플로우를 사용자 정의합니다.
워크플로우가 트리거되면 매개 변수가 워크플로우의 이벤트 변수에 수집되고 워크플로우 내에서 사용할 수 있습니다. 이벤트 [변수로 사용자 정의할 수 있는 모든 활동에 대한 설명서는](https://helpx.adobe.com/campaign/standard/automating/using/calling-a-workflow-with-external-parameters.html) 참조하십시오.

   * 테스트 활동 구성(19.2의 새로운 기능)
   * 대상 읽기 및 이메일 배달 활동 구성

1. **외부 매개 변수를 사용하여** 워크플로우를 호출하도록 종료 활동 구성

>[!VIDEO](https://video.tv.adobe.com/v/27249/?quality=12)

## 추가 자료

* [외부 신호(설명서)](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/data-management-activities/external-api.html)