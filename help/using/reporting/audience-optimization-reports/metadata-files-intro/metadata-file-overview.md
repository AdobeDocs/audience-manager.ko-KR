---
description: 메타데이터 파일은 읽고 이해할 수 있는 이름의 숫자 ID를 연결합니다. Audience Optimization 보고서에는 다양한 보고서 옵션 메뉴에 읽을 수 있는 이름이 표시됩니다.
seo-description: 메타데이터 파일은 읽고 이해할 수 있는 이름의 숫자 ID를 연결합니다. Audience Optimization 보고서에는 다양한 보고서 옵션 메뉴에 읽을 수 있는 이름이 표시됩니다.
seo-title: 메타데이터 파일에 대한 개요 및 매핑
solution: Audience Manager
title: 메타데이터 파일에 대한 개요 및 매핑
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: 로그 파일
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 4%

---

# 메타데이터 파일에 대한 개요 및 매핑{#overview-and-mappings-for-metadata-files}

메타데이터 파일은 읽고 이해할 수 있는 이름의 숫자 ID를 연결합니다. Audience Optimization 보고서에는 다양한 보고서 옵션 메뉴에 읽을 수 있는 이름이 표시됩니다.

## 개요 {#overview}

메타데이터 및 메타데이터 사용 방법을 검토합니다. 메타데이터 파일에는 데이터 파일이 있어야 합니다. 메타데이터 파일 컨텐츠는 보고서 메뉴에서 읽을 수 있는 관련 레이블과 데이터 파일 정보를 일치시킵니다. 자세한 내용은 [Audience Optimization 보고서용 데이터 파일 및 실행 가능한 로그 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)을 참조하십시오.

### 메타데이터 파일에는 다른 데이터에 대한 데이터가 포함됩니다.

메타데이터 파일에는 다른 데이터 유형에 대한 정보가 들어 있습니다. 이 작동 방식을 이해하려면 [!DNL Audience Manager]이(가) 데이터를 받는 방법을 살펴보십시오.

노출 또는 클릭 이벤트 중에 [!DNL Audience Manager]은 *이벤트 호출*&#x200B;이라고 하는 URL 문자열의 데이터를 받습니다.

이벤트 호출은 정의된 키-값 쌍 집합에 정보를 구성합니다. 키-값 쌍의 값에 숫자 데이터가 포함됩니다. 메타데이터 파일에는 각 키-값 쌍의 ID에 해당하는 이름 및 기타 읽을 수 있는 정보가 포함되어 있습니다.

### 메타데이터 링크 ID를 읽을 수 있는 이름에 연결

메타데이터 파일은 숫자 ID를 읽을 수 있는 이름에 연결해야 합니다. 예를 들어 이벤트 호출에는 다음과 같은 키-값 쌍에 크리에이티브 ID가 포함되어 있다고 가정해 보십시오.`d_creative:1234`. 메타데이터 파일이 없으면 이 크리에이티브는 옵션 메뉴에 1234로 표시됩니다.

그러나 제대로 서식이 지정된 메타데이터 파일은 이 크리에이티브를 보고서에서 읽고 인식할 수 있는 이름인 &quot;광고주 크리에이티브 A&quot;와 같은 실제 이름으로 연결할 수 있습니다.

### 메타데이터 파일이 필요한 시기

먼저, 메타데이터 파일 및 아래 나열된 모든 매개 변수는 [Audience Optimization 보고서](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)를 사용하려는 경우 이벤트 호출에 필요합니다.

둘째, 데이터를 [!DNL Audience Manager]에 보내거나 통합되지 않은 다른 공급자의 보고서에 데이터를 표시하려면 메타데이터 파일이 필요합니다. 예를 들어 [!DNL Audience Manager]은(는) Google의 [캠페인 관리자](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)(DCM)와 통합되어 있습니다. 이러한 관계로 인해 [!DNL Audience Manager]은(는) ID를 보고서 옵션에서 사용하는 이름 및 설명에 연결할 수 있습니다. 통합이 없으면 데이터를 인제스트할 수 있지만 보고서 옵션은 설명 이름 대신 숫자 ID를 표시합니다.

