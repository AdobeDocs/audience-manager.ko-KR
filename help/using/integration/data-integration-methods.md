---
description: Audience Manager이 다른 데이터 제공업체 및 시스템과 정보를 교환하는 방법에 대한 개요
seo-description: Audience Manager이 다른 데이터 제공업체 및 시스템과 정보를 교환하는 방법에 대한 개요
seo-title: 데이터 통합 방법
solution: Audience Manager
title: 데이터 통합 방법
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 1%

---


# 데이터 통합 방법 {#data-integration-methods}

Audience Manager이 다른 데이터 제공업체 및 시스템과 정보를 교환하는 방법에 대한 개요

## 지원되는 데이터 통합 방법: 실시간 및 [!DNL Server-to-Server] {#supported-methods}

적합한 통합 방법을 선택하는 것은 데이터 파트너의 비즈니스 요구 사항과 기술 기능의 조합에 따라 달라집니다. Audience Manager은 다음 방법 중 하나로 방문자 정보를 다른 데이터 공급자와 교환합니다.

* **실시간:** 사용자가 사이트를 방문할 때 즉시 데이터를 전송합니다. 이 메서드를 *`synchronous`* 통합이라고도 합니다.
* **배치([!DNL Server-to-Server]):** 방문자가 페이지를 떠난 후 설정된 일정에 있는 서버 간에 데이터를 전송합니다. 이 메서드는 *`out-of-band`* 또는 *`asynchronous`* 통합이라고도 합니다.

## 전제 조건: 특성 분류 만들기 {#prereqs}

