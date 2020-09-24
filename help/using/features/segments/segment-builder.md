---
description: 세그먼트 빌더로 세그먼트를 만드는 방법을 설명합니다.
seo-description: 세그먼트 빌더로 세그먼트를 만드는 방법을 설명합니다.
seo-title: 세그먼트 빌더
solution: Audience Manager
title: 세그먼트 빌더
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
translation-type: tm+mt
source-git-commit: 4bf32099e964c421d943d9925c74dd0d4d6ee576
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 2%

---


# [!UICONTROL Segment Builder] {#segment-builder}

세그먼트를 만드는 필수 단계와 선택 사항을 설명합니다 [!UICONTROL Segment Builder].

## 비디오 데모

먼저 Audience Manager에서 세그먼트 [만들기 비디오를 시청하십시오](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). 이 비디오에서는 세그먼트 작성 프로세스를 안내합니다. 자세한 내용은 아래 섹션을 참조하십시오.

## 웹 사이트에 있는 각각의 고유한 랜딩 위치에 대해 [!UICONTROL Segment] {#create-segment}

### 세그먼트 빌더 섹션

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 세 개의 개별 섹션으로 구성됩니다. [!UICONTROL Basic Information], [!UICONTROL Traits]and [!UICONTROL Destinations Mapping]. 컨텐츠를 만들려면 [!UICONTROL segment]및 섹션의 필수 필드 [!UICONTROL Basic Information] 를 [!UICONTROL Traits] 완료합니다. [!UICONTROL Destinations Mapping] 설정은 선택 사항입니다. 자세한 내용은 아래 지침을 참조하십시오.

