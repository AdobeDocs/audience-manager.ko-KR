---
description: 실행 가능한 로그 파일을 사용하면 광고 서버 로그 파일에서 미디어 신호를 캡처하여 Audience Manager에서 트레이트를 만들 수 있습니다. 픽셀을 추가하지 않고도 광고 서버의 노출, 클릭 수 및 전환을 트레이트로 캡처할 수 있습니다.
keywords: 실행 가능 로그, alf, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: 실행 가능 로그 파일
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 2%

---

# 실행 가능 로그 파일 {#actionable-log-files}

[!UICONTROL Actionable Log Files]을(를) 사용하면 광고 서버 로그 파일에서 미디어 데이터를 캡처하고 이 데이터를 사용하여 Audience Manager에서 특성을 만들 수 있습니다. [픽셀](../../integration/media-data-integration/impression-data-pixels.md)을(를) 추가하지 않고도 광고 서버의 노출 횟수, 클릭 수 및 전환을 트레이트로 캡처할 수 있습니다.

>[!NOTE]
>
>이 문서의 텍스트 스타일(`monospaced text`, *기울임꼴*, 대괄호 `[ ]` `( )` 등)은 코드 요소와 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../reference/code-style-elements.md)을 참조하십시오.

## 용도 {#purpose}

[!UICONTROL Actionable Log Files]은(는) 광고 서버에서 노출 횟수, 클릭 수 및 전환을 캡처하는 방법을 간소화합니다. [!DNL Audience Manager]에 캠페인 특성을 보내기 위해 미디어를 수동으로 픽셀하지 않고도 사용자 세분화에 이 정보를 사용합니다.

## 시작하기 {#getting-started}

[!UICONTROL Actionable Log Files]을(를) 시작하려면 로그 데이터를 [!DNL Audience Manager]&#x200B;(으)로 가져와야 합니다. 다음 링크는 시작하는 데 도움이 됩니다.

