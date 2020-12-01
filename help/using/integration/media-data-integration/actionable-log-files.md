---
description: 실행 가능한 로그 파일을 사용하면 광고 서버 로그 파일에서 미디어 신호를 캡처하여 Audience Manager에서 트레이트를 만들 수 있습니다. 픽셀을 추가하지 않고도 광고 서버의 노출, 클릭 및 전환을 트레이트로 캡처할 수 있습니다.
keywords: actionable logs, alf, ALF
seo-description: 실행 가능한 로그 파일을 사용하면 광고 서버 로그 파일에서 미디어 신호를 캡처하여 Audience Manager에서 트레이트를 만들 수 있습니다. 픽셀을 추가하지 않고도 광고 서버의 노출, 클릭 및 전환을 트레이트로 캡처할 수 있습니다.
seo-title: 실행 가능 로그 파일
solution: Audience Manager
title: 실행 가능 로그 파일
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
translation-type: tm+mt
source-git-commit: a4d86fb0324a03002123f8713eb9786b5b74c38e
workflow-type: tm+mt
source-wordcount: '1605'
ht-degree: 3%

---


# 실행 가능 로그 파일 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 광고 서버 로그 파일에서 미디어 데이터를 캡처하고 데이터를 사용하여 Audience Manager에서 트레이트를 만들 수 있습니다. [pixels](../../integration/media-data-integration/impression-data-pixels.md)를 추가하지 않고도 광고 서버의 노출, 클릭 및 전환을 트레이트로 캡처할 수 있습니다.

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 이 문서에서는 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../reference/code-style-elements.md)을 참조하십시오.

## 용도 {#purpose}

[!UICONTROL Actionable Log Files] 광고 서버에서 노출, 클릭 및 전환을 캡처하는 방법을 간소화할 수 있습니다. 캠페인 속성을 [!DNL Audience Manager]으로 전송하려면 수동으로 픽셀 미디어를 사용하지 않고도 사용자 세그먼테이션에 이 정보를 사용하십시오.

## 시작하기 {#getting-started}

[!UICONTROL Actionable Log Files]으로 시작하려면 로그 데이터를 [!DNL Audience Manager]로 가져와야 합니다. 다음 링크를 통해 시작할 수 있습니다.

