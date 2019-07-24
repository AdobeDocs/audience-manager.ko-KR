---
description: 실행 가능한 로그 파일을 사용하면 Google DCM 로그 파일에서 미디어 데이터를 캡처하고 데이터를 사용하여 Audience Manager에서 트레이트를 만들 수 있습니다. 픽셀 호출을 사용하지 않고 광고 서버의 노출 수, 클릭 수 및 전환 수를 트레이트로 캡처합니다.
keywords: 실행 가능한 로그
seo-description: 실행 가능한 로그 파일을 사용하면 Google DCM 로그 파일에서 미디어 데이터를 캡처하고 데이터를 사용하여 Audience Manager에서 트레이트를 만들 수 있습니다. 픽셀 호출을 사용하지 않고 광고 서버의 노출 수, 클릭 수 및 전환 수를 트레이트로 캡처합니다.
seo-title: 실행 가능 로그 파일
solution: Audience Manager
title: 실행 가능 로그 파일
uuid: 4 C 47615 F-ED 47-41 BA -8694-1 D 7 DE 4 F 55 D 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 실행 가능 로그 파일 {#actionable-log-files}

[!UICONTROL Actionable Log Files] Adobe Audience Manager에서 [!DNL Google DCM] 로그 파일에서 미디어 데이터를 캡처하고 데이터를 사용하여 트레이트를 만들 수 있습니다. 픽셀 호출을 사용하지 않고 광고 서버의 노출 수, 클릭 수 및 전환 수를 트레이트로 캡처합니다.

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 이 문서에서는 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../reference/code-style-elements.md)을 참조하십시오.

## 용도 {#purpose}

[!UICONTROL Actionable Log Files] 광고 서버에서 노출 횟수, 클릭 수 및 전환율을 캡처하는 방식을 간소화할 수 있습니다. Use this information for user segmentation without having to manually pixel media to send campaign attributes to [!DNL Audience Manager].

## 시작하기 {#getting-started}

