---
description: 실행 가능한 로그 파일을 사용하면 Google DCM 로그 파일에서 미디어 데이터를 캡처하고 데이터를 사용하여 Audience Manager에서 트레이트를 만들 수 있습니다. 픽셀 호출을 사용하지 않고 광고 서버의 노출 수, 클릭 수 및 전환 수를 트레이트로 캡처합니다.
keywords: 실행 가능한 로그
seo-description: 실행 가능한 로그 파일을 사용하면 Google DCM 로그 파일에서 미디어 데이터를 캡처하고 데이터를 사용하여 Audience Manager에서 트레이트를 만들 수 있습니다. 픽셀 호출을 사용하지 않고 광고 서버의 노출 수, 클릭 수 및 전환 수를 트레이트로 캡처합니다.
seo-title: 실행 가능 로그 파일
solution: Audience Manager
title: 실행 가능 로그 파일
uuid: 4 C 47615 F-ED 47-41 BA -8694-1 D 7 DE 4 F 55 D 62
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# 실행 가능 로그 파일 {#actionable-log-files}

[!UICONTROL Actionable Log Files] Adobe Audience Manager에서 [!DNL Google DCM] 로그 파일에서 미디어 데이터를 캡처하고 데이터를 사용하여 트레이트를 만들 수 있습니다. 픽셀 호출을 사용하지 않고 광고 서버의 노출 수, 클릭 수 및 전환 수를 트레이트로 캡처합니다.

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 이 문서에서는 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../reference/code-style-elements.md)을 참조하십시오.

## 용도 {#purpose}

[!UICONTROL Actionable Log Files] 광고 서버에서 노출 횟수, 클릭 수 및 전환율을 캡처하는 방식을 간소화할 수 있습니다. 수동으로 픽셀 미디어를 보낼 필요 없이 사용자 세그멘테이션에 이 정보를 사용하여 캠페인 속성을 [!DNL Audience Manager]보낼 수 있습니다.

## 시작하기 {#getting-started}

