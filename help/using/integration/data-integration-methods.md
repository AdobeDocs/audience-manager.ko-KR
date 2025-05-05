---
description: Audience Manager이 다른 데이터 공급자 및 시스템과 정보를 교환하는 방법에 대한 높은 수준의 개요입니다.
seo-description: A high-level overview of how Audience Manager exchanges information with other data providers and systems.
seo-title: Data Integration Methods
solution: Audience Manager
title: 데이터 통합 방법
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third-party Integration
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# 데이터 통합 방법 {#data-integration-methods}

Audience Manager이 다른 데이터 공급자 및 시스템과 정보를 교환하는 방법에 대한 높은 수준의 개요입니다.

## 지원되는 데이터 통합 방법: 실시간 및 [!DNL Server-to-Server] {#supported-methods}

적합한 통합 방법의 선택은 비즈니스 요구 사항과 데이터 파트너의 기술 기능의 조합에 따라 다릅니다. Audience Manager은 다음 방법 중 하나를 사용하여 다른 데이터 공급자와 방문자 정보를 교환합니다.

* **실시간:** 사용자가 사이트를 방문할 때 데이터를 즉시 전송합니다. 이 메서드를 *`synchronous`* 통합이라고도 합니다.
* **일괄 처리([!DNL Server-to-Server]):** 방문자가 페이지에서 나간 후 설정된 일정에 따라 서버 간에 데이터를 전송합니다. 이 메서드를 *`out-of-band`* 또는 *`asynchronous`* 통합이라고도 합니다.

## 사전 요구 사항: 트레이트 분류 만들기 {#prereqs}