![메타데이터 메뉴 이미지](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## 파일 매핑 {#file-mappings}

다음 표는 [!UICONTROL Audience Optimization] 보고서에서 사용한 데이터를 포함하는 키-값 쌍을 나열합니다. 메타데이터 파일을 사용해야 할 경우 이 키-값 쌍의 값에 해당하는 사람이 읽을 수 있는 정보가 포함됩니다. 이러한 키의 값은 정수만 사용합니다(데이터 유형 INT). 참고: *기울임체*&#x200B;는 변수 자리 표시자를 나타냅니다. 다른 요소는 상수 또는 키이며 변경되지 않습니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization] 보고서를 사용하는 경우 이벤트 호출에서 이러한 값의 *모두*&#x200B;가 필요합니다.

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
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>데이터 소스를 만들 때 제공되는 광고주의 데이터 소스 ID 또는 통합 코드입니다. <a href="../../../features/manage-datasources.md#create-data-source"> 데이터 소스 만들기</a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>사업부(BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>캠페인 </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>크리에이티브 </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>2개의 서로 다른 키-값 쌍을 허용합니다. </p> 
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

## 이벤트 호출 시 ID의 모양 파일 이름, 내용 및 배달 경로 {#how-ids-shape-file-names}

이러한 키-값 쌍으로 전달된 ID는 메타데이터 파일 이름 및 해당 내용을 만드는 데 도움이 됩니다. 다음 섹션 및 일러스트레이션은 이 기능이 어떻게 작동하는지 보여줍니다. 이러한 예제에서는 캠페인에 있는 크리에이티브 이름이 포함된 파일을 만들지만 다른 조합은 가능합니다.

### 이벤트 호출

이 예에서는 크리에이티브 이름을 [!UICONTROL Audience Optimization] 보고서에 가져오는 메타데이터 파일을 만듭니다. 이를 위해서는 이벤트 호출에서 크리에이티브, 캠페인 및 데이터 소스 ID를 추출해야 합니다.

![이벤트 호출 이미지](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### 파일 이름

파일 이름은 크리에이티브, 캠페인 및 데이터 소스 ID를 기반으로 합니다. 이 경우 이벤트 호출에서 키-값 데이터와 파일 이름에 사용되는 방법 간의 차이점을 비교할 수 있습니다.

파일 이름:

* 데이터 소스 키가 `d_src`에서 `dpid`으로 변경됩니다.

* 크리에이티브 및 캠페인 ID는 실제 식별자가 아니라 카테고리를 나타냅니다.

![파일 이름 작성 방법](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

메타데이터 파일에 대한 [이름 지정 규칙](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)을 참조하십시오.

### 파일 내용

이 예에서 파일 콘텐츠는 이벤트 호출에 전달된 크리에이티브 및 캠페인 ID를 반영합니다. 여기에서 새 요소는 읽을 수 있는 이름입니다. 처리가 완료되면 이 파일의 이름이 [!UICONTROL Audience Optimization] 보고서의 크리에이티브 메뉴에 옵션으로 표시됩니다.

![메타데이터 파일의 내용](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

메타데이터 파일에 대한 [콘텐츠 형식](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md)을 참조하십시오.

### 파일 배달

이름을 지정하고 파일에 데이터를 추가한 후 [!DNL Audience Manager]에서 제공하는 Amazon CS3 저장소 디렉토리로 보냅니다. 메타데이터 파일에 대한 [배달 방법](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md)을 참조하십시오.

>[!MORELIKETHIS]
>
>* [Audience Optimization 보고서용 데이터 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [픽셀 호출을 통해 캠페인 클릭 데이터 캡처](../../../integration/media-data-integration/click-data-pixels.md)
>* [픽셀 호출을 통해 캠페인 노출 횟수 데이터 캡처](../../../integration/media-data-integration/impression-data-pixels.md)

