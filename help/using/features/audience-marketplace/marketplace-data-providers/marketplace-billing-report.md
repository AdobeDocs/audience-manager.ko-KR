---
description: 각 구독자에 대한 이전 달의 데이터 피드 사용을 보려면 Audience Marketplace 청구 보고서를 생성합니다. 언제든지 이전 달에 대한 보고서를 만들 수 있습니다. 하지만 이번 달 10일 이후에 보고서를 생성할 때는 더 정확합니다.
seo-description: 각 구독자에 대한 이전 달의 데이터 피드 사용을 보려면 Audience Marketplace 청구 보고서를 생성합니다. 언제든지 이전 달에 대한 보고서를 만들 수 있습니다. 하지만 이번 달 10일 이후에 보고서를 생성할 때는 더 정확합니다.
seo-title: 데이터 피드 공급자에 대한 청구
solution: Audience Manager
title: 데이터 피드 공급자에 대한 청구
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 6%

---

# 데이터 피드 공급자에 대한 청구 {#billing-for-data-feed-providers}

각 구독자에 대한 이전 달의 데이터 피드 사용을 보려면 [!DNL Audience Marketplace] 청구 보고서를 생성합니다. 언제든지 이전 달에 대한 보고서를 만들 수 있습니다. 하지만 이번 달 10일 이후에 보고서를 생성할 때는 더 정확합니다.

## 청구 보고서 다운로드 {#download-billing-report}

보고서를 다운로드하려면:

1. **[!UICONTROL Audience Marketplace > Receivables]**(으)로 이동합니다.
1. 클릭 **[!UICONTROL Generate Billing Report]**.

## 정의된 보고서 필드 {#report-fields-defined}

청구 보고서에는 다음 정보가 포함됩니다.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 보고서 필드 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 데이터 공급자 PID</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 데이터 공급자 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 데이터 공급자 이름</span></b> </p> </td> 
   <td colname="col2"> <p>회사 또는 조직 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 구매자 PID</span></b> </p> </td> 
   <td colname="col2"> <p>구매자(가입자) ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 구매자명</span></b> </p> </td> 
   <td colname="col2"> <p>구매자의 회사 또는 조직명입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 피드 ID</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 피드의 ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 피드 이름</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 피드의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 계획 사용 사례</span></b> </p> </td> 
   <td colname="col2"> <p>사용 사례는 판매자가 구매자의 데이터 사용 방식을 제어할 수 있도록 해줍니다. 옵션은 다음과 같습니다. </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">세그먼트 및 겹치기 </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">모델링 </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">활성화 </li> 
    </ul> <p>데이터 피드에 대한 <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> 계획 유형</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> UOM</span></b> </p> </td> 
   <td colname="col2"> <p>CPM 또는 정액 요금 청구를 나타냅니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 장부 가격</span></b> </p> </td> 
   <td colname="col2"> <p>각 데이터 피드의 구독 요금. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 할인된 가격</span></b> </p> </td> 
   <td colname="col2"> <p>할인된 데이터 피드에 대한 구독 요금. 데이터 제공업체를 위한 <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> 할인</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 판매량</span></b> </p> </td> 
   <td colname="col2"> <p>피드 가격 유형에 따라 달라집니다. </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">정액 요금 데이터 피드:1만 반환합니다. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM 데이터 피드:CPM 데이터 피드에 대한 실제 사용량 반환 가입자가 CPM 피드에 대한 노출 데이터를 제공하지 않은 경우 단위 셀이 비어 있고 플래그 셀이 1로 설정됩니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 총 비용</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 금액은 구매자에게 청구됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 청구 기간</span></b> </p> </td> 
   <td colname="col2"> <p> 보고서에서 이는 이전 달의 마지막 날입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 시작 날짜</span></b> </p> </td> 
   <td colname="col2"> <p>구매자가 가입/사용 정보를 입력한 일자. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 구독 시작 날짜</span></b> </p> </td> 
   <td colname="col2"> <p>구매자가 데이터 피드 구독을 시작한 날짜입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 구독 종료 날짜</span></b> </p> </td> 
   <td colname="col2"> <p>구매자가 데이터 피드 구독을 종료한 날짜입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 플래그</span></b> </p> </td> 
   <td colname="col2"> <p> <i>CPM 피드의 경우에만</i>. 플래그 옵션은 다음과 같습니다. </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0:구독자가 <span class="keyword"> Audience Manager</span>에 사용 정보를 보고한 것을 나타냅니다. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1:구독자가 <span class="keyword"> Audience Manager</span>에 사용 정보를 보고하지 않았음을 나타냅니다. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [CPM 데이터 피드에 대한 청구 및 노출 할당](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
* [정액 요금 데이터 피드에 대한 청구 및 노출 할당](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
* [CPM 사용을 보고하는 방법](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

