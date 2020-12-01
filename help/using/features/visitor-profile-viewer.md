---
description: 방문자 프로필 뷰어를 사용하여 트레이트 및 세그먼트를 포함하여 현재 브라우저에 대한 사용자 프로필의 현재 상태를 표시합니다. 각 트레이트에 대해 SID, 이름, 방문자 트레이트 구현 방법(퍼스트 파티 또는 서드 파티), 구현 날짜 및 재조명 빈도를 볼 수 있습니다. 각 세그먼트에 대해 SID, 이름 및 세그먼트 멤버십 날짜를 볼 수 있습니다. 다른 Audience Manager 프로필 ID(UUID)에 대한 방문자 프로필을 볼 수도 있습니다. 방문자 프로필 뷰어는 문제 해결을 위해 유용합니다.
keywords: location;location parameter
seo-description: 방문자 프로필 뷰어를 사용하여 트레이트 및 세그먼트를 포함하여 현재 브라우저에 대한 사용자 프로필의 현재 상태를 표시합니다. 각 트레이트에 대해 SID, 이름, 방문자 트레이트 구현 방법(퍼스트 파티 또는 서드 파티), 구현 날짜 및 재조명 빈도를 볼 수 있습니다. 각 세그먼트에 대해 SID, 이름 및 세그먼트 멤버십 날짜를 볼 수 있습니다. 다른 Audience Manager 프로필 ID(UUID)에 대한 방문자 프로필을 볼 수도 있습니다. 방문자 프로필 뷰어는 문제 해결을 위해 유용합니다.
seo-title: 방문자 프로필 뷰어
solution: Audience Manager
title: 방문자 프로필 뷰어
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 2%

---


# 방문자 프로필 뷰어 {#visitor-profile-viewer}

[!UICONTROL Visitor Profile Viewer]을(를) 사용하여 현재 브라우저에 대한 사용자 프로필의 현재 상태(트레이트 및 세그먼트 포함)를 표시합니다. 각 트레이트에 대해 [!UICONTROL SID], 이름, 방문자 트레이트가 실현되는 방법(퍼스트 파티 또는 서드 파티), 구현 날짜 및 재조명 빈도를 볼 수 있습니다. 각 세그먼트에 대해 [!UICONTROL SID], 이름 및 세그먼트 멤버십 날짜를 볼 수 있습니다. 다른 Audience Manager 프로필 ID([!UICONTROL UUID])에 대한 방문자 프로필을 볼 수도 있습니다. [!UICONTROL Visitor Profile Viewer]은 문제 해결에 유용합니다.

>[!NOTE]
>
>* 액세스하려면 [!UICONTROL Administrator] 권한이 필요합니다.
>* 실현된 세그먼트와 온보드 트레이트에 대한 정보가 사용자 인터페이스에 표시되기 전에 24시간이 지연됩니다.


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. 클릭 **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *(선택 사항)* 트레이트 이름을 클릭하여 트레이트를 에 표시합니다 [!UICONTROL Trait Builder].

   자세한 내용은 [트레이트](../features/traits/trait-details-page.md)를 참조하십시오.

1. *(선택 사항)* 세그먼트 이름을 클릭하여 세그먼트에 표시합니다 [!UICONTROL Segment Builder].

   자세한 내용은 [세그먼트](../features/segments/segments-purpose.md)를 참조하십시오.

1. *(조건부)*  **[!UICONTROL UUID]** 상자에서 다른 Audience Manager 프로필 ID를 지정한 다음 을 클릭하여 해당 사용자의 트레이트와 세그먼트 **[!UICONTROL Refresh]** 를 봅니다.