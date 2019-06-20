---
description: 세그먼트 빌더로 세그먼트를 만드는 방법을 설명합니다.
seo-description: 세그먼트 빌더로 세그먼트를 만드는 방법을 설명합니다.
seo-title: 세그먼트 빌더
solution: Audience Manager
title: 세그먼트 빌더
uuid: 5 CA 924 A 5-2 B 29-4802-AB 02-E 292 D 77 A 0 AAE
translation-type: tm+mt
source-git-commit: b346dbe500f1e662c7b121a18c6cc0704ef3cfac

---


# 세그먼트 빌더 {#segment-builder}

Describes the required and optional steps that create a segment in [!UICONTROL Segment Builder].

## 세그먼트 만들기 {#create-segment}

### 세그먼트 빌더 섹션

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 세 개의 별도 섹션으로 구성됩니다. [!UICONTROL Basic Information], [!UICONTROL Traits]및 [!UICONTROL Destinations Mapping]. To create a segment, complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. [!UICONTROL Destinations Mapping] 설정은 선택 사항입니다. 추가 도움말은 아래 지침을 참조하십시오.

1. In the [Basic Information](../../features/segments/segment-builder.md#segment-builder-controls-basics) section:
   * 세그먼트 이름을 지정합니다. 세그먼트 이름의 최대 길이는 255 자입니다.
   * 세그먼트 상태를 설정합니다 (활성은 기본값).
   * 데이터 소스를 선택합니다.
   * 세그먼트 자격 조건에 사용할 프로필 병합 규칙을 선택합니다.
   * 저장소 폴더에 세그먼트를 할당합니다.
1. [traits](../../features/segments/segment-builder.md#segment-builder-controls-traits) 섹션에서 다음을 수행합니다.
   * Search for the trait you want to add to a segment and click **[!UICONTROL Add Trait]**. 다른 트레이트를 추가하여 트레이트 그룹을 만듭니다.
   * Bring up the Advanced Search modal by clicking **[!UICONTROL Browse All Traits]**. 이름, ID, 설명 또는 데이터 소스별로 트레이트를 검색할 수 있습니다. 검색 중에 폴더를 클릭하여 해당 폴더 및 하위 폴더로 결과를 제한합니다. 트레이트 유형별로 트레이트를 필터링할 수도 있습니다.
   * Get live [trait recommendations](trait-recommendations.md) as you build your segment.
   * 트레이트를 클릭하고 드래그하여 별도의 그룹을 만듭니다.
   * Hover between groups to set relationships with Boolean [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] values.
   * Hover over the clock icon to add [recency and frequency](../../features/segments/recency-and-frequency.md) rules to the trait.
   * 트레이트를 추가하거나 제거할 때 세그먼트 모집단 데이터를 볼 수 있습니다. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers. Read more about [segment population data](../../features/segments/segment-builder-data.md#segment-populations) in the Segment Builder.
   * Click **[!UICONTROL Save]** when done.
1. *(선택 사항)* [대상 매핑](../../features/segments/segment-builder.md#segment-builder-controls-destinations) 섹션의 대상에 세그먼트를 매핑합니다.
   * Search for the destination and click **[!UICONTROL Add Destination]**. 세그먼트를 세그먼트에 추가하려면 먼저 대상이 존재해야 합니다.
   * Click **[!UICONTROL Save]** when done.

## Segment Builder Controls: Basic Information Section {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] settings let you create new, or edit existing traits. 새 세그먼트를 만들려면 이름, 데이터 소스를 지정하고 저장소 폴더를 선택합니다. 다른 모든 필드는 선택 사항입니다. Move on to the [!UICONTROL Traits] section when done.

<!-- r_segment_basic_info_section.xml -->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 필드 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> 이름 </b> </td> 
   <td colname="col2"> <p>세그먼트에 함수 또는 목적을 설명하는 짧고 논리적인 이름을 지정합니다. 약자 및 특수 문자를 사용하지 마십시오. 세그먼트 이름의 최대 길이는 255 자입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>설명</b> </td> 
   <td colname="col2"> <p>세그먼트에 대한 추가 설명 정보를 위한 필드입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>통합 코드</b> </td> 
   <td colname="col2"> <p>사용자 정의 ID 또는 기타 회사별 정보에 대한 필드입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>데이터 소스</b> </td> 
   <td colname="col2"> <p>세그먼트를 특정 데이터 공급자에 연결합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>프로필 병합 규칙</b> </td> 
   <td colname="col2"> <p>세그먼트 자격 조건에 사용할 프로필 병합 규칙을 선택합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>상태</b> </td> 
   <td colname="col2"> <p>세그먼트를 활성화 또는 비활성화합니다 (기본적으로 활성). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>폴더 저장소</b> </td> 
   <td colname="col2"> <p>세그먼트가 속한 저장소 폴더를 결정합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment Builder Controls: Traits Section {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], the [!UICONTROL Traits] section lets you manage traits in a segment, create trait groups, and set qualification criteria. To add a trait to a segment, type the trait name in the search field and click [!UICONTROL Add Trait]. Save the trait (if finished) or move on to [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**전제 조건:** 섹션의 필수 필드를 [!UICONTROL Basic Information] 완료합니다.

| 필드 | 설명 |
|--- |--- |
| 기본 보기 | 이 섹션에서는 다음을 수행할 수 있는 시각적 컨트롤을 제공합니다. <ul><li>새로운 세그먼트 작성 및 기존 세그먼트 관리</li><li>세그먼트에서 트레이트를 제거할 수 있습니다.</li><li>세그먼트에 최대 50 개의 트레이트를 추가합니다.</li><li>트레이트를 드래그하여 놓아 새 그룹을 만듭니다.</li><li>세그먼트에서 트레이트 및 트레이트 그룹을 볼 수 있습니다.</li><li>부울 표현식, 비교 연산자 및 최근/빈도 설정으로 자격 기준을 설정할 수 있습니다.</li></ul> |
| 코드 뷰 | 시각적 인터페이스 대신 코드를 사용하여 특성, 그룹 및 자격 조건을 만들고 관리할 수 있는 개발 환경을 엽니다. 코드 보기는 세그먼트에 다음과 같은 경우에 유용합니다. <ul><li>개별 세그먼트에 50 개 이상의 트레이트를 포함합니다. 참고: 세그먼트는 5000 개의 트레이트 (최대) 로 제한됩니다.</li><li>여러 특성 그룹을 포함합니다.</li><li>복잡한 자격 조건을 갖추고 있습니다.</li></ul> |
| 검색 | 세그먼트에 추가할 트레이트를 찾는 데 도움이 됩니다. |
| 권장 사항 | 비슷한 트레이트에 대한 라이브 추천을 사용하여 세그먼트 규칙에 추가합니다. Read more in [Trait Recommendations](trait-recommendations.md). |
| 실제 예상 세그먼트 크기 데이터 | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Remove Traits from a Segment {#remove-traits}

세그먼트의 특성을 관리하는 것은 세그먼트를 가능한 상태로 유지하는 중요한 부분입니다. 세그먼트에서 트레이트를 제거해야 하는 경우 다음 단계를 따르십시오.

세그먼트에서 트레이트를 제거하려면 다음을 수행하십시오.

1. **대상 데이터 &gt; 세그먼트로 이동합니다**. 목록을 스크롤하거나 검색 기능을 사용하여 작업할 세그먼트를 찾습니다.
2. 세그먼트 이름을 클릭하여 세그먼트 세부 사항 화면을 엽니다.
3. **편집을** 클릭하여 세그먼트 빌더를 연 다음 **트레이트를** 클릭하여 트레이트 패널을 엽니다.
4. 삭제할 트레이트 위로 마우스를 가져간 다음 X를 클릭합니다. 이렇게 하면 세그먼트에서 트레이트가 즉시 제거됩니다.

## Segment Builder Controls: Destinations Mappings Section {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], the optional [!UICONTROL Destinations Mapping] section lets you send segment data to a third-party [!DNL cookie], [!DNL URL], or server-to-server destination. To add a destination, search (or browse) for a destination, provide destination specific information, and click **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### 전제 조건

[!UICONTROL Basic Information] AND [!UICONTROL Traits] 섹션에서 필수 필드를 완료합니다. 또한 대상이 이미 존재해야 합니다.

### 대상 매핑 검색 도구

**[!UICONTROL Destination Mappings]** 패널에 아래 표에 설명된 검색 도구가 포함되어 있습니다.

| 검색 유형 | 설명 |
|---|---|
| **대상 이름별로 검색** | 이름별로 특정 대상을 검색할 수 있습니다. 검색하려면 입력을 시작합니다. 필드는 검색어를 기준으로 자동 완성 됩니다. Click **[!UICONTROL Add Destination]** when done. |
| **모든 대상 찾아보기** | *사용 가능한* 모든 대상 목록을 찾아보십시오. 팝업 목록에서 세그먼트를 선택하여 세그먼트에 추가합니다. |

## Fields in the Destination Mappings Pop-up Windows {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], the [!UICONTROL Add Destination] dialog appears after you select a destination. 이 창에는 대상에 대한 정적 정보와 대상 유형에 따라 달라지는 필드가 표시됩니다. 빈 필드에 필요한 정보를 제공하여 대상 매핑을 설정합니다.

>[!NOTE]
>
>발행 날짜는 선택 사항입니다. 비어 있으면 대상이 활성화되고 만료되지 않습니다.

<!-- r_add_mappings_pop.xml -->

### 쿠키 대상 필드

[!UICONTROL Destination Mapping] 필드에 데이터를 대상으로 전송하는 데 사용되는 키-값 쌍을 지정합니다. 첫 번째 필드에 키를 입력하고 두 번째 필드에 값을 입력합니다. 쿠키 대상 팝업은 다음과 비슷합니다.

![](assets/cookie_modal.PNG)

### URL 대상 필드

[!UICONTROL URL] 및 [!UICONTROL Secure URL] 필드에 데이터를 대상으로 전송하는 데 사용되는 전체 표준 또는 보안 주소를 지정합니다.

![](assets/url_modal.PNG)

### 서버-서버 대상 필드

[!UICONTROL Destination Value] 필드에 데이터를 대상으로 전송하는 데 사용되는 값 (키-값 쌍의 일부) 를 지정합니다.

![](assets/s2s_modal.PNG)

>[!MORE_ like_ this]
>
>* [쿠키 대상 만들기](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [URL 대상 만들기](../../features/destinations/manage-destinations.md#configure-url-destination)

