---
description: 방문자 프로필 뷰어 를 사용하여 트레이트 및 세그먼트를 포함하여 현재 브라우저에 대한 사용자 프로필의 현재 상태를 표시할 수 있습니다. 각 트레이트에 대해 SID, 이름, 방문자 트레이트가 실현된 방법에 대한 세부 정보(자사 또는 타사), 실현 날짜 및 실현 빈도를 볼 수 있습니다. 각 세그먼트에 대한 SID, 이름 및 세그먼트 멤버십 날짜를 볼 수 있습니다. 다른 Audience Manager 프로필 ID(UUID)에 대한 방문자 프로필을 볼 수도 있습니다. 방문자 프로필 뷰어는 문제 해결 목적으로 유용합니다.
keywords: 위치;위치 매개 변수
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: 방문자 프로필 뷰어
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# 방문자 프로필 뷰어 {#visitor-profile-viewer}

[!UICONTROL Visitor Profile Viewer]을(를) 사용하여 특성 및 세그먼트를 포함하여 현재 브라우저에 대한 사용자 프로필의 현재 상태를 표시합니다. 각 트레이트에 대해 해당 [!UICONTROL SID], 이름, 방문자 트레이트가 실현된 방식에 대한 세부 정보(자사 또는 타사), 실현 날짜 및 실현 빈도를 볼 수 있습니다. 각 세그먼트에 대해 [!UICONTROL SID], 이름 및 세그먼트 멤버십 날짜를 볼 수 있습니다. 다른 Audience Manager 프로필 ID([!UICONTROL UUID])에 대한 방문자 프로필을 볼 수도 있습니다. [!UICONTROL Visitor Profile Viewer]은(는) 문제 해결에 유용합니다.

>[!NOTE]
>
>* 액세스하려면 [!UICONTROL Administrator] 권한이 필요합니다.
>* 실현된 세그먼트 및 온보딩된 트레이트에 대한 정보가 사용자 인터페이스에 나타나려면 24시간이 지연됩니다.

<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**&#x200B;을(를) 클릭합니다.

1. *(선택 사항)* 특성 이름을 클릭하여 [!UICONTROL Trait Builder]에 해당 특성을 표시합니다.

   자세한 내용은 [트레이트](../features/traits/trait-details-page.md)를 참조하세요.

1. *(선택 사항)* 세그먼트 이름을 클릭하여 [!UICONTROL Segment Builder]에 해당 세그먼트를 표시합니다.

   자세한 내용은 [세그먼트](../features/segments/segments-purpose.md)를 참조하십시오.

1. *(조건부)* **[!UICONTROL UUID]** 상자에서 다른 Audience Manager 프로필 ID를 지정한 다음 **[!UICONTROL Refresh]**&#x200B;을(를) 클릭하여 해당 사용자의 트레이트 및 세그먼트를 봅니다.