* [!UICONTROL Google Campaign Manager] 로그의 경우 [Google Campaign Manager 데이터 파일을 Audience Manager으로 가져오기](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *및*&#x200B;을(를) 참조하십시오. [!DNL Audience Manager] 컨설턴트에게 문의하십시오.
* [!UICONTROL Google Ad Manager]&#x200B;(이전 Google DFP) 로그의 경우 [Audience Manager으로 Google Ad Manager 데이터 파일 가져오기](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *및*&#x200B;를 참조하십시오. [!DNL Audience Manager] 컨설턴트에게 문의하십시오.
* 다른 광고 서버 로그의 경우 [데이터 및 메타데이터 파일](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *및*&#x200B;을(를) 참조하여 [!DNL Audience Manager] 컨설턴트에게 문의하십시오.

이미 로그 데이터를 [!DNL Audience Manager]&#x200B;(으)로 가져오는 경우 [!DNL Audience Manager] 컨설턴트 또는 [고객 지원 센터](https://helpx.adobe.com/kr/contact/enterprise-support.ec.html)에 [!UICONTROL Actionable Log Files]을(를) 활성화하도록 요청하세요.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## 실행 가능 로그 파일 작업 {#working-with-actionable-log-files}

[!UICONTROL Actionable Log Files]을(를) 사용하면 광고 서버 로그의 정보가 실시간 웹 사이트 상호 작용에서 데이터를 캡처하는 것과 같은 방식으로 [!DNL Audience Manager]에 캡처됩니다. [!DNL Audience Manager]이(가) 광고 서버 로그 저장소에 연결하고, 로그에서 정보를 구문 분석하고, 로그 데이터를 실행 가능한 신호로 [데이터 수집 서버](../../reference/system-components/components-data-collection.md#dcs-pcs)에 보냅니다.

실행 가능한 신호를 캡처하려면 규칙 기반 트레이트를 설정해야 합니다. [Audience Manager 사용자 인터페이스](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)에서 또는 [대량 관리 도구](../../reference/bulk-management-tools/bulk-create.md)를 사용하여 규칙 기반 특성을 설정하는 방법을 알아보세요. [실행 가능한 신호](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) 섹션까지 아래로 스크롤하여 규칙 기반 트레이트에 사용할 수 있는 모든 키 목록을 확인하십시오.

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] *픽셀 호출* 대신 [&#128279;](../../integration/media-data-integration/impression-data-pixels.md)을(를) 구현하는 것이 좋습니다. 이 경우 트레이트의 빈도가 증가하므로 두 옵션을 모두 사용하지 않도록 합니다.

## 실행 가능한 신호 {#actionable-signals}

신호는 [에서 ](../../reference/signal-trait-segment.md)가장 작은 데이터 단위[!DNL Audience Manager]입니다. [!UICONTROL Actionable Log Files]을(를) 사용하면 광고 서버 로그의 신호로 광고주, 사업부, 광고 및 캠페인 값, 노출 이벤트, 클릭 이벤트 및 전환 이벤트를 캡처할 수 있습니다.

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files]은(는) 다음 광고 서버에 대해 지원됩니다.
>&#x200B;> <br>
>
> * [Google 캠페인 관리자](#dcm-logs-signals)
> * [Google 광고 관리자](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud, Flashtalking 및 Sizmek](#generic-logs-signals)

대상 만들기 및 세분화에 이 정보를 사용하려면 규칙 기반 특성을 직접 설정해야 합니다.

### Google Campaign Manager 로그에서 실행 가능한 신호 {#dcm-logs-signals}

표에는 [!DNL Google Campaign Manager] 로그 파일에서 실행 가능한 신호가 나열되어 있습니다.

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 로그 파일의 헤더 이름 </th> 
   <th colname="col2" class="entry"> 신호 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
   <th colname="col4" class="entry"> 값 예 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>전환 이벤트에만 사용할 수 있습니다. </p> <p>Google Campaign Manager에서 전환 활동에 대한 숫자 ID를 나타냅니다. 이 필드는 Google Campaign Manager의 활동 ID에 매핑됩니다. </p> <p> <p>팁: Google Campaign Manager에서 여러 전환 활동 또는 특정 전환 활동을 캡처할 수 있습니다. Google Campaign Manager의 각 전환 활동에 대해 <code> d_conversion = activity ID</code>을(를) 사용하여 트레이트를 만듭니다. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>전환 이벤트에만 사용할 수 있습니다. </p> <p>이 필드는 Google Campaign Manager의 전환 ID에 매핑됩니다. Google Campaign Manager에서 사용자 전환 이전의 활동을 나타냅니다. </p> <p>허용되는 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code>(후 클릭 전환). </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> 노출 후 전환의 경우 <code> 2</code>. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> 일치하지 않는 전환의 경우 <code> 0</code>입니다. 전환은 이전 활동과 일치시킬 수 없습니다. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">노출, 클릭 또는 전환 이벤트에 대한 UTC 날짜 및 시간입니다. 1970-01-01 00:00:00 UTC 이후 마이크로초로 표시됩니다.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>광고주의 데이터 소스에 대한 통합 코드. 이는 Audience Manager 데이터 소스와 관련이 없습니다.</p> <p>이 필드는 Google Campaign Manager의 광고주 그룹 ID에 매핑됩니다. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>사업부 ID. 이 필드는 Google Campaign Manager의 광고주 ID에 매핑됩니다. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Google Campaign Manager에서 제공한 캠페인 ID.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Google Campaign Manager에서 제공한 Creative ID. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 판매 금액(USD) -6의 거듭제곱입니다. 달러 금액으로 보려면 1.000.000을 곱하십시오.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>이벤트 유형을 나타냅니다. Audience Manager은 Google Campaign Manager 로그 파일 이름에서 이벤트 유형을 읽고 실행 가능한 신호로 변환합니다. </p> <p>허용되는 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> 노출 횟수는 <code> d_event = imp</code>입니다. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> 클릭 수에 대해 <code> d_event = click</code>입니다. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> 전환용 <code> d_event = conv</code>. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>Google 캠페인 관리자 데이터를 캡처하는 데 사용하는 데이터 소스의 ID입니다. <a href="../../features/manage-datasources.md#create-data-source"> 데이터 Source을 만드는 방법</a>을 참조하세요. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

표에 설명된 신호는 실시간 [!DNL Audience Manager] 호출처럼 `HTTP`에 캡처됩니다. 아래 예제 호출에는 [!DNL Google Campaign Manager]의 전환 이벤트에 대한 정보가 포함되어 있습니다. 호출은 예제 호출의 신호를 *모두*&#x200B;포함할 필요가 없습니다.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

평균 크기의 [!DNL Google Campaign Manager] 로그 파일(200만 줄)의 경우 실행 가능한 신호로 만들어진 모든 트레이트는 로그를 처리한 후 약 1시간 이내에 실현됩니다.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Google Campaign Manager] 로그에 제공된 이벤트 타임스탬프가 적용되며 [!UICONTROL Data Collection Servers]에 전달됩니다.
>
>* [!DNL Google Campaign Manager] 로그 파일의 데이터 행에 타임스탬프를 사용할 수 없는 경우 `HTTP` 호출 시간을 이벤트 타임스탬프로 사용합니다.
>* [!DNL Google Campaign Manager] 로그 파일의 데이터 행에 잘못된 형식의 타임스탬프가 들어 있으면 전체 행을 무시합니다.

<br> 

### [!DNL Google Ad Manager] 로그에서 실행 가능한 신호 {#ad-manager-logs-signals}

표에는 [!DNL Google Ad Manager] 로그 파일에서 실행 가능한 신호가 나열되어 있습니다.


| 로그 파일의 헤더 이름 | 신호 | 설명 |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | 게재된 광고 관리자 라인 항목에 대한 숫자 ID |
| `OrderId` | `d_orderid` | 배달된 라인 항목 및 크리에이티브가 포함된 광고 관리자 주문의 숫자 ID입니다. |
| `CreativeId` | `d_creative` | 게재된 광고 관리자 크리에이티브에 대한 숫자 ID입니다. |
| `-` | `d_event` | 이벤트 유형을 나타냅니다. Audience Manager은 Ad Manager 로그 파일 이름에서 이벤트 유형을 읽고 실행 가능한 신호로 변환합니다. 허용되는 값: <br> <ul><li>d_event = 노출 횟수에 대한 imp.</li><li>d_event = 클릭 수를 클릭합니다.</li><li>d_event = 전환 및 활동에 대한 conv.</li></ul> |
| `-` | `d_src` | Ad Manager 데이터를 캡처하는 데 사용하는 데이터 소스의 ID입니다. [데이터 Source을 만드는 방법](/help/using/features/manage-datasources.md)을 참조하세요. |

표에 설명된 신호는 실시간 HTTP 호출과 같이 Audience Manager에서 캡처됩니다. 아래 예제 호출에는 Google Ad Manager의 전환 이벤트에 대한 정보가 포함되어 있습니다. 호출이 반드시 예제 호출의 모든 신호를 포함할 필요는 없습니다.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>[!DNL Google Ad Manager] 로그에 제공된 이벤트 타임스탬프가 적용되며 [!UICONTROL Data Collection Servers]에 전달됩니다.
>
>
>* [!DNL Google Ad Manager] 로그 파일의 데이터 행에 타임스탬프를 사용할 수 없는 경우 `HTTP` 호출 시간을 이벤트 타임스탬프로 사용합니다.
>* [!DNL Google Ad Manager] 로그 파일의 데이터 행에 잘못된 형식의 타임스탬프가 들어 있으면 전체 행을 무시합니다.

<br> 

### Adobe Advertising Cloud, Flashtalking 및 Sizmek 광고 서버 로그에서 실행 가능한 신호 {#generic-logs-signals}

먼저 Amazon S3 버킷에 광고 서버 로그를 배치해야 합니다. 이를 위해 [Audience Optimization 보고서 및 실행 가능한 로그 파일에 대한 데이터 파일](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *및*&#x200B;을(를) 읽으십시오.[!DNL Audience Manager] 컨설턴트에게 문의하십시오. 표에는 광고 서버 로그 파일에서 실행 가능한 신호가 나열되어 있습니다.

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 로그 파일의 헤더 이름 </th> 
   <th colname="col2" class="entry"> 신호 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
   <th colname="col4" class="entry"> 값 예 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>전환이 일치하는지 여부를 나타냅니다. 옵션은 다음과 같습니다. </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> 노출 횟수 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> 클릭 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> 속성 또는 알 수 없음 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> 노출, 클릭 또는 전환 이벤트에 대한 UTC 날짜 및 시간입니다. <code>yyyy-MM-dd HH:mm:ss</code> 형식을 사용합니다. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>광고주의 데이터 소스에 대한 통합 코드. 이 필드는 <a href="../../features/datasources-list-and-settings.md">Audience Manager 데이터 원본</a>과(와) 관련이 없습니다.</p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>사업부 ID.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>로그 파일의 캠페인 ID입니다.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>로그 파일의 Creative ID입니다. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 구매 또는 기타 전환 금액. 데이터 유형: 부동 소수점 </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>이벤트 유형을 나타냅니다. Audience Manager은 로그 파일 이름에서 이벤트 유형을 읽고 실행 가능한 신호로 변환합니다. <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">로그 파일 이름 지정 규칙</a>을 참조하십시오. </p> <p>허용되는 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> 노출 횟수는 <code> d_event = imp</code>입니다. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> 클릭 수에 대해 <code> d_event = click</code>입니다. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> 전환용 <code> d_event = conv</code>. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>로그 데이터를 캡처하는 데 사용하는 데이터 소스의 ID입니다. <a href="../../features/manage-datasources.md#create-data-source"> 데이터 Source을 만드는 방법</a>을 참조하세요. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

표에 설명된 신호는 실시간 [!DNL Audience Manager] 호출처럼 `HTTP`에 캡처됩니다. 호출은 예제 호출의 신호를 *모두*&#x200B;포함할 필요가 없습니다.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Audience Manager 사용자 인터페이스에서 실행 가능한 신호 작업 {#actionable-signals-in-ui}

[신호 검색](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) 인터페이스에서 들어오는 실행 가능한 신호를 볼 수 있습니다.

**대상 데이터** (1) > **신호** (2) > **검색** (3)으로 이동하고 **실행 가능한 로그 파일** (4) 필터를 선택합니다.

UI의 ![실행 가능한 신호](/help/using/integration/assets/alf-in-signals.png)

실행 가능한 신호를 사용하여 규칙 기반 특성을 만들려면 **실행 가능한 로그 파일**(1)을 선택하고 특성 규칙으로 사용할 실행 가능한 신호를 선택한 다음(2) **선택한 신호에서 특성 만들기**(3)를 누릅니다.

![신호에서 트레이트 만들기](/help/using/integration/assets/alf-create-trait.png)


## 사용 사례 {#use-cases}

[!UICONTROL Actionable Log Files]을(를) 구현하면 실행 가능한 신호가 포함된 [규칙 기반 특성](../../features/segments/recency-and-frequency.md)에 [최신성 및 빈도](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 컨트롤을 적용할 수 있습니다. 예를 들어 미디어 캠페인 내에서 사용자가 특정 크리에이티브를 표시하는 횟수를 제한할 수 있습니다. 이 작업을 수행하는 방법에 대해 알아보려면 [즉각적인 장치 간 억제](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)를 읽어 보십시오. 기타 사용 사례는 다음과 같습니다.

### 사용자 재타겟팅

creative 123을 보았지만 클릭하거나 전환하지 않고 creative 456을 표시한 사용자를 재타겟팅합니다. 다음을 수행합니다.

1. 트레이트를 만들어 크리에이티브를 본 사용자를 캡처합니다. 트레이트 이름을 [!DNL Creative Trait 123]로 정해 보겠습니다. 트레이트 규칙 사용:

   `d_creative == 123 AND d_event == imp`

2. 클릭하거나 전환하는 사용자를 캡처할 트레이트를 만듭니다. 이름을 [!DNL Click and Converter]&#x200B;(으)로 지정한다고 가정해 보겠습니다. 트레이트 규칙 사용:

   `d_event == click OR d_event=conv`

3. Creative 123을 보았지만 클릭하거나 전환하지 않은 사용자로 채우려면 세그먼트를 만듭니다. 이름을 [!DNL Retarget Users]로 지정하고 세그먼트 규칙을 사용합니다.

   `Creative Trait 123 AND NOT Click and Converter`

4. Creative 456을 사용하여 세그먼트 [!DNL Retarget Users]을(를) 대상 및 대상의 대상 사용자에 매핑합니다.

### Google 보고서 또는 Audience Lab에서 Audience Optimization Campaign Manager Floodlight 활동 사용

[Floodlight 태그](https://support.google.com/dcm/partner/answer/4293719?hl=en)를 통해 광고주는 사용자 전환을 추적할 수 있습니다. [!UICONTROL Actionable Log Files]을(를) 사용하면 [!DNL Google Campaign Manager]Audience Optimization 보고서[ 또는 ](../../reporting/audience-optimization-reports/audience-optimization-reports.md)대상 랩[에서 ](../../features/audience-lab/audience-lab.md) 전환을 추적할 수 있습니다.

1. 트레이트를 만들고 다음 트레이트 규칙을 사용하여 광고 서버 로그에서 전환을 캡처합니다.

   `d_event == conv AND d_conversion == 123`

   Audience Manager [!UICONTROL UI]에서 특성을 만들 때 [!UICONTROL Conversion]을(를) [!UICONTROL Event Type]&#x200B;(으)로 선택합니다.

2. 트레이트를 만들면 [!UICONTROL Audience Optimization Reports]과(와) [!UICONTROL Audience Lab]에 대한 전환이 보고되기 시작합니다.

>[!MORELIKETHIS]
>
>* [Google Campaign Manager 데이터 파일을 Audience Manager으로 가져오기](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [대상자 최적화 보고서](../../reporting/audience-optimization-reports/audience-optimization-reports.md)
