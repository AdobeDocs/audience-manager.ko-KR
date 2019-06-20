---
description: Audience Manager가 다른 데이터 공급자와 시스템과 정보를 교환하는 방법에 대한 간략한 개요입니다.
seo-description: Audience Manager가 다른 데이터 공급자와 시스템과 정보를 교환하는 방법에 대한 간략한 개요입니다.
seo-title: 데이터 통합 방법
solution: Audience Manager
title: 데이터 통합 방법
uuid: 17 A 4179 A-E 99 B -49 EB -8 F 45-F 2946 AFBD 27 F
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 데이터 통합 방법 {#data-integration-methods}

Audience Manager가 다른 데이터 공급자와 시스템과 정보를 교환하는 방법에 대한 간략한 개요입니다.

## Supported Data Integration Methods: Real-Time and Server-to-Server {#supported-methods}

올바른 통합 방법은 비즈니스 요건과 데이터 파트너의 기술 기능에 따라 달라집니다. Audience Manager는 다음 방법 중 하나를 통해 다른 데이터 공급자와 방문자 정보를 교환합니다.

* **실시간:** 사용자가 사이트를 방문하면 즉시 데이터를 전송합니다. This method is also known as a *`synchronous`* integration.
* **일괄 처리 (서버-서버):** 방문자가 페이지를 떠난 후 설정된 일정에 따라 서버 간에 데이터를 전송합니다. This method is also known as an *`out-of-band`* or *`asynchronous`* integration.

## Prerequisites: Create a Trait Taxonomy {#prereqs}

Before the integration process begins, remember to [create traits](../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI. 분류법은 논리적 계층 구조로 구성된 모든 트레이트를 포함합니다.

## Integration Use Cases {#integration-use-cases}

각 솔루션의 장점과 단점과 함께 Audience Manager 데이터 통합 방법의 사용 사례 요약입니다.

### 서버 간의 실시간 통합

<!-- c_int_types_use_cases.xml -->

서버 간 데이터 통합은 Audience Manager 서버와 다른 타깃팅 시스템 간에 사용자 데이터를 빠르게 동기화합니다. 대부분의 경우 데이터 교환은 타깃팅 시스템의 새로 고침 비율에 따라 몇 초 또는 분 내에 이루어집니다. 그러나 대상 시스템은 Audience Manager가 아닌 이 새로 고침 간격을 결정합니다. 또한 새로 고침 속도는 서로 다른 시스템마다 다를 수 있습니다. 실시간 서버 간 통합은 데이터 교환을 위한 기본 통합 유형입니다. 타깃팅 파트너가 지원할 수 있을 때마다 Audience Manager는 이 방법을 사용합니다.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>장점: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">페이지, 비디오 플레이어 등에서 다시 볼 필요 없이 세그먼트에 대한 사용자를 자격을 얻을 수 있습니다. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> 페이지에서 HTTP 호출 수를 줄입니다. 호출 수가 적을수록 사용자 경험이 유지됩니다. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">시간 민감도 타깃팅에 도움이 되므로 자격이 있는 사용자에 대해 조치를 취할 수 있습니다. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">오프사이트 타깃팅을 위해 DSP로 이동할 때 유용합니다. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 단점:</td>
  <td class="stentry"> 해당 세그먼트에 대한 사용자를 적격한 사용자를 기준으로, 동일한 페이지 또는 다음 페이지에서 사용자를 타깃팅해야 할 때 온사이트 타깃팅에 유용합니다.</td>
 </tr>
</table>

### 서버 간 일괄 통합

서버 간 일괄 통합은 데이터를 번들로 묶을 수 있으며 거의 실시간으로 이 데이터를 다른 시스템으로 보낼 수 있습니다. 데이터 전송 간격은 24 시간부터 시작됩니다. 일부 데이터 공급자는 이 통합 유형만 지원합니다. 그러나 Adobe는 실시간 통합 방법론에 대한 일괄 통합과는 완전히 다른 추세를 보이고 있습니다.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>장점: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">페이지, 비디오 플레이어 등에서 다시 볼 필요 없이 세그먼트에 대한 사용자를 자격을 얻을 수 있습니다. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">시간이 너무 민감하지 않은 타깃팅에 유용합니다. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 단점:</td>
  <td class="stentry"> 동기화 구간은 가장 최근의 데이터에 대한 타깃팅을 지연시킬 수 있습니다.</td>
 </tr>
</table>

### 실시간 호출

사용자가 사이트를 방문하거나 페이지에서 조치를 취할 때 실시간 호출은 Audience Manager와 데이터를 즉시 교환합니다. 이 방법을 사용하면 타깃팅 시스템은 가장 많이 업데이트된 세그먼트 자격 데이터를 얻고 컨텐츠 또는 광고 전달 결정 중에 해당 정보를 고려할 수 있습니다. 또한 이 프로세스는 Adobe가 자격이 있는 세그먼트를 주요-값 쌍으로 읽은 퍼스트 파티 쿠키로 업데이트하는 게시자 광고 서버와 연동됩니다. Currently, Audience Manager uses real-time calls to integrate with [!DNL Target] and other content management systems.

<table> 
 <tr>
  <td> <p>장점: </p></td>
  <td> <p> 가장 최근의 세그먼트 자격 조건을 기반으로 다음 페이지, 컨텐츠 영역 또는 광고 임프레션을 타깃팅할 수 있습니다. </p></td> 
 </tr> 
 <tr>
  <td> <p>단점: </p></td>
  <td> <p>Audience Manager에 대한 호출을 페이지에서 추가합니다.</p></td>
 </tr> 
</table>


### 픽셀이 타깃팅 시스템과 동기화됩니다.

픽셀 동기화가 세그먼트를 페이지의 픽셀에 매핑합니다. 사용자가 특정 세그먼트에 대한 자격을 부여하면 픽셀이 실행되고 데이터를 전송합니다. 픽셀 동기화는 완벽하고 신뢰할 수 없는 데이터 전송 메커니즘입니다. 주요 계층 데이터 제공업체와 시스템은 거의 사용하지 않습니다.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>장점: </p></td>
  <td class="stentry"> <p> 실시간 데이터 전송. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>단점: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">페이지에서 많은 클라이언트측 호출을 추가할 수 있습니다. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">데이터 전송에 안정적이지 못함 5% ~ 20% 손실은 정상입니다. </li>
   </ul></td>
 </tr> 
</table>

## How to Choose a Data Delivery Method {#data-delivery-choices}

동기식 (실시간) 또는 비동기 (서버-서버) 방법론을 통해 데이터를 전송하는 기술적 및 비즈니스 이유를 설명합니다.

<!-- c_int_delivery_choices.xml -->

### 데이터 배달 유형 선택

* **기술적인 고려 사항:** 데이터 전달은 데이터 파트너의 기술 기능에 따라 달라집니다. Audience Manager는 브라우저 또는 서버 간 통신 프로세스를 통해 데이터를 실시간으로 보내거나 일괄적으로 데이터를 받을 수 있습니다.
* **비즈니스 고려 사항:** 전달 방법 중 하나를 선택해야 하는 비즈니스 이유는 대상 파트너의 기술적 기능과 이 데이터를 사용하는 방법에 따라 달라집니다. 일반적으로 동기 데이터 전송은 사용자 데이터에 즉시 조치를 취해야 할 때 유용합니다. 비동기 데이터 전송은 즉각적인 작업이 필요하지 않고 나중에 사용할 수 있도록 더 깊은 사용자 프로필을 만들 시간이 있을 때 유용합니다.

## Real-Time Data Transfer Process {#real-time-data-transfer-process}

Audience Manager가 타사 공급업체와의 동기식 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.

### 실시간 데이터 전송

<!-- c_int_overview_sync.xml -->

실시간 데이터 전송은 사용자가 사이트에서 방문 또는 조치를 취할 때 세그먼트 ID를 전송하고 수신합니다. 일반적으로 동기 데이터 전송은 인벤토리를 탐색하면서 사용자를 바로 자격을 부여하거나 세그먼트화해야 할 때 유용합니다.

### 실시간 데이터 통합 단계

실시간 데이터 통합 프로세스는 다음과 같이 작동합니다.

1. 사용자가 Audience Manager 코드가 들어 있는 고객 사이트를 방문합니다.
1. Audience Manager loads an Iframe and makes a call to the [!UICONTROL Data Collection Server] ([!UICONTROL DCS]).
1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. 제 3 자는 해당 사용자에 대한 세그먼트 정보를 Audience Manager로 반환합니다.
1. Audience Manager는 세그먼트 정보를 인제스트하여 타깃팅에 사용할 수 있도록 합니다.

![](assets/rt_reduce70.png)

## Batch Data Transfer Process {#batch-data-transfer-process}

Audience Manager가 타사 공급업체와의 데이터를 동기식으로 (실시간으로) 교환하는 방법에 대한 일반 개요입니다.

### 일괄 데이터 통합

<!-- c_int_overview_async.xml -->

Batch (server-to-server) 데이터 통합 프로세스는 실시간 데이터 전송 프로세스에 설명된 대부분의 단계를 따릅니다. 그러나 세그먼트 ID를 즉시 반환하는 대신 사용자 정보가 서버에 저장되고 정기적으로 타사 데이터 공급자와 동기화됩니다. 비동기 데이터 전송 프로세스는 다음과 같은 경우에 유용합니다.

* 즉각적인 데이터 전송은 필요하지 않습니다.
* 데이터를 수집하여 세그먼트화된 대규모 사용자 풀 만들기
* You want to reduce data discrepancies and `HTTP` calls from the browser.

### 일괄 데이터 통합 단계

1. 사용자가 고객 사이트를 방문합니다.
1. Audience Manager와 타사 데이터 공급자는 방문자에게 고유 ID (일반적으로 쿠키와 함께) 를 할당합니다.
1. Audience Manager는 방문자 ID와 일치하도록 타사 데이터 공급자를 호출합니다.
1. 일반적으로 일별 간격으로 예약된 요청은 Audience Manager와 타사 데이터 공급자 간에 방문자 세그먼트 데이터를 교환합니다.

![](assets/s2s_70.png)

For information describing the time frames when Audience Manager processes inbound and outbound Server-to-Server ([!UICONTROL S2S]) file transfers, see [Reporting and File Transfer Time-Frame Guidelines](../reference/reporting-file-transfer-timeframe.md).