To get started with [!UICONTROL Actionable Log Files], and to use our [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md), you need to import DCM log data into [!DNL Audience Manager]. See [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *and* contact your [!DNL Audience Manager] consultant.

[!UICONTROL DCM] 이미 로그 데이터를 가져오는 [!DNL Audience Manager]경우 [!DNL Audience Manager] 컨설턴트나 [고객 지원 팀에](https://helpx.adobe.com/contact/enterprise-support.ec.html) 활성화를 [!UICONTROL Actionable Log Files] 요청하십시오.

>[!NOTE] {importance = "high"}
>
>[!UICONTROL Actionable Log Files] 로그 파일로만 [!DNL Google DCM] 작업할 수 있습니다.

## Working with Actionable Log Files {#working-with-actionable-log-files}

With [!UICONTROL Actionable Log Files], the information from [!DNL DCM] logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager][!DNL Google Cloud] 스토리지에 연결하고, 로그에서 [!DNL DCM] 정보를 구문 분석하며, 로그 데이터를 실행 가능한 신호로 [데이터 수집 서버에 보냅니다](../../reference/system-components/components-data-collection.md#dcs-pcs).

실행 가능한 신호를 캡처하려면 규칙 기반의 트레이트를 설정해야 합니다. [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 에서 규칙 기반 트레이트를 설정하거나 [대량 관리 도구를 사용하는 방법을 참조하십시오](../../reference/bulk-management-tools/bulk-create.md). [실행 가능한 신호](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) 섹션으로 스크롤하여 규칙 기반의 트레이트에 사용할 수 있는 모든 키 목록을 표시합니다.

For an average-sized [!DNL DCM] log file of 2 million lines, any traits created from actionable signals are realized within approximately one hour after we process the logs.

>[!IMPORTANT] {importance = "high"}
>
>We recommend implementing [!UICONTROL Actionable Log Files] *instead of*  [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). 두 옵션 모두 사용할 수 없으므로 트레이트에 대한 빈도 수가 늘어납니다.

## Actionable Signals {#actionable-signals}

Signals are the [smallest data units](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] 노출 이벤트, 클릭 이벤트 및 전환 이벤트의 광고주, 비즈니스 유닛, 크리에이티브 및 캠페인 값을 [!DNL DCM] 로그의 신호로 캡처할 수 있습니다.

이러한 정보를 고객 생성 및 세그멘테이션에 사용하려면 규칙 기반의 트레이트를 직접 설정해야 합니다. The table lists the actionable signals from [!DNL DCM] log files:

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
   <td colname="col2"> <p>전환 이벤트에만 사용할 수 있습니다. </p> <p>DCM의 전환 활동에 대한 숫자 ID를 나타냅니다. 이 필드는 DCM의 활동 ID로 매핑됩니다. </p> <p> <p>팁: DCM에서 여러 또는 특정 전환 활동을 캡처할 수 있습니다. Create traits using <code> d_conversion = activity ID</code> for each conversion activity from DCM. </p> </p> </td> 
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
   <td colname="col2"> <p>광고주 ID. 이 필드는 DCM의 광고주 그룹 ID로 매핑됩니다. </p> </td> 
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
   <td colname="col2"> <p>DCM 데이터를 캡처하는 데 사용하는 데이터 소스의 ID. See <a href="../../features/manage-datasources.md#create-data-source"> How to Create a Data Source</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

The signals described in the table are captured in [!DNL Audience Manager] like a real-time `HTTP` call. The example call below contains information on a conversion event from [!DNL DCM]. Calls do not necessarily have to include *all* the signals in the example call.

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

One benefit of implementing [!UICONTROL Actionable Log Files] is the option to apply [recency and frequency](../../features/segments/recency-and-frequency.md) controls to any [rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) that contain actionable signals. 예를 들어, 미디어 캠페인 내에서 사용자가 특정 크리에이티브를 보이는 횟수를 빈도수로 지정할 수 있습니다. 다른 사용 사례에는 다음이 포함됩니다.

### 사용자 리디렉션

Creative 123를 보았으나 클릭 또는 변환하거나 Creative 456를 표시하지 않은 사용자를 재타깃팅합니다. 방법:

1. 크리에이티브를 본 사용자를 캡처하는 트레이트를 만들 수 있습니다. Let's say you name the trait [!DNL Creative Trait 123]. 특성 규칙을 사용합니다.

   `d_creative == 123 AND d_event == imp`

1. 트레이트를 통해 클릭하거나 전환하는 사용자를 캡처할 수 있습니다. [!DNL Click and Converter]이 이름을 지정한다고 가정합니다. 특성 규칙을 사용합니다.

   `d_event == click OR d_event=conv`

1. Creative 123를 보았으나 클릭하거나 변환하지 않은 사용자로 채울 세그먼트를 만듭니다. Name it [!DNL Retarget Users] and use the segment rule:

   `Creative Trait 123 AND NOT Click and Converter`

1. Map the segment [!DNL Retarget Users] to a destination and target users in the destination with creative 456.

### Audience Optimization 보고서나 Audience Lab에서 DCM Floodlight 활동 사용

[Floodlight 태그를 사용하면](https://support.google.com/dcm/partner/answer/4293719?hl=en) 광고주가 사용자 전환을 추적할 수 있습니다. With [!UICONTROL Actionable Log Files], you can track the [!DNL DCM] conversions in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md) or in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. 트레이트를 만들고 다음 트레이트 규칙을 사용하여 광고 서버 로그에서 전환을 캡처합니다.

   `d_event == conv AND d_conversion == 123`

   When creating the trait in the Audience Manager [!UICONTROL UI], select [!UICONTROL Conversion] as the [!UICONTROL Event Type].

2. Once you have created the trait, the conversion will begin to be reported against in the [!UICONTROL Audience Optimization Reports] and in [!UICONTROL Audience Lab].

>[!MORE_ like_ this]
>
>* [Audience Manager로 DCM 데이터 파일 가져오기](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [고객 최적화 보고서](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

