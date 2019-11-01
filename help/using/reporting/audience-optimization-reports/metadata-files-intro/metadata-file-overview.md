---
description: 메타데이터 파일은 읽고 이해할 수 있는 이름의 숫자 ID를 연결합니다. 대상 최적화 보고서는 다양한 보고서 옵션 메뉴에 읽을 수 있는 이름을 표시합니다.
seo-description: 메타데이터 파일은 읽고 이해할 수 있는 이름의 숫자 ID를 연결합니다. 대상 최적화 보고서는 다양한 보고서 옵션 메뉴에 읽을 수 있는 이름을 표시합니다.
seo-title: 메타데이터 파일에 대한 개요 및 매핑
solution: Audience Manager
title: 메타데이터 파일에 대한 개요 및 매핑
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 메타데이터 파일에 대한 개요 및 매핑{#overview-and-mappings-for-metadata-files}

메타데이터 파일은 읽고 이해할 수 있는 이름의 숫자 ID를 연결합니다. 대상 최적화 보고서는 다양한 보고서 옵션 메뉴에 읽을 수 있는 이름을 표시합니다.

## 개요 {#overview}

메타데이터 및 사용 방법에 대한 검토 메타데이터 파일에는 데이터 파일이 있어야 합니다. 메타데이터 파일 내용은 데이터 파일 정보를 보고서 메뉴에서 읽을 수 있는 관련 레이블과 일치시킵니다. 자세한 내용은 대상 최적화 [보고서용 데이터 파일을 참조하십시오](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### 메타데이터 파일에는 다른 데이터에 대한 데이터가 들어 있습니다.

메타데이터 파일에는 다른 유형의 데이터에 대한 정보가 들어 있습니다. 이 방법을 이해하는 데 도움이 되도록 데이터를 받는 방법을 [!DNL Audience Manager] 살펴보도록 하겠습니다.

임프레션 또는 클릭 이벤트가 진행되는 동안 [!DNL Audience Manager] URL 문자열의 *이벤트 호출이라고*&#x200B;하는 데이터를 받습니다.

이벤트 호출은 정보를 정의된 키-값 쌍 세트로 구성합니다. 키-값 쌍의 값에 숫자 데이터가 포함되어 있습니다. 메타데이터 파일에는 각 키-값 쌍의 ID에 해당하는 이름 및 기타 읽을 수 있는 정보가 포함되어 있습니다.

### 메타데이터 링크 ID를 읽을 수 있는 이름에 연결

메타데이터 파일은 숫자 ID를 읽을 수 있는 이름에 연결해야 합니다. 예를 들어 이벤트 호출에는 다음과 같은 키-값 쌍에 크리에이티브 ID가 포함되어 있다고 가정해 보십시오. `d_creative:1234`Adobe 메타데이터 파일이 없으면 이 크리에이티브가 옵션 메뉴에 1234로 표시됩니다.

그러나 제대로 포맷된 메타데이터 파일은 이 크리에이티브를 보고서에서 읽고 인식할 수 있는 이름인 "광고주 Creative A"와 같은 실제 이름으로 연결할 수 있습니다.

### 메타데이터 파일이 언제 필요합니까

먼저, 대상 최적화 보고서를 사용하려면 이벤트 호출에 메타데이터 파일과 아래에 나열된 모든 매개 변수가 [필요합니다](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

둘째, 데이터를 다른 제공업체의 보고서에 있는 데이터를 보려는 경우 [!DNL Audience Manager] 메타데이터 파일이 필요합니다. 예를 들어, [!DNL Audience Manager] Google의 Double- [click 캠페인 관리자](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM)와 통합됩니다. 이러한 관계로 인해 ID를 보고서 옵션에서 사용하는 이름 및 설명과 연결할 [!DNL Audience Manager] 수 있습니다. 통합이 없으면 데이터를 인제스트할 수 있지만 보고서 옵션은 설명 이름 대신 숫자 ID를 표시합니다.

![](assets/metadata_menu.png)

## 파일 매핑 {#file-mappings}

다음 표에는 [!UICONTROL Audience Optimization] 보고서에서 사용되는 데이터를 보유하는 키-값 쌍이 나열됩니다. 메타데이터 파일을 사용해야 하는 경우 이 키-값 쌍의 값에 해당하는 사람이 읽을 수 있는 정보가 포함됩니다. 이러한 키의 값은 정수만 사용합니다(데이터 유형 INT). Note, *italics* indicates a variable placeholder. 다른 요소는 상수 또는 키이며 변경되지 않습니다.

>[!IMPORTANT]
>
>보고서를 사용하는 경우 이벤트 호출에 이러한 [!UICONTROL Audience Optimization] 모든 ** 값이 필요합니다.

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
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>데이터 소스를 만들 때 제공되는 광고주의 데이터 소스 ID 또는 통합 코드입니다. 데이터 <a href="../../../features/manage-datasources.md#create-data-source"> 소스 만들기를 참조하십시오</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU(Business Unit) </p> </td> 
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
   <td colname="col2"> <p>두 개의 서로 다른 키-값 쌍을 수락합니다. </p> 
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

## 이벤트 호출 ID의 모양 파일 이름, 내용 및 전달 경로 {#how-ids-shape-file-names}

이러한 키-값 쌍으로 전달된 ID는 메타데이터 파일 이름과 해당 내용을 만드는 데 도움이 됩니다. 다음 섹션 및 일러스트레이션은 이러한 기능이 어떻게 작동하는지 보여줍니다. 이러한 예는 캠페인에서 크리에이티브 이름이 포함된 파일을 만들지만 다른 조합은 가능합니다.

### 이벤트 호출

이 예에서는 크리에이티브 이름을 [!UICONTROL Audience Optimization] 보고서에 가져오는 메타데이터 파일을 만듭니다. 이를 위해서는 이벤트 호출에서 크리에이티브, 캠페인 및 데이터 소스 ID를 추출해야 합니다.

![](assets/metadata_file_event.png)

### 파일 이름

파일 이름은 크리에이티브, 캠페인 및 데이터 소스 ID를 기반으로 합니다. 이 경우 여기에서 이벤트 호출의 키-값 데이터와 파일 이름에 사용되는 방법 간의 차이점을 비교합니다.

파일 이름:

* 데이터 소스 키가 에서 (으)로 `dpid` 변경됩니다 `d_src`.

* 크리에이티브 및 캠페인 ID는 실제 식별자가 아닌 카테고리를 나타냅니다.

![](assets/metadata_file_name.png)

메타데이터 [파일에 대한 이름 지정 규칙을 참조하십시오](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### 파일 내용

이 예에서 파일 내용은 이벤트 호출에 전달된 크리에이티브 및 캠페인 ID를 반영합니다. 여기에서 새 요소는 읽을 수 있는 이름입니다. 처리되면 이 파일의 이름이 [!UICONTROL Audience Optimization] 보고서의 크리에이티브 메뉴에 옵션으로 표시됩니다.

![](assets/metadata_file_contents.png)

메타데이터 [파일에 대한 컨텐츠 형식을 참조하십시오](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### 파일 배달

파일에 이름을 지정하고 데이터를 추가한 후 에서 제공하는 Amazon S3 스토리지 디렉토리로 보냅니다. [!DNL Audience Manager] 메타데이터 [파일에 대한 배달 방법을 참조하십시오](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [대상 최적화 보고서용 데이터 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [픽셀 호출을 통해 캠페인 클릭 데이터 캡처](../../../integration/media-data-integration/click-data-pixels.md)
>* [픽셀 호출을 통해 캠페인 노출 횟수 데이터 캡처](../../../integration/media-data-integration/impression-data-pixels.md)

