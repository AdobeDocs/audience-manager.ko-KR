---
description: 방문자 프로필 뷰어를 사용하여 특성 및 세그먼트를 포함하여 현재 브라우저에 대한 사용자 프로필의 현재 상태를 표시할 수 있습니다. 각 트레이트 동안 SID, 이름, 방문자 트레이트를 실현한 방법 (첫 번째 또는 서드 파티), 실현일 및 실현빈도수를 볼 수 있습니다. 각 세그먼트에 대해 SID, 이름 및 세그먼트 멤버십 날짜를 볼 수 있습니다. 다른 Audience Manager 프로필 ID (UUID) 에 대한 방문자 프로필을 볼 수도 있습니다. 방문자 프로필 뷰어는 문제 해결에 유용합니다.
keywords: 위치; 위치 매개 변수
seo-description: 방문자 프로필 뷰어를 사용하여 특성 및 세그먼트를 포함하여 현재 브라우저에 대한 사용자 프로필의 현재 상태를 표시할 수 있습니다. 각 트레이트 동안 SID, 이름, 방문자 트레이트를 실현한 방법 (첫 번째 또는 서드 파티), 실현일 및 실현빈도수를 볼 수 있습니다. 각 세그먼트에 대해 SID, 이름 및 세그먼트 멤버십 날짜를 볼 수 있습니다. 다른 Audience Manager 프로필 ID (UUID) 에 대한 방문자 프로필을 볼 수도 있습니다. 방문자 프로필 뷰어는 문제 해결에 유용합니다.
seo-title: 방문자 프로필 뷰어
solution: Audience Manager
title: 방문자 프로필 뷰어
uuid: 77 ffe 134-E 08 F -41 DE -8 FC 4-15494847 B 1 D 0
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Visitor Profile Viewer {#visitor-profile-viewer}

Use the [!UICONTROL Visitor Profile Viewer] to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its [!UICONTROL SID], name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its [!UICONTROL SID], name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID ([!UICONTROL UUID]). The [!UICONTROL Visitor Profile Viewer] is helpful for troubleshooting purposes.

>[!NOTE]
>
>* Access requires [!UICONTROL Administrator] permissions.
>* 구현된 세그먼트와 온보드 트레이트에 대한 정보가 사용자 인터페이스에 표시되기 전에 24 시간 지연이 있습니다.


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. **[!UICONTROL Tools]****[!UICONTROL Visitor Profile Viewer]**&gt;를 클릭합니다.

1. *(선택 사항)* 트레이트 이름을 클릭하여 해당 트레이트를에 [!UICONTROL Trait Builder]표시합니다.

   For more information, see [Traits](../features/traits/trait-details-page.md).

1. *(선택 사항)* 세그먼트 이름을 클릭하여 해당 세그먼트를에 [!UICONTROL Segment Builder]표시합니다.

   For more information, see [Segments](../features/segments/segments-purpose.md).

1. *(조건부)* **[!UICONTROL UUID]** 상자에서 다른 Audience Manager 프로필 ID를 지정한 다음을 클릭하여 **[!UICONTROL Refresh]** 해당 사용자의 트레이트 및 세그먼트를 봅니다.