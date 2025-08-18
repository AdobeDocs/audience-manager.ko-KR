---
description: Audience Manager가 게시자에 대한 대상 최적화를 활성화할 수 있으려면 먼저 이 문서에 설명된 모든 전제 조건이 충족되는지 확인해야 합니다. 모든 전제 조건을 확인한 후 고객 지원에 문의하십시오.
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: Google Ad Manager 데이터 파일을 Audience Manager으로 가져오기
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 14%

---

# Google Ad Manager(이전의 DFP) 데이터 파일을 Audience Manager에 가져오기{#import-dfp-data-files-into-audience-manager}

Audience Manager가 게시자에 대한 대상 최적화를 활성화할 수 있으려면 먼저 이 문서에 설명된 모든 전제 조건이 충족되는지 확인해야 합니다. 모든 전제 조건을 확인한 후 고객 지원에 문의하십시오.

## Google Ad Manager 로그 수집을 위한 사전 요구 사항 {#prereqs-dfp-ingestion}

로그 수집 활성화를 위한 필수 조건으로 전환하려면 이 섹션에서 설명하는 프로세스를 *이전*&#x200B;에 완료해야 합니다.

[!DNL Google Ad Manager]에서 [!DNL Audience Manager]&#x200B;(이전 Google DFP) 로그 파일을 사용하려면 먼저 광고 태그 호출에서 [Audience Manager UUID(고유 사용자 ID)](../../../reference/ids-in-aam.md)을(를) 설정해야 합니다. 이렇게 하면 ID가 [!DNL Google Ad Manager] 로그에 포함되며 [!DNL Google Ad Manager]과(와) [!DNL Audience Manager] 사이의 ID를 일치시킬 수 있습니다. [!DNL Audience Manager] [!UICONTROL DIL] 코드 또는 [!UICONTROL Audience Management Module]을(를) 사용하여 자사 쿠키에 [!DNL Audience Manager] UUID를 설정합니다.

설명서에 설명된 대로 광고 태그 호출에서 [!DNL Audience Manager] ID를 설정하는 방법은 다음과 같습니다.

* [GPT(Google 게시자 태그)를 통해](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [쿠키 대상을 통해](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

[!DNL Audience Manager] ID를 직접 설정해야 하며, [!DNL Audience Manager] 컨설팅과 함께 모든 것이 작동하는지 확인할 수 있습니다. 다음과 같은 경우 [!DNL Audience Manager] ID를 올바르게 설정했습니다.

* `'aamid'`은(는) 식별자로 사용되는 키입니다.
* [!DNL Audience Manager]Audience Manager의 ID 색인[에 설명된 대로 사용자 ID 값의 형식이 ](../../../reference/ids-in-aam.md) UUID로 올바르게 지정되었습니다.
* [!DNL Audience Manager] 로그의 정의된 필드에 [!DNL Google Ad Manager] UUID를 포함했습니다(예: CustomTargeting).

## 로그 수집 활성화를 위한 사전 요구 사항 {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> UUID를 설정하는 데 필요한 단계(위에 설명)가 2단계로 이동하기 전에 완료되었는지 확인합니다 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> 고객 지원 센터 또는 컨설팅 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2단계 </p> </td> 
   <td colname="col2"> <p>Google Ad Manager 관리자는 다음을 생성합니다. </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Google Ad Manager를 수집하기 위한 서비스 계정은 <span class="keyword"> Audience Manager</span>에 로그인합니다. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">새 자격 증명. <p>참고: 이 작업에는 이 프로젝트와 관련된 고유한 이메일 주소가 필요할 수 있으며 Google 스토리지 버킷에 대한 액세스 권한을 프로비저닝할 때 사용됩니다. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">개인 키(JSON 기반 자격 증명) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Google 광고 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3단계 </p> </td> 
   <td colname="col2"> <p>Google Ad Manager 관리자는 서비스 계정에 대한 API 액세스 권한을 부여합니다. 이 단계에서는 메타데이터에 액세스하여 차원(라인 항목, 주문, 크리에이티브)을 설명할 수 있습니다. <p>참고: 2단계에서 설정한 서비스 계정 전자 메일 액세스를 사용하여 API에 대한 액세스 권한을 부여합니다. </p> </p> </td> 
   <td colname="col3"> <p>Google 광고 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4단계 </p> </td> 
   <td colname="col2"> <p>Google Ad Manager 관리자가 Google 스토리지 버킷에 대한 액세스를 설정합니다. 기억하십시오. </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">이 작업은 Google 그룹을 통해 수행할 수 있습니다. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">서비스 계정에 할당된 고유한 이메일 주소를 저장소 버킷에 연결합니다. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Google 광고 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5단계 </p> </td> 
   <td colname="col2"> <p>Google Ad Manager 관리자가 Google Ad Manager 네트워크 ID를 제공합니다. 이렇게 하면 API를 호출할 때 네트워크 ID를 전달할 수 있습니다. </p> </td> 
   <td colname="col3"> <p>Google 광고 관리자 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Step 6 </p> </td> 
   <td colname="col2"> <p>로그 수집 프로세스를 시작하려면 필수 구성 요소를 컴파일하고 자세한 <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html?lang=ko">여기</a>의 지침에 따라 지원 티켓을 여십시오. </p> </td> 
   <td colname="col3"> <p>귀하 또는 귀하를 대신하여 <span class="keyword"> Audience Manager</span> 컨설팅 </p> </td> 
  </tr> 
 </tbody> 
</table>
