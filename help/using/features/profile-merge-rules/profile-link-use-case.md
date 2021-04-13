---
description: 프로필 링크 장치 그래프를 사용한 세그먼트 리타겟팅 및 개인화된 세그먼트 자격 검증을 위한 Recommendations 및 사용 사례
seo-description: 프로필 링크 장치 그래프를 사용한 세그먼트 리타겟팅 및 개인화된 세그먼트 자격 검증을 위한 Recommendations 및 사용 사례
seo-title: 프로필 링크 장치 그래프 사용 사례
solution: Audience Manager
title: 프로필 링크 장치 그래프 사용 사례
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: 프로필 병합
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 9%

---

# 프로필 링크 장치 그래프 사용 사례 {#profile-link-device-graph-use-cases}

Recommendations 및 세그먼트 재타깃팅 및 [!UICONTROL Profile Link Device Graph]을(를) 통한 개인화된 세그먼트 자격 검증을 위한 사용 사례

## 권장 사항 {#recommendations}

다음의 캠페인에 대해 [!UICONTROL Profile Link] 장치 그래프를 고려합니다.

* 디지털 자산에서 높은 수준의 인증을 받을 수 있습니다. 인증된 사용자 수가 적은 경우 [외부 장치 그래프 옵션](merge-rule-definitions.md#device-options)을 사용합니다.
* 알려진 고객을 정확하게 타깃팅해야 합니다. [!UICONTROL Profile Link Device Graph]은(는) 인증된 첫 번째 데이터를 사용하여 만들어집니다.
* Target은 인증된 상태와 인증되지 않은 상태 전반의 대상을 실시간으로 파악했습니다.

![](assets/merge-rule-triangle2.png)

## 크로스 장치 타깃팅 {#cross-device-personalization}

John이 휴일 패키지 거래를 찾기 위해 정기적으로 사용하는 세 개의 장치를 가지고 있다고 가정해 봅시다.그의 노트북([!DNL Device 1]), 그의 스마트폰([!DNL Device 2]) 및 태블릿([!DNL Device 3]). 하지만, 존은 그의 장치를 사용하여 패키지 거래의 다른 항목을 검색합니다.

* 노트북으로 항공편을 검색한다.
* 그는 스마트폰을 이용해 호텔을 찾는다.
* 그는 자신의 태블릿을 사용하여 가이드 투어를 검색합니다.

John이 위에서 언급한 세 장치 모두에서 인증되지 않은 경우에도, **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** 규칙을 사용하여 휴일 패키지 제공자는 이 장치를 John의 인증된 프로필에 연결할 수 있습니다. 단, 마지막 사용자가 이 세 장치 모두에서 인증되었다고 가정합니다.

![마지막 장치 그래프](assets/last-device-graph.png)

Audience Manager은 세그먼트에 대해 프로필 병합에 참여한 모든 장치 프로파일을 일치시키므로 3개의 장치 프로필이 모두 세그먼트화됩니다. [!UICONTROL Profile Link Device Graph]을 사용하면 Audience Manager이 3개 장치 모두에서 동작을 확인하고 단일 장치 프로필이 자체적으로 적합하지 않은 세그먼트에 대해 모든 장치를 평가할 수 있습니다.

이 [!UICONTROL Profile Merge Rule]을 사용하면 마케터는 개별 장치 활동 대신 사용자 활동을 기반으로 한 사용자가 소유한 모든 장치에 일관된 경험을 제공할 수 있습니다.

![크로스 디바이스 개인화](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [외부 장치 그래프 사용 사례](external-graph-use-cases.md)
>* [프로필 병합 규칙에 대한 일반 사용 사례](merge-rule-targeting-options.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

