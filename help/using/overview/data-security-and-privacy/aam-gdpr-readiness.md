---
description: Audience Manager 고객을 위한 GDPR 준비 지침
seo-description: GDPR Readiness Guidance for Audience Manager Customers
seo-title: GDPR Readiness Guidance for Audience Manager Customers
solution: Audience Manager
title: Audience Manager 고객을 위한 GDPR 준비 지침
feature: Data Governance & Privacy
exl-id: 353b9035-20f3-41ff-819c-71f161e6b1e1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 99%

---

# Audience Manager 고객을 위한 GDPR 준비 지침 (데이터 컨트롤러) {#gdpr-readiness-guidance}

Audience Manager는 데이터 거버넌스 및 조직의 준비성 영역에서 선제적으로 대처할 것을 권장합니다. 이것은 소비자 데이터가 액세스 또는 삭제 요청과 관련된 프로세스용으로 조직화되고, 팀은 이러한 요청을 관리할 수 있게 되며 소비자(데이터 주체)는 브랜드와 관련하여 긍정적이고 차별화된 경험을 갖도록 하는 데 도움이 됩니다.

데이터 처리자인 Adobe는 GDPR 요구 사항과 데이터 주체의 동의를 얻는 프로세스에 대한 법률 자문을 제공할 수 없습니다. 조직의 GDPR 준수에 대한 지침은 법률 고문과 상담하십시오.

## 데이터 거버넌스: Audience Manager 인스턴스에서 소비자 데이터를 관리하는 방법에 대해 고민을 시작합니다

* 마케팅팀이 Audience Manager에서 사용자를 식별하는 데 사용하는 다양한 고객 ID와 이 ID가 저장된 데이터 소스를 검토합니다. 이렇게 하면 특정 데이터 유형이 Audience Manager에서 처리되기 전에 팀에서 해시하므로 요청(삭제 또는 액세스 등) 프로세스가 간소화됩니다.
* IDFA/GAID 모바일 장치 ID는 Audience Manager에서 여러 사용 사례에 사용됩니다. Adobe Mobile SDK를 사용 중이라면 IDFA/GAID와 함께 Experience Cloud ID(MID)를 제출하여 GDPR 응답이 완료되었는지 확인하십시오.
* 더욱 확장되고 있는 개인 데이터의 정의에 따라 IP 주소는 해당 지역의 개인 데이터로 간주될 수 있습니다. Adobe Consulting에 적극적으로 참여하여 마지막 옥텟을 난독화합니다.
* 데이터 주체가 GDPR 요청을 할 때 데이터 주체 ID 확인을 위한 유효성 확인/인증 정책 및 프로세스를 결정합니다.
* 개인 데이터를 수용하는 기술에 대한 대상 활성화를 차단하는 [데이터 내보내기 제어](../../features/data-export-controls.md) 기능의 사용을 고려해 보십시오. 예를 들어 타사 데이터가 있는 세그먼트는 이메일 서비스 공급자에게 배급되어서는 안 됩니다. 조직의 누군가가 이 데이터를 실수로 활성화하지 않도록 [!UICONTROL Data Export Control]를 설정하십시오.
* [역할 기반 액세스 제어](../../features/administration/administration-overview.md) 기능을 활용하여 적절한 팀이 의도한 데이터에 액세스할 수 있도록 합니다.
* 데이터에 대한 적절한 [유지 기간](../../faq/faq-privacy.md#data-retention-faq)을 고려합니다.
* ID 연결 및 개인 정보 보호 정책 및 법적 요구 사항을 검토하여 ID 세트들을 언제 어디서 함께 연결하는 것이 적절한지 확인하십시오. Audience Manager의 [프로필 병합 규칙](../../features/profile-merge-rules/merge-rules-overview.md)을 적절하게 사용하십시오.

## 조직 준비: 비즈니스 프로세스를 구축합니다

* 데이터 주체의 요청을 받고 응답하는 프로세스를 확인합니다. Audience Manager에 요청을 제출하는 자동화된 도구 작성을 고려하십시오.
* 최고 DMP 센터 내에 개인 정보 보호 담당자를 지정합니다. 조직의 개인 정보 보호 담당자와 Audience Manager 제품 사용팀을 연결하여 입력 ID 요구 사항 관리에 사용할 수 있는 방법을 이해합니다.
* 데이터 주체와 공유하기 전에 데이터 검토를 수행합니다. 마련하는 단계들을 문서화하여 신뢰성을 확립합니다.
