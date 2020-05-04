---
description: 세그먼트 빌더로 세그먼트를 만드는 방법을 설명합니다.
seo-description: 세그먼트 빌더로 세그먼트를 만드는 방법을 설명합니다.
seo-title: 세그먼트 빌더
solution: Audience Manager
title: 세그먼트 빌더
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: 859e55fa5d93c7c56cef4bf2a112cdd4ff318d97

---


# 세그먼트 빌더 {#segment-builder}

세그먼트를 만드는 필수 단계와 선택 사항을 설명합니다 [!UICONTROL Segment Builder].

## 비디오 데모

먼저 Audience Manager에서 세그먼트 [만들기 비디오를 시청하십시오](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). 이 비디오에서는 세그먼트 작성 프로세스를 안내합니다. 자세한 내용은 아래 섹션을 참조하십시오.

## 세그먼트 만들기 {#create-segment}

### 세그먼트 빌더 섹션

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 세 개의 개별 섹션으로 구성됩니다. [!UICONTROL Basic Information], [!UICONTROL Traits]and [!UICONTROL Destinations Mapping]. 세그먼트를 만들려면 [!UICONTROL Basic Information] 및 섹션의 필수 필드를 [!UICONTROL Traits] 완료합니다. [!UICONTROL Destinations Mapping] 설정은 선택 사항입니다. 자세한 내용은 아래 지침을 참조하십시오.