통합 프로세스가 시작되기 전에 [!DNL Audience Manager] UI에서 [특성을 만들고](../features/traits/create-onboarded-rule-based-traits.md) [폴더 구조를 만듭니다](../features/traits/trait-storage.md#create-trait-storage-folder)해야 합니다. 분류에는 논리 계층 구조로 구성된 모든 [!UICONTROL traits]이(가) 포함됩니다.

## 통합 사용 사례 {#integration-use-cases}

각각의 장점과 단점과 함께 Audience Manager 데이터 통합 방법에 대한 사용 사례 요약입니다.

### 실시간 [!DNL Server-to-Server] 통합

<!-- c_int_types_use_cases.xml -->

실시간 [!DNL server-to-server] 데이터 통합은 Audience Manager 서버와 다른 타깃팅 시스템 간에 사용자 데이터를 빠르게 동기화합니다. 대부분의 경우 데이터 교환은 타겟팅 시스템의 새로 고침 빈도에 따라 초 또는 분 이내에 발생합니다. 단, 타겟팅된 시스템은 Audience Manager이 아니라 이 새로 고침 간격을 결정합니다. 또한, 리프레시 속도는 상이한 시스템들간에 변할 수 있다. 실시간 [!UICONTROL server-to-server] 통합은 데이터 교환에 선호하는 통합 유형입니다. Audience Manager은 타기팅 파트너가 지원할 수 있을 때마다 이 메서드를 사용합니다.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>장점: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">페이지, 비디오 플레이어 등에서 다시 보지 않고 세그먼트를 사용할 수 있는 자격을 사용자에게 부여할 수 있습니다. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> 페이지에서 전송되는 HTTP 호출 수를 줄입니다. 호출이 적으면 사용자 경험을 유지하는 데 도움이 됩니다. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">적격 사용자에 대한 조치를 신속하게 취할 수 있도록 시간에 민감한 타겟팅에 도움이 됩니다. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">오프사이트 타겟팅을 위해 DSP으로 이동할 때 유용합니다. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 단점:</td>
  <td class="stentry"> 해당 세그먼트에 대한 사용자 자격을 기준으로 동일한 페이지 또는 다음 페이지에서 사용자를 타깃팅해야 하는 경우 온사이트 타깃팅에 덜 유용합니다.</td>
 </tr>
</table>

### [!DNL Server-to-Server] 일괄 처리 통합

[!DNL server-to-server] 일괄 처리 통합은 데이터를 번들로 만들어 실시간에 가깝지 않고 설정된 간격에 따라 다른 시스템에 보냅니다. 데이터 전송 간격은 24시간부터 시작됩니다. 일부 데이터 공급자는 이 통합 유형만 지원합니다. 하지만 배치 통합에서 실시간 통합 방법론에 이르기까지 일반적인 추세를 살펴보았습니다.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>장점: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">페이지, 비디오 플레이어 등에서 다시 보지 않고 세그먼트를 사용할 수 있는 자격을 사용자에게 부여할 수 있습니다. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">시간에 민감하지 않은 타겟팅에 유용합니다. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 단점:</td>
  <td class="stentry"> 동기화 간격은 가장 최근 데이터에 대한 타겟팅을 지연시킬 수 있습니다.</td>
 </tr>
</table>

### 실시간 호출

실시간 호출은 사용자가 사이트를 방문하거나 페이지에서 작업을 수행할 때 즉시 Audience Manager과 데이터를 교환합니다. 이 방법을 사용하면 타겟팅 시스템이 가장 업데이트된 세그먼트 자격 데이터를 가져오고 콘텐츠 또는 광고 게재 결정 동안 해당 정보를 고려할 수 있습니다. 또한 이 프로세스는 자격을 갖춘 세그먼트를 키-값 쌍으로 광고 호출로 읽히는 자사 쿠키로 업데이트하는 게시자 광고 서버에서 작동합니다. 현재 Audience Manager은 실시간 호출을 사용하여 [!DNL Adobe Target] 및 다른 콘텐츠 관리 시스템과 통합됩니다.

<table> 
 <tr>
  <td> <p>장점: </p></td>
  <td> <p> 가장 최근 세그먼트 자격을 기준으로 다음 페이지, 콘텐츠 영역 또는 광고 노출을 타깃팅할 수 있습니다. </p></td> 
 </tr> 
 <tr>
  <td> <p>단점: </p></td>
  <td> <p>페이지에서 Audience Manager 호출을 추가합니다.</p></td>
 </tr> 
</table>


### 픽셀이 타깃팅 시스템과 동기화됨

픽셀 동기화는 세그먼트를 페이지의 픽셀에 매핑합니다. 픽셀은 사용자가 특정 세그먼트에 대한 자격이 있을 때 실행되고 데이터를 전송합니다. 픽셀 동기화는 기초적이고 신뢰할 수 없는 데이터 전송 메커니즘입니다. 최상위 계층 데이터 공급자 및 시스템은 이를 거의 사용하지 않습니다.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>장점: </p></td>
  <td class="stentry"> <p> 실시간 데이터 전송. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>단점: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">페이지에서 클라이언트측 호출을 많이 추가할 수 있습니다. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">데이터 전송에 대해 신뢰할 수 없음. 5%~20% 손실은 정상입니다. </li>
   </ul></td>
 </tr> 
</table>

## 데이터 전달 방법을 선택하는 방법 {#data-delivery-choices}

동기식(실시간) 또는 비동기식(서버 간) 방법론을 통해 데이터를 전송해야 하는 기술 및 비즈니스 이유에 대해 설명합니다.

<!-- c_int_delivery_choices.xml -->

### 데이터 전송 유형 선택

* **기술 고려 사항:** 데이터 전달은 데이터 파트너의 기술 기능에 따라 다릅니다. Audience Manager은 브라우저에서 실시간으로 또는 오프라인, 서버 간 통신 프로세스를 통해 일괄 업데이트를 통해 데이터를 송수신할 수 있습니다.
* **비즈니스 고려 사항:** 배달 방법 중 하나를 선택하는 비즈니스 이유는 대상 파트너의 기술 기능과 이 데이터를 사용하는 방법에 따라 다릅니다. 일반적으로 동기 데이터 전송은 사용자 데이터에 대한 작업을 즉시 수행해야 할 때 유용합니다. 비동기 데이터 전송은 즉각적인 작업이 필요하지 않고 나중에 사용할 수 있도록 더 자세한 사용자 프로필을 빌드할 시간이 있는 경우 유용할 수 있습니다.

## 실시간 데이터 전송 프로세스 {#real-time-data-transfer-process}

Audience Manager이 타사 공급업체와 동기식 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.

### 실시간 데이터 전송

<!-- c_int_overview_sync.xml -->

실시간 데이터 전송은 사용자가 사이트를 방문하거나 사이트에서 작업을 수행할 때 세그먼트 ID를 보내고 받습니다. 일반적으로 동기 데이터 전송은 사용자가 인벤토리를 탐색할 때 자격을 부여하거나 즉시 세그먼트화해야 할 때 유용합니다.

### 실시간 데이터 통합 단계

실시간 데이터 통합 프로세스는 다음과 같이 작동합니다.

1. 사용자가 Audience Manager 코드가 포함된 고객의 사이트를 방문합니다.
1. Audience Manager이 Iframe을 로드하고 [!UICONTROL Data Collection Server] ([!DNL DCS])을 호출합니다.
1. [!DNL DCS]은(는) 서드파티 서버를 실시간으로 호출하여 공급업체에 사용자에 대한 세그먼트 정보가 있는지 확인합니다.
1. 서드파티는 해당 사용자에 대한 Audience Manager 정보를 사용자에게 반환합니다.
1. Audience Manager은 세그먼트 정보를 수집하여 타깃팅에 사용할 수 있도록 합니다.

![](assets/rt_reduce70.png)

## 일괄 데이터 전송 프로세스 {#batch-data-transfer-process}

Audience Manager이 타사 공급업체와 동기적으로(실시간으로) 데이터를 교환하는 방법에 대한 일반적인 개요입니다.

### 일괄 데이터 통합

<!-- c_int_overview_async.xml -->

일괄 처리([!DNL server-to-server]) 데이터 통합 프로세스는 실시간 데이터 전송 프로세스에 설명된 대부분의 단계를 따릅니다. 그러나 세그먼트 ID를 즉시 반환하는 대신 사용자 정보가 서버에 저장되고 정기적으로 타사 데이터 공급자와 동기화됩니다. 비동기 데이터 전송 프로세스는 다음과 같은 경우에 유용합니다.

* 즉각적인 데이터 전송은 필요하지 않습니다.
* 데이터를 수집하여 세그먼트화된 사용자의 대규모 풀 구축
* 데이터 불일치 및 브라우저에서 `HTTP` 호출을 줄이려고 합니다.

### 일괄 데이터 통합 단계

1. 사용자가 고객 사이트를 방문하고
1. Audience Manager 및 타사 데이터 공급자는 방문자에게 고유 ID(일반적으로 쿠키와 함께)를 할당합니다.
1. Audience Manager이 방문자 ID를 일치시키기 위해 타사 데이터 공급자를 호출합니다.
1. 예약된 요청(일반적으로 매일 간격)은 Audience Manager과 타사 데이터 공급자 간에 방문자 세그먼트 데이터를 교환합니다.

![](assets/s2s_70.png)

Audience Manager이 인바운드 및 아웃바운드 [!DNL Server-to-Server] ([!UICONTROL S2S]) 파일 전송을 처리하는 기간에 대한 자세한 내용은 [보고 및 파일 전송 기간 지침](../reference/reporting-file-transfer-timeframe.md)을 참조하십시오.
