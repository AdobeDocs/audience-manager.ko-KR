---
description: Audience Manager 고객을 위한 GDPR 준비 지침
seo-description: Audience Manager 고객을 위한 GDPR 준비 지침
seo-title: Audience Manager 고객을 위한 GDPR 준비 지침
solution: Audience Manager
title: Audience Manager 고객을 위한 GDPR 준비 지침
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# Audience Manager 고객을 위한 GDPR 준비 지침(데이터 관리자) {#gdpr-readiness-guidance}

Audience Manager는 데이터 거버넌스 및 조직의 준비 영역에서 사전 예방적 조치를 취할 것을 권장합니다. 이를 통해 소비자 데이터가 액세스 또는 삭제 요청과 관련된 프로세스에 맞게 구성되고 팀이 이러한 요청을 활성화하고 관리할 수 있으며 소비자(데이터 주체)는 브랜드에 긍정적이고 차별화된 경험을 제공할 수 있습니다.

Adobe는 데이터 프로세서로서 GDPR 요구 사항과 귀하의 데이터 주체로부터 동의를 얻기 위한 프로세스에 대한 법률 자문을 제공할 수 없습니다. 조직의 GDPR 준수에 대한 지침은 법률 자문을 참조하십시오.

## 데이터 거버넌스:Audience Manager 인스턴스에서 소비자 데이터를 관리하는 방법에 대해 생각해 보십시오

* 마케팅 팀이 Audience Manager의 사용자를 식별하는 데 사용하는 다양한 고객 ID와 저장된 데이터 소스를 검토합니다. 이렇게 하면 특정 데이터 유형이 Audience Manager에 수집되기 전에 팀에서 해시하므로 요청(예: 삭제 또는 액세스)에 대한 프로세스가 간소화됩니다.
* IDFA/GAID 모바일 장치 ID 파섹 Adobe Mobile SDK를 사용하는 경우 IDFA/GAID와 함께 Experience Cloud ID(MID)를 제출하여 GDPR 응답이 완료되었는지 확인하십시오.
* 개인 데이터의 정의가 더욱 확대되고 있으므로 IP 주소는 해당 지역의 개인 데이터로 간주될 수 있습니다. Adobe Consulting과 적극적으로 협력하여 마지막 8진수를 난독화합니다.
* GDPR 요청 시 데이터 주체의 ID를 확인하는 유효성 검사/인증 정책 및 프로세스를 결정합니다.
* 데이터 내보내기 [제어 기능을](../../features/data-export-controls.md) 사용하여 개인 데이터를 포함하는 기술에 대한 고객 활성화를 차단하는 것이 좋습니다. 예를 들어 서드 파티 데이터가 있는 세그먼트는 이메일 서비스 제공업체에 전달되어서는 안 됩니다. 조직 내에서 이 데이터를 실수로 활성화하지 [!UICONTROL Data Export Control] 않도록 을 설정합니다.
* 역할 기반 [액세스 제어](../../features/administration/administration-overview.md) 기능을 활용하여 적합한 팀이 적절한 데이터에 액세스할 수 있도록 합니다.
* 데이터에 적절한 [보존 기간을](../../faq/faq-privacy.md#data-retention-faq) 고려합니다.
* ID 연결 및 개인 정보 보호 정책 및 법적 요구 사항을 검토하여 ID를 언제 어디서 연계할 수 있는지 확인합니다.audience Manager의 프로필 병합 규칙을 통해 [적절하게 사용하십시오](../../features/profile-merge-rules/merge-rules-overview.md).

## 조직 준비:비즈니스 프로세스 수립

* 데이터 주체의 요청을 받고 응답하는 프로세스를 식별합니다. Audience Manager에 요청을 제출할 수 있는 자동화된 툴을 구축하는 것이 좋습니다.
* 탁월한 DMP 센터에서 개인 정보 보호 담당자를 지정할 수 있습니다. 조직의 개인 정보 보호 담당자와 Audience Manager 제품 사용 팀과 연결하여 입력 ID 요구 사항을 관리하는 방법을 이해합니다.
* 데이터 주체와 공유하기 전에 데이터 검토를 수행합니다. 적절한 단계를 문서화하여 책임을 확정할 수 있습니다.
