---
description: Audience Manager이 다른 데이터 공급자 및 시스템과 정보를 교환하는 방법에 대한 높은 수준의 개요입니다.
seo-description: Audience Manager이 다른 데이터 공급자 및 시스템과 정보를 교환하는 방법에 대한 높은 수준의 개요입니다.
seo-title: 데이터 통합 방법
solution: Audience Manager
title: 데이터 통합 방법
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: 타사 통합
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 1%

---

# 데이터 통합 방법 {#data-integration-methods}

Audience Manager이 다른 데이터 공급자 및 시스템과 정보를 교환하는 방법에 대한 높은 수준의 개요입니다.

## 지원되는 데이터 통합 방법:실시간 및 [!DNL Server-to-Server] {#supported-methods}

올바른 통합 방법을 선택하는 것은 비즈니스 요구 사항과 데이터 파트너의 기술 기능의 조합에 따라 다릅니다. Audience Manager은 다음 방법 중 하나로 방문자 정보를 다른 데이터 공급자와 교환합니다.

* **실시간:** 사용자가 사이트를 방문할 때 데이터를 즉시 전송합니다. 이 메서드를 *`synchronous`* 통합이라고도 합니다.
* **배치([!DNL Server-to-Server]):** 방문자가 페이지를 떠난 후 설정된 일정에 따라 서버 간에 데이터를 전송합니다. 이 메서드를 *`out-of-band`* 또는 *`asynchronous`* 통합이라고도 합니다.

## 전제 조건:특성 분류 체계 만들기 {#prereqs}

