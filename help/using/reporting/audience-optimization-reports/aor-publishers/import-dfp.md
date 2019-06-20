---
description: Audience Manager가 게시자에 대한 대상 최적화를 활성화할 수 있으려면 먼저 이 문서에 설명된 모든 전제 조건이 충족되는지 확인해야 합니다. 모든 전제 조건을 확인한 후 고객 지원에 문의하십시오.
seo-description: Audience Manager가 게시자에 대한 대상 최적화를 활성화할 수 있으려면 먼저 이 문서에 설명된 모든 전제 조건이 충족되는지 확인해야 합니다. 모든 전제 조건을 확인한 후 고객 지원에 문의하십시오.
seo-title: DFP 데이터 파일을 Audience Manager에 가져오기
solution: Audience Manager
title: DFP 데이터 파일을 Audience Manager에 가져오기
uuid: c 685 f 34 f -3 e 50-4 c 4 b -99 fa-d 8 bbafe 0 b 268
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DFP 데이터 파일을 Audience Manager에 가져오기{#import-dfp-data-files-into-audience-manager}

Audience Manager가 게시자에 대한 대상 최적화를 활성화할 수 있으려면 먼저 이 문서에 설명된 모든 전제 조건이 충족되는지 확인해야 합니다. 모든 전제 조건을 확인한 후 고객 지원에 문의하십시오.

## Prerequisites for DFP Log Ingestion {#prereqs-dfp-ingestion}

Note that the process described in this section must be completed *before* you move on to the prerequisites for log ingestion enablement.

In order to use DFP ( [!DNL DoubleClick For Publishers]) log files in [!DNL Audience Manager], you must first set our [Audience Manager Unique User ID (UUID)](../../../reference/ids-in-aam.md) in the ad tag call. By doing this, our ID is included in the DFP logs and we can match IDs between DFP and [!DNL Audience Manager]. [!DNL Audience Manager][!UICONTROL DIL] 코드 또는을 [!UICONTROL Audience Management Module] 사용하여 [!DNL Audience Manager] 자사 쿠키의 UUID를 설정합니다.

Here is how to set the [!DNL Audience Manager] ID in the ad tag call, as explained in our documentation:

* [Google Publisher 태그 (GPT) 를 통해](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
* [쿠키 대상 사용](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)

[!DNL Audience Manager] ID를 직접 설정해야 하며 컨설팅을 통해 [!DNL Audience Manager] 모든 기능이 작동하는지 확인할 수 있습니다. You have set the [!DNL Audience Manager] ID correctly if:

* `'aamid'` 는 식별자로 사용되는 키입니다.
* The User ID value is correctly formatted as the [!DNL Audience Manager] UUID, as described in our [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md).
* You have included the [!DNL Audience Manager] UUID in a defined field in your DFP logs (e.g. CustomTargeting).

## Prerequisites for Log Ingestion Enablement {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 단계 </th> 
   <th colname="col2" class="entry"> 세부 사항 </th> 
   <th colname="col3" class="entry"> 소유자 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1단계 </p> </td> 
   <td colname="col2"> <p>Confirm that the required steps to set the <span class="keyword"> Audience Manager</span> UUID (outlined above) have been completed prior to moving to Step 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> 고객 지원 또는 컨설팅 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2단계 </p> </td> 
   <td colname="col2"> <p>DFP 관리자가 만드는 내용: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">A service account for ingesting DFP logs into <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">새 자격 증명. <p>참고: 이 경우 이 프로젝트에 고유한 고유한 이메일 주소가 필요하며 Google 스토리지 버킷에 대한 액세스 권한을 부여할 때 사용됩니다. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">개인 키 (JSON 기반 자격 증명) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>DFP 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3단계 </p> </td> 
   <td colname="col2"> <p>DFP 관리자가 API 액세스 권한을 서비스 계정에 부여합니다. 이 단계에서는 메타데이터를 사용하여 차원 (라인 항목, 주문, 크리에이티브) 를 구분할 수 있습니다. <p>참고: 2 단계에서 설정한 서비스 계정 전자 메일 액세스를 사용하여 API에 액세스할 수 있는 권한을 부여합니다. </p> </p> </td> 
   <td colname="col3"> <p>DFP 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4단계 </p> </td> 
   <td colname="col2"> <p>DFP 관리자가 Google 스토리지 버킷에 대한 액세스를 설정합니다. 기억: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Google 그룹을 통해 수행할 수 있습니다. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">서비스 계정에 할당된 고유한 이메일 주소를 저장소 버킷에 연결합니다. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>DFP 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5단계 </p> </td> 
   <td colname="col2"> <p>DFP 관리자는 DFP 네트워크 ID를 제공합니다. 이렇게 하면 API를 호출할 때 네트워크 ID를 전달할 수 있습니다. </p> </td> 
   <td colname="col3"> <p>DFP 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 6 </p> </td> 
   <td colname="col2"> <p>사전 이수 과정을 AAM 고객 지원 센터 (aamsupport@adobe.com) 로 컴파일하여 로그 처리 과정을 시작합니다. 다음 섹션의 템플릿을 사용하여 전자 메일을 작성합니다. </p> </td> 
   <td colname="col3"> <p>You, or <span class="keyword"> Audience Manager</span> Consulting on your behalf </p> </td> 
  </tr> 
 </tbody> 
</table>

## E-Mail Template {#email-template}

로그 통합 지원을 완료하려면 aamsupport@adobe.com로 이메일을 보내주십시오. [첨부된 이메일 템플릿을 사용하십시오](assets/enable_dfp_ingestion.txt).