시작하려면, Adobe의 대상 [!UICONTROL Actionable Log Files]최적화 [보고서를](../../reporting/audience-optimization-reports/audience-optimization-reports.md)사용하여 DCM 로그 데이터를 가져와야 [!DNL Audience Manager]합니다. Audience Manager로 DCM 데이터 파일 [가져오기를](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *참조하고* [!DNL Audience Manager] 컨설턴트에게 문의하십시오.

[!UICONTROL DCM] 이미 로그 데이터를 가져오는 [!DNL Audience Manager]경우 [!DNL Audience Manager] 컨설턴트나 [고객 지원 팀에](https://helpx.adobe.com/contact/enterprise-support.ec.html) 활성화를 [!UICONTROL Actionable Log Files] 요청하십시오.

>[!NOTE] {importance = "high"}
>
>[!UICONTROL Actionable Log Files] 로그 파일로만 [!DNL Google DCM] 작업할 수 있습니다.

## 실행 가능한 로그 파일 작업 {#working-with-actionable-log-files}

에서 [!UICONTROL Actionable Log Files], [!DNL DCM] 로그의 정보는 실시간 웹 사이트 [!DNL Audience Manager] 상호 작용에서 데이터를 캡처하는 것과 동일한 방식으로 캡처됩니다. [!DNL Audience Manager][!DNL Google Cloud] 스토리지에 연결하고, 로그에서 [!DNL DCM] 정보를 구문 분석하며, 로그 데이터를 실행 가능한 신호로 [데이터 수집 서버에 보냅니다](../../reference/system-components/components-data-collection.md#dcs-pcs).

실행 가능한 신호를 캡처하려면 규칙 기반의 트레이트를 설정해야 합니다. [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 에서 규칙 기반 트레이트를 설정하거나 [대량 관리 도구를 사용하는 방법을 참조하십시오](../../reference/bulk-management-tools/bulk-create.md). [실행 가능한 신호](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) 섹션으로 스크롤하여 규칙 기반의 트레이트에 사용할 수 있는 모든 키 목록을 표시합니다.

2 백만 라인의 평균 [!DNL DCM] 로그 파일에 대해 실행 가능한 신호에서 만들어진 모든 트레이트 구현은 로그를 처리한 후 약 1 시간 내에 구현됩니다.

>[!IMPORTANT] {importance = "high"}
>
>픽셀 호출 대신 구현하는 [!UICONTROL Actionable Log Files]**[](../../integration/media-data-integration/impression-data-pixels.md)것이 좋습니다. 두 옵션 모두 사용할 수 없으므로 트레이트에 대한 빈도 수가 늘어납니다.

## 실행 가능한 신호 {#actionable-signals}

신호는 가장 [작은 데이터](../../reference/signal-trait-segment.md) [!DNL Audience Manager]단위입니다. [!UICONTROL Actionable Log Files] 노출 이벤트, 클릭 이벤트 및 전환 이벤트의 광고주, 비즈니스 유닛, 크리에이티브 및 캠페인 값을 [!DNL DCM] 로그의 신호로 캡처할 수 있습니다.

이러한 정보를 고객 생성 및 세그멘테이션에 사용하려면 규칙 기반의 트레이트를 직접 설정해야 합니다. 아래 표는 [!DNL DCM] 로그 파일에서 실행 가능한 신호를 설명한 것입니다.

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 신호 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
   <th colname="col3" class="entry"> 값 예 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ event</code> </p> </td> 
   <td colname="col2"> <p>DCM의 이벤트 유형을 가리킵니다. </p> <p>허용되는 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_ event = 노출</code> 횟수에 대한 IMP. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_ event = 클릭</code> 수를 클릭합니다. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_ event = conv</code> 변환을 위한. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> IMP, 클릭, CONV</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversion</code> </p> </td> 
   <td colname="col2"> <p>전환 이벤트에만 사용할 수 있습니다. </p> <p>DCM의 전환 활동에 대한 숫자 ID를 나타냅니다. 이 필드는 DCM의 활동 ID로 매핑됩니다. </p> <p> <p>팁: DCM에서 여러 또는 특정 전환 활동을 캡처할 수 있습니다. DCM의 각 전환 활동에 <code> 대해 d_ conversion = Activity ID</code> 를 사용하여 트레이트를 만듭니다. </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversiontype</code> </p> </td> 
   <td colname="col2"> <p>전환 이벤트에만 사용할 수 있습니다. </p> <p>이 필드는 DCM의 전환 ID로 매핑됩니다. DCM에서 사용자 전환 이전에 발생한 활동을 나타냅니다. </p> <p>허용되는 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> 클릭 후 전환의 경우. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> 노출 후 전환의 경우. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> 에 일치하지 않는 전환입니다. 전환을 이전 활동과 비교할 수 없습니다. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col2"> <p>광고주 ID.</p> <p>광고주의 데이터 소스에 대한 통합 코드. Audience Manager Data Sources 와는 관련이 없습니다.</p> <p>이 필드는 DCM의 광고주 그룹 ID로 매핑됩니다. </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col2"> <p>사업부 ID. 이 필드는 DCM의 광고주 ID로 매핑됩니다. </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col2"> <p>DCM에서 제공하는 캠페인 ID. </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col2"> <p>DCM에서 제공하는 크리에이티브 ID. </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col2"> <p>DCM 데이터를 캡처하는 데 사용하는 데이터 소스의 ID. 데이터 <a href="../../features/manage-datasources.md#create-data-source"> 소스를 만드는</a>방법을 참조하십시오. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

테이블에 설명된 신호는 실시간 [!DNL Audience Manager]`HTTP` 호출처럼 캡처됩니다. 아래의 예에는 전환 이벤트에 대한 정보가 포함되어 [!DNL DCM]있습니다. 호출에 예시 호출에 모든 신호를 포함할 *필요는 없습니다.*

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance = "high"}
>
>[!DNL DCM] 로그에 제공된 이벤트 타임스탬프가 인정되고 [!UICONTROL Data Collection Servers]에 전달됩니다.
>
>* [!DNL DCM] 로그 파일에서 데이터 행에 타임스탬프를 사용할 수 없는 경우 `HTTP` , 호출 시간을 이벤트 타임스탬프로 사용합니다.
>* [!DNL DCM] 로그 파일의 데이터 행에 잘못된 형식의 타임스탬프가 있는 경우 전체 행을 무시합니다.


## 사용 사례 {#use-cases}

구현의 [!UICONTROL Actionable Log Files] 한 가지 이점은 [실행 가능한 신호를 포함하는 규칙 기반의 트레이트에 최근 및 빈도](../../features/segments/recency-and-frequency.md) [제어를](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 적용하는 옵션입니다. 예를 들어, 미디어 캠페인 내에서 사용자가 특정 크리에이티브를 보이는 횟수를 빈도수로 지정할 수 있습니다. 다른 사용 사례에는 다음이 포함됩니다.

### 사용자 리디렉션

Creative 123를 보았으나 클릭 또는 변환하거나 Creative 456를 표시하지 않은 사용자를 재타깃팅합니다. 방법:

1. 크리에이티브를 본 사용자를 캡처하는 트레이트를 만들 수 있습니다. 트레이트 이름을 지정한다고 가정합니다. [!DNL Creative Trait 123] 특성 규칙을 사용합니다.

   `d_creative == 123 AND d_event == imp`

1. 트레이트를 통해 클릭하거나 전환하는 사용자를 캡처할 수 있습니다. [!DNL Click and Converter]이 이름을 지정한다고 가정합니다. 특성 규칙을 사용합니다.

   `d_event == click OR d_event=conv`

1. Creative 123를 보았으나 클릭하거나 변환하지 않은 사용자로 채울 세그먼트를 만듭니다. 이름을 지정하고 [!DNL Retarget Users] 세그먼트 규칙을 사용합니다.

   `Creative Trait 123 AND NOT Click and Converter`

1. 세그먼트를 [!DNL Retarget Users] 대상에 매핑하고 Creative 456를 사용하여 대상의 사용자를 타깃팅합니다.

### Audience Optimization 보고서나 Audience Lab에서 DCM Floodlight 활동 사용

[Floodlight 태그를 사용하면](https://support.google.com/dcm/partner/answer/4293719?hl=en) 광고주가 사용자 전환을 추적할 수 있습니다. 를 사용하면 [!UICONTROL Actionable Log Files][!DNL DCM][대상 최적화 보고서나](../../reporting/audience-optimization-reports/audience-optimization-reports.md) [Audience Lab에서 전환을 추적할](../../features/audience-lab/audience-lab.md)수 있습니다.

1. 트레이트를 만들고 다음 트레이트 규칙을 사용하여 광고 서버 로그에서 전환을 캡처합니다.

   `d_event == conv AND d_conversion == 123`

   Audience Manager [!UICONTROL UI]에서 트레이트를 만들 때 [!UICONTROL Conversion][!UICONTROL Event Type]를 선택합니다.

2. 트레이트를 만들어지면 전환 및 in [!UICONTROL Audience Optimization Reports][!UICONTROL Audience Lab]에서 전환이 보고됩니다.

>[!MORE_ like_ this]
>
>* [Audience Manager로 DCM 데이터 파일 가져오기](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [고객 최적화 보고서](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