통합 프로세스가 시작되기 전에 [UI에서 트레이트](../features/traits/create-onboarded-rule-based-traits.md) 및 [폴더 구조를](../features/traits/trait-storage.md#create-trait-storage-folder) 만들어야 [!DNL Audience Manager] 합니다. 분류에는 논리 계층 구조에 구성된 모든 [!UICONTROL traits] 항목이 포함됩니다.

## 통합 사용 사례 {#integration-use-cases}

Audience Manager 데이터 통합 방법의 사용 사례 요약과 각 솔루션의 장점과 단점

### 실시간 [!DNL Server-to-Server] 통합

<!-- c_int_types_use_cases.xml -->

실시간 데이터 통합은 Audience Manager 서버와 다른 타깃팅 시스템 간에 사용자 데이터를 신속하게 동기화합니다. [!DNL server-to-server] 대부분의 경우 데이터 교환은 타깃팅 시스템의 새로 고침 비율에 따라 초 또는 분 내에 수행됩니다. 그러나 타깃팅된 시스템은 Audience Manager이 아닌 이 새로 고침 간격을 결정합니다. 또한 새로 고침률은 서로 다른 시스템에 따라 다를 수 있습니다. 실시간 통합은 데이터 교환의 기본 [!UICONTROL server-to-server] 통합 유형입니다. Audience Manager은 타깃팅 파트너가 지원할 수 있을 때마다 이 메서드를 사용합니다.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>장점: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">페이지에서, 비디오 플레이어 등에서 세그먼트를 다시 보지 않고 세그먼트에 대해 자격을 부여할 수 있습니다. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> 페이지에서 HTTP 호출 수를 줄입니다. 호출 수가 적을수록 사용자 경험이 유지됩니다. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">시간 구분 타깃팅을 통해 자격 조건을 갖춘 사용자를 신속하게 처리할 수 있습니다. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">오프사이트 타깃팅을 위해 DSP로 이동할 때 유용합니다. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 단점:</td>
  <td class="stentry"> 해당 세그먼트에 대한 사용자 자격을 기준으로 동일한 페이지 또는 다음 페이지에서 사용자를 타깃팅해야 할 경우 온사이트 타깃팅에 덜 유용합니다.</td>
 </tr>
</table>

### [!DNL Server-to-Server] 일괄 통합

일괄 [!DNL server-to-server] 통합은 데이터를 번들로 묶어서 거의 실시간으로 이루어지는 것이 아니라 정해진 간격으로 다른 시스템으로 전송합니다. 데이터 전송 간격이 24시간에서 시작됩니다. 일부 데이터 공급자는 이 통합 유형만 지원합니다. 하지만 일괄 통합에서 실시간 통합 방법론으로 이어지는 일반적인 트렌드가 나타났습니다.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>장점: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">페이지에서, 비디오 플레이어 등에서 세그먼트를 다시 보지 않고 세그먼트에 대해 자격을 부여할 수 있습니다. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">시간 민감하지 않은 타깃팅에 유용합니다. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 단점:</td>
  <td class="stentry"> 동기화 간격은 최신 데이터에 대한 타깃팅을 지연할 수 있습니다.</td>
 </tr>
</table>

### 실시간 호출

사용자가 사이트를 방문하거나 페이지에서 조치를 취할 때 실시간 호출은 Audience Manager과 데이터를 즉시 교환합니다. 이 방법으로 타깃팅 시스템은 가장 업데이트된 세그먼트 자격 데이터를 얻으며 컨텐츠 또는 광고 게재 결정 동안 해당 정보를 고려할 수 있습니다. 또한 이 프로세스는 게시자 및 서버와 연동되므로 자격을 갖춘 세그먼트를 키-값 쌍으로 광고 호출로 읽은 퍼스트 파티 쿠키로 업데이트합니다. 현재 Audience Manager은 실시간 호출을 사용하여 [!DNL Adobe Target] 기타 컨텐츠 관리 시스템과 통합합니다.

<table> 
 <tr>
  <td> <p>장점: </p></td>
  <td> <p> 가장 최근 세그먼트 자격 조건을 기준으로 다음 페이지, 컨텐츠 영역 또는 광고 임프레션을 타깃팅할 수 있습니다. </p></td> 
 </tr> 
 <tr>
  <td> <p>단점: </p></td>
  <td> <p>페이지에서 Audience Manager에 대한 호출을 추가합니다.</p></td>
 </tr> 
</table>


### 픽셀이 타깃팅 시스템과 동기화됨

픽셀 동기화는 세그먼트를 페이지의 픽셀에 매핑합니다. 픽셀은 사용자가 특정 세그먼트에 맞는 경우 데이터를 실행하고 전송합니다. 픽셀 동기화는 기본적인 데이터 전송 메커니즘이며 안정성이 없습니다. 최고 계층의 데이터 제공업체 및 시스템은 거의 사용하지 않습니다.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>장점: </p></td>
  <td class="stentry"> <p> 실시간 데이터 전송 </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>단점: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">페이지에서 많은 클라이언트측 호출을 추가할 수 있습니다. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">데이터 전송 시 신뢰할 수 없음 5%에서 20%의 손실은 정상입니다. </li>
   </ul></td>
 </tr> 
</table>

## 데이터 전달 방법을 선택하는 방법 {#data-delivery-choices}

동기식(실시간) 또는 비동기식(서버 간) 방법을 통해 데이터를 전송하는 기술 및 비즈니스 이유를 설명합니다.

<!-- c_int_delivery_choices.xml -->

### 데이터 배달 유형 선택

* **기술 고려 사항:** 데이터 전달은 데이터 파트너의 기술 기능에 따라 달라집니다. Audience Manager은 브라우저에서 실시간으로 데이터를 전송/수신하거나 오프라인, 서버 간 통신 프로세스를 통해 일괄적으로 업데이트할 수 있습니다.
* **비즈니스 고려 사항:** 배달 방법 중 하나를 선택하거나 다른 방법을 선택하는 이유는 대상 파트너의 기술 기능과 이 데이터를 어떻게 사용할지를 결정합니다. 일반적으로 동기식 데이터 전송은 사용자 데이터에 대해 즉각적인 조치를 취해야 할 때 유용합니다. 비동기 데이터 전송은 즉각적인 작업이 필요하지 않고 나중에 사용할 수 있도록 더 깊은 사용자 프로필을 빌드할 시간이 있는 경우에 유용합니다.

## Real-Time Data Transfer Process {#real-time-data-transfer-process}

Audience Manager이 타사 공급업체와의 동기식 데이터 교환을 수행하는 방법에 대한 일반적인 개요입니다.

### 실시간 데이터 전송

<!-- c_int_overview_sync.xml -->

실시간 데이터 전송은 사용자가 사이트를 방문하거나 조치를 취할 때 세그먼트 ID를 보내고 받습니다. 일반적으로, 동기 데이터 전송은 재고를 탐색하면서 사용자를 자격 조건화하거나 즉시 세그먼트화해야 할 때 유용합니다.

### 실시간 데이터 통합 단계

실시간 데이터 통합 프로세스는 다음과 같이 작동합니다.

1. 사용자가 Audience Manager 코드를 포함하는 고객의 사이트를 방문합니다.
1. Audience Manager은 Iframe을 로드하고 [!UICONTROL Data Collection Server] ([!DNL DCS])에 대한 호출을 만듭니다.
1. 타사 서버 [!DNL DCS] (실시간으로)를 호출하여 공급업체가 사용자에 대한 세그먼트 정보를 가지고 있는지 확인합니다.
1. 제3자는 해당 사용자에 대한 세그먼트 정보를 Audience Manager에 반환합니다.
1. Audience Manager 인제스트 세그먼트 정보를 사용하여 타깃팅에 사용할 수 있도록 합니다.

![](assets/rt_reduce70.png)

## 배치 데이터 전송 프로세스 {#batch-data-transfer-process}

Audience Manager이 데이터를 타사 공급업체와 동기적으로(실시간으로) 교환하는 방법에 대한 일반적인 개요입니다.

### 일괄 데이터 통합

<!-- c_int_overview_async.xml -->

배치([!DNL server-to-server]) 데이터 통합 프로세스는 실시간 데이터 전송 프로세스에 설명된 대부분의 단계를 따릅니다. 하지만 세그먼트 ID를 즉시 반환하는 대신 사용자 정보가 서버에 저장되고 정기적으로 타사 데이터 공급자와 동기화됩니다. 비동기 데이터 전송 프로세스는 다음과 같은 경우에 유용합니다.

* 즉각적인 데이터 양도는 필요하지 않습니다.
* 데이터를 수집하여 세분화된 대규모 사용자 풀을 작성합니다.
* 브라우저의 데이터 불일치 및 `HTTP` 호출을 줄이고자 합니다.

### 일괄 데이터 통합 단계

1. 사용자가 고객 사이트를 방문합니다.
1. Audience Manager 및 타사 데이터 제공자는 방문자에게 고유한 ID(일반적으로 쿠키와 함께)를 할당합니다.
1. Audience Manager은 방문자 ID와 일치하도록 타사 데이터 공급자를 호출합니다.
1. 일반적으로 일별 간격인 예약된 요청은 Audience Manager과 타사 데이터 공급자 간에 방문자 세그먼트 데이터를 교환합니다.

![](assets/s2s_70.png)

Audience Manager이 인바운드 및 아웃바운드 [!DNL Server-to-Server] ([!UICONTROL S2S]) 파일 전송을 처리할 때의 시간 프레임을 설명하는 자세한 내용은 [보고 및 파일 전송 시간 프레임 지침을 참조하십시오](../reference/reporting-file-transfer-timeframe.md).