1. 기본 [정보](../../features/segments/segment-builder.md#segment-builder-controls-basics) 섹션에서 다음을 수행합니다.

   ![create-segment](assets/create-segment.png)

   * 이름을 [!UICONTROL segment]지정합니다. 이름의 최대 길이는 255자입니다. [!UICONTROL segment]
   * 상태를 [!UICONTROL segment] 설정합니다(활성 상태).
   * 원하는 [!UICONTROL data source]항목 선택 첫 번째 드롭다운 메뉴를 사용하여 Audience Manager, Adobe Analytics 보고서 세트 [!UICONTROL data sources]또는 둘 다 간에 필터링합니다. 그런 다음 두 번째 드롭다운 메뉴를 사용하여 원하는 메뉴를 선택합니다 [!UICONTROL data source]. Adobe Analytics 보고서 세트를 사용하지 않는 경우, 유형 선택기가 비활성화되어 [!UICONTROL data source] Audience Manager 데이터 소스만 기본값으로 설정됩니다.
   * 자격에 [!UICONTROL profile merge rule] 사용할 항목을 [!UICONTROL segment] 선택합니다.
   * 저장소 폴더 [!UICONTROL segment] 에 할당합니다.

1. 트레이트 [섹션에서](../../features/segments/segment-builder.md#segment-builder-controls-traits) 다음을 수행합니다.
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * 세그먼트에 추가할 세그먼트 [!UICONTROL trait] 를 검색하고 을 클릭합니다 **[!UICONTROL Add Trait]**. 그룹을 만들 다른 [!UICONTROL trait] 를 [!UICONTROL trait] 추가합니다.
   * 클릭하면 [!UICONTROL Advanced Search] 모달 **[!UICONTROL Browse All Traits]**&#x200B;이 표시됩니다. 이름, [!UICONTROL traits] ID, 설명 또는 이름별로 검색할 수 [!UICONTROL data source]있습니다. 검색 중에 해당 폴더 및 하위 폴더로 결과를 제한하려면 폴더를 클릭합니다. ( [!UICONTROL traits] 장치 ID [!UICONTROL trait type] 및[!UICONTROL Folder Trait]는) 또는 인구 유형( [!UICONTROL Rule-based]장치 ID 및 [!UICONTROL Onboarded][!UICONTROL Algorithmic][](../../reference/ids-in-aam.md) [](../../reference/ids-in-aam.md)CrossDevice ID)별로 필터링할 수도 있습니다.
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * 구축 시 [트레이트](trait-recommendations.md) 권장 사항을 실시간으로 얻을 수 [!UICONTROL segment]있습니다.
   * 클릭 및 드래그하여 별도의 그룹 [!UICONTROL traits] 을 만들 수 있습니다.
   * 그룹 간 마우스를 가져가면 부울, 값 [!UICONTROL AND]과 관계를 설정할 수 [!UICONTROL OR]있습니다 [!UICONTROL AND NOT] .
   * 시계 아이콘 위로 마우스를 가져가면 [최근 및 빈도](../../features/segments/recency-and-frequency.md) 규칙이 [!UICONTROL trait]추가됩니다.
   * 추가 또는 제거하면서 세그먼트 모집단 데이터를 볼 수 있습니다 [!UICONTROL traits]. 예상 인구 수를 **[!UICONTROL Calculate Estimates]** 보거나 새로 고치려면 을 클릭합니다. 의 [세그먼트 모집단 데이터에](../../features/segments/segment-builder-data.md#segment-populations) 대한 자세한 내용을 [!UICONTROL Segment Builder]참조하십시오.
   * 완료되면 을 **[!UICONTROL Save]** 클릭합니다.

1. *(선택 사항)* 대상 매핑 [!UICONTROL segment] 섹션 [!UICONTROL destination] 에서 [a를](../../features/segments/segment-builder.md#segment-builder-controls-destinations) 매핑합니다.
   * 를 검색하고 [!UICONTROL destination] 을 클릭합니다 **[!UICONTROL Add Destination]**. 에 추가하려면 먼저 [!UICONTROL destination] 가 있어야 합니다 [!UICONTROL segment].
   * 완료되면 을 **[!UICONTROL Save]** 클릭합니다.

크로스 디바이스 지표가 작동하는 방식을 자세히 살펴보려면 아래 비디오를 참조하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/33445/)

## [!UICONTROL Segment Builder] 컨트롤: [!UICONTROL Basic Information] 섹션 {#segment-builder-controls-basics}

에서 [!UICONTROL Segment Builder]설정을 사용하면 [!UICONTROL the Basic Information] 새 트레이트를 만들거나 기존 트레이트를 편집할 수 있습니다. 새로 만들려면 이름 [!UICONTROL segment]을 입력하고 저장소 폴더 [!UICONTROL data source]를 선택합니다. 다른 모든 필드는 선택 사항입니다. 완료되면 섹션으로 [!UICONTROL Traits] 이동합니다.

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
| **[!UICONTROL Name]** | 세그먼트의 기능 또는 목적을 설명하는 짧고 논리적인 이름을 지정합니다. 약자와 특수 문자는 사용하지 마십시오. 세그먼트 이름의 최대 길이는 255자입니다. |
| **[!UICONTROL Description]** | 세그먼트에 대한 추가 설명 정보를 위한 필드입니다. |
| **[!UICONTROL Integration Code]** | 사용자 정의 ID 또는 기타 회사별 정보에 대한 필드입니다. |
| **[!UICONTROL Data Source]** | 세그먼트를 특정 데이터 공급자에 연결합니다. <br> 첫 번째 드롭다운 메뉴를 사용하여 Audience Manager 데이터 소스, Adobe Analytics 보고서 세트 또는 둘 다 필터링합니다. 그런 다음 두 번째 드롭다운 메뉴를 사용하여 데이터 소스를 선택합니다. <br> Adobe Analytics 보고서 세트를 사용하지 않는 경우 데이터 소스 유형 선택기가 비활성화되어 Audience Manager 데이터 소스만 기본값으로 설정됩니다. |
| **[!UICONTROL Profile Merge Rule]** | 세그먼트 자격에 사용할 프로필 병합 규칙을 선택합니다. |
| **[!UICONTROL Status]** | 세그먼트를 활성화하거나 비활성화합니다(기본적으로 활성화됨). |
| **폴더 저장소** | 세그먼트가 속한 저장소 폴더를 결정합니다. |

## [!UICONTROL Segment Builder] 컨트롤: [!UICONTROL Traits] 섹션 {#segment-builder-controls-traits}

에서 섹션 [!UICONTROL Segment Builder]을 사용하면 [!UICONTROL Traits] a [!UICONTROL traits] [!UICONTROL segment][!UICONTROL trait] 에서 관리하고, 그룹을 만들고, 자격 조건을 설정할 수 있습니다. 에 [!UICONTROL trait] 를 추가하려면 [!UICONTROL segment]검색 필드 [!UICONTROL trait] 에 이름을 입력하고 을 클릭합니다 [!UICONTROL Add Trait]. ( [!UICONTROL trait] 완료되면)를 저장하거나 다음으로 이동합니다 [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**전제 조건:** 섹션의 필수 필드를 [!UICONTROL Basic Information] 완료합니다.

| 필드 | 설명 |
|--- |--- |
| **[!UICONTROL Basic View]** | 이 섹션에서는 다음과 같은 시각적 컨트롤을 제공합니다. <ul><li>신규 구축 및 기존 관리 [!UICONTROL segments].</li><li>Remove [!UICONTROL traits] from a [!UICONTROL segment].</li><li>최대 50개(최대) [!UICONTROL traits] 를 [!UICONTROL segment]추가합니다.</li><li>드래그 앤 드롭 [!UICONTROL traits] 으로 새 그룹을 만듭니다.</li><li>한 곳에서 [!UICONTROL traits] 및 [!UICONTROL trait] 그룹 [!UICONTROL segment]보기</li><li>부울 표현식, 비교 연산자 및 최근/빈도 설정으로 자격 조건을 설정합니다.</li></ul> |
| **[!UICONTROL Code View]** | 시각적 인터페이스 대신 코드를 사용하여 요구 사항 [!UICONTROL traits]을 작성 및 관리하고, 그룹 및 자격을 평가할 수 있는 개발 환경을 엽니다. 코드 보기는 다음과 같은 경우에 유용합니다. [!UICONTROL segments] <ul><li>한 개인 [!UICONTROL traits] 에 50개 이상을 포함합니다 [!UICONTROL segment]. 참고: [!UICONTROL Segments] 은 5000 [!UICONTROL traits] (최대)으로 제한됩니다.</li><li>여러 그룹을 [!UICONTROL trait] 포함합니다.</li><li>자격 조건은 복잡합니다.</li></ul> |
| 검색 | Add [!UICONTROL traits] to a를 찾는 데 도움이 [!UICONTROL segment]됩니다. |
| 권장 사항 | 가입한 자사 [!UICONTROL traits]및 [!UICONTROL traits] [!UICONTROL Audience Marketplace] 데이터 피드에서 유사한 제품에 대한 라이브 추천을 받을 수 있습니다. 이러한 권장 사항을 규칙에 [!UICONTROL segment] 추가하여 대상을 확장합니다. 트레이트 Recommendations에서 자세한 [내용을 살펴보십시오](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | 가입하지 않은 데이터 피드 [!UICONTROL traits]에서 유사한 기능의 [!UICONTROL Audience Marketplace] 라이브 추천을 받을 수 있습니다. 트레이트 Recommendations에서 자세한 [내용을 살펴보십시오](trait-recommendations.md). |
| 실제 및 예상 [!UICONTROL Segment] 크기 데이터 | [세그먼트 빌더의 트레이트 및 세그먼트 인구 데이터](segment-builder-data.md)를 참조하십시오. |

## Remove [!UICONTROL Traits] from a [!UICONTROL Segment] {#remove-traits}

당신의 [!UICONTROL traits] 안에서 [!UICONTROL segments] 그것을 관리하는 것은 실행 가능한 것을 유지하는 중요한 [!UICONTROL segments] 부분이다. 에서 제거해야 하는 경우 다음 단계 [!UICONTROL traits] 를 수행합니다 [!UICONTROL segment].

To remove [!UICONTROL traits] from a [!UICONTROL segment]:

1. 로 **[!UICONTROL Audience Data > Segments]**&#x200B;이동합니다. 목록을 스크롤하거나 검색 기능을 사용하여 작업할 [!UICONTROL segment] 항목을 찾습니다.
2. 이름을 [!UICONTROL segment] 클릭하여 세부 사항 화면을 [!UICONTROL segment] 엽니다.
3. 편집 **을** 클릭하여 [!UICONTROL Segment Builder] 연 다음 트레이트 **를 클릭하여** [!UICONTROL traits] 패널을 엽니다.
4. 삭제할 항목 위로 마우스를 가져간 다음 X를 클릭합니다. 이 작업은 사용자 [!UICONTROL trait] 에서 해당 항목을 즉시 제거합니다 [!UICONTROL trait] [!UICONTROL segment].

## [!UICONTROL Segment Builder] 컨트롤: [!UICONTROL Destinations Mappings] 섹션 {#segment-builder-controls-destinations}

에서 선택 [!UICONTROL Segment Builder]섹션 [!UICONTROL Destinations Mapping] 을 사용하면 [!UICONTROL segment] 데이터를 타사 [!DNL cookie], [!DNL URL]또는 [!UICONTROL server-to-server destination]으로 보낼 수 있습니다. 를 [!UICONTROL destination]추가, 검색(또는 탐색) [!UICONTROL destination]및 [!UICONTROL destination] 특정 정보를 입력하고 를 클릭합니다 **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### 사전 요구 사항

및 섹션의 필수 필드 [!UICONTROL Basic Information] 를 [!UICONTROL Traits] 완료합니다. 또한 대상이 이미 존재해야 합니다.

### [!UICONTROL Destination Mappings] 검색 도구

아래 표에 설명된 대로 **[!UICONTROL Destination Mappings]** 패널에는 검색 도구가 포함되어 있습니다.

| 검색 유형 | 설명 |
|---|---|
| **[!UICONTROL Search by Destination Name]** | 이름별로 특정 항목을 검색할 [!UICONTROL destination] 수 있습니다. 검색하려면 입력을 시작합니다. 이 필드는 검색어에 따라 자동으로 완성됩니다. 완료되면 을 **[!UICONTROL Add Destination]** 클릭합니다. |
| **[!UICONTROL Browse All Destinations]** | 사용 가능한 *모든* 목록 [!UICONTROL destinations] 찾아보기 팝업 목록 [!UICONTROL destinations] 에서 [!UICONTROL segment] 을 선택하여 추가합니다. |

## 팝업 [!UICONTROL Destination Mappings] 창의 필드 {#fields-in-dest-mappings}

에서 [!UICONTROL Segment Builder]는 [!UICONTROL Add Destination] 대화 상자를 선택한 후 나타납니다 [!UICONTROL destination]. 이 창에는 유형에 따라 [!UICONTROL destination] 변화하는 필드 및 필드에 대한 정적 정보가 [!UICONTROL destination] 표시됩니다. 빈 필드에 필수 정보를 입력하여 JavaScript 코드를 설정할 수 있습니다 [!UICONTROL destination mapping].

>[!NOTE]
>
>발행일은 선택 사항입니다. 비어 있으면 대상이 활성화되고 만료되지 않습니다.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] 필드

필드에서 [!UICONTROL Destination Mapping] 데이터를 보낼 때 사용되는 키-값 쌍을 지정합니다 [!UICONTROL destination]. 첫 번째 필드에 키를 입력하고 두 번째 필드에 값을 입력합니다. 팝이 다음과 [!UICONTROL cookie destination] 비슷합니다.

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] 필드

및 필드 [!UICONTROL URL] 에서 데이터를 보낼 때 사용되는 전체 표준 또는 보안 주소를 [!UICONTROL Secure URL] [!UICONTROL destination]지정합니다.

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] 필드

필드에서 [!UICONTROL Destination Value] 데이터를 보낼 때 사용되는 값(키-값 쌍의 일부)을 지정합니다 [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [쿠키 대상 만들기](../../features/destinations/create-cookie-destination.md)
>* [URL 대상 만들기](../../features/destinations/create-url-destination.md)

