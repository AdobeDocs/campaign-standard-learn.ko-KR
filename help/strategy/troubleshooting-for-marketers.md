---
title: 마케터 문제 해결
description: 가장 일반적인 오류를 아는 것은 더 빠른 문제 해결과 생산성 향상에 도움이 될 수 있습니다. 이러한 문제 해결 팁은 유사한 오류가 발생할 때 효과적으로 오류를 해결하는 데 도움이 됩니다.
version: Standard
feature: Workflows
role: User
level: Beginner, Intermediate, Experienced
doc-type: Article
last-substantial-update: 2023-05-18T00:00:00Z
jira: KT-13256
thumbnail: KT-13256.jpeg
source-git-commit: f7f2b6abb26075b25a3b55e4ceed744172691ce8
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 1%

---


# 마케터 문제 해결: 5가지 일반적인 워크플로우 및 게재 오류

기준: [수라즈 파트라](https://www.linkedin.com/in/suraj-p-51612053/){target="_blank"}, 수석 컨설턴트, Meijer

지난 5년간 Adobe Experience Cloud 제품에 대한 수석 엔지니어 및 고객 전문가로 Adobe에서는 [메이저](https://www.meijer.com/){target="_blank"}ACS를 사용하여 복잡한 마케팅 및 트랜잭션 캠페인을 실행하도록 1934년에 설립된 미국 수퍼센터 체인인 American Supercenter Chain입니다. 제가 작업한 몇 가지 프로젝트에는 개인화를 위한 오퍼 및 주문 세부 사항을 저장하는 사용자 지정된 캠페인, Adobe Audience Manager과 통합, 세그먼트 수집을 위한 고객 통찰력이 포함되어 있습니다.


ACS를 사용하는 내 시간에, 나는 문제를 해결하는데 시간이 걸리고 좌절감을 줄 수 있는 오류들이 있다. 가장 일반적인 오류를 아는 것은 더 빠른 문제 해결과 생산성 향상에 도움이 될 수 있습니다. 다음은 유사한 오류가 발생할 때 효과적으로 오류를 해결하는 데 도움이 되는 문제 해결 팁입니다.

## 데이터 형식 불일치 오류

**오류 코드:**
`PGS-220000 PostgreSQL error: ERROR: operator does not exist: character varying = bigint`

**원인:**
이러한 유형의 오류는 다른 데이터 유형의 필드를 사용하여 조정하려고 할 때 워크플로우에 나타납니다. 예를 들어 문자열 필드가 있는 로드 파일을 사용하여 파일을 업로드하고 문자열 필드를 int 데이터 유형이 있는 프로필 필드로 조정하려고 합니다.

![data-type-mismatch-error](/help/assets/kt-13256/data-type-mismatch.png)

**솔루션:**
파일 로드 활동의 필드 데이터 유형을 일치하는 필드로 변경합니다. &quot;파일 로드&quot; 활동을 엽니다. &quot;열 정의&quot; 탭으로 이동하여 원하는 필드의 데이터 유형을 변경합니다.


![data-type-mismatch-solution](/help/assets/kt-13256/data-type-mismatch-solution.png)

## 게재 개인화 오류

**오류 코드:**
`The schema for profiles specified in the transition ('') is not compatible with the schema defined in the delivery template ('nms:recipient'). They should be identical.`

**원인:**
이 오류는 주소로 이메일을 보낼 때 표시되지만 이메일 또는 다른 식별자가 프로필과 조정되지 않습니다. 이메일 통신을 전송하려면 이메일 또는 식별자를 항상 프로필에 연결해야 합니다.

아래와 같이 조정 활동을 사용하십시오.

![조정 활동을 사용한 워크플로우](/help/assets/kt-13256/del-persn-error-wf.png)

**솔루션:**
수신자 테이블이 있는 로드된 파일에서 공통 ID가 있어야 합니다. 이 공통 키는 조정 활동 내에서 로드 파일을 수신자 테이블에 연결합니다. 워크플로우 내에서 이 조정 단계가 필요한 수신자 표에 없는 레코드로 이메일을 보낼 수 없습니다. 이렇게 하면 들어오는 로드 파일 활동을 프로필의 이메일 ID와 같은 식별자로 조정합니다. 다음 `nms:recipient` 스키마는 프로필 테이블을 참조하며 들어오는 레코드를 프로필로 조정하면 전자 메일을 준비하는 동안 사용할 수 있습니다.

아래 표시된 것처럼 조정 활동에 대해서는 스크린샷을 참조하십시오.

![조정 세부 사항이 있는 워크플로우](/help/assets/kt-13256/del-persn-error-wf-solution.png)

추가 정보 [조정](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/data-management-activities/reconciliation.html?lang=en).

## 일반 필드 데이터 집합 오류

**오류 코드:**
`The document types of inbound events (''and'') are incompatible (step 'Exclusion'). Unable to perform the operation. `

**원인:**
이 문제는 **제외 활동** ACS 워크플로우에서 사용할 수 있습니다. ID를 기반으로 하여 수행 및 제외를 수행할 때 기본 세트와 제외된 세트에 동일한 필드 이름이 없을 때 오류가 발생합니다.


![일반 필드 데이터 집합 오류](/help/assets/kt-13256/dataset-error.png)

**솔루션:**

이 오류를 해결하는 방법에는 두 가지가 있습니다.

1. 기본 및 제외 모두에서 동일한 필드 이름을 사용하고 해당 필드를 ID로 사용합니다

   또는

1. JOINS 제외 방법을 사용하여 레코드를 제외할 필드를 선택합니다.

![공통 필드 데이터 집합 오류 - 솔루션 ](/help/assets/kt-13256/dataset-error-solution.png)

## 필드 이름이 삭제됨 오류

**오류 코드:**
`XTK-170036 Unable to parse expression 'i__name'`

**원인:**

실패 포인트는 **데이터 보강 활동**. 가장 일반적인 중 하나가 아래에 표시됩니다.

![필드 이름이 삭제됨 오류](/help/assets/kt-13256/field-name-dropped-error.png)

이 문제는 활동에서 표현식 이름을 수동으로 편집할 때 발생합니다. 이 그림에서는 표현식이 `name `to `i__name`.

**솔루션:**

다음 세 가지 방법으로 이 오류를 해결할 수 있습니다.

1. 이름을 원래 있던 식으로 다시 변경합니다.

2. 새 이름을 사용하려면 **데이터 보강 활동**.

3. 변경된 사항을 기억하지 않는다면 활동을 다시 만들어야 합니다.

## 임시 테이블 삭제 오류 

**오류 코드:**
`XTK-170024 The temporary schema "temp:deliveryEmail1" is not defined in the current context.`

**원인:**
데이터 보강 또는 다른 활동과 관련된 복잡한 워크플로우에서 일반적인 오류입니다. 즉, 워크플로우를 여러 번 변경하는 동안 일부 활동 워크플로우가 올바르게 저장되지 않을 수 있습니다.

![임시 테이블 삭제 오류 ](/help/assets/kt-13256/temp-table-dropped-error.png)

**솔루션:**
이 오류가 발생할 수 있는 방법에는 여러 가지가 있으므로 간단한 수정 사항이 없습니다. 간단한 워크플로우라면 활동을 다시 구성하는 것이 좋습니다. 복잡한 워크플로우에서는 워크플로우 활동을 새 워크플로우에 복사하고 저장하고 다시 실행하는 것이 좋습니다.