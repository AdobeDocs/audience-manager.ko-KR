---
description: 프로필 병합 규칙을 사용하면 세그멘테이션에 사용되는 데이터 세트를 제어할 수 있고 여러 장치에서 사람을 정확하게 타깃팅할 수 있습니다.
seo-description: 프로필 병합 규칙을 사용하면 세그멘테이션에 사용되는 데이터 세트를 제어할 수 있고 여러 장치에서 사람을 정확하게 타깃팅할 수 있습니다.
seo-title: 프로필 병합 규칙 개요
solution: Audience Manager
title: 프로필 병합 규칙 개요
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---


# [!UICONTROL Profile Merge Rules] 개요 {#profile-merge-rules-overview}

[!UICONTROL Profile Merge Rules]을 사용하면 세그먼테이션에 사용되는 데이터 세트를 제어할 수 있으며 여러 장치에서 사용자를 정확하게 타깃팅할 수 있습니다.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## 익명 및 인증된 프로필 {#data-collection-targeting} 포함 데이터 수집 및 타깃팅

일반적으로 고객 세분화 및 타깃팅은 디바이스의 모든 사용자가 수집한 데이터를 기반으로 합니다. 디바이스 수준 데이터를 기반으로 데이터 수집 및 타깃팅에 몇 가지 단점이 있습니다. 예를 들어 장치를 공유하는 여러 사용자를 구별하거나 여러 장치에서 사용자를 정확하게 타깃팅할 수 없습니다. 디바이스 중심의 데이터 수집만으로는 디지털 마케팅 캠페인 또는 크로스 디바이스 타깃팅에 충분하지 않습니다.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 기본적으로 타깃팅을 위해 사용자와 세그먼트를  [!DNL Audience Manager] 수집하는 방법을 변경합니다. 이 기능을 사용하면 2개의 서로 다른 프로필, 장치 프로필 및 [인증된 프로필](../../reference/visitor-authentication-states.md)을 사용하여 작업할 수 있습니다.

| 프로필 유형 | 설명 |
|---|---|
| [!UICONTROL Device Profile] | [!UICONTROL device profile]은 [!UICONTROL cookie] ID 또는 모바일 장치 ID와 같은 지정된 장치의 ID에 연결되어 있습니다.<br><br>이러한 서비스에는 다음이 포함됩니다.<ul><li>[!UICONTROL Rule-based traits] 사용자가 인증되지 않은 경우 실현됩니다.</li><li>[!UICONTROL Onboarded traits] 타사 데이터와 같은 장치 ID에  [!UICONTROL cookie-based]연결되어 있습니다.</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile]은 사용자가 사이트에 로그인할 때 전달된 사용자 ID에 연결되어 있습니다.<br><br>이러한 서비스에는 다음이 포함됩니다.<ul><li>[!UICONTROL Rule-based traits] 사용자가 인증될 때 장치 간에 수집됩니다.</li><li>[!UICONTROL Onboarded traits] 를 채우는 것이 좋습니다.</li></ul> |

이러한 다양한 프로필은 세그먼테이션에 사용할 수 있는 데이터를 제어합니다. 예를 들어, [인증된 프로필](../../reference/visitor-authentication-states.md)을 사용하면 단일 사용자에 대해 여러 장치의 데이터를 기반으로 정확한 [!UICONTROL segments]를 만들 수 있습니다. 이를 통해 다양한 디바이스를 사용하는 고객에게 일관된 브랜드 경험을 제공할 수 있습니다. [!DNL Audience Manager] achieve this by storing the different devices a mapping of a person for their online activities to their  [authenticated profile](../../reference/visitor-authentication-states.md). 이러한 매핑을 [!UICONTROL Profile Link Device Graph]이라고 합니다.

![](assets/authenticated2.png)

## 장점 {#advantages}

[!UICONTROL Profile Merge Rules]을 사용하여 다음을 수행할 수 있습니다.

* Target 사용자는 [인증된 프로필](../../reference/visitor-authentication-states.md), 익명 프로파일 또는 두 가지 조합을 기반으로 합니다.
* 모든 디바이스에서 특정 고객 Target
* 결정 데이터를 기반으로 디바이스 그래프를 만듭니다.
* 다른 프로필에 따라 [!UICONTROL segments]의 데이터를 세밀하게 조정합니다.
* 고객에 대한 추가 인사이트 확보