* [!UICONTROL Google Campaign Manager] 로그의 경우 [Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *로 Google Campaign Manager 데이터 파일 가져오기를 참조하고* 컨설턴트에게 문의하십시오.[!DNL Audience Manager]
* [!UICONTROL Google Ad Manager](이전 Google DFP) 로그의 경우 [Audience Manager으로 Google Ad Manager 데이터 파일 가져오기](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *를 참조하고* 컨설턴트에게 문의하십시오.[!DNL Audience Manager]
* 다른 광고 서버 로그에 대해서는 [데이터 및 메타데이터 파일](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *과*&#x200B;을(를) 참조하여 [!DNL Audience Manager] 컨설턴트에게 문의하십시오.

로그 데이터를 이미 [!DNL Audience Manager]으로 가져오는 경우 [!DNL Audience Manager] 컨설턴트 또는 [고객 지원 센터](https://helpx.adobe.com/kr/contact/enterprise-support.ec.html)에 문의하여 [!UICONTROL Actionable Log Files]를 활성화하십시오.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## 실행 가능한 로그 파일 작업 {#working-with-actionable-log-files}

[!UICONTROL Actionable Log Files]에서는 실시간 웹 사이트 상호 작용에서 데이터를 캡처하는 것과 동일한 방식으로 광고 서버 로그의 정보가 [!DNL Audience Manager]에 캡처됩니다. [!DNL Audience Manager] 광고 서버 로그 스토리지에 연결하고, 로그에서 정보를 구문 분석하고, 로그 데이터를 실행 가능한 신호로  [데이터 수집 서버에 전송합니다](../../reference/system-components/components-data-collection.md#dcs-pcs).

실행 가능한 신호를 캡처하려면 규칙 기반의 트레이트를 설정해야 합니다. [Audience Manager 사용자 인터페이스](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)에서 또는 [벌크 관리 도구](../../reference/bulk-management-tools/bulk-create.md)에서 규칙 기반 트레이트를 설정하는 방법을 참조하십시오. 규칙 기반 트레이트에서 사용할 수 있는 모든 키 목록을 보려면 [실행 가능 신호](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) 섹션으로 스크롤하십시오.

>[!IMPORTANT]
>
>*[픽셀 호출](../../integration/media-data-integration/impression-data-pixels.md) 대신 [!UICONTROL Actionable Log Files]*&#x200B;을(를) 구현하는 것이 좋습니다. 따라서 트레이트의 빈도 수가 증가하므로 두 옵션 모두 사용하지 않습니다.

## 실행 가능 신호 {#actionable-signals}

신호는 [!DNL Audience Manager]의 [가장 작은 데이터 단위](../../reference/signal-trait-segment.md)입니다. [!UICONTROL Actionable Log Files] 광고 서버 로그로부터 오는 신호로 광고, 사업 부서, 크리에이티브 및 캠페인 값을 노출 이벤트, 클릭 이벤트 및 전환 이벤트에서 캡처할 수 있습니다.

고객 생성 및 세분화에 이 정보를 사용하려면 규칙 기반 트레이트를 직접 설정해야 합니다.

### Google Campaign Manager에서 {#dcm-logs-signals} 실행 가능한 신호

아래 표는 [!DNL Google Campaign Manager] 로그 파일의 실행 가능한 신호를 보여 줍니다.

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
   <td colname="col3"> <p>전환 이벤트에만 사용할 수 있습니다. </p> <p>Google Campaign Manager의 전환 활동에 대한 숫자 ID를 나타냅니다. 이 필드는 Google 캠페인 관리자의 활동 ID에 매핑됩니다. </p> <p> <p>팁:Google Campaign Manager에서 여러 가지 또는 특정 전환 활동을 캡처할 수 있습니다. Google Campaign Manager의 각 전환 활동에 대해 <code> d_conversion = activity ID</code>을(를) 사용하여 트레이트를 만듭니다. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>전환 이벤트에만 사용할 수 있습니다. </p> <p>이 필드는 Google 캠페인 관리자의 전환 ID에 매핑됩니다. Google Campaign Manager에서 사용자 전환 전의 활동을 나타냅니다. </p> <p>허용된 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> 을 참조하십시오. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> 을 참조하십시오. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> 대/소문자를 구분하지 않습니다. 전환은 이전 활동과 일치할 수 없습니다. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">노출, 클릭 또는 전환 이벤트의 UTC 날짜 및 시간입니다. 1970-01-01 00:00:00 UTC 이후 마이크로초 단위로 표현되었습니다.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>광고주의 데이터 소스에 대한 통합 코드입니다. Audience Manager 데이터 소스는 관련이 없습니다.</p> <p>이 필드는 Google 캠페인 관리자의 광고주 그룹 ID에 매핑됩니다. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>비즈니스 단위 ID. 이 필드는 Google 캠페인 관리자의 광고주 ID에 매핑됩니다. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Google 캠페인 관리자가 제공한 캠페인 ID.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Google 캠페인 관리자에서 제공하는 크리에이티브 ID. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> USD의 매출 금액으로서 -6입니다. 1.000.000을 곱하면 달러 금액으로 표시됩니다.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>이벤트 유형을 나타냅니다. Audience Manager은 Google Campaign Manager 로그 파일 이름에서 이벤트 유형을 읽고 실행 가능한 신호로 변환합니다. </p> <p>허용된 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> for expressions. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 를 참조하십시오. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> 을 참조하십시오. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>Google 캠페인 관리자 데이터를 캡처하는 데 사용하는 데이터 소스의 ID입니다. <a href="../../features/manage-datasources.md#create-data-source"> 데이터 소스 생성 방법</a>을 참조하십시오. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

표에 설명된 신호는 실시간 `HTTP` 호출과 같이 [!DNL Audience Manager]에서 캡처됩니다. 아래 예제 호출에는 [!DNL Google Campaign Manager]의 전환 이벤트에 대한 정보가 포함되어 있습니다. 호출에는 예제 호출에서 *모두*&#x200B;의 신호가 반드시 포함되어야 할 필요는 없습니다.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

200만 라인의 평균 크기 [!DNL Google Campaign Manager] 로그 파일의 경우 실행 가능한 신호로 생성된 모든 트레이트는 로그를 처리한 후 약 1시간 이내에 실현됩니다.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Google Campaign Manager] 로그에 제공된 이벤트 타임스탬프가 적용되어 [!UICONTROL Data Collection Servers](으)로 전달됩니다.
>
>* [!DNL Google Campaign Manager] 로그 파일의 데이터 행에 타임스탬프를 사용할 수 없는 경우 `HTTP` 호출 시간을 이벤트 타임스탬프로 사용합니다.
>* [!DNL Google Campaign Manager] 로그 파일의 데이터 행에 잘못된 타임스탬프가 포함되어 있으면 전체 행을 무시합니다.


<br> 

### [!DNL Google Ad Manager]에서 {#ad-manager-logs-signals}을(를) 기록하는 실행 가능 신호

아래 표는 [!DNL Google Ad Manager] 로그 파일의 실행 가능한 신호를 보여 줍니다.


| 로그 파일의 헤더 이름 | 신호 | 설명 |
---------|----------|---------
| `LineItemId` | `d_lineitem` | 배달된 광고 관리자 라인 항목에 대한 숫자 ID |
| `OrderId` | `d_orderid` | 배달된 라인 항목 및 크리에이티브가 포함된 광고 관리자 주문에 대한 숫자 ID입니다. |
| `CreativeId` | `d_creative` | 배달된 Ad Manager 크리에이티브의 숫자 ID. |
| `-` | `d_event` | 이벤트 유형을 나타냅니다. Audience Manager은 광고 관리자 로그 파일 이름에서 이벤트 유형을 읽고 실행 가능한 신호로 변환합니다. 허용된 값은 다음과 같습니다.<br> <ul><li>d_event = 노출 횟수에 대한 imp</li><li>d_event = 클릭을 위한 클릭.</li><li>d_event = 전환 및 활동에 대한 conv</li></ul> |
| `-` | `d_src` | 광고 관리자 데이터를 캡처하는 데 사용하는 데이터 소스의 ID입니다. [데이터 소스 생성 방법](/help/using/features/manage-datasources.md)을 참조하십시오. |

표에 설명된 신호들은 실시간 HTTP 호출처럼 Audience Manager에서 캡처됩니다. 아래 예제 호출에는 Google 광고 관리자의 전환 이벤트에 대한 정보가 포함되어 있습니다. 호출에는 예제 호출에 모든 신호가 포함될 필요는 없습니다.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>[!DNL Google Ad Manager] 로그에 제공된 이벤트 타임스탬프가 적용되어 [!UICONTROL Data Collection Servers](으)로 전달됩니다.
>
>* [!DNL Google Ad Manager] 로그 파일의 데이터 행에 타임스탬프를 사용할 수 없는 경우 `HTTP` 호출 시간을 이벤트 타임스탬프로 사용합니다.
>* [!DNL Google Ad Manager] 로그 파일의 데이터 행에 잘못된 타임스탬프가 포함되어 있으면 전체 행을 무시합니다.


<br> 

### 일반 광고 서버 로그의 실행 가능 신호 {#generic-logs-signals}

먼저, 광고 서버 로그를 Amazon S3 버킷에 보관해야 합니다. 이 작업을 수행하려면 [Audience Optimization 보고서 및 실행 가능한 로그 파일](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *과*&#x200B;을(를) 읽고 [!DNL Audience Manager] 컨설턴트에게 문의하십시오. 아래 표는 일반 로그 파일에서 실행 가능한 신호를 보여 줍니다.

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
   <td colname="col3"> <p>전환과 일치하는지 여부를 나타냅니다. 옵션은 다음과 같습니다. </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> 노출 횟수 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> 클릭 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> 특성 없음 또는 알 수 없음 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> 노출, 클릭 또는 전환 이벤트의 UTC 날짜 및 시간입니다. <code>yyyy-MM-dd HH:mm:ss</code> 형식을 사용합니다. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>광고주의 데이터 소스에 대한 통합 코드입니다. 이 필드는 <a href="../../features/datasources-list-and-settings.md">Audience Manager 데이터 소스와 관련이 없습니다.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>비즈니스 단위 ID.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>로그 파일의 캠페인 ID.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>로그 파일의 Creative ID. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 구매 또는 기타 전환 금액 데이터 유형:부동. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>이벤트 유형을 나타냅니다. Audience Manager은 로그 파일 이름에서 이벤트 유형을 읽고 실행 가능한 신호로 변환합니다. <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">로그 파일 이름 지정 규칙</a>을 참조하십시오. </p> <p>허용된 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> for expressions. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 를 참조하십시오. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> 을 참조하십시오. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>로그 데이터를 캡처하는 데 사용하는 데이터 소스의 ID입니다. <a href="../../features/manage-datasources.md#create-data-source"> 데이터 소스 생성 방법</a>을 참조하십시오. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

표에 설명된 신호는 실시간 `HTTP` 호출과 같이 [!DNL Audience Manager]에서 캡처됩니다. 호출에는 예제 호출에서 *모두*&#x200B;의 신호가 반드시 포함되어야 할 필요는 없습니다.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Audience Manager 사용자 인터페이스 {#actionable-signals-in-ui}에서 실행 가능한 신호 작업

[신호 검색](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) 인터페이스에서 들어오는 실행 가능 신호를 볼 수 있습니다.

**대상 데이터** (1) > **신호** (2) > **검색** (3)으로 이동하고 **실행 가능한 로그 파일** (4) 필터를 선택합니다.

![UI의 실행 가능한 신호](/help/using/integration/assets/alf-in-signals.png)

실행 가능한 신호를 사용하여 규칙 기반 트레이트를 만들려면 **실행 가능한 로그 파일** (1)을 선택하고 트레이트 규칙으로 사용할 실행 가능한 신호(2)를 선택한 다음 **선택한 신호로 트레이트 만들기** (3)를 누릅니다.

![신호로부터 트레이트 생성](/help/using/integration/assets/alf-create-trait.png)


## 사용 사례 {#use-cases}

[!UICONTROL Actionable Log Files]을(를) 구현할 때 얻을 수 있는 이점은 실행 가능한 신호를 포함하는 [규칙 기반 특성](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)에 [최신 및 빈도](../../features/segments/recency-and-frequency.md) 컨트롤을 적용하는 옵션입니다. 예를 들어 미디어 캠페인 내에서 특정 크리에이티브를 사용자가 표시하는 횟수를 제한하는 경우가 있습니다. 이 작업을 수행하는 방법에 대해 알아보려면 [인스턴트 크로스 장치 억제](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)를 읽어 보십시오. 기타 사용 사례는 다음과 같습니다.

### 사용자 리타겟팅

크리에이티브 123을 열람했지만 클릭 또는 전환하지 않고 크리에이티브 456을 보여 준 사용자를 리타겟팅합니다. 방법:

1. 크리에이티브를 본 사용자를 캡처할 트레이트를 만듭니다. 특성 이름을 [!DNL Creative Trait 123]이라고 합시다. 특성 규칙 사용:

   `d_creative == 123 AND d_event == imp`

2. 클릭 또는 전환 사용자를 캡처할 트레이트를 만듭니다. 이 이름을 [!DNL Click and Converter]이라고 합시다. 특성 규칙 사용:

   `d_event == click OR d_event=conv`

3. 크리에이티브 123을 보았으나 클릭 또는 전환을 하지 않은 사용자로 채울 세그먼트를 만듭니다. 이름을 [!DNL Retarget Users]으로 지정하고 세그먼트 규칙을 사용합니다.

   `Creative Trait 123 AND NOT Click and Converter`

4. 세그먼트 [!DNL Retarget Users]를 대상에 매핑하고 대상에 있는 사용자를 타깃팅합니다.

### Audience Optimization 보고서 또는 Audience Lab에서 Google Campaign Manager Floodlight 활동 사용

[Floodlight ](https://support.google.com/dcm/partner/answer/4293719?hl=en) 태그될 수 있는 광고업체는 사용자 전환을 추적할 수 있습니다. [!UICONTROL Actionable Log Files]에서는 [Audience Optimization 보고서](../../reporting/audience-optimization-reports/audience-optimization-reports.md) 또는 [Audience Lab](../../features/audience-lab/audience-lab.md)에서 [!DNL Google Campaign Manager] 변환을 추적할 수 있습니다.

1. 트레이트를 만들고 다음 트레이트 규칙을 사용하여 광고 서버 로그에서 변환을 캡처합니다.

   `d_event == conv AND d_conversion == 123`

   Audience Manager [!UICONTROL UI]에서 트레이트를 만들 때 [!UICONTROL Conversion]을 [!UICONTROL Event Type](으)로 선택합니다.

2. 특성을 만들면 [!UICONTROL Audience Optimization Reports] 및 [!UICONTROL Audience Lab]에서 전환이 보고됩니다.

>[!MORELIKETHIS]
>
>* [Google Campaign Manager 데이터 파일을 Audience Manager으로 가져오기](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [대상 최적화 보고서](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

