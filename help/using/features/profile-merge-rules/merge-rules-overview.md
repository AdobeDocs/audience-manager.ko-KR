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
source-wordcount: '335'
ht-degree: 3%

---

# [!UICONTROL Profile Merge Rules] 개요 {#profile-merge-rules-overview}

포함 [!UICONTROL Profile Merge Rules] 세그먼테이션에 사용되는 데이터 세트를 제어하고 여러 디바이스에서 사용자를 정확하게 타깃팅할 수 있습니다.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## 익명 및 인증된 프로필로 데이터 수집 및 타겟팅 {#data-collection-targeting}

일반적으로 대상 세분화 및 타깃팅은 장치의 모든 사용자로부터 수집된 데이터에 의존합니다. 디바이스 수준 데이터를 기반으로 한 데이터 수집 및 타겟팅에는 몇 가지 단점이 있습니다. 예를 들어, 디바이스를 공유하는 여러 사용자를 구별하거나 여러 디바이스의 사용자를 정확하게 타겟팅할 수 없습니다. 장치 중심 데이터 수집은 더 이상 디지털 마케팅 캠페인이나 크로스 디바이스 타깃팅에 충분하지 않습니다.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 근본적으로 변경 방법 [!DNL Audience Manager] 은 타깃팅할 데이터 및 사용자를 수집합니다. 장치 프로필과 이라는 두 가지 유형의 프로필로 작업할 수 있습니다. [인증된 프로필](../../reference/visitor-authentication-states.md).

| 프로필 유형 | 설명 |
|---|---|
| [!UICONTROL Device Profile] | A [!UICONTROL device profile] 는 과 같은 특정 디바이스의 ID에 연결되어 있습니다. [!UICONTROL cookie] ID 또는 모바일 장치 ID.<br><br>이러한 서비스에는 다음이 포함됩니다.<ul><li>[!UICONTROL Rule-based traits] 사용자가 인증되지 않은 경우 인식됩니다.</li><li>[!UICONTROL Onboarded traits] 과 같은 장치 ID에 연결됨 [!UICONTROL cookie-based], 타사 데이터.</li></ul> |
| [!UICONTROL Authenticated Profile] | 다음 [!UICONTROL authenticated profile] 사용자가 사이트에 로그인할 때 전달된 사용자 ID에 연결되어 있습니다.<br><br>이러한 서비스에는 다음이 포함됩니다.<ul><li>[!UICONTROL Rule-based traits] 사용자가 인증되면 장치 간에 수집됩니다.</li><li>[!UICONTROL Onboarded traits] 동일한 사용자 ID에 연결된 오프라인 파일에서</li></ul> |

이러한 다양한 프로필은 세그멘테이션에 사용할 수 있는 데이터를 제어합니다. 예를 들어, [인증된 프로필](../../reference/visitor-authentication-states.md), 정확하게 빌드할 수 있습니다 [!UICONTROL segments] 단일 사용자에 대한 여러 장치의 데이터를 기반으로 합니다. 즉, 여러 장치의 고객에게 일관된 브랜드 경험을 제공할 수 있습니다. [!DNL Audience Manager] 은 개인이 온라인 활동에 사용하는 다양한 디바이스를 해당 디바이스에 매핑하여 저장합니다 [인증된 프로필](../../reference/visitor-authentication-states.md). 이러한 매핑을 라고 합니다. [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## 장점 {#advantages}

포함 [!UICONTROL Profile Merge Rules] 다음을 수행할 수 있습니다.

* Target 기준 [인증된 프로필](../../reference/visitor-authentication-states.md), 익명 프로필 또는 두 가지 모두를 조합하여 사용할 수 있습니다.
* 특정 고객을 해당 디바이스에서 Target.
* 결정론적 데이터를 기반으로 디바이스 그래프를 작성합니다.
* 의 데이터를 미세 조정하십시오. [!UICONTROL segments] 다른 프로필을 기반으로 합니다.
* 대상자에 대한 추가적인 통찰력을 얻으십시오.
