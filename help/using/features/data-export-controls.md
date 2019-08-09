---
description: 데이터 내보내기 컨트롤을 사용하면 이 작업이 데이터 개인 정보 또는 데이터 사용 계약을 위반하는 경우 대상을 대상으로 보낼 수 없습니다.
seo-description: 데이터 내보내기 컨트롤을 사용하면 이 작업이 데이터 개인 정보 또는 데이터 사용 계약을 위반하는 경우 대상을 대상으로 보낼 수 없습니다.
seo-title: 데이터 내보내기 제어
solution: Audience Manager
title: 데이터 내보내기 제어
uuid: DE 7 F 3608-C 0 CB -4049-973 A -8 BE 54525 C 600
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# 데이터 내보내기 제어 {#data-export-controls}

[!UICONTROL Data Export Controls] 이 작업이 데이터 개인 정보 또는 데이터 사용 계약을 위반하는 경우 대상에 데이터를 보내지 않도록 합니다.

## 개요 {#overview}

[!UICONTROL Data Export Controls][Data Sources](../features/datasources-list-and-settings.md#data-sources-list-and-settings) 및 [대상을 분류할](../features/destinations/destinations.md)수 있습니다. 적용하는 분류는 데이터를 대상으로 내보낼 수 있을 때와 내보낼 수 없을 때를 결정합니다. 이 기능은 다음과 같이 구성됩니다.

* **[!UICONTROL Data Export Controls]**: 데이터 소스에 대한 데이터 내보내기 컨트롤을 *설정할*&#x200B;수 있습니다. 데이터 소스에 설정되면 이러한 컨트롤은 데이터 소스와 해당 특성을 사용할 수 있는 방법을 제한합니다.
* **[!UICONTROL Data Export Labels]**: 대상에 데이터 내보내기 레이블을 설정할 **&#x200B;수 있습니다. 대상에 설정되면, 이러한 레이블은 대상이 데이터를 사용하는 방법을 식별합니다. 대상에 [레이블 내보내기 추가 방법을 알아보려면 대상에](/help/using/features/destinations/add-data-export-labels.md) 데이터 내보내기 레이블 추가를 참조하십시오.

데이터 소스 및 대상에 적용된 분류에 따라 내보내기 컨트롤은 다음 위치에서 사용자를 중지합니다.

* 세그먼트가 매핑되는 하나 이상의 대상에 대한 데이터 내보내기 레이블과 호환하지 않는 데이터 내보내기 제어가 있는 데이터 소스에 속성이 속해 있을 때 세그먼트에 특성 추가.
예를 들어, 세그먼트가 Export 레이블 **[Uicontrol를 사용하여 대상에 매핑된다고 가정해 보겠습니다. 이 대상에서는 PII (개인 식별 정보]**) 와의 결합을 활성화할 수 있습니다. 내보내기가 속한 데이터 소스에 Uicontrol 이 있는 **[데이터 내보내기 컨트롤이 있으면 내보내기 컨트롤을 사용하면 해당 세그먼트에 트레이트를 추가하지 않아도 됩니다. 개인 식별 정보 (PII]**) 에 연결할 수 없습니다.
* 대상 목적지로 데이터를 전송하는 경우 데이터 내보내기 제어 기능으로 차단된 데이터 내보내기 레이블이 있습니다.
   * 포함된 트레이트의 데이터 소스;
   * 포함된 세그먼트에 사용되는 트레이트 데이터 소스
   * 포함된 세그먼트에 의해 활용되는 프로필 병합 규칙
   * 포함된 세그먼트의 프로필 병합 규칙이 사용하는 데이터 소스.

[!UICONTROL Data Export Controls] 모든 Audience Manager 고객에게 자동으로 제공됩니다. 그러나 데이터 소스에 내보내기 컨트롤을 추가하려면 관리자 권한이 필요합니다. 대상에 레이블을 추가하려면 관리자 권한이 *필요하거나* 대상을 만들거나 편집할 수 있는 충분한 권한이 필요합니다.

## 정의된 컨트롤 및 레이블 {#controls-labels}

[!UICONTROL Data Export Controls] 데이터 소스 및 대상을 분류하는 데 도움이 되는 다음 컨트롤을 제공합니다.

데이터 배달을 차단하려면 내보내기 컨트롤을 사용하여 데이터 소스를 분류하고 대상에 내보내기 레이블을 추가해야 합니다. 데이터 소스 또는 대상에 내보내기 컨트롤을 적용하는 경우 이 기능은 데이터 제공을 제한하지 않습니다. 데이터 소스와 *대상 모두에 대해* 설정되면, 내보내기 컨트롤이 세그먼트에 추가할 수 있는 트레이트를 제한하고 세그먼트 구성원을 대상에 보내지 못하도록 합니다.

또한, 데이터 배달 제한이 적용되기 전에 하나 이상의 내보내기 레이블이 내보내기 제어와 일치해야 합니다. 예를 들어 데이터 소스에 [!UICONTROL PII] 내보내기 컨트롤을 추가하는 경우 다음으로 온사이트 타깃팅 레이블을 대상에 추가합니다. 이 경우, 설정이 일치하지 않으므로 내보내기 컨트롤이 데이터 배달을 제한하지 않습니다. 그러나 대상 [!UICONTROL PII] 내보내기 레이블을 대상에 추가하면 내보내기 컨트롤이 내보내기를 차단합니다.

>[!IMPORTANT]
>
>[세그먼트 데이터 소스에 데이터 내보내기 컨트롤을 배치하여 세그먼트 내보내기를 차단할 수 없습니다. 다음 중 한 항목에 대한 컨트롤을 설정해야 합니다.
> * 세그먼트에 사용된 트레이트의 데이터 소스
> * 세그먼트에 의해 활용되는 프로필 병합 규칙
> * 세그먼트의 프로필 병합 규칙이 사용하는 데이터 소스.


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
   <td colname="col3"> 기본적으로 내보내기 제한 사항은 새 데이터 소스 및 대상에 대해 설정되지 않습니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> PII (개인 식별 정보</span></b> ) 에 연결할 수 없음 </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 PII (개인 식별 정보) 와의 결합을 활성화할 수 있습니다.</span></b> </td> 
   <td colname="col3">선택하면 다음 작업을 수행할 수 없습니다. 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">PII를 사용하는 대상에 매핑된 세그먼트에 트레이트를 추가할 수 있습니다. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">데이터 소스의 트레이트로 작성된 세그먼트를 PII를 사용하는 대상에 매핑합니다. </li> 
    </ul> <p>이는 종종 타사 데이터 공급자가 광고/미디어 추적 정보가 들어 있는 데이터 소스를 사용할 때 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 온사이트 광고 타깃팅에 사용할 수 없음</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 사이트 내 광고 타깃팅에 사용될 수 있습니다.</span></b> </td> 
   <td colname="col3">선택하면 다음 작업을 수행할 수 없습니다. 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">방문자의 웹 탐색 내역을 기반으로 광고 배달을 사용자 정의하는 대상에 매핑된 세그먼트에 트레이트를 추가합니다. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">방문자의 웹 검색 내역을 기반으로 광고 전달을 맞춤화하는 대상 데이터 소스의 트레이트로 작성된 세그먼트를 매핑할 수 있습니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 오프사이트 광고 타깃팅에 사용할 수 없음</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 오프사이트 광고 타깃팅에 사용될 수 있습니다.</span></b> </td> 
   <td colname="col3">이러한 제한 사항은 일반적으로 선택되었을 때 사용됩니다. 다음 사항은 사용할 수 없습니다. 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">다른 사이트에서 사용자를 재타깃팅하는 대상에 매핑된 세그먼트에 트레이트를 추가할 수 있습니다. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">데이터 소스의 트레이트로 구축된 세그먼트를 다른 사이트에서 사용자를 재타깃팅하는 대상에 매핑합니다. </li> 
    </ul> <p>소셜 미디어 플랫폼의 데이터를 사용하여 작업할 때 필요합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 온사이트 개인화에 사용할 수 없음</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 이 대상은 사이트 내 광고 개인화에 사용될 수 있습니다.</span></b> </td> 
   <td colname="col3">선택하면 다음 작업을 수행할 수 없습니다. 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">사용자 관심사나 웹 검색 내역을 기반으로 컨텐츠를 맞춤화하는 대상에 매핑된 세그먼트에 트레이트를 추가할 수 있습니다. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">데이터 소스에서 사용자 관심사 또는 웹 검색 내역을 기반으로 컨텐츠를 맞춤화하는 대상에 트레이트를 사용하여 구축된 세그먼트를 매핑할 수 있습니다. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 워크플로우 {#workflow}

시작하려면 데이터 소스 및 대상 설명서를 검토하십시오. 다음 문서에서는 데이터 소스 및 대상에 내보내기 컨트롤과 레이블을 추가하는 방법에 대한 지침을 제공합니다.

* [데이터 소스 만들기](../features/manage-datasources.md#create-data-source)
* [대상에 데이터 내보내기 레이블 추가](../features/destinations/add-data-export-labels.md)