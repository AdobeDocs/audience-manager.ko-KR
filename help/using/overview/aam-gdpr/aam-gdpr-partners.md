---
description: 이 페이지에서는 Adobe Audience Manager 연습과 관련된 의미와 함께 제공되는 정보에 대해 설명합니다. 이러한 업데이트를 수행하는 파트너에게 중요한 의미는 2018년 5월 25일부터 시행된 GDPR(General Data Protection Regulation) 및 새로운 IAB GDPR Transparency & Consent Framework(IAB Framework)의 결과입니다.
seo-description: 이 페이지에서는 Adobe Audience Manager 연습과 관련된 의미와 함께 제공되는 정보에 대해 설명합니다. 이러한 업데이트를 수행하는 파트너에게 중요한 의미는 2018년 5월 25일부터 시행된 GDPR(General Data Protection Regulation) 및 새로운 IAB GDPR Transparency & Consent Framework(IAB Framework)의 결과입니다.
seo-title: 대상에 대한 GDPR 고려 사항
solution: Audience Manager
title: 대상에 대한 GDPR 고려 사항
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# 대상에 대한 GDPR 고려 사항{#gdpr-considerations-for-destinations}

이 페이지에서는 Adobe Audience Manager 연습과 관련된 의미와 함께 제공되는 정보에 대해 설명합니다. 이러한 업데이트를 수행하는 파트너에게 중요한 의미는 2018년 5월 25일부터 시행된 GDPR(General Data Protection Regulation) 및 새로운 IAB GDPR Transparency &amp; Consent Framework(IAB Framework)의 결과입니다.

Adobe 파트너는 업무 처리 과정을 소유하고 있으며 Audience Manager와의 통합 요구 사항을 수시로 업데이트하기로 결정할 수 있습니다. Adobe는 Adobe Audience Manager 파트너 에코시스템과 적극적으로 협력하여 고객이 변경 사항을 인지할 수 있도록 지원하고 있습니다.

## Audience Manager 파트너 업데이트 - ID 동기화 {#partner-updates-id-syncs}

아래 표에 나와 있는 바와 같이 일부 파트너는 GDPR 표준을 준수하기 위해 IAB Framework 기반의 지원을 포함하도록 Audience Manager와의 통합 요구 사항을 변경했습니다.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>예상 영향 </p> </th> 
   <th colname="col3" class="entry"> <p>변경 상태 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>유럽 연합의 사용자에 대한 ID 동기화가 파트너에 의해 삭제됩니다. </p> </td> 
   <td colname="col3"> <p>2018년 5월 22일부터 라이브 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>무역부 </p> </td> 
   <td colname="col2"> <p>유럽 연합의 사용자에 대한 ID 동기화가 파트너에 의해 삭제됩니다. </p> </td> 
   <td colname="col3"> <p>아직 살지 않음 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>유럽 연합의 사용자에 대한 ID 동기화가 파트너에 의해 삭제됩니다. </p> </td> 
   <td colname="col3"> <p>아직 살지 않음 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> LiveRamp </p> </td> 
   <td colname="col2"> <p>유럽 연합의 사용자에 대한 ID 동기화가 파트너에 의해 삭제됩니다. </p> </td> 
   <td colname="col3"> <p>아직 살지 않음 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager UI 업데이트 - Yahoo/Oath/DataX 통합 {#ui-update}

위에 언급된 IAB 프레임워크에 대한 업데이트 외에 Yahoo/Oath/DataX는 분류 및 대상 API에 새로운 매개 변수, **gdpr** 및 **gdpr_mode**&#x200B;를 추가했습니다. Their parameters inform Yahoo/Oath/DataX that they have the rights to process a certain segment as a Data Processor or as a Data Controller. 그 결과 Yahoo/Oath/DataX 대상으로 세그먼트를 전송하는 Audience Manager 고객은 Oath와의 계약에 따라 적절한 매개 변수(프로세서 또는 컨트롤러)를 지정해야 합니다.

Please reach out to your Consultant or Client Care to set the correct parameter. Adobe cannot make this update on behalf of a customer unless we receive written correspondence, requesting this update. Please reach out to your Yahoo/Oath/DataX representative to understand the full definition of these parameters.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

In order to help our customers automate GDPR requests, Audience Manager notifies our activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

However, some of our activation partners:

1. Cannot support unsegment requests from Adobe and/or
1. Are not able to receive updates from us more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through Audience Manager. Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx) to see which Audience Manager activation partners support unsegment.
