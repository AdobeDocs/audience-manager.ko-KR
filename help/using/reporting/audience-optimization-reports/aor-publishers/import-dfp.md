---
description: Audience Manager가 게시자에 대한 대상 최적화를 활성화할 수 있으려면 먼저 이 문서에 설명된 모든 전제 조건이 충족되는지 확인해야 합니다. 모든 전제 조건을 확인한 후 고객 지원에 문의하십시오.
seo-description: Audience Manager가 게시자에 대한 대상 최적화를 활성화할 수 있으려면 먼저 이 문서에 설명된 모든 전제 조건이 충족되는지 확인해야 합니다. 모든 전제 조건을 확인한 후 고객 지원에 문의하십시오.
seo-title: DFP 데이터 파일을 Audience Manager에 가져오기
solution: Audience Manager
title: DFP 데이터 파일을 Audience Manager에 가져오기
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DFP 데이터 파일을 Audience Manager에 가져오기{#import-dfp-data-files-into-audience-manager}

Audience Manager가 게시자에 대한 대상 최적화를 활성화할 수 있으려면 먼저 이 문서에 설명된 모든 전제 조건이 충족되는지 확인해야 합니다. 모든 전제 조건을 확인한 후 고객 지원에 문의하십시오.

## DFP 로그 섭취를 위한 사전 요구 사항 {#prereqs-dfp-ingestion}

이 섹션에 설명된 프로세스는 로그 통합 활성화를 위한 전제 조건으로 이동하기 *전에* 완료되어야 합니다.

DFP( [!DNL DoubleClick For Publishers]) 로그 파일을 [!DNL Audience Manager]사용하려면 먼저 [광고 태그 호출에서 Audience Manager UUID(](../../../reference/ids-in-aam.md) Unique User ID)를 설정해야 합니다. 이렇게 하면 ID가 DFP 로그에 포함되며 DFP와 DFP 사이의 ID와 일치시킬 수 [!DNL Audience Manager]있습니다. 퍼스트 파티 쿠키에 UUID [!DNL Audience Manager] 를 설정하려면 [!UICONTROL DIL] 코드 [!UICONTROL Audience Management Module] [!DNL Audience Manager] 또는 를 사용합니다.

다음은 Adobe 설명서에 설명된 대로 광고 태그 [!DNL Audience Manager] 호출에서 ID를 설정하는 방법입니다.

* [Google 게시자 태그(GPT) 사용](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
* [쿠키 대상 사용](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)

ID를 직접 [!DNL Audience Manager] 설정하고 모든 것이 제대로 작동하는지 확인하기 위해 컨설팅 서비스를 [!DNL Audience Manager] 사용할 수 있습니다. 다음과 같은 경우 ID를 [!DNL Audience Manager] 올바르게 설정했습니다.

* `'aamid'` 는 식별자로 사용되는 키입니다.
* Audience Manager의 ID 인덱스에 설명된 대로 사용자 ID 값의 [!DNL Audience Manager] 형식이 UUID [로 올바르게 지정됩니다](../../../reference/ids-in-aam.md).
* DFP 로그의 [!DNL Audience Manager] 정의된 필드(예: CustomTargeting)에 UUID를 포함했습니다.

## 로그 통합 활성화를 위한 전제 조건 {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>2단계로 이동하기 전에 Audience Manager UUID <span class="keyword"> 를</span> 설정하는 데 필요한 단계가 완료되었는지 확인합니다. </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> 고객 지원 센터 또는 컨설팅 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2단계 </p> </td> 
   <td colname="col2"> <p>DFP 관리자가 만드는 작업: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">DFP 로그를 Audience Manager에 인제스트하기 위한 서비스 <span class="keyword"> 계정</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">새 자격 증명. <p>참고: 이 작업에는 이 프로젝트와 관련된 고유한 전자 메일 주소가 필요할 수 있으며 Google 저장소 버킷에 대한 액세스 권한을 프로비저닝할 때 사용됩니다. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">개인 키(JSON 기반 자격 증명) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>DFP 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3단계 </p> </td> 
   <td colname="col2"> <p>DFP 관리자는 서비스 계정에 대한 액세스 권한을 API에 부여합니다. 이 단계에서는 메타데이터에 액세스하여 차원(라인 항목, 주문, 크리에이티브)을 지정할 수 있습니다. <p>참고: 2단계에서 설정한 서비스 계정 전자 메일 액세스를 사용하여 API에 액세스할 수 있는 권한을 부여합니다. </p> </p> </td> 
   <td colname="col3"> <p>DFP 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4단계 </p> </td> 
   <td colname="col2"> <p>DFP 관리자가 Google 저장소 버킷에 대한 액세스를 설정합니다. 기억하십시오. </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">이 작업은 Google 그룹을 통해 수행할 수 있습니다. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">서비스 계정에 할당된 고유한 이메일 주소를 저장소 버킷에 연결합니다. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>DFP 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5단계 </p> </td> 
   <td colname="col2"> <p>DFP 관리자는 DFP 네트워크 ID를 제공합니다. 따라서 API를 호출할 때 네트워크 ID를 전달할 수 있습니다. </p> </td> 
   <td colname="col3"> <p>DFP 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 6 </p> </td> 
   <td colname="col2"> <p>AAM 고객 지원 센터(aamsupport@adobe.com)에 전자 메일에 사전 요구 사항을 컴파일하여 로그 통합 프로세스를 시작합니다. 다음 섹션의 템플릿을 사용하여 전자 메일 초안을 작성합니다. </p> </td> 
   <td colname="col3"> <p>귀하 또는 Audience <span class="keyword"> Manager</span> Consulting을 대신하여 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 이메일 템플릿 {#email-template}

로그 통합 활성화를 마무리하려면 aamsupport@adobe.com으로 이메일을 보내주십시오. 첨부한 [이메일 템플릿을](assets/enable_dfp_ingestion.txt)사용하십시오.
