---
description: 세그먼트 빌더로 세그먼트를 만드는 방법에 대해 설명합니다.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: 세그먼트 빌더
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

에서 세그먼트를 만드는 필수 단계 및 선택적 단계에 대해 설명합니다. [!UICONTROL Segment Builder].

## 비디오 데모

다음 항목을 보는 것으로 시작하십시오. [Audience Manager 비디오에서 세그먼트 만들기](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). 이 비디오에서는 세그먼트 만들기 프로세스를 안내합니다. 자세한 내용은 아래 섹션을 참조하십시오.

## 웹 사이트에 있는 각각의 고유한 랜딩 위치에 대해 [!UICONTROL Segment] {#create-segment}

### 세그먼트 빌더 섹션

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 는 3개의 별도 섹션으로 구성됩니다. [!UICONTROL Basic Information], [!UICONTROL Traits], 및 [!UICONTROL Destinations Mapping]. 을(를) 만들려면 [!UICONTROL segment]에서 필수 필드를 작성합니다. [!UICONTROL Basic Information] 및 [!UICONTROL Traits] 섹션. [!UICONTROL Destinations Mapping] 설정은 선택 사항입니다. 추가 도움말은 아래 지침을 참조하십시오.

1. 다음에서 [기본 정보](../../features/segments/segment-builder.md#segment-builder-controls-basics) 섹션:

   ![create-segment](assets/create-segment.png)

   * 이름 지정 [!UICONTROL segment]. 의 최대 길이 [!UICONTROL segment] 이름은 255자입니다.
   * 설정 [!UICONTROL segment] 상태(활성은 기본값).
   * 선택 [!UICONTROL data source]. 첫 번째 드롭다운 메뉴를 사용하여 Audience Manager 간 필터링 [!UICONTROL data sources], Adobe Analytics 보고서 세트 또는 둘 다. 그런 다음 두 번째 드롭다운 메뉴를 사용하여 [!UICONTROL data source]. Adobe Analytics 보고서 세트를 사용하지 않는 경우 [!UICONTROL data source] 유형 선택기가 비활성화되고 Audience Manager 데이터 소스로만 기본 설정됩니다.
   * 선택 [!UICONTROL profile merge rule] 다음에 사용: [!UICONTROL segment] 자격 요건.
   * 할당 [!UICONTROL segment] 스토리지 폴더로.

1. 다음에서 [트레이트](../../features/segments/segment-builder.md#segment-builder-controls-traits) 섹션:
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * 검색 [!UICONTROL trait] 을(를) 세그먼트에 추가하고 **[!UICONTROL Add Trait]**. 다른 항목 추가 [!UICONTROL trait] 을(를) 만들려면 [!UICONTROL trait] 그룹입니다.
   * 을(를) 표시합니다. [!UICONTROL Advanced Search] 다음을 클릭하여 모달 **[!UICONTROL Browse All Traits]**. 검색 대상 [!UICONTROL traits] 이름, ID, 설명 또는 [!UICONTROL data source]. 검색 중에 폴더를 클릭하여 해당 폴더 및 그 하위 폴더로 결과를 제한합니다. 필터링할 수도 있습니다 [!UICONTROL traits] 작성자: [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded], 및 [!UICONTROL Algorithmic]) 또는 모집단 유형([장치 ID](../../reference/ids-in-aam.md) 및 [교차 장치 ID](../../reference/ids-in-aam.md)).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * 라이브 가져오기 [트레이트 권장 사항](trait-recommendations.md) 을(를) 작성하는 동안 [!UICONTROL segment].
   * 클릭하여 끌기 [!UICONTROL traits] 을 클릭하여 별도의 그룹을 생성합니다.
   * 그룹 간에 마우스를 가져가면 부울과의 관계를 설정할 수 있습니다. [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] 값.
   * 시계 아이콘 위로 마우스를 가져가 추가 [최신성 및 빈도](../../features/segments/recency-and-frequency.md) 에 대한 규칙 [!UICONTROL trait].
   * 추가하거나 제거할 때 세그먼트 모집단 데이터 보기 [!UICONTROL traits]. 클릭 **[!UICONTROL Calculate Estimates]** 예상 모집단 수를 보거나 새로 고칩니다. 자세한 내용 [세그먼트 모집단 데이터](../../features/segments/segment-builder-data.md#segment-populations) 다음에서 [!UICONTROL Segment Builder].
   * 클릭 **[!UICONTROL Save]** 완료 시.

1. *(선택 사항)* 매핑 [!UICONTROL segment] (으)로 [!UICONTROL destination] 다음에서 [대상 매핑](../../features/segments/segment-builder.md#segment-builder-controls-destinations) 섹션:
   * 검색 [!UICONTROL destination] 및 클릭 **[!UICONTROL Add Destination]**. 참고: [!UICONTROL destination] 에 추가하려면 먼저 이(가) 존재해야 합니다. [!UICONTROL segment].
   * 클릭 **[!UICONTROL Save]** 완료 시.

크로스 디바이스 지표가 작동하는 방식에 대한 자세한 내용은 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] 컨트롤: [!UICONTROL Basic Information] 섹션 {#segment-builder-controls-basics}

위치 [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] 설정을 사용하여 새 트레이트를 만들거나 기존 트레이트를 편집할 수 있습니다. 새로 만들려면 [!UICONTROL segment], 이름 입력, [!UICONTROL data source]스토리지 폴더를 선택합니다. 다른 모든 필드는 선택 사항입니다. 다음으로 이동 [!UICONTROL Traits] 섹션에 있는 마지막 항목이 될 필요가 없습니다.

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| 필드 | 설명 |
---------|----------
| **[!UICONTROL Name]** | 세그먼트에 기능 또는 목적을 설명하는 짧은 논리적 이름을 지정합니다. 약어 및 특수 문자를 사용하지 마십시오. 세그먼트 이름의 최대 길이는 255자입니다. |
| **[!UICONTROL Description]** | 세그먼트에 대한 추가 설명 정보를 위한 필드입니다. |
| **[!UICONTROL Integration Code]** | 사용자 정의 ID 또는 기타 특정 회사에 대한 정보를 위한 필드. |
| **[!UICONTROL Data Source]** | 세그먼트를 특정 데이터 공급자와 연결합니다. <br> 첫 번째 드롭다운 메뉴를 사용하여 Audience Manager 데이터 소스, Adobe Analytics 보고서 세트 또는 둘 다 간에 필터링합니다. 그런 다음 두 번째 드롭다운 메뉴를 사용하여 데이터 소스를 선택합니다. <br> Adobe Analytics 보고서 세트를 사용하지 않는 경우 데이터 소스 유형 선택기가 비활성화되고 기본값이 Audience Manager 데이터 소스로만 설정됩니다. |
| **[!UICONTROL Profile Merge Rule]** | 세그먼트 자격에 사용할 프로필 병합 규칙을 선택합니다. |
| **[!UICONTROL Status]** | 세그먼트를 활성화하거나 비활성화합니다(기본적으로 활성화됨). |
| **폴더 스토리지** | 세그먼트가 속한 저장소 폴더를 결정합니다. |

## [!UICONTROL Segment Builder] 컨트롤: [!UICONTROL Traits] 섹션 {#segment-builder-controls-traits}

위치 [!UICONTROL Segment Builder], [!UICONTROL Traits] 섹션을 통해 다음을 관리할 수 있습니다. [!UICONTROL traits] 다음 기간: [!UICONTROL segment], 만들기 [!UICONTROL trait] 을 그룹화하고 자격 기준을 설정합니다. 을(를) 추가하려면 [!UICONTROL trait] (으)로 [!UICONTROL segment], 다음을 입력합니다. [!UICONTROL trait] 검색 필드에 이름을 지정하고 [!UICONTROL Add Trait]. 저장 [!UICONTROL trait] (완료된 경우) 또는 다음으로 이동 [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**사전 요구 사항:** 의 필수 필드를 작성합니다. [!UICONTROL Basic Information] 섹션.

| 필드 | 설명 |
|--- |--- |
| **[!UICONTROL Basic View]** | 이 단원에서는 다음과 같은 시각적 컨트롤을 제공합니다. <ul><li>새로 작성 및 기존 항목 관리 [!UICONTROL segments].</li><li>제거 [!UICONTROL traits] 다음에서: [!UICONTROL segment].</li><li>최대 50개(최대) 추가 [!UICONTROL traits] (으)로 [!UICONTROL segment].</li><li>드래그 앤 드롭 [!UICONTROL traits] 새 그룹을 만들 수 있습니다.</li><li>보기 [!UICONTROL traits] 및 [!UICONTROL trait] 의 그룹 [!UICONTROL segment].</li><li>부울 표현식, 비교 연산자 및 최신성/빈도 설정을 사용하여 자격 기준을 설정합니다.</li></ul> |
| **[!UICONTROL Code View]** | 만들고 관리할 수 있는 개발 환경을 엽니다. [!UICONTROL traits], 그룹 및 자격 요구 사항(시각적 인터페이스 대신 코드 사용) 코드 보기는 [!UICONTROL segments]: <ul><li>50개 이상 포함 [!UICONTROL traits] 개인 사용자 [!UICONTROL segment]. 참고: [!UICONTROL Segments] 5000개로 제한됨 [!UICONTROL traits] (최대).</li><li>많이 포함 [!UICONTROL trait] 그룹.</li><li>복잡한 자격 요구 사항이 있습니다.</li></ul> |
| 검색 | 다음을 찾는 데 도움이 됩니다. [!UICONTROL traits] 을(를) 에 추가하려면 [!UICONTROL segment]. |
| 권장 사항 | 유사성을 위한 라이브 추천 받기 [!UICONTROL traits], 자사 [!UICONTROL traits] 및 [!UICONTROL Audience Marketplace] 구독 중인 데이터 피드. 이 권장 사항을 [!UICONTROL segment] 대상자를 확장하는 규칙입니다. 자세한 내용 [트레이트 Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | 유사성을 위한 라이브 추천 받기 [!UICONTROL traits], 출처 [!UICONTROL Audience Marketplace] 구독하지 않은 데이터 피드. 자세한 내용 [트레이트 Recommendations](trait-recommendations.md). |
| 실제 및 예상 [!UICONTROL Segment] 데이터 크기 조정 | [세그먼트 빌더의 트레이트 및 세그먼트 인구 데이터](segment-builder-data.md)를 참조하십시오. |

## 제거 [!UICONTROL Traits] 다음에서: [!UICONTROL Segment] {#remove-traits}

관리 [!UICONTROL traits] (으)로 [!UICONTROL segments] 는 보관의 중요한 부분입니다 [!UICONTROL segments] 실행 가능. 제거해야 하는 경우 다음 단계를 따르십시오 [!UICONTROL traits] 다음에서: [!UICONTROL segment].

제거하려면 [!UICONTROL traits] 다음에서: [!UICONTROL segment]:

1. 다음으로 이동 **[!UICONTROL Audience Data > Segments]**. 목록을 스크롤하거나 검색 기능을 사용하여 [!UICONTROL segment] 함께 작업하고 싶으신 거군요.
2. 다음을 클릭합니다. [!UICONTROL segment] 을(를) 열 이름 [!UICONTROL segment] 세부 정보 화면입니다.
3. 클릭 **편집** 열다 [!UICONTROL Segment Builder] 그런 다음 을 클릭합니다. **트레이트** 을(를) 열려면 [!UICONTROL traits] 패널.
4. 마우스로 가리키기 [!UICONTROL trait] 을(를) 삭제한 다음 X를 클릭합니다. 이 작업은 즉시 [!UICONTROL trait] (으)로부터 [!UICONTROL segment].

## [!UICONTROL Segment Builder] 컨트롤: [!UICONTROL Destinations Mappings] 섹션 {#segment-builder-controls-destinations}

위치 [!UICONTROL Segment Builder], 선택 사항 [!UICONTROL Destinations Mapping] 섹션을 통해 다음을 보낼 수 있습니다. [!UICONTROL segment] 서드파티로 데이터 보내기 [!DNL cookie], [!DNL URL], 또는 [!UICONTROL server-to-server destination]. 을(를) 추가하려면 [!UICONTROL destination], 검색(또는 찾아보기) [!UICONTROL destination], 제공 [!UICONTROL destination] 특정 정보 및 클릭 **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### 사전 요구 사항

의 필수 필드를 작성합니다. [!UICONTROL Basic Information] 및 [!UICONTROL Traits] 섹션. 또한 대상이 이미 있어야 합니다.

### [!UICONTROL Destination Mappings] 검색 도구

다음 **[!UICONTROL Destination Mappings]** 패널에는 아래 표에 설명된 대로 검색 도구가 포함되어 있습니다.

| 검색 유형 | 설명 |
|---|---|
| **[!UICONTROL Search by Destination Name]** | 특정 항목을 검색할 수 있습니다 [!UICONTROL destination] 이름으로. 검색하려면 입력을 시작합니다. 필드는 검색어에 따라 자동으로 완성됩니다. 클릭 **[!UICONTROL Add Destination]** 완료 시. |
| **[!UICONTROL Browse All Destinations]** | 목록 찾아보기 *모두* [!UICONTROL destinations] 사용할 수 있습니다. 선택 및 추가 [!UICONTROL destinations] (으)로 [!UICONTROL segment] 을 클릭합니다. |

## 의 필드 [!UICONTROL Destination Mappings] 팝업 창 {#fields-in-dest-mappings}

위치 [!UICONTROL Segment Builder], [!UICONTROL Add Destination] 대화 상자는 다음을 선택하면 나타납니다. [!UICONTROL destination]. 이 창에는 [!UICONTROL destination] 및에 따라 달라지는 필드 [!UICONTROL destination] 유형. 을(를) 설정하려면 빈 필드에 필요한 정보를 입력하십시오. [!UICONTROL destination mapping].

>[!NOTE]
>
>게시 날짜는 선택 사항입니다. 비어 있는 경우 대상이 활성화되고 만료되지 않습니다.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] 필드

다음에서 [!UICONTROL Destination Mapping] 필드에서에 데이터를 전송하는 데 사용되는 키-값 쌍을 지정합니다. [!UICONTROL destination]. 첫 번째 필드에 키를 입력하고 두 번째 필드에 값을 입력합니다. 사용자 [!UICONTROL cookie destination] pop는 다음과 유사할 수 있습니다.

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] 필드

다음에서 [!UICONTROL URL] 및 [!UICONTROL Secure URL] 필드에 데이터를 로 전송하는 데 사용되는 전체 표준 또는 보안 주소를 지정합니다. [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] 필드

다음에서 [!UICONTROL Destination Value] 필드는 데이터를 로 보내는 데 사용되는 값(키-값 쌍의 일부)을 지정합니다. [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [쿠키 대상 만들기](../../features/destinations/create-cookie-destination.md)
>* [URL 대상 만들기](../../features/destinations/create-url-destination.md)

