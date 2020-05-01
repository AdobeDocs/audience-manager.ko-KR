---
description: Audience Lab 기능에 대한 FAQ
seo-description: Audience Lab 기능에 대한 FAQ
seo-title: Audience Lab FAQ
solution: Audience Manager
title: Audience Lab FAQ
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Audience Lab FAQ{#audience-lab-faq}

Audience Lab 기능에 대한 FAQ

<!-- 

audience-lab-faq.xml

 -->

<br> 

**테스트 그룹에서 만든 테스트 세그먼트에 다른 세그먼트 ID가 있습니까? ID를 다른 대상에 매핑하려면 어떻게 해야 합니까?**

예. 테스트 세그먼트에는 다른 세그먼트 ID가 있습니다. 대상 [!UICONTROL Auto-fill Destination Mapping] 이 있거나 세그먼트 [!DNL Google][!UICONTROL Audience Lab] 가 전송된 대상의 경우, 목적지가 정상적으로 수행하는 것처럼 매핑 값을 처리합니다.

<br> 

**동일한 전환 트레이트를 여러 테스트 그룹과 연결할 수 있습니까?**

네, 가능합니다. 전환 X에 연결된 남성 세그먼트를 사용하는 한 테스트와 전환 X에 연결된 여성 세그먼트를 사용하는 한 테스트의 경우를 생각해 보십시오. 두 테스트 모두 서로 다른 두 대상을 테스트하므로 전환을 유도하는 것은 문제가 되지 않습니다.

<br> 

**테스트 그룹이 테스트 세그먼트 분할에 대해 인증된 프로필을 사용하고 있다고 가정합니다. 인증된 프로필은 4개의[Audience Manager UUID에 연결되어 있습니다](../reference/ids-in-aam.md). 방문자가 4개의 UUID 중 하나에서 전환 트레이트를[!UICONTROL Audience Lab]발견하면 1개 또는 4개의 전환으로 계산합니까?**

이 경우 한 [!UICONTROL Audience Lab] 개의 전환만 계산합니다.

<br> 

**위의 사례에서 방문자가 먼저 인증된 프로필과 연결된 4개의 UUID 중 하나에서 전환 트레이트를 보여준 다음 인증된 프로필에 연결된 2개의 다른 UUID에서 전환 트레이트를 나타내면 어떻게 됩니까? 이 경우 1 또는 3개의 전환으로 계산됩니까?**

이 경우, 인증 트레이트를 표시했던 각 장치에 대해 1개의 전환으로 세 개의 전환을 계산합니다. [!UICONTROL Audience Lab]

<br> 

**사용자가[!UICONTROL Segment: Read-Only]액세스할 수 있지만 세그먼트 생성 액세스도[!UICONTROL Audience Lab]테스트할 수 있습니까?**

권한 [과 함께](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 사용하는 방법에 대한 자세한 내용은 세그먼트 테스트 그룹 [!UICONTROL Audience Lab] 만들기를 [!UICONTROL RBAC] 참조하십시오.

**및 외부 장치 그래프[!UICONTROL Audience Lab]와 함께 사용할 수[!UICONTROL Profile Link Device Graph]있습니까([Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html), Tapad Device Graph, Liveramp Device Graph)?**

현재 세그먼트 모집단을 사용할 때 적격한 장치에 연결된 장치별로 분할할 [!UICONTROL Audience Lab] 수 있습니다 [!UICONTROL Profile Link Device Graph]. 다른 디바이스 그래프에 대한 지원 [!UICONTROL Audience Lab] 을 추가하려고 노력하고 있으며 지원 시기를 알려드릴 것입니다.
