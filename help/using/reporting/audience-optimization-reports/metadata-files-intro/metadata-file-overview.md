---
description: 메타데이터 파일은 읽고 이해할 수 있는 이름의 숫자 ID를 연결합니다. Audience Optimization 보고서에는 다양한 보고서 옵션 메뉴에 읽을 수 있는 이름이 표시됩니다.
seo-description: 메타데이터 파일은 읽고 이해할 수 있는 이름의 숫자 ID를 연결합니다. Audience Optimization 보고서에는 다양한 보고서 옵션 메뉴에 읽을 수 있는 이름이 표시됩니다.
seo-title: 메타데이터 파일에 대한 개요 및 매핑
solution: Audience Manager
title: 메타데이터 파일에 대한 개요 및 매핑
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: 로그 파일
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 4%

---

# 메타데이터 파일에 대한 개요 및 매핑{#overview-and-mappings-for-metadata-files}

메타데이터 파일은 읽고 이해할 수 있는 이름의 숫자 ID를 연결합니다. Audience Optimization 보고서에는 다양한 보고서 옵션 메뉴에 읽을 수 있는 이름이 표시됩니다.

## 개요 {#overview}

메타데이터와 메타데이터 사용 방법에 대한 검토. 메타데이터 파일에는 데이터 파일이 포함되어야 합니다. 메타데이터 파일 내용은 데이터 파일 정보와 보고서 메뉴의 사람이 읽을 수 있는 관련 레이블과 일치합니다. 자세한 내용은 [Audience Optimization 보고서 및 실행 가능 로그 파일용 데이터 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)을 참조하십시오.

### 메타데이터 파일에 다른 데이터에 대한 데이터가 포함됩니다.

메타데이터 파일에는 다른 유형의 데이터에 대한 정보가 들어 있습니다. 이 작동 방식을 이해하는 데 도움이 되도록 [!DNL Audience Manager] 이 데이터를 수신하는 방법을 살펴보겠습니다.

노출 또는 클릭 이벤트 동안 [!DNL Audience Manager]은 *이벤트 호출*&#x200B;로 알려진 URL 문자열의 데이터를 수신합니다.

이벤트 호출은 정보를 정의된 키-값 쌍 세트로 구성합니다. 키-값 쌍의 값에 숫자 데이터가 포함됩니다. 메타데이터 파일에는 각 키-값 쌍의 ID에 해당하는 이름 및 읽을 수 있는 정보가 포함되어 있습니다.

### 메타데이터 링크 ID를 읽을 수 있는 이름

메타데이터 파일은 숫자 ID를 읽을 수 있는 이름에 연결해야 합니다. 예를 들어, 이벤트 호출에 다음과 같은 키-값 쌍에 광고 ID가 포함되어 있다고 가정합니다.`d_creative:1234` 메타데이터 파일이 없으면 이 광고 문안은 옵션 메뉴에 1234로 표시됩니다.

그러나 올바르게 포맷된 메타데이터 파일은 이 크리에이티브를 보고서에서 읽고 인식할 수 있는 이름인 &quot;Advertiser Creative A&quot;와 같은 실제 이름으로 다시 연결할 수 있습니다.

### 메타데이터 파일이 필요한 시기

먼저, 메타데이터 파일과 아래 나열된 모든 매개 변수는 [Audience Optimization 보고서](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)를 사용하려는 경우 이벤트 호출에 필요합니다.

둘째, 자신의 데이터를 [!DNL Audience Manager]에 보내거나 Adobe와 통합되지 않은 다른 공급자의 보고서에 데이터를 보려는 경우 메타데이터 파일이 필요합니다. 예를 들어 [!DNL Audience Manager]은 Google의 [캠페인 관리자](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)(DCM)를 두 번 클릭하는 것과 통합되었습니다. 이 관계 때문에 [!DNL Audience Manager] 은 ID를 보고서 옵션에서 사용하는 이름 및 설명과 연결할 수 있습니다. 통합이 없으면 여전히 데이터를 수집할 수 있지만 보고서 옵션에는 수사적 이름 대신 숫자 ID가 표시됩니다.

