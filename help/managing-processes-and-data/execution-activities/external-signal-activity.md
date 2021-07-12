---
title: 외부 신호 활동 - 매개 변수를 사용하여 워크플로우 호출
description: 한 워크플로우를 다른 워크플로우에서 시작하여 더 복잡한 고객 여정을 지원하면서 문제를 보다 효과적으로 모니터링하고 대응할 수 있는 방법을 알아봅니다.
feature: 실행 활동
kt: 2750
thumbnail: 27249
doc-type: feature video
activity: use
team: TM
exl-id: d3996185-681c-4906-85f0-0543ab767519
role: User, Developer
level: Experienced
source-git-commit: 2be2719ddd84490b796d9abc6300376fa896ff0c
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 9%

---

# [!UICONTROL External Signal activity ]- 매개 변수를 사용하여 워크플로우 호출

[!UICONTROL External Signal activity] 은 동일한 고객 여정의 일부인 다른 프로세스를 다른 워크플로우로 구성하고 오케스트레이션하는 데 사용됩니다. 한 워크플로우를 다른 워크플로우에서 시작할 수 있게 하여 더 복잡한 고객 여정을 지원하는 동시에 문제가 발생하는 경우 보다 효과적으로 모니터링하고 대응할 수 있습니다.

ACS 19.2에서 [!UICONTROL External Signal activity]은(는) 워크플로우를 호출할 뿐만 아니라 워크플로우에 매개 변수 전달(target에 대한 대상 이름, 가져올 파일 이름, 메시지 컨텐츠의 일부 등)도 할 수 있습니다. 다른 워크플로우나 REST API 호출의 워크플로우로 마이그레이션하여 외부 시스템과 통합합니다.

여기에는 이 기능에 대한 테스트를 실행할 수 있는 새 **테스트** 활동이 포함되어 있습니다.

다음 비디오에서는 다음 작업에 필요한 구성 단계를 설명합니다.

1. **CRM(** 콘텐츠 관리 시스템)과 같은 외부 시스템에서 외부 매개 변수를 받습니다.

   * 외부 신호 활동에서 매개 변수를 선언합니다
   * 매개 변수를 정의하고 워크플로우 외부 신호 활동을 트리거하도록 API 호출을 구성합니다. API 호출을 구성하는 방법에 대한 자세한 내용은 [신호 활동 트리거](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity)를 참조하십시오.

1. **외부 매개 변수** (이벤트 변수)를 사용하여 워크플로우를 사용자 지정합니다.

   워크플로우가 트리거되면 매개 변수를 워크플로우의 이벤트 변수에 수집하여 워크플로우 내에서 사용할 수 있습니다. 이벤트 변수로 사용자 지정할 수 있는 모든 활동에 대해서는 [설명서](https://helpx.adobe.com/campaign/standard/automating/using/calling-a-workflow-with-external-parameters.html)를 참조하십시오.

   * 테스트 활동 구성(19.2의 새로운 기능)
   * 대상자 읽기 및 이메일 전달 활동 구성

1. **외부 매개 변수** 로 워크플로우를 호출하도록 종료 활동 구성

>[!VIDEO](https://video.tv.adobe.com/v/27249/?quality=12)

## 추가 리소스

* [외부 신호(설명서)](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/calling-workflow-external-parameters/calling-a-workflow-with-external-parameters.html)
