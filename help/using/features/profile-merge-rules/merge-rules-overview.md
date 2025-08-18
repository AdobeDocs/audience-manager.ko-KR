---
description: 프로필 병합 규칙 을 통해 세그멘테이션에 사용되는 데이터 세트를 제어할 수 있고 여러 디바이스에서 개인을 정확하게 타깃팅할 수 있습니다.
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: 프로필 병합 규칙 개요
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# [!UICONTROL Profile Merge Rules] 개요 {#profile-merge-rules-overview}

[!UICONTROL Profile Merge Rules]을(를) 사용하면 세그먼테이션에 사용되는 데이터 집합을 제어하고 여러 장치에서 사용자를 정확하게 타깃팅할 수 있습니다.

>[!VIDEO](https://video.tv.adobe.com/v/31964?captions=kor)

## 익명 및 인증된 프로필로 데이터 수집 및 타겟팅 {#data-collection-targeting}

일반적으로 대상 세분화 및 타깃팅은 장치의 모든 사용자로부터 수집된 데이터에 의존합니다. 디바이스 수준 데이터를 기반으로 한 데이터 수집 및 타겟팅에는 몇 가지 단점이 있습니다. 예를 들어, 디바이스를 공유하는 여러 사용자를 구별하거나 여러 디바이스의 사용자를 정확하게 타겟팅할 수 없습니다. 장치 중심 데이터 수집은 더 이상 디지털 마케팅 캠페인이나 크로스 디바이스 타깃팅에 충분하지 않습니다.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules]은(는) 기본적으로 [!DNL Audience Manager]이(가) 타깃팅을 위해 사용자와 세그먼트를 수집하는 방법을 변경합니다. 장치 프로필과 [인증된 프로필](../../reference/visitor-authentication-states.md)이라는 두 가지 유형의 프로필을 사용하여 작업할 수 있습니다.

| 프로필 유형 | 설명 |
|---|---|
| [!UICONTROL Device Profile] | [!UICONTROL device profile]은(는) [!UICONTROL cookie] ID 또는 모바일 장치 ID와 같은 특정 장치의 ID에 연결되어 있습니다.<br><br> 다음을 포함합니다.<ul><li>사용자가 인증되지 않은 경우 [!UICONTROL Rule-based traits]이(가) 인식됩니다.</li><li>[!UICONTROL Onboarded traits]이(가) [!UICONTROL cookie-based], 타사 데이터와 같은 장치 ID에 연결되어 있습니다.</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile]은(는) 사용자가 사이트에 로그인할 때 전달된 사용자 ID에 연결되어 있습니다.<br><br>다음을 포함합니다.<ul><li>사용자가 인증되면 장치 간에 [!UICONTROL Rule-based traits]이(가) 수집됩니다.</li><li>동일한 사용자 ID에 연결된 오프라인 파일의 [!UICONTROL Onboarded traits].</li></ul> |

이러한 다양한 프로필은 세그멘테이션에 사용할 수 있는 데이터를 제어합니다. 예를 들어 [인증된 프로필](../../reference/visitor-authentication-states.md)을 사용하면 단일 사용자에 대해 여러 장치의 데이터를 기반으로 정확한 [!UICONTROL segments]을(를) 작성할 수 있습니다. 즉, 여러 장치의 고객에게 일관된 브랜드 경험을 제공할 수 있습니다. [!DNL Audience Manager]은(는) 사용자가 온라인 활동에 사용하는 다른 장치를 [인증된 프로필](../../reference/visitor-authentication-states.md)에 매핑하여 저장합니다. 이러한 매핑을 [!UICONTROL Profile Link Device Graph]이라고 합니다.

![](assets/authenticated2.png)

## 장점 {#advantages}

[!UICONTROL Profile Merge Rules]을(를) 사용하여 다음을 수행할 수 있습니다.

* [인증된 프로필](../../reference/visitor-authentication-states.md), 익명 프로필 또는 두 가지 모두의 조합을 기반으로 사용자를 타깃팅합니다.
* 디바이스 전체에서 특정 고객을 타겟팅합니다.
* 결정론적 데이터를 기반으로 디바이스 그래프를 작성합니다.
* 다른 프로필을 기준으로 [!UICONTROL segments]의 데이터를 미세 조정하십시오.
* 대상에 대한 추가 insight을 확보하십시오.
