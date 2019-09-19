---
description: Audience Lab 기능에 대한 FAQ입니다.
seo-description: Audience Lab 기능에 대한 FAQ입니다.
seo-title: Audience Lab FAQ
solution: Audience Manager
title: Audience Lab FAQ
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab FAQ{#audience-lab-faq}

Audience Lab 기능에 대한 FAQ입니다.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**테스트 그룹에서 만든 테스트 세그먼트에 다른 세그먼트 ID가 있습니까? ID 파섹**

예. 테스트 세그먼트에는 다른 세그먼트 ID가 있습니다. 대상이 [!UICONTROL Auto-fill Destination Mapping] 있거나 세그먼트가 전송된 대상의 [!DNL Google][!UICONTROL Audience Lab] 경우, 대상이 정상적으로 이루어지는 것과 같이 매핑 값을 처리합니다.

<br> 

**동일한 전환 트레이트를 여러 테스트 그룹과 연결할 수 있습니까?**

네, 가능합니다. 전환 X에 연결된 남성 세그먼트를 사용하는 테스트와 전환 X에 연결된 여성 세그먼트를 사용하는 하나의 테스트 사례를 생각해 보십시오.두 테스트 모두 서로 다른 두 고객을 테스트하고 있으므로 전환율을 높이는 것은 중요하지 않습니다.

<br> 

**테스트 그룹이 테스트 세그먼트 분할에 대해 인증된 프로필을 사용하고 있다고 가정해 보겠습니다. 인증된 프로필은 4개의 Audience Manager[UUID에 연결됩니다](../reference/ids-in-aam.md). 방문자가 4개의 UUID 중 하나에서 전환 트레이트를 표시할 때 1개 또는 4개의 전환으로[!UICONTROL Audience Lab]계산됩니까?**

이 경우 [!UICONTROL Audience Lab] 하나의 전환만 계산합니다.

<br> 

**위의 사례 방문자가 먼저 인증된 프로필과 연결된 4개의 UUID 중 하나에서 전환 트레이트를 보여준 다음 인증된 프로필에 연결된 2개의 다른 UUID에서 전환 트레이트를 표시하는 경우 어떻게 합니까? 이 경우 1 또는 3개의 전환으로 계산됩니까?**

이 경우, 인증 트레이트를 표시한 장치마다 각각 하나씩, 세 개의 전환을 [!UICONTROL Audience Lab] 계산합니다.

<br> 

**사용자가[!UICONTROL Segment: Read-Only]액세스할 수 있지만 세그먼트 생성 액세스도[!UICONTROL Audience Lab]테스트할 수 있습니까?**

권한과 [함께 사용하는](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 방법에 대한 자세한 내용은 세그먼트 테스트 그룹 만들기를 [!UICONTROL Audience Lab] [!UICONTROL RBAC] 참조하십시오.

**외부 장치 그래프(Adobe Experience Cloud Device Co-op,[!UICONTROL Audience Lab]Tapad Device Graph, Liveramp Device Graph[!UICONTROL Profile Link Device Graph][](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html))와 함께 사용할 수 있습니까?**

현재 [!UICONTROL Audience Lab] 세그먼트 모집단을 사용할 때 적격한 장치에 연결된 장치별로 분할할 수 [!UICONTROL Profile Link Device Graph]있습니다. Adobe는 다른 장치 그래프에 [!UICONTROL Audience Lab] 대한 지원을 추가하고 있으며 지원 시기를 알려드릴 것입니다.