![메타데이터 메뉴 이미지](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## 파일 매핑 {#file-mappings}

다음 표에는 [!UICONTROL Audience Optimization] 보고서에서 사용하는 데이터를 포함하는 키-값 쌍이 나열되어 있습니다. 메타데이터 파일을 사용해야 하는 경우 이 키-값 쌍의 값에 해당하는 사람이 읽을 수 있는 정보가 포함됩니다. 이러한 키의 값은 정수만 사용합니다(데이터 유형 INT). 참고: *기울임체*&#x200B;는 변수 자리 표시자를 나타냅니다. 다른 요소는 상수 또는 키이며 변경되지 않습니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization] 보고서를 사용하는 경우 이러한 값의 *모두*&#x200B;가 이벤트 호출에 필요합니다.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 보고서 옵션 </th> 
   <th colname="col2" class="entry"> 메타데이터 키-값 쌍 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>광고주 </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>데이터 소스를 만들 때 제공된 광고주의 데이터 소스 ID 또는 통합 코드입니다. <a href="../../../features/manage-datasources.md#create-data-source"> 데이터 소스 만들기</a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>비즈니스 단위(BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>캠페인 </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>두 개의 다른 키-값 쌍을 허용합니다. </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>삽입 순서(IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>플랫폼 </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>메타데이터 정보를 제공하는 플랫폼의 <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 데이터 소스</a> ID입니다(예: DFA, Atlas, GBM, MediaMath 등). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>전술 </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>세로 </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 이벤트 호출 ID가 셰이프 파일 이름, 콘텐츠 및 배달 경로 {#how-ids-shape-file-names}

이러한 키-값 쌍에서 전달한 ID는 메타데이터 파일 이름 및 해당 컨텐츠를 만드는 데 도움이 됩니다. 다음 섹션 및 그림에서는 이 작동 방식을 보여 줍니다. 이러한 예제에서는 캠페인에 있는 광고 이름이 포함된 파일을 만들지만, 다른 조합은 가능합니다.

### 이벤트 호출

이 예에서는 광고 이름을 [!UICONTROL Audience Optimization] 보고서에 가져오는 메타데이터 파일을 만듭니다. 이를 위해 이벤트 호출에서 크리에이티브, 캠페인 및 데이터 소스 ID를 추출해야 합니다.

![이벤트 호출 이미지](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### 파일 이름

파일 이름은 크리에이티브, 캠페인 및 데이터 소스 ID를 기반으로 합니다. 이 경우 여기에서 이벤트 호출의 키-값 데이터와 파일 이름에 이 데이터가 사용되는 방법 간의 차이점을 비교합니다.

파일 이름:

* 데이터 소스 키가 `d_src`에서 `dpid`으로 변경됩니다.

* 광고 및 캠페인 ID는 실제 식별자가 아니라 카테고리를 나타냅니다.

![파일 이름 작성 방법](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

메타데이터 파일에 대한 이름 지정 규칙](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)을 참조하십시오.[

### 파일 내용

이 예에서 파일 콘텐츠는 이벤트 호출 시 전달된 광고 및 캠페인 ID를 반영합니다. 여기에서 새 요소는 읽을 수 있는 이름입니다. 처리되면 이 파일의 이름은 [!UICONTROL Audience Optimization] 보고서의 크리에이티브 메뉴에 옵션으로 나타납니다.

![메타데이터 파일의 내용](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

메타데이터 파일에 대한 [컨텐츠 형식](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md)을 참조하십시오.

### 파일 전달

이름을 지정하고 데이터를 파일에 추가하면 [!DNL Audience Manager]에서 제공하는 Amazon S3 저장소 디렉토리에 데이터를 보냅니다. 메타데이터 파일에 대한 [전달 방법](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md)을 참조하십시오.

>[!MORELIKETHIS]
>
>* [Audience Optimization 보고서용 데이터 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
* [픽셀 호출을 통해 캠페인 클릭 데이터 캡처](../../../integration/media-data-integration/click-data-pixels.md)
* [픽셀 호출을 통해 캠페인 노출 횟수 데이터 캡처](../../../integration/media-data-integration/impression-data-pixels.md)