통합 프로세스가 시작되기 전에 [특성](../features/traits/create-onboarded-rule-based-traits.md)과 [!DNL Audience Manager] UI에서 [폴더 구조](../features/traits/trait-storage.md#create-trait-storage-folder)를 만들어야 합니다. 분류법은 논리 계층 구조로 구성된 모든 [!UICONTROL traits]을 포함합니다.

## 통합 사용 사례 {#integration-use-cases}

각 솔루션의 장점과 단점과 함께 Audience Manager 데이터 통합 방법의 사용 사례 요약입니다.

### 실시간 [!DNL Server-to-Server] 통합

<!-- c_int_types_use_cases.xml -->

실시간 [!DNL server-to-server] 데이터 통합은 Audience Manager 서버와 다른 타깃팅 시스템 간에 사용자 데이터를 신속하게 동기화합니다. 대부분의 경우 타겟팅 시스템의 새로 고침 비율에 따라 데이터 교환이 초 또는 분 내에 수행됩니다. 그러나 타깃팅된 시스템에서는 Audience Manager이 아니라 이 새로 고침 간격을 결정합니다. 또한, 새로 고침 속도는 서로 다른 시스템마다 다를 수 있다. 실시간 [!UICONTROL server-to-server] 통합은 데이터 교환을 위한 기본 통합 유형입니다. Audience Manager은 타깃팅 파트너가 지원할 수 있을 때마다 이 메서드를 사용합니다.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>장점: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">페이지, 비디오 플레이어 등에서 세그먼트를 다시 보지 않고 세그먼트에 대한 자격을 부여할 수 있습니다. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> 페이지에서 HTTP 호출 수를 줄입니다. 적은 호출로 사용자 경험을 유지할 수 있습니다. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">적절한 사용자에 대해 작업을 신속하게 수행할 수 있도록 시간을 구분하는 타겟팅에 도움이 됩니다. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">오프사이트 타깃팅을 위해 DSP으로 이동할 때 유용합니다. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 단점:</td>
  <td class="stentry"> 해당 세그먼트에 대한 자격을 부여받은 사용자를 기준으로 동일한 페이지 또는 다음 페이지에서 사용자를 타깃팅해야 하는 경우 온사이트 타깃팅에 덜 유용합니다.</td>
 </tr>
</table>

### [!DNL Server-to-Server] 배치 통합

[!DNL server-to-server] 배치 통합은 데이터를 번들로 하여 거의 실시간으로 전송되지 않고 설정된 간격으로 다른 시스템으로 전송합니다. 데이터 전송 간격은 24시간에서 시작됩니다. 일부 데이터 공급자는 이 통합 유형만 지원합니다. 하지만 배치 통합에서 실시간 통합 방법론을 향한 일반적인 트렌드를 보았습니다.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>장점: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">페이지, 비디오 플레이어 등에서 세그먼트를 다시 보지 않고 세그먼트에 대한 자격을 부여할 수 있습니다. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">시간이 별로 중요하지 않은 타깃팅에 유용합니다. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 단점:</td>
  <td class="stentry"> 동기화 간격은 가장 최신 데이터에 대한 타깃팅을 지연시킬 수 있습니다.</td>
 </tr>
</table>

### 실시간 호출

실시간 호출은 사용자가 사이트를 방문하거나 페이지에서 작업을 수행할 때 데이터를 즉시 Audience Manager과 교환합니다. 이 방법을 사용하면 타깃팅 시스템에서 가장 업데이트된 세그먼트 자격 데이터를 가져오고 콘텐츠 또는 광고 게재 결정 중에 해당 정보를 고려할 수 있습니다. 또한 이 프로세스는 게시자 광고 서버에서 작동합니다. 여기서 Adobe는 자격이 있는 세그먼트를 키-값 쌍으로 광고 호출을 인식하는 자사 쿠키로 업데이트합니다. 현재 Audience Manager은 실시간 호출을 사용하여 [!DNL Adobe Target] 및 기타 컨텐츠 관리 시스템과 통합합니다.

<table> 
 <tr>
  <td> <p>장점: </p></td>
  <td> <p> 가장 최근 세그먼트 자격을 기반으로 다음 페이지, 컨텐츠 영역 또는 광고 노출 횟수를 타깃팅할 수 있습니다. </p></td> 
 </tr> 
 <tr>
  <td> <p>단점: </p></td>
  <td> <p>페이지에서 Audience Manager에 호출을 추가합니다.</p></td>
 </tr> 
</table>


### 픽셀이 타깃팅 시스템에 동기화됨

픽셀 동기화는 세그먼트를 페이지의 픽셀에 매핑합니다. 픽셀은 사용자가 특정 세그먼트에 대한 자격을 얻으면 데이터를 실행하고 전송합니다. 픽셀 동기화는 기본적이고 신뢰할 수 없는 데이터 전송 메커니즘입니다. 최상위 계층 데이터 공급자와 시스템은 거의 사용하지 않습니다.

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
    <li id="li_CD91F3DC92F2429293787D61506E5E04">데이터 전송에 대한 신뢰성이 없습니다. 5%~20% 손실이 정상입니다. </li>
   </ul></td>
 </tr> 
</table>

## 데이터 전달 방법 {#data-delivery-choices} 선택 방법

동기(실시간) 또는 비동기(서버 간) 방법론을 통해 데이터를 전송하는 기술 및 비즈니스 이유에 대해 설명합니다.

<!-- c_int_delivery_choices.xml -->

### 데이터 전달 유형 선택

* **기술 고려 사항:**  데이터 전달은 데이터 파트너의 기술 기능에 따라 다릅니다. Audience Manager은 브라우저에서 실시간으로 또는 오프라인 서버 간 통신 프로세스를 통해 일괄 업데이트로 데이터를 전송/수신할 수 있습니다.
* **비즈니스 고려 사항:** 하나의 게재 방법 또는 다른 방법을 선택하는 비즈니스 이유는 대상 파트너의 기술 기능과 이 데이터를 사용하려는 방법에 따라 다릅니다. 일반적으로 동기 데이터 전송은 사용자 데이터에 대해 즉시 조치를 취해야 할 때 유용합니다. 비동기 데이터 전송은 즉각적인 작업이 필요하지 않고 나중에 사용할 수 있도록 더 깊은 사용자 프로필을 빌드할 시간이 있는 경우 유용할 수 있습니다.

## 실시간 데이터 전송 프로세스 {#real-time-data-transfer-process}

Audience Manager이 타사 공급업체와 동기식 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.

### 실시간 데이터 전송

<!-- c_int_overview_sync.xml -->

실시간 데이터 전송은 사용자가 사이트를 방문하거나 사이트에서 작업을 수행할 때 세그먼트 ID를 전송하고 받습니다. 일반적으로 동기 데이터 전송은 인벤토리를 탐색할 때 사용자를 즉시 분류하거나 자격을 부여해야 할 때 유용합니다.

### 실시간 데이터 통합 단계

실시간 데이터 통합 프로세스는 다음과 같이 작동합니다.

1. 사용자가 Audience Manager 코드를 포함하는 고객의 사이트를 방문합니다.
1. Audience Manager은 Iframe을 로드하고 [!UICONTROL Data Collection Server]([!DNL DCS])를 호출합니다.
1. [!DNL DCS] 은 타사 서버를 호출하여(실시간으로) 공급업체가 사용자에 대한 세그먼트 정보를 가지고 있는지 확인합니다.
1. 타사에서 해당 사용자에 대한 Audience Manager 정보를 반환합니다.
1. Audience Manager 수집은 세그먼트 정보를 타겟팅에 사용할 수 있도록 합니다.

![](assets/rt_reduce70.png)

## 배치 데이터 전송 프로세스 {#batch-data-transfer-process}

Audience Manager이 타사 공급업체와 동기적으로(실시간으로) 데이터를 교환하는 방법에 대한 일반적인 개요입니다.

### 배치 데이터 통합

<!-- c_int_overview_async.xml -->

배치([!DNL server-to-server]) 데이터 통합 프로세스는 실시간 데이터 전송 프로세스에 설명된 대부분의 단계를 따릅니다. 하지만 세그먼트 ID를 즉시 반환하는 대신, 사용자 정보가 서버에 저장되고 정기적으로 타사 데이터 공급자와 동기화됩니다. 비동기 데이터 전송 프로세스는 다음과 같은 경우에 유용합니다.

* 즉각적인 데이터 전송이 필요하지 않습니다.
* 데이터를 수집하여 세그먼트화된 사용자의 대규모 풀을 구축합니다.
* 브라우저에서 데이터 불일치 및 `HTTP` 호출을 줄이려고 합니다.

### 배치 데이터 통합 단계

1. 사용자가 고객 사이트를 방문합니다.
1. Audience Manager 및 타사 데이터 공급자는 방문자에게 고유 ID(일반적으로 쿠키와 함께)를 지정합니다.
1. Audience Manager은 방문자 ID와 일치하도록 타사 데이터 공급자를 호출합니다.
1. 일반적으로 일별 간격으로 예약된 요청은 Audience Manager과 타사 데이터 공급자 간에 방문자 세그먼트 데이터를 교환합니다.

![](assets/s2s_70.png)

Audience Manager이 인바운드 및 아웃바운드 [!DNL Server-to-Server]([!UICONTROL S2S]) 파일 전송을 처리할 때의 시간 프레임을 설명하는 정보는 [보고 및 파일 전송 시간 프레임 지침](../reference/reporting-file-transfer-timeframe.md)을 참조하십시오.
