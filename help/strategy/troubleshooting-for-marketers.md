---
title: 마케터 문제 해결
description: 가장 일반적인 오류를 파악하면 보다 빠른 문제 해결과 생산성 향상에 도움이 될 수 있습니다. 이러한 문제 해결 팁은 유사한 오류가 발생할 때 효과적으로 해결하는 데 도움이 됩니다.
version: Standard
feature: Workflows
role: User
level: Beginner, Intermediate, Experienced
doc-type: Article
last-substantial-update: 2023-05-18T00:00:00Z
jira: KT-13256
thumbnail: KT-13256.jpeg
exl-id: 24a6815b-52d1-4bd6-9d27-522720a91f83
source-git-commit: cfa097e1ea0d5ca8c97c1062ea8717c37a51530d
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# 마케터 문제 해결: 5가지 일반적인 워크플로우 및 게재 오류

수행한 사람: [수라지 파트라](https://www.linkedin.com/in/suraj-p-51612053/){target="_blank"}, 수석 컨설턴트, Meijer

지난 5년 동안 Adobe Experience Cloud 제품에 대한 수석 엔지니어 및 고객 전문가로서 비즈니스 사용자 지원 [마이어](https://www.meijer.com/){target="_blank"}, ACS와 함께 복잡한 마케팅 및 트랜잭션 캠페인을 실행하기 위해 1934년에 설립된 미국 슈퍼센터 체인입니다. 제가 작업한 몇 가지 프로젝트에는 개인화를 위해 오퍼와 주문 세부 사항을 저장하는 사용자 지정 캠페인, Adobe Audience Manager과 통합 및 세그먼트 수집을 위한 고객 인사이트가 포함됩니다.


ACS를 사용하는 동안 오류가 발생했으며, 이로 인해 시간이 많이 소요되고 해결하기 어려운 문제가 발생할 수 있습니다. 가장 일반적인 오류를 파악하면 보다 빠른 문제 해결과 생산성 향상에 도움이 될 수 있습니다. 다음은 유사한 오류가 발생할 때 효과적으로 해결하는 데 도움이 되는 내 문제 해결 팁입니다.

## 데이터 유형 불일치 오류

**오류 코드:**
`PGS-220000 PostgreSQL error: ERROR: operator does not exist: character varying = bigint`

**원인:**
이러한 유형의 오류는 다른 데이터 유형의 필드를 사용하여 조정하려고 할 때 워크플로우에 나타납니다. 예를 들어 문자열 필드가 있는 파일 로드를 사용하여 파일을 업로드할 때 문자열 필드를 데이터 유형이 int인 프로필 필드로 조정하려고 합니다.

![data-type-mismatch-error](/help/assets/kt-13256/data-type-mismatch.png)

**해결 방법:**
&quot;파일 로드&quot; 활동에서 필드의 데이터 유형을 일치시키는 유형으로 변경합니다. &quot;파일 로드&quot; 활동을 엽니다. &quot;열 정의&quot; 탭으로 이동하여 원하는 필드의 데이터 유형을 변경합니다.


![data-type-mismatch-solution](/help/assets/kt-13256/data-type-mismatch-solution.png)

## 게재 개인화 오류

**오류 코드:**
`The schema for profiles specified in the transition ('') is not compatible with the schema defined in the delivery template ('nms:recipient'). They should be identical.`

**원인:**
이 오류는 주소로 이메일을 보내지만 이메일 또는 다른 식별자가 프로필과 조정되지 않은 경우에 나타납니다. 이메일 통신을 보내려면 이메일 또는 식별자가 항상 프로필에 연결되어 있어야 합니다.

![조정 활동이 있는 워크플로우](/help/assets/kt-13256/del-persn-error-wf.png)

**해결 방법:**
수신자 테이블과 함께 로드된 파일의 공통 ID가 있어야 합니다. 이 공통 키는 조정 활동 내의 수신자 테이블에 로드 파일을 조인합니다. 수신자 표에 없는 레코드에는 이메일을 보낼 수 없습니다. 이 레코드는 워크플로우 내에 이 조정 단계가 필요합니다. 이렇게 하면 들어오는 파일 로드 활동을 프로필의 이메일 ID와 같은 식별자로 조정합니다. 다음 `nms:recipient` 스키마는 프로필 테이블을 참조하며 수신 레코드를 프로필과 일치시키면 이메일 준비 중에 사용할 수 있습니다.

아래 표시된 대로 조정 활동에 대한 스크린샷을 참조하십시오.

![조정 세부 정보가 포함된 워크플로우](/help/assets/kt-13256/del-persn-error-wf-solution.png)

자세히 알아보기 [조정](https://experienceleague.adobe.com/en/docs/campaign-standard/using/managing-processes-and-data/data-management-activities/reconciliation).

## 공통 필드 데이터 세트 오류

**오류 코드:**
`The document types of inbound events (''and'') are incompatible (step 'Exclusion'). Unable to perform the operation. `

**원인:**
이 문제는 을 사용하는 동안 발생합니다. **제외 활동** acs 워크플로우에서 ID를 기반으로 제외를 수행할 때 기본 세트와 제외된 세트의 필드 이름이 동일하지 않은 경우.


![공통 필드 데이터 세트 오류](/help/assets/kt-13256/dataset-error.png)

**해결 방법:**

이 오류를 해결하는 방법에는 두 가지가 있습니다.

1. 기본 및 제외에서 동일한 필드 이름을 사용하고 해당 필드를 ID로 사용

   또는

2. JOINS 제외 방법을 사용하여 레코드를 제외할 필드를 선택합니다.

![일반 필드 데이터 세트 오류 - 솔루션 ](/help/assets/kt-13256/dataset-error-solution.png)

## 필드 이름 삭제 오류

**오류 코드:**
`XTK-170036 Unable to parse expression 'i__name'`

**원인:**

실패 지점은 다음 위치에서 발생할 수 있습니다. **데이터 보강 활동**. 가장 일반적인 항목 중 하나가 아래에 표시됩니다.

![필드 이름 삭제 오류](/help/assets/kt-13256/field-name-dropped-error.png)

이 문제는 활동에서 표현식 이름을 수동으로 편집할 때 발생합니다. 이 그림에서는 표현식이 다음 위치에서 수정되었음을 보여 줍니다. `name `끝 `i__name`.

**해결 방법:**

다음 세 가지 방법으로 이 오류를 해결할 수 있습니다.

1. 원래 있던 표현식으로 이름을 다시 변경합니다.

2. 새 이름을 사용하려면 **데이터 보강 활동**.

3. 변경된 내용을 기억하지 못하는 경우 활동을 다시 만드는 것이 가장 좋습니다.

## 임시 테이블 삭제 오류 

**오류 코드:**
`XTK-170024 The temporary schema "temp:deliveryEmail1" is not defined in the current context.`

**원인:**
데이터 보강 또는 기타 활동과 관련된 복잡한 워크플로의 일반적인 오류입니다. 이는 일부 활동 워크플로우가 워크플로우를 여러 번 변경하는 동안 올바르게 저장되지 않음을 의미할 수 있습니다.

![임시 테이블 삭제 오류 ](/help/assets/kt-13256/temp-table-dropped-error.png)

**해결 방법:**
이 오류가 발생할 수 있는 방법은 여러 가지가 있으므로 간단한 해결은 없습니다. 단순 워크플로우인 경우 활동을 다시 구성하는 것이 좋습니다. 복잡한 워크플로우에서는 워크플로우 활동을 새 워크플로우에 복사하고 저장한 다음 다시 실행하는 것이 좋습니다.
