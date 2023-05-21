---
description: 데이터 내보내기 제어 를 사용하면 이 작업이 데이터 개인 정보 보호 또는 데이터 사용 계약을 위반하는 경우 데이터를 대상으로 보내지 못합니다.
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: 데이터 내보내기 제어
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: 26aa0a210a045b40b2329844324315a092947188
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# 데이터 내보내기 제어 {#data-export-controls}

[!UICONTROL Data Export Controls] 이 작업이 데이터 개인 정보 보호 또는 데이터 사용 계약을 위반하는 경우 데이터를 대상으로 보내지 못하게 합니다.

## 개요 {#overview}

[!UICONTROL Data Export Controls] 분류할 수 있음 [데이터 소스](../features/datasources-list-and-settings.md#data-sources-list-and-settings) 및 [대상](../features/destinations/destinations.md). 적용하는 분류는 데이터를 대상으로 내보낼 수 있는 시기와 보낼 수 없는 시기를 결정합니다. 이 기능은 다음과 같이 구성됩니다.

* **[!UICONTROL Data Export Controls]**: 데이터 내보내기 제어 설정 *데이터 소스*. 데이터 소스에 설정된 경우 이러한 컨트롤은 해당 데이터 소스와 해당 트레이트의 사용 방법을 제한합니다.
* **[!UICONTROL Data Export Labels]**: 데이터 내보내기 레이블 을 설정할 수 있습니다 *대상*. 대상에 설정된 경우 이러한 레이블은 대상이 데이터를 사용하는 방법을 식별합니다. 다음을 참조하십시오 [대상에 데이터 내보내기 레이블 추가](/help/using/features/destinations/add-data-export-labels.md) 대상에 내보내기 레이블을 추가하는 방법을 알아봅니다.

데이터 소스 및 대상에 적용된 분류를 기반으로 내보내기 제어 기능을 사용하면 다음이 중지됩니다.

* 트레이트가 세그먼트가 매핑된 대상 중 하나 이상에 있는 데이터 내보내기 레이블과 호환되지 않는 데이터 내보내기 컨트롤이 있는 데이터 소스에 속하는 경우 세그먼트에 트레이트를 추가합니다.
예를 들어 세그먼트가 내보내기 레이블이 있는 대상에 매핑된다고 가정합니다 **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. 트레이트가 속한 데이터 소스에 다음과 같은 데이터 내보내기 컨트롤이 있는 경우 내보내기 컨트롤을 사용하면 해당 세그먼트에 트레이트를 추가할 수 없습니다 **[!DNL Cannot be tied to personally identifiable information (PII)]**.
* 다음 중 하나의 데이터 내보내기 제어에 의해 차단된 데이터 내보내기 레이블이 있는 대상에 데이터 보내기:
   * 포함된 트레이트의 데이터 소스
   * 포함된 세그먼트에 사용된 트레이트의 데이터 소스
   * 포함된 세그먼트에서 활용하는 프로필 병합 규칙
   * 포함된 세그먼트의 프로필 병합 규칙에서 사용하는 모든 데이터 소스입니다.

[!UICONTROL Data Export Controls] 모든 Audience Manager 고객이 자동으로 사용할 수 있습니다. 그러나 데이터 소스에 내보내기 컨트롤을 추가하려면 관리자 권한이 필요합니다. 대상에 내보내기 레이블을 추가하려면 관리자 권한이 필요합니다. *또는* 대상을 만들거나 편집할 수 있는 충분한 권한이 있습니다.

## 컨트롤 및 레이블 정의됨 {#controls-labels}

[!UICONTROL Data Export Controls] 데이터 소스 및 대상을 분류하는 데 도움이 되는 다음 컨트롤을 제공합니다.

데이터 전달을 차단하려면 내보내기 컨트롤을 사용하여 데이터 소스를 분류하고 내보내기 레이블을 대상에 추가해야 합니다. 데이터 소스 또는 대상에만 내보내기 컨트롤을 적용하는 경우 이 기능은 데이터 전달을 제한하지 않습니다. 두 데이터 소스 모두에서 설정된 경우 *및* 대상 내보내기 컨트롤은 세그먼트에 추가할 수 있는 트레이트를 제한하고 세그먼트 멤버를 대상으로 보내지 못하게 합니다.

또한 데이터 전달 제한이 적용되려면 먼저 하나 이상의 내보내기 레이블이 내보내기 컨트롤과 일치해야 합니다. 예를 들어 다음을 추가한다고 가정합니다. [!UICONTROL PII] 데이터 소스로 컨트롤을 내보냅니다. 다음으로, 온사이트 타겟팅 레이블을 대상에 추가합니다. 이 경우 설정이 일치하지 않으므로 내보내기 컨트롤이 데이터 전달을 제한하지 않습니다. 그러나 를 추가하는 경우 [!UICONTROL PII] 레이블을 대상으로 내보내면 내보내기 컨트롤이 내보내기를 차단합니다.

>[!IMPORTANT]
>
>세그먼트의 데이터 소스에 데이터 내보내기 컨트롤을 배치하여 세그먼트의 내보내기를 차단할 수 없습니다. 다음 중 하나에 컨트롤을 설정해야 합니다.
> * 세그먼트에 사용된 트레이트의 데이터 소스
> * 세그먼트가 활용하는 프로필 병합 규칙
> * 세그먼트의 프로필 병합 규칙이 사용하는 모든 데이터 소스입니다.


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 데이터 소스에 대한 데이터 내보내기 제어 </th> 
   <th colname="col2" class="entry"> 대상에 대한 데이터 내보내기 레이블 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 제한 없음</span></b> </td> 
   <td colname="col2"> n/a </td> 
   <td colname="col3"> 기본적으로 내보내기 제한 사항은 새 데이터 소스 및 대상에 설정되어 있지 않습니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 개인 식별 정보에 연결할 수 없음</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 PII(개인 식별 정보)와의 조합을 활성화할 수 있습니다</span></b> </td> 
   <td colname="col3">이 옵션을 선택하면 다음 작업을 수행할 수 없습니다. 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">PII를 사용하는 대상에 매핑된 세그먼트에 트레이트를 추가합니다. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">데이터 소스의 트레이트로 구축된 세그먼트를 PII를 사용하는 대상에 매핑합니다. </li> 
    </ul> <p>타사 데이터 공급자에 필요하며 광고/미디어 추적 정보가 포함된 데이터 소스를 사용할 때 필요한 경우가 많습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 온사이트 광고 타겟팅에는 사용할 수 없음</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 온사이트 광고 타겟팅에 사용할 수 있습니다.</span></b> </td> 
   <td colname="col3">이 옵션을 선택하면 다음 작업을 수행할 수 없습니다. 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">방문자의 웹 검색 기록을 기반으로 광고 게재를 사용자 지정하는 대상에 매핑된 세그먼트에 트레이트를 추가합니다. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">데이터 소스의 트레이트로 구축된 세그먼트를 방문자의 웹 검색 기록을 기반으로 광고 전달을 사용자 지정하는 대상에 매핑합니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 오프사이트 광고 타겟팅에는 사용할 수 없음</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 오프사이트 광고 타겟팅에 사용할 수 있습니다.</span></b> </td> 
   <td colname="col3">이 옵션을 선택하면 다음 작업을 수행할 수 없습니다. 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">다른 사이트의 사용자를 다시 타겟팅하는 대상에 매핑된 세그먼트에 트레이트를 추가합니다. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">데이터 소스의 트레이트로 구축된 세그먼트를 다른 사이트의 사용자를 다시 타겟팅하는 대상에 매핑합니다. </li> 
    </ul> <p>소셜 미디어 플랫폼의 데이터로 작업할 때 필요한 경우가 많습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 온사이트 개인화에 사용할 수 없음</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 온사이트 및 개인화에 사용할 수 있습니다.</span></b> </td> 
   <td colname="col3">이 옵션을 선택하면 다음 작업을 수행할 수 없습니다. 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">사용자 관심 분야나 웹 검색 기록을 기반으로 콘텐츠를 사용자 지정하는 대상에 매핑된 세그먼트에 트레이트를 추가합니다. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">데이터 소스의 트레이트로 빌드된 세그먼트를 사용자 관심사나 웹 검색 기록을 기반으로 콘텐츠를 사용자 지정하는 대상에 매핑합니다. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 워크플로 {#workflow}

시작하려면 데이터 소스 및 대상 설명서를 검토하십시오. 이 문서에서는 데이터 소스 및 대상에 내보내기 제어 및 레이블을 추가하는 방법에 대한 지침을 제공합니다.

* [데이터 소스 만들기](../features/manage-datasources.md#create-data-source)
* [대상에 데이터 내보내기 레이블 추가](../features/destinations/add-data-export-labels.md)
