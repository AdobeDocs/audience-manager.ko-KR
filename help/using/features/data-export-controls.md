---
description: 데이터 내보내기 제어를 사용하면 이 작업이 데이터 개인 정보 또는 데이터 사용 계약을 위반하는 경우 데이터를 대상으로 보내지 못합니다.
seo-description: 데이터 내보내기 제어를 사용하면 이 작업이 데이터 개인 정보 또는 데이터 사용 계약을 위반하는 경우 데이터를 대상으로 보내지 못합니다.
seo-title: 데이터 내보내기 제어
solution: Audience Manager
title: 데이터 내보내기 제어
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 1%

---


# 데이터 내보내기 제어 {#data-export-controls}

[!UICONTROL Data Export Controls] 데이터 개인 정보 또는 데이터 사용 계약을 위반하는 경우 데이터를 대상으로 보내지 마십시오.

## 개요 {#overview}

[!UICONTROL Data Export Controls] 데이터 소스 및  [대상을 ](../features/datasources-list-and-settings.md#data-sources-list-and-settings) 분류할  [수 있습니다](../features/destinations/destinations.md). 적용하는 분류에서 데이터를 대상으로 내보낼 수 있거나 내보낼 수 없는 시기를 결정합니다. 이 기능은 다음과 같이 구성됩니다.

* **[!UICONTROL Data Export Controls]**:데이터 소스에 데이터 내보내기 컨트롤을 설정할 수  *있습니다*. 데이터 소스를 설정할 때 이러한 컨트롤은 데이터 소스 및 해당 트레이트의 사용 방법을 제한합니다.
* **[!UICONTROL Data Export Labels]**:대상에 데이터 내보내기 레이블을 설정할 수  *있습니다*. 대상에 설정되면, 이러한 레이블은 대상이 데이터를 사용하는 방법을 식별합니다. 대상에 내보내기 레이블을 추가하는 방법을 알려면 [데이터 내보내기 레이블 추가를 참조하십시오.](/help/using/features/destinations/add-data-export-labels.md)

데이터 소스 및 대상에 적용된 분류를 기반으로 내보내기 컨트롤을 사용하면 다음 작업을 수행할 수 없습니다.

* 세그먼트가 매핑된 대상 중 하나 이상에 데이터 내보내기 레이블과 호환되지 않는 데이터 내보내기 컨트롤이 있는 데이터 원본에 트레이트를 세그먼트에 추가합니다.
예를 들어 세그먼트가 내보내기 레이블이 **[!DNL This destination may enable a combination with personally identifiable information (PII)]**&#x200B;인 대상에 매핑된다고 가정할 경우 트레이트가 속한 데이터 소스에 **[!DNL Cannot be tied to personally identifiable information (PII)]**&#x200B;이라는 데이터 내보내기 컨트롤이 있는 경우 내보내기 컨트롤을 사용하면 해당 세그먼트에 트레이트를 추가할 수 없습니다.
* 대상 대상으로 데이터를 전송하는 경우 데이터 내보내기 레이블이 다음 중 하나에 대해 데이터 내보내기 컨트롤에 의해 차단됩니다.
   * 포함된 트레이트의 데이터 소스
   * 포함된 세그먼트에서 사용되는 트레이트의 데이터 소스
   * 포함된 세그먼트가 활용하는 프로필 병합 규칙;
   * 포함된 세그먼트의 프로필 병합 규칙이 사용하는 모든 데이터 소스

[!UICONTROL Data Export Controls] 모든 Audience Manager 고객에게 자동으로 제공됩니다. 그러나 데이터 소스에 내보내기 컨트롤을 추가하려면 관리자 권한이 필요합니다. 대상에 내보내기 레이블을 추가하려면 대상을 만들거나 편집할 수 있는 관리자 권한 *또는*&#x200B;이(가) 필요합니다.

## {#controls-labels} 컨트롤 및 레이블 정의

[!UICONTROL Data Export Controls] 데이터 소스 및 대상을 분류하는 데 도움이 되는 다음 컨트롤을 제공합니다.

데이터 배달을 차단하려면 내보내기 컨트롤을 사용하여 데이터 소스를 분류하고 대상에 내보내기 레이블을 추가해야 합니다. 데이터 소스 또는 대상에만 내보내기 컨트롤을 적용하는 경우 이 기능은 데이터 제공을 제한하지 않습니다. 데이터 소스 *과* 대상에 모두 설정된 경우 내보내기 컨트롤은 세그먼트에 추가할 수 있는 트레이트를 제한하고 세그먼트 구성원을 대상으로 보내지 않습니다.

또한 데이터 전달 제한이 적용되기 전에 하나 이상의 내보내기 레이블이 내보내기 컨트롤과 일치해야 합니다. 예를 들어 데이터 소스에 [!UICONTROL PII] 내보내기 컨트롤을 추가한다고 가정해 보십시오. 그런 다음 대상에 온사이트 타깃팅 레이블을 추가합니다. 이 경우 설정이 일치하지 않으므로 내보내기 컨트롤이 데이터 배달을 제한하지 않습니다. 그러나 [!UICONTROL PII] 내보내기 레이블을 대상에 추가하면 내보내기 컨트롤이 내보내기를 차단합니다.

>[!IMPORTANT]
>
>세그먼트의 데이터 소스에 데이터 내보내기 컨트롤을 배치하여 세그먼트 내보내기를 차단할 수 없습니다. 다음 중 하나에서 컨트롤을 설정해야 합니다.
> * 세그먼트에 사용된 트레이트의 데이터 소스
> * 세그먼트가 활용하는 프로필 병합 규칙;
> * 세그먼트의 프로필 병합 규칙이 사용하는 모든 데이터 소스.


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 데이터 소스에 대한 데이터 내보내기 컨트롤 </th> 
   <th colname="col2" class="entry"> 대상에 대한 데이터 내보내기 레이블 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 제한 없음</span></b> </td> 
   <td colname="col2"> n/a </td> 
   <td colname="col3"> 기본적으로 새 데이터 소스 및 대상에 대해 내보내기 제한이 설정되지 않습니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 개인 식별 정보</span></b> (PII)에 연결할 수 없습니다. </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 PII(개인 식별 정보)와 결합할 수 있습니다.</span></b> </td> 
   <td colname="col3">선택할 경우 다음을 수행할 수 없습니다. 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">PII를 사용하는 대상에 매핑된 세그먼트에 트레이트를 추가합니다. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">데이터 소스에서 PII를 사용하는 대상에 트레이트로 작성한 세그먼트를 매핑합니다. </li> 
    </ul> <p>이는 종종 타사 데이터 공급자와 광고/미디어 추적 정보가 포함된 데이터 소스를 사용하는 경우에 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 온사이트 광고 타깃팅에 사용할 수 없음</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 온사이트 광고 타깃팅에 사용할 수 있습니다.</span></b> </td> 
   <td colname="col3">선택할 경우 다음을 수행할 수 없습니다. 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">방문자의 웹 탐색 기록에 따라 광고 배달을 사용자 지정하는 대상에 매핑된 세그먼트에 트레이트를 추가합니다. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">데이터 소스에서 타깃팅으로 만들어진 세그먼트를 방문자의 웹 탐색 기록에 따라 광고 전달을 사용자 지정하는 대상에 매핑합니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 오프라인 광고 타깃팅에 사용할 수 없음</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 오프사이트 광고 타깃팅에 사용할 수 있습니다.</span></b> </td> 
   <td colname="col3">이러한 제한 사항은 일반적으로 [선택 시]와 함께 사용됩니다. 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">다른 사이트에서 사용자를 다시 타깃팅하는 대상에 매핑된 세그먼트에 트레이트를 추가합니다. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">데이터 소스에서 트레이트로 작성한 세그먼트를 다른 사이트의 사용자를 다시 타깃팅하는 대상에 매핑합니다. </li> 
    </ul> <p>소셜 미디어 플랫폼의 데이터를 사용하여 작업하는 경우 종종 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 온사이트 개인화에 사용할 수 없음</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 온사이트 광고 개인화에 사용될 수 있습니다.</span></b> </td> 
   <td colname="col3">선택할 경우 다음을 수행할 수 없습니다. 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">사용자 관심사 또는 웹 탐색 기록에 따라 컨텐츠를 사용자 지정하는 대상에 매핑된 세그먼트에 트레이트를 추가합니다. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">사용자 관심사 또는 웹 검색 내역을 기반으로 컨텐츠를 사용자 정의하는 대상에 데이터 소스에서 트레이트로 작성한 세그먼트를 매핑합니다. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 워크플로우 {#workflow}

시작하려면 데이터 소스 및 대상 설명서를 검토하십시오. 이 문서에서는 데이터 소스 및 대상에 내보내기 제어 및 레이블을 추가하는 방법에 대한 지침을 제공합니다.

* [데이터 소스 만들기](../features/manage-datasources.md#create-data-source)
* [대상에 데이터 내보내기 레이블 추가](../features/destinations/add-data-export-labels.md)