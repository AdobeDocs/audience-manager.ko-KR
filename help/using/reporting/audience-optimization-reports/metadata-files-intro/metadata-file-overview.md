---
description: 메타데이터 파일은 읽고 이해할 수 있는 이름으로 숫자 ID를 연결합니다. Audience Optimization 보고서에는 다양한 보고서 옵션 메뉴에 읽을 수 있는 이름이 표시됩니다.
seo-description: A metadata file links numeric IDs with names you can read and understand. The Audience Optimization reports display readable names in the various report options menus.
seo-title: Overview and Mappings for Metadata Files
solution: Audience Manager
title: 메타데이터 파일에 대한 개요 및 매핑
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: Log Files
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 4%

---

# 메타데이터 파일에 대한 개요 및 매핑{#overview-and-mappings-for-metadata-files}

메타데이터 파일은 읽고 이해할 수 있는 이름으로 숫자 ID를 연결합니다. Audience Optimization 보고서에는 다양한 보고서 옵션 메뉴에 읽을 수 있는 이름이 표시됩니다.

## 개요 {#overview}

메타데이터 및 메타데이터 사용 방법에 대한 리뷰입니다. 메타데이터 파일은 데이터 파일과 함께 있어야 합니다. 메타데이터 파일 콘텐츠는 보고서 메뉴에서 사람이 읽을 수 있는 관련 레이블에 데이터 파일 정보를 일치시킵니다. 자세한 내용은 [Audience Optimization 보고서용 데이터 파일 및 실행 가능 로그 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### 메타데이터 파일에는 다른 데이터에 대한 데이터가 포함되어 있습니다

메타데이터 파일에는 다른 유형의 데이터에 대한 정보가 들어 있습니다. 이 작동 방식을 이해하는 데 도움이 되도록 방법을 검토해 보겠습니다 [!DNL Audience Manager] 데이터를 받습니다.

노출 또는 클릭 이벤트 동안 [!DNL Audience Manager] 는 URL 문자열로서 데이터를 수신합니다. *이벤트 호출*.

이벤트 호출은 정보를 정의된 키-값 쌍 세트로 구성합니다. 키-값 쌍의 값에는 숫자 데이터가 포함됩니다. 메타데이터 파일에는 각 키-값 쌍의 ID에 해당하는 이름 및 기타 읽기 가능한 정보가 포함되어 있습니다.

### 메타데이터는 ID를 읽을 수 있는 이름에 연결합니다.

메타데이터 파일은 숫자 ID를 읽을 수 있는 이름에 연결하는 데 필요합니다. 예를 들어 이벤트 호출에 다음과 같이 키-값 쌍에 Creative ID가 포함되어 있다고 가정해 보겠습니다. `d_creative:1234`. 메타데이터 파일이 없으면 이 크리에이티브는 옵션 메뉴에 1234로 표시됩니다.

그러나 적절한 형식의 메타데이터 파일은 이 크리에이티브를 보고서에서 읽고 인식할 수 있는 이름인 &quot;Advertiser Creative A&quot;와 같은 실제 이름으로 다시 연결할 수 있습니다.

### 메타데이터 파일이 필요한 경우

먼저, 를 사용하려는 경우 이벤트 호출에 메타데이터 파일 및 아래에 나열된 모든 매개 변수가 필요합니다. [Audience Optimization 보고서](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

두 번째로, 자신의 데이터를에 전송하는 경우 메타데이터 파일이 필요합니다 [!DNL Audience Manager] 또는 통합되지 않은 다른 공급자의 보고서에서 데이터를 보려는 경우. 예를 들어, [!DNL Audience Manager] 은 Google의 와 통합됩니다. [Campaign Manager 두 번 클릭](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) DCM. 이 관계 때문에, [!DNL Audience Manager] 는 ID를 보고서 옵션에서 사용하는 이름 및 설명과 연결할 수 있습니다. 통합이 없어도 데이터를 수집할 수 있지만 보고서 옵션에는 수사적 이름 대신 숫자 ID가 표시됩니다.

![메타데이터 메뉴 이미지](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## 파일 매핑 {#file-mappings}

다음 표에는 가 사용하는 데이터가 들어 있는 키-값 쌍이 나열되어 있습니다 [!UICONTROL Audience Optimization] 보고서. 메타데이터 파일을 사용해야 하는 경우 여기에는 이러한 키-값 쌍의 값에 해당하는 사람이 읽을 수 있는 정보가 포함됩니다. 이 키의 값은 정수만 허용합니다(데이터 유형 INT). 참고, *기울임체* 변수 자리 표시자를 나타냅니다. 다른 요소는 상수 또는 키이며 변경되지 않습니다.

>[!IMPORTANT]
>
>를 사용하는 경우 [!UICONTROL Audience Optimization] 보고서, *모두* 이벤트 호출에는 이러한 값 중 하나가 필요합니다.

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
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>데이터 소스를 만들 때 제공된 광고주의 데이터 소스 ID 또는 통합 코드입니다. 다음을 참조하십시오 <a href="../../../features/manage-datasources.md#create-data-source"> 데이터 소스 만들기</a>. </p> </td> 
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
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>다음 은 <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 데이터 소스</a> 메타데이터 정보를 제공하는 플랫폼의 ID(예: DFA, Atlas, GBM, MediaMath 등). </p> </td> 
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

## 이벤트 호출 ID가 파일 이름, 콘텐츠 및 게재 경로를 형성하는 방법 {#how-ids-shape-file-names}

이러한 키-값 쌍에 의해 전달된 ID는 메타데이터 파일 이름 및 해당 컨텐츠를 만드는 데 도움이 됩니다. 다음 섹션 및 그림은 이 기능이 어떻게 작동하는지 보여 줍니다. 이러한 예제에서는 캠페인의 크리에이티브 이름을 포함하는 파일을 작성하지만 다른 조합을 만들 수도 있습니다.

### 이벤트 호출

이 예제에서는 크리에이티브 이름을 로 가져오는 메타데이터 파일을 만듭니다. [!UICONTROL Audience Optimization] 보고서. 이렇게 하려면 이벤트 호출에서 크리에이티브, 캠페인 및 데이터 소스 ID를 추출해야 합니다.

![이벤트 호출 이미지](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### 파일 이름

파일 이름은 크리에이티브, 캠페인 및 데이터 소스 ID를 기반으로 합니다. 이 경우 여기에서 이벤트 호출의 키-값 데이터와 파일 이름에서 사용하는 방법의 차이점을 비교합니다.

파일 이름:

* 데이터 소스 키가 다음으로 변경됨 `dpid` 출처: `d_src`.

* 광고 및 캠페인 ID는 실제 식별자가 아닌 카테고리를 나타냅니다.

![파일 이름 작성 방법](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

다음을 참조하십시오 [메타데이터 파일에 대한 이름 지정 규칙](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### 파일 내용

이 예에서 파일 콘텐츠는 이벤트 호출 시 전달된 크리에이티브 및 캠페인 ID를 반영합니다. 여기에서 새 요소는 읽을 수 있는 이름입니다. 이 파일이 처리되면 이 파일의 이름은 의 Creative 메뉴에 옵션으로 나타납니다. [!UICONTROL Audience Optimization] 보고서.

![메타데이터 파일의 내용](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

다음을 참조하십시오 [메타데이터 파일에 대한 컨텐츠 형식](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### 파일 게재

이름을 지정하고 데이터를 파일에 추가하면 다음에서 제공하는 Amazon S3 스토리지 디렉토리로 전송됩니다. [!DNL Audience Manager]. 다음을 참조하십시오 [메타데이터 파일에 대한 전달 방법](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [Audience Optimization 보고서용 데이터 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [픽셀 호출을 통해 캠페인 클릭 데이터 캡처](../../../integration/media-data-integration/click-data-pixels.md)
>* [픽셀 호출을 통해 캠페인 노출 횟수 데이터 캡처](../../../integration/media-data-integration/impression-data-pixels.md)

