---
description: Audience Lab 기능에 대한 FAQ 입니다.
seo-description: Audience Lab 기능에 대한 FAQ 입니다.
seo-title: Audience Lab FAQ
solution: Audience Manager
title: Audience Lab FAQ
topic: DIL API
uuid: b 1 daf 99 d-af 60-4 f 65-987 d -794 a 6 d 45 d 566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab FAQ{#audience-lab-faq}

Audience Lab 기능에 대한 FAQ 입니다.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**테스트 그룹에서 만들어진 테스트 세그먼트에는 서로 다른 세그먼트 ID가 있습니까? How do I map the IDs to different destinations?**

예. 테스트 세그먼트에는 서로 다른 세그먼트 ID가 있습니다. For destinations with [!UICONTROL Auto-fill Destination Mapping] or segments sent to [!DNL Google], [!UICONTROL Audience Lab] will handle the mapping values just like the destinations normally would.

<br> 

**동일한 전환 트레이트를 여러 테스트 그룹과 연결할 수 있습니까?**

예, 가능합니다. 전환 X와 연관된 남성 세그먼트를 사용하는 한 테스트, 전환 X와 연관된 여성 세그먼트를 사용하는 한 테스트 경우를 생각해 보십시오. 두 테스트 모두 두 개의 서로 다른 고객을 테스트하고 있으므로 전환율을 높일 수 있습니다.

<br> 

**테스트 그룹이 테스트 세그먼트 분할에 대해 인증된 프로필을 사용하고 있다고 가정합니다. The authenticated profile is linked to 4[Audience Manager UUIDs](../reference/ids-in-aam.md). When the visitor exhibits a conversion trait from one of the four UUIDs, does[!UICONTROL Audience Lab]count this as one or four conversions?**

In this case, [!UICONTROL Audience Lab] only counts one conversion.

<br> 

**위의 사례에서 방문자가 먼저 인증된 프로필에 연결된 네 개의 UUID 중 하나에서 전환 트레이트를 확인한 후, 인증된 프로필에 연결된 다른 두 UI에서 전환 트레이트를 표시하는 경우 어떻게 됩니까? Does this case count as one or three conversions?**

In this case, [!UICONTROL Audience Lab] counts three conversions, one for each device that has exhibited the authentication trait.

<br> 

**사용자가 액세스할 수[!UICONTROL Segment: Read-Only]있지만 세그먼트 작성 액세스도[!UICONTROL Audience Lab]테스트할 수 있습니까?**

See [Create Segment Test Group](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) for information on how to use [!UICONTROL Audience Lab] with [!UICONTROL RBAC] privileges.

**외부[!UICONTROL Audience Lab]장치 그래프[!UICONTROL Profile Link Device Graph]([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Tapad Device Graph, Liveramp 장치 그래프) 와 함께 사용할 수 있습니까?**

For now, [!UICONTROL Audience Lab] can only split out segment populations by the devices connected to a qualifying device, when using the [!UICONTROL Profile Link Device Graph]. We are working on adding support in [!UICONTROL Audience Lab] for the other device graphs and will let you know when we do so.
