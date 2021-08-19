---
description: 대상 랩 기능에 대한 FAQ
seo-description: 대상 랩 기능에 대한 FAQ
seo-title: 대상 랩 FAQ
solution: Audience Manager
title: 대상 랩 FAQ
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
exl-id: 25bdabb5-2ba8-45d2-81ca-05c0590d7d96
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 98%

---

# 대상 랩 FAQ{#audience-lab-faq}

대상 랩 기능에 대한 FAQ

<!-- 

audience-lab-faq.xml

 -->

<br> 

**테스트 그룹에서 만든 테스트 세그먼트에 다양한 세그먼트 ID가 있습니까? ID를 다른 대상에 매핑하려면 어떻게 해야 합니까?**

예. 테스트 세그먼트에는 다양한 세그먼트 ID가 있습니다. [!UICONTROL Auto-fill Destination Mapping]을 사용하는 대상 또는 [!DNL Google]에 전송되는 세그먼트의 경우 [!UICONTROL Audience Lab]은 대상이 일반적으로 처리하는 것처럼 맵핑 값을 처리합니다.

<br> 

**동일한 전환 트레이트를 여러 테스트 그룹과 연결할 수 있습니까?**

예, 가능합니다. 전환 X에 연결된 남성 세그먼트를 사용하는 한 테스트와 전환 X에 연결된 여성 세그먼트를 사용하는 한 테스트의 경우를 생각해 보십시오. 두 테스트 모두 서로 다른 두 대상을 테스트하므로 전환을 유도하는 것은 문제가 되지 않습니다.

<br> 

**테스트 그룹이 테스트 세그먼트 분할에 대해 인증된 프로필을 사용하고 있다고 가정합니다. 인증된 프로필은 4개의 [Audience Manager UUID](../reference/ids-in-aam.md)에 연결되어 있습니다. 방문자가 4개의 UUID 중 하나로부터 전환 트레이트를 보이면 [!UICONTROL Audience Lab]은 이것을 1개의 전환으로 계산합니까, 아니면 4개의 전환으로 계산합니까?**

이 경우 한 [!UICONTROL Audience Lab]은 1개의 전환만 계산합니다.

<br> 

**위 경우의 방문자가 인증된 프로필과 연결된 4개의 UUID 중 하나로부터 전환 트레이트를 먼저 보인 다음, 인증된 프로필에 연결된 2개의 다른 UUID로부터도 전환 트레이트를 보이면 어떻게 됩니까? 이 경우 전환은 1개로 계산됩니까, 아니면 3개로 계산됩니까?**

이 경우, [!UICONTROL Audience Lab]은 인증 트레이트를 보였던 각 장치에 대해 1개씩, 모두 세 개의 전환을 계산합니다.

<br> 

**사용자는 [!UICONTROL Segment: Read-Only] 액세스 권한과 함께 [!UICONTROL Audience Lab] 테스트 세그먼트 생성 액세스 권한도 보유할 수 있습니까?**

[!UICONTROL RBAC] 권한과 함께 [!UICONTROL Audience Lab]을 사용하는 방법에 대한 내용은 [세그먼트 테스트 그룹 만들기](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)를 참조하십시오.

**[!UICONTROL Profile Link Device Graph] 및 외부 장치 그래프([Adobe Experience Cloud Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/home.html), Tapad 장치 그래프, Liveramp 장치 그래프)와 함께 [!UICONTROL Audience Lab]을 사용할 수 있습니까?**

현재, [!UICONTROL Audience Lab]은 [!UICONTROL Profile Link Device Graph]를 사용할 때 자격을 부여하는 장치에 연결된 장치로만 세그먼트 인구를 분할할 수 있습니다. [!UICONTROL Audience Lab]에서 다른 장치 그래프에 대한 지원을 추가하는 작업이 진행 중이며 추가되면 알려드리겠습니다.
