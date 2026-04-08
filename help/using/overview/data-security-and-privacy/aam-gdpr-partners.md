---
description: 이 페이지에서는 Audience Manager 사용과 관련된 함의와 함께 파트너가 직접 제공하는 정보에 대해 설명합니다. 이러한 업데이트를 수행하는 파트너에게 중요한 의미는 2018년 5월 25일부터 적용된 GDPR(일반 개인정보보호 규정)과 새로운 IAB GDPR 투명성 및 동의 프레임워크(IAB 프레임워크)의 결과입니다.
seo-description: This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR Considerations for Destinations
solution: Audience Manager
title: 대상에 대한 GDPR 고려 사항
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Data Governance & Privacy
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
TQID: https://experienceleague.adobe.com/QJr4SR9ZcwBH-xkX-0CJ23GQ09SDmkgTeN7Vl4djSb4
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d095671a-1355-40aa-8b5f-06c33c68080bid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 3c88464c2249b7848c9ae80ca4c0ed58fcb81070
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 96%

---

# 대상에 대한 GDPR 고려 사항{#gdpr-considerations-for-destinations}

이 페이지에서는 Audience Manager 사용과 관련된 함의와 함께 파트너가 직접 제공하는 정보에 대해 설명합니다. 이러한 업데이트를 수행하는 파트너에게 중요한 의미는 2018년 5월 25일부터 적용된 GDPR(일반 개인정보보호 규정)과 새로운 IAB GDPR 투명성 및 동의 프레임워크(IAB 프레임워크)의 결과입니다.

Adobe 파트너는 자체 비즈니스 프로세스를 운영하고 있으며 수시로 Audience Manager와의 통합 요구 사항을 업데이트하도록 결정할 수 있습니다. Adobe는 Audience Manager 파트너 에코시스템과 적극적으로 협력하여 고객에게 변경 사항을 계속 알리고 있습니다.

<!--
## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table>
-->

## Audience Manager 사용자 인터페이스 업데이트 - Yahoo/Oath/DataX 통합 {#ui-update}

위에 언급된 IAB 프레임워크에 대한 업데이트 외에도 Yahoo/Oath/DataX는 분류법 및 대상자 API에 새로운 매개 변수인 **gdpr**&#x200B;과 **gdpr_mode**&#x200B;를 추가했습니다. 이 매개 변수들은 Yahoo/Oath/DataX에 데이터 처리자나 데이터 통제자로서 특정 세그먼트를 처리할 권한이 있음을 알려줍니다. 그 결과 Yahoo/Oath/DataX 대상에 세그먼트를 보내는 Audience Manager 고객은 Oath와의 계약에 따라 적절한 매개 변수를 지정해야 합니다(처리자 또는 통제자).

올바른 매개 변수를 설정하려면 컨설턴트 또는 Client Care에 문의하십시오. Adobe는 이 업데이트를 요청하는 서면 메시지를 받지 않는 한 고객을 대신하여 이 업데이트를 수행할 수 없습니다. 이러한 매개 변수에 대한 전체 정의를 알려면 Yahoo/Oath/DataX 담당자에게 문의하십시오.
