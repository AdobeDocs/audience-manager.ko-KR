---
description: 실행 가능한 로그 파일을 사용하면 Google DCM 로그 파일에서 미디어 데이터를 캡처하고 데이터를 사용하여 Audience Manager에서 트레이트를 만들 수 있습니다. 픽셀 호출을 사용하지 않고 광고 서버의 노출 수, 클릭 수 및 전환 수를 트레이트로 캡처합니다.
keywords: 실행 가능한 로그
seo-description: 실행 가능한 로그 파일을 사용하면 Google DCM 로그 파일에서 미디어 데이터를 캡처하고 데이터를 사용하여 Audience Manager에서 트레이트를 만들 수 있습니다. 픽셀 호출을 사용하지 않고 광고 서버의 노출 수, 클릭 수 및 전환 수를 트레이트로 캡처합니다.
seo-title: 실행 가능 로그 파일
solution: Audience Manager
title: 실행 가능 로그 파일
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# 실행 가능 로그 파일 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 로그 파일에서 미디어 데이터를 캡처하고 데이터를 사용하여 Audience Manager에서 트레이트를 만들 수 있습니다. [!DNL Google DCM] 픽셀 호출을 사용하지 않고 광고 서버의 노출 수, 클릭 수 및 전환 수를 트레이트로 캡처합니다.

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 이 문서에서는 코드 요소와 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../reference/code-style-elements.md)을 참조하십시오.

## 용도 {#purpose}

[!UICONTROL Actionable Log Files] 광고 서버에서 노출, 클릭 및 전환을 캡처하는 방법을 간소화할 수 있습니다. 캠페인 속성을 전송하려면 수동으로 픽셀 미디어를 전송하지 않고도 사용자 세그먼테이션에 이 정보를 [!DNL Audience Manager]사용합니다.

## 시작하기 {#getting-started}

Adobe 고객 최적화 보고서를 사용하여 [!UICONTROL Actionable Log Files]시작하려면 [DCM](../../reporting/audience-optimization-reports/audience-optimization-reports.md)로그 데이터를 [!DNL Audience Manager]로 가져와야 합니다. Audience [Manager로 DCM 데이터 파일 가져오기를](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)** 참조하고 [!DNL Audience Manager] 컨설턴트에게 문의하십시오.