1. 기본 [정보](../../features/segments/segment-builder.md#segment-builder-controls-basics) 섹션에서 다음을 수행합니다.

   ![create-segment](assets/create-segment.png)

   * 세그먼트 이름을 지정합니다. 세그먼트 이름의 최대 길이는 255자입니다.
   * 세그먼트 상태(활성 상태)를 설정합니다.
   * 데이터 소스를 선택합니다. 첫 번째 드롭다운 메뉴를 사용하여 Audience Manager 데이터 소스, Adobe Analytics 보고서 세트 또는 둘 다 간에 필터링합니다. 그런 다음 두 번째 드롭다운 메뉴를 사용하여 데이터 소스를 선택합니다. Adobe Analytics 보고서 세트를 사용하지 않는 경우 데이터 소스 유형 선택기가 비활성화되어 Audience Manager 데이터 소스로만 기본값이 설정됩니다.
   * 세그먼트 자격에 사용할 프로필 병합 규칙을 선택합니다.
   * 세그먼트를 저장소 폴더에 할당합니다.

1. 트레이트 [섹션에서](../../features/segments/segment-builder.md#segment-builder-controls-traits) 다음을 수행합니다.
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * 세그먼트에 추가할 트레이트를 검색하고 클릭합니다 **[!UICONTROL Add Trait]**. 트레이트 그룹을 만들려면 다른 트레이트를 추가합니다.
   * 클릭하여 고급 검색 모델을 불러옵니다 **[!UICONTROL Browse All Traits]**. 이름, ID, 설명 또는 데이터 소스별로 트레이트를 검색합니다. 검색 중에 해당 폴더 및 하위 폴더로 결과를 제한하려면 폴더를 클릭합니다. 트레이트를 트레이트 유형([!UICONTROL Folder Trait], [!UICONTROL Rule-based][!UICONTROL Onboarded]및 [!UICONTROL Algorithmic]) 또는 인구 유형([장치 ID](../../reference/ids-in-aam.md) 및 [](../../reference/ids-in-aam.md)크로스 장치 ID)별로 필터링할 수도 있습니다.
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * 세그먼트를 만들 때 라이브 [트레이트](trait-recommendations.md) 추천을 얻을 수 있습니다.
   * 트레이트를 클릭하고 드래그하여 별도의 그룹을 만듭니다.
   * 그룹 간 마우스를 가져가면 부울, 값 [!UICONTROL AND]과 관계를 설정할 수 [!UICONTROL OR]있습니다 [!UICONTROL AND NOT] .
   * 시계 아이콘 위로 마우스를 가져가면 [최근 및 빈도](../../features/segments/recency-and-frequency.md) 규칙이 트레이트에 추가됩니다.
   * 트레이트를 추가하거나 제거하면 세그먼트 모집단 데이터를 볼 수 있습니다. 예상 인구 수를 **[!UICONTROL Calculate Estimates]** 보거나 새로 고치려면 을 클릭합니다. 세그먼트 빌더의 [세그먼트 모집단 데이터에](../../features/segments/segment-builder-data.md#segment-populations) 대한 자세한 내용을 참조하십시오.
   * 완료되면 을 **[!UICONTROL Save]** 클릭합니다.

1. *(선택 사항)* 대상 매핑 [섹션에서 대상에 세그먼트를](../../features/segments/segment-builder.md#segment-builder-controls-destinations) 매핑합니다.
   * 대상을 검색하고 클릭합니다 **[!UICONTROL Add Destination]**. 세그먼트에 대상을 추가하려면 대상이 이미 있어야 합니다.
   * 완료되면 을 **[!UICONTROL Save]** 클릭합니다.

크로스 디바이스 지표가 작동하는 방식을 자세히 살펴보려면 아래 비디오를 참조하십시오.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## 세그먼트 빌더 컨트롤: 기본 정보 섹션 {#segment-builder-controls-basics}

에서 [!UICONTROL Segment Builder]설정을 사용하면 [!UICONTROL the Basic Information] 새 트레이트를 만들거나 기존 트레이트를 편집할 수 있습니다. 새 세그먼트를 만들려면 이름, 데이터 소스를 입력하고 저장소 폴더를 선택합니다. 다른 모든 필드는 선택 사항입니다. 완료되면 섹션으로 [!UICONTROL Traits] 이동합니다.

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
   <td colname="col2"> <p>세그먼트의 기능 또는 목적을 설명하는 짧고 논리적인 이름을 지정합니다. 약자와 특수 문자는 사용하지 마십시오. 세그먼트 이름의 최대 길이는 255자입니다. </p> </td> 
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
   <td colname="col2"> <p>세그먼트를 특정 데이터 공급자에 연결합니다. <p>첫 번째 드롭다운 메뉴를 사용하여 Audience Manager 데이터 소스, Adobe Analytics 보고서 세트 또는 둘 다 간에 필터링합니다. 그런 다음 두 번째 드롭다운 메뉴를 사용하여 데이터 소스를 선택합니다.</p><p> Adobe Analytics 보고서 세트를 사용하지 않는 경우 데이터 소스 유형 선택기가 비활성화되어 Audience Manager 데이터 소스로만 기본값이 설정됩니다.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>프로필 병합 규칙</b> </td> 
   <td colname="col2"> <p>세그먼트 자격에 사용할 프로필 병합 규칙을 선택합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>상태</b> </td> 
   <td colname="col2"> <p>세그먼트를 활성화하거나 비활성화합니다(기본적으로 활성화됨). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>폴더 저장소</b> </td> 
   <td colname="col2"> <p>세그먼트가 속한 저장소 폴더를 결정합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 세그먼트 빌더 컨트롤: 트레이트 섹션 {#segment-builder-controls-traits}

에서 섹션 [!UICONTROL Segment Builder]을 사용하면 [!UICONTROL Traits] 세그먼트의 트레이트를 관리하고 트레이트 그룹을 만들고 자격 기준을 설정할 수 있습니다. 세그먼트에 트레이트를 추가하려면 검색 필드에 트레이트 이름을 입력하고 클릭합니다 [!UICONTROL Add Trait]. 트레이트를 저장(완료되면)하거나 다음으로 이동합니다 [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**전제 조건:** 섹션의 필수 필드를 [!UICONTROL Basic Information] 완료합니다.

| 필드 | 설명 |
|--- |--- |
| 기본 보기 | 이 섹션에서는 다음과 같은 시각적 컨트롤을 제공합니다. <ul><li>새로운 세그먼트를 만들고 기존 세그먼트를 관리합니다.</li><li>세그먼트에서 트레이트를 제거합니다.</li><li>세그먼트에 최대 50개의 트레이트를 추가합니다.</li><li>트레이트를 드래그 앤 드롭하여 새 그룹을 만듭니다.</li><li>세그먼트에서 트레이트 및 트레이트 그룹 보기</li><li>부울 표현식, 비교 연산자 및 최근/빈도 설정으로 자격 조건을 설정합니다.</li></ul> |
| 코드 보기 | 시각적 인터페이스 대신 코드를 사용하여 트레이트, 그룹 및 자격 요구 사항을 만들고 관리할 수 있는 개발 환경을 엽니다. 코드 보기는 세그먼트가 <ul><li>개별 세그먼트에 50개 이상의 트레이트를 포함합니다. 참고: 세그먼트는 5000개 트레이트로 제한됩니다.</li><li>트레이트 그룹을 많이 포함합니다.</li><li>자격 조건은 복잡합니다.</li></ul> |
| 검색 | 세그먼트에 추가할 트레이트를 찾는 데 도움이 됩니다. |
| 권장 사항 | 가입한 자사 트레이트와 데이터 피드에서 유사한 트레이트에 대한 라이브 추천을 받을 수 있습니다. [!UICONTROL Audience Marketplace] 이러한 권장 사항을 세그먼트 규칙에 추가하여 대상을 확장합니다. 트레이트 추천에서 [자세히 알아보십시오](trait-recommendations.md). |
| 마켓플레이스 추천 | 가입하지 않은 데이터 피드에서 유사한 트레이트에 대한 [!UICONTROL Audience Marketplace] 라이브 추천을 받을 수 있습니다. 트레이트 추천에서 [자세히 알아보십시오](trait-recommendations.md). |
| 실제 및 예상 세그먼트 크기 데이터 | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## 세그먼트에서 트레이트 제거 {#remove-traits}

세그먼트의 트레이트를 관리하는 것은 세그먼트를 실행 가능하게 유지하는 중요한 부분입니다. 세그먼트에서 트레이트를 제거해야 하는 경우 다음 단계를 수행합니다.

세그먼트에서 트레이트를 제거하려면:

1. 대상 **데이터 > 세그먼트로 이동합니다**. 목록을 스크롤하거나 검색 기능을 사용하여 작업할 세그먼트를 찾습니다.
2. 세그먼트 이름을 클릭하여 세그먼트 세부 사항 화면을 엽니다.
3. 편집을 **클릭하여** 세그먼트 빌더를 연 다음 **트레이트** 를 클릭하여 트레이트 패널을 엽니다.
4. 삭제할 트레이트 위로 마우스를 가져간 다음 X를 클릭합니다. 이 작업은 세그먼트에서 트레이트를 즉시 제거합니다.

## 세그먼트 빌더 컨트롤: 대상 매핑 섹션 {#segment-builder-controls-destinations}

에서 [!UICONTROL Segment Builder]선택 [!UICONTROL Destinations Mapping] 섹션에서 세그먼트 데이터를 타사 [!DNL cookie][!DNL URL]또는 서버간 대상으로 보낼 수 있습니다. 대상을 추가하려면 대상을 검색(또는 탐색)하고, 대상 특정 정보를 제공한 다음 을 클릭합니다 **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### 전제 조건

및 섹션의 필수 필드 [!UICONTROL Basic Information] 를 [!UICONTROL Traits] 완료합니다. 또한 대상이 이미 존재해야 합니다.

### 대상 매핑 검색 도구

아래 표에 설명된 대로 **[!UICONTROL Destination Mappings]** 패널에는 검색 도구가 포함되어 있습니다.

| 검색 유형 | 설명 |
|---|---|
| **대상 이름별 검색** | 이름별로 특정 대상을 검색할 수 있도록 해줍니다. 검색하려면 입력을 시작합니다. 이 필드는 검색어에 따라 자동으로 완성됩니다. 완료되면 을 **[!UICONTROL Add Destination]** 클릭합니다. |
| **모든 대상 찾아보기** | 사용 가능한 *모든* 대상 목록을 찾아봅니다. 팝업 목록에서 대상을 선택하고 세그먼트에 추가합니다. |

## 대상 매핑 팝업 창의 필드 {#fields-in-dest-mappings}

에서 [!UICONTROL Segment Builder]는 대상을 선택하면 대화 상자가 [!UICONTROL Add Destination] 나타납니다. 이 창에는 대상 유형에 따라 변화하는 대상 및 필드에 대한 정적 정보가 표시됩니다. 대상 매핑을 설정하려면 빈 필드에 필수 정보를 입력합니다.

>[!NOTE]
>
>발행일은 선택 사항입니다. 비어 있으면 대상이 활성화되고 만료되지 않습니다.

<!-- r_add_mappings_pop.xml -->

### 쿠키 대상 필드

필드에서 [!UICONTROL Destination Mapping] 데이터를 대상으로 전송하는 데 사용되는 키-값 쌍을 지정합니다. 첫 번째 필드에 키를 입력하고 두 번째 필드에 값을 입력합니다. 쿠키 대상 팝이 다음과 비슷합니다.

![](assets/cookie_modal.PNG)

### URL 대상 필드

및 필드 [!UICONTROL URL] 에서 데이터 [!UICONTROL Secure URL] 를 대상으로 전송하는 데 사용되는 전체 표준 또는 보안 주소를 지정합니다.

![](assets/url_modal.PNG)

### 서버 간 대상 필드

필드에서 [!UICONTROL Destination Value] 데이터를 대상으로 전송하는 데 사용되는 값(키-값 쌍의 일부)을 지정합니다.

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [쿠키 대상 만들기](../../features/destinations/create-cookie-destination.md)
>* [URL 대상 만들기](../../features/destinations/create-url-destination.md)