로그 데이터를 이미 [!UICONTROL DCM] 로 가져오는 [!DNL Audience Manager]경우 [!DNL Audience Manager] 컨설턴트나 고객 지원 센터에 [문의하여](https://helpx.adobe.com/contact/enterprise-support.ec.html) [!UICONTROL Actionable Log Files] 활성화를 요청하십시오.

>[!NOTE] {importance="high"}
>
>[!UICONTROL Actionable Log Files] 로그 파일에서만 [!DNL Google DCM] 작업할 수 있습니다.

## 실행 가능한 로그 파일 작업 {#working-with-actionable-log-files}

를 [!UICONTROL Actionable Log Files]사용하면 [!DNL DCM] 로그의 정보가 실시간 웹 사이트 상호 작용에서 데이터를 캡처하는 것과 [!DNL Audience Manager] 같은 방식으로 캡처됩니다. [!DNL Audience Manager] 스토리지 [!DNL Google Cloud] 접속, [!DNL DCM] 로그의 정보 구문 분석 및 실행 가능한 신호로 로그 데이터를 Adobe 데이터 수집 서버에 [전송합니다](../../reference/system-components/components-data-collection.md#dcs-pcs).

실행 가능한 신호를 캡처하려면 규칙 기반 트레이트를 설정해야 합니다. Audience Manager UI에서 또는 벌크 관리 [도구를](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 사용하여 규칙 기반 [트레이트를](../../reference/bulk-management-tools/bulk-create.md)설정하는 방법을참조하십시오. 규칙 기반 트레이트에서 [사용할](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) 수 있는 모든 키 목록을 보려면 실행 가능 신호 섹션으로 스크롤하십시오.

평균 크기의 200만 줄의 [!DNL DCM] 로그 파일의 경우 실행 가능한 신호로 생성된 모든 트레이트는 로그를 처리한 후 약 1시간 이내에 실현됩니다.

>[!IMPORTANT] {importance="high"}
>
>픽셀 호출 [!UICONTROL Actionable Log Files] 대신 *구현하는 것이* 좋습니다 [](../../integration/media-data-integration/impression-data-pixels.md). 트레이트의 주파수 카운트가 증가하므로 두 옵션 모두 사용하지 않습니다.

## 실행 가능한 신호 {#actionable-signals}

신호는 [가장 작은 데이터](../../reference/signal-trait-segment.md) 단위입니다 [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] 노출 이벤트, 클릭 이벤트 및 전환 이벤트에서 광고주, 사업부, 크리에이티브 및 캠페인 값을 [!DNL DCM] 로그로부터의 신호로 캡처할 수 있습니다.

고객 생성 및 세그멘테이션에 이 정보를 사용하려면 규칙 기반 트레이트를 직접 설정해야 합니다. 이 표에는 [!DNL DCM] 로그 파일의 실행 가능한 신호가 나열됩니다.

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
   <td colname="col1"> <p> <code> d_event</code> </p> </td> 
   <td colname="col2"> <p>DCM의 이벤트 유형을 나타냅니다. </p> <p>허용된 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = 노출 횟수에</code> 대한 imp </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = 클릭에 대한 클릭</code> . </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> for conversions. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col2"> <p>전환 이벤트에만 사용할 수 있습니다. </p> <p>DCM의 전환 활동에 대한 숫자 ID를 나타냅니다. 이 필드는 DCM 파섹 </p> <p> <p>팁:DCM 파섹 DCM의 각 전환 활동에 대해 <code> d_conversion = 활동</code> ID를 사용하여 트레이트를 만듭니다. </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversionType</code> </p> </td> 
   <td colname="col2"> <p>전환 이벤트에만 사용할 수 있습니다. </p> <p>이 필드는 DCM 파섹 DCM에서 사용자 변환 이전의 활동을 나타냅니다. </p> <p>허용된 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> - 클릭 후 전환용 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> 노출 후 전환을 위한 솔루션 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> - 일치하지 않는 전환의 경우. 전환은 이전 활동과 일치할 수 없습니다. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col2"> <p>광고주 ID.</p> <p>광고주의 데이터 소스에 대한 통합 코드입니다. 이 데이터는 Audience Manager 데이터 소스와 관련이 없습니다.</p> <p>이 필드는 DCM의 광고주 그룹 ID에 매핑됩니다. </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col2"> <p>사업 단위 ID. 이 필드는 DCM 파섹 </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col2"> <p>DCM에서 제공하는 캠페인 ID입니다. </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col2"> <p>DCM에서 제공하는 크리에이티브 ID. </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col2"> <p>DCM 데이터를 캡처하는 데 사용하는 데이터 소스의 ID입니다. 데이터 <a href="../../features/manage-datasources.md#create-data-source"> 소스 생성 방법을 참조하십시오</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

표에 설명된 신호들은 실시간 [!DNL Audience Manager] 호출과 `HTTP` 같이 캡처됩니다. 아래 예제 호출에는 전환 이벤트에 대한 정보가 포함되어 [!DNL DCM]있습니다. 호출은 예제 호출에 *모든* 신호를 포함해야 하는 것은 아닙니다.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance="high"}
>
>로그에 제공된 이벤트 타임스탬프는 [!DNL DCM] 그대로 유지되고 [!UICONTROL Data Collection Servers]사용자에게 전달됩니다.
>
>* 로그 파일의 데이터 행에 타임스탬프를 사용할 수 없는 [!DNL DCM] 경우 `HTTP` 호출 시간을 이벤트 타임스탬프로 사용합니다.
>* 로그 파일의 데이터 행에 잘못된 형식의 타임스탬프가 포함되어 있으면 전체 행을 무시합니다. [!DNL DCM]


## 사용 사례 {#use-cases}

구현의 [!UICONTROL Actionable Log Files] 한 가지 이점은 실행 가능한 신호가 포함된 [규칙 기반의 트레이트에](../../features/segments/recency-and-frequency.md) 최근 [및 빈도](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 제어를 적용할 수 있다는 것입니다. 예를 들어 미디어 캠페인 내에서 특정 크리에이티브를 사용자가 표시하는 횟수를 주파수로 제한할 수 있습니다. 기타 사용 사례는 다음과 같습니다.

### 사용자 리타겟팅

크리에이티브 123을 보았으나 클릭 또는 전환하지 않고 크리에이티브 456을 표시한 사용자를 리타겟팅합니다. 방법:

1. 크리에이티브를 본 사용자를 캡처할 트레이트를 만듭니다. 트레이트 이름을 [!DNL Creative Trait 123]말해봅시다. 특성 규칙을 사용합니다.

   `d_creative == 123 AND d_event == imp`

1. 클릭 또는 전환 사용자를 캡처할 트레이트를 만듭니다. 이 이름을 [!DNL Click and Converter]알려주세요 특성 규칙을 사용합니다.

   `d_event == click OR d_event=conv`

1. 크리에이티브 123을 보았으나 클릭하거나 변환하지 않은 사용자로 채울 세그먼트를 만듭니다. 이름을 지정하고 세그먼트 규칙을 [!DNL Retarget Users] 사용합니다.

   `Creative Trait 123 AND NOT Click and Converter`

1. 크리에이티브 456을 사용하여 세그먼트를 대상에 [!DNL Retarget Users] 매핑하고 대상의 사용자를 타깃팅합니다.

### 고객 최적화 보고서 또는 Audience Lab에서 DCM Floodlight 활동 사용

[Floodlight 태그를](https://support.google.com/dcm/partner/answer/4293719?hl=en) 사용하면 광고주가 사용자 전환을 추적할 수 있습니다. 를 [!UICONTROL Actionable Log Files]사용하면 대상 최적화 보고서 또는 Audience Lab에서 [!DNL DCM][전환을 추적할](../../reporting/audience-optimization-reports/audience-optimization-reports.md) 수 [있습니다](../../features/audience-lab/audience-lab.md).

1. 트레이트를 만들고 다음 트레이트 규칙을 사용하여 광고 서버 로그에서 변환을 캡처합니다.

   `d_event == conv AND d_conversion == 123`

   Audience Manager에서 트레이트를 만들 [!UICONTROL UI]때 트레이트를 [!UICONTROL Conversion] 로 선택합니다 [!UICONTROL Event Type].

2. 트레이트를 만든 후, 전환은 [!UICONTROL Audience Optimization Reports] 및 에서 보고됩니다 [!UICONTROL Audience Lab].

>[!MORELIKE_THIS]
>
>* [Audience Manager로 DCM 데이터 파일 가져오기](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [고객 최적화 보고서](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

