---
description: 현재 구성된 데이터 소스 목록을 보고 새 데이터 소스를 추가하고 기존 소스를 편집합니다.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: 데이터 소스 목록 및 설정
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---

# [!UICONTROL Data Sources] 목록 및 설정 {#data-sources-list-and-settings}

현재 구성된 목록 보기 [!UICONTROL data sources], 새로 추가 [!UICONTROL data sources], 기존 , 편집 [!UICONTROL data sources].

관리할 수도 있습니다 [!UICONTROL data sources] 사용 [!DNL API] 메서드를 사용합니다. 자세한 내용은 [데이터 소스 API 메서드](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] 목록 보기 {#list-view}

다음 [!UICONTROL Data Sources] 대시보드는 데이터 소스를 관리하는 중앙 집중식 작업 공간입니다.

다음 [!UICONTROL Data Sources] 대시보드 (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**)에는 다음과 같은 데 도움이 되는 기능 및 도구가 포함되어 있습니다.

* 기존 항목 모두 보기 [!UICONTROL data sources]각 데이터 소스의 설명, 상태 및 해당 여부 등 [!UICONTROL Inbound], [!UICONTROL Outbound], 둘 다 또는 [!UICONTROL Shared Provider].
* 검색 대상 [!UICONTROL data sources] 이름별로
* 만들기, 편집 및 삭제 [!UICONTROL data sources].

## [!DNL Data Source] 설정 및 메뉴 옵션 {#settings-menu-options}

의 다른 섹션에 있는 설정 [!UICONTROL Data Source] 관리 인터페이스 식별 [!DNL data source]를 사용하여 사용 방법 또는 공유 방법을 확인하고, [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] 세부 사항 {#details}

텍스트 필드 외에 [!UICONTROL Data Source Details] 섹션에는 아래에 나열된 컨트롤과 옵션이 포함되어 있습니다.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 설정 </th> 
   <th colname="col2" class="entry"> 메뉴 옵션 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 유형</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> 쿠키</span></b>: 장치를 식별하는 쿠키 ID입니다. 데이터 소스가 웹 브라우저이거나 단일 사용자와 연결할 수 없는 익명 데이터 또는 데이터로 작업하는 경우 이 옵션을 선택합니다. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> 장치 광고 ID</span></b>: 모바일 장치 식별자입니다. 데이터 소스가 모바일 장치 또는 인터넷 지원 장치인 경우 이 옵션을 선택합니다. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> 교차 장치</span></b>: 고객이 제공한 인증된 ID입니다. 만들려는 경우 다음 옵션을 선택합니다. 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">교차 장치 데이터 소스 및 <span class="wintitle"> 프로필 병합 규칙</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">와 통합된 타사 장치 그래프에서 제공하는 링크를 사용하는 데이터 소스입니다 <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 정의</span></b> </p> </td> 
   <td colname="col2"> <p>다음 <b><span class="uicontrol"> ID 정의</span></b> 옵션은 데이터 소스가 <span class="keyword"> Audience Manager</span> 와 통합된 타사 장치 그래프에 의해 연결된 사용자 ID(UUID) 및 관련 장치 <span class="keyword"> Audience Manager</span>. 옵션은 다음과 같습니다. </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> 개인:</span></b> 단일 개인을 정의하는 데 사용되는 ID입니다. 이 ID를 여러 ID에 매핑할 수 있습니다 <span class="keyword"> Audience Manager</span> ID. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> 가족:</span></b> 사람 그룹을 정의하는 데 사용되는 ID입니다. 이 ID를 여러 Audience Manager ID에 매핑할 수 있습니다. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[데이터 내보내기 제어](../features/data-export-controls.md) 는 선택적인 분류 규칙으로서, [!UICONTROL data source] 및 [!UICONTROL destination]. 이로 인해 데이터를 [!UICONTROL destination] 해당 작업이 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우. 사용하지 않는 경우 이 섹션을 건너뜁니다 [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>에 일치하는 내보내기 레이블을 설정하지 않으면 내보내기 제한이 작동하지 않습니다 [!UICONTROL destination].

옵션은 다음과 같습니다.

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] 설정 {#data-source-settings}

다음 [!UICONTROL Data Source Settings] 아래에 나열된 컨트롤과 옵션을 포함합니다. 이러한 설정 중 일부에는 데이터 소스를 수정하기 위해 선택할 수 있는 추가 하위 옵션 및 메뉴 항목이 있습니다.

### [!UICONTROL Inbound Data Source] 설정

을(를) 선택합니다 **[!UICONTROL Inbound]** 데이터 소스가 인바운드 데이터를 수신하도록 디자인되면 확인란을 선택합니다. 선택 **[!UICONTROL Inbound]** 이 확인란은 아래에 설명된 2개의 추가 컨트롤 그룹을 표시합니다.

>[!NOTE]
>
>다음 **[!UICONTROL Inbound]** 확인란을 선택하면 [!UICONTROL data source] 아래에 설명된 컨트롤입니다. 확인 취소 **[!UICONTROL Inbound]** 옵션은 데이터 처리에 어떤 식으로든 영향을 주지 않습니다. 이 옵션을 선택하면 온보딩된 데이터가 처리됩니다.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 설정 </th> 
   <th colname="col2" class="entry"> 메뉴 옵션 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 유형</span></b> </p> </td> 
   <td colname="col2"> <p>다음 <b><span class="uicontrol"> 인바운드</span></b> 옵션에는 ID 유형이 필요합니다. 옵션은 다음과 같습니다. </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> 고객 ID</span></b>: 고객 ID로 인바운드 데이터를 식별합니다. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>: 를 사용하여 인바운드 데이터 식별 <span class="keyword"> Audience Manager</span> ID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: 를 사용하여 인바운드 데이터 식별 <span class="keyword"> Experience Cloud</span> ID. 자세한 내용은 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> 쿠키 및 Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 파일 형식 문제 해결</span></b> </p> </td> 
   <td colname="col2"> <p>선택 <b><span class="uicontrol"> 파일 오류 샘플링 활성화</span></b> 인바운드 파일 처리 문제를 해결해야 하는 경우. 이 기능은 파일 형식 및 구문 오류를 보여주는 오류 샘플 보고서를 생성합니다. </p> <p>자세한 내용은 <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> 온보딩 상태 보고서: 정보</a> 오류 보고 및 오류 샘플링에 대한 자세한 내용은 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 기타 [!UICONTROL Data Source] 설정

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 설정 </th> 
   <th colname="col2" class="entry"> 선택 시기 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 아웃바운드</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 소스가 데이터를 대상에 전송합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 공유 사용</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 소스는 다른 파트너와 공유할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 인증된 프로필로 사용</span></b> </p> </td> 
   <td colname="col2"> <p>교차 장치 데이터 소스에 인증된 ID가 포함되어 있습니다. 인증된 ID가 수집되어 <span class="keyword"> Audience Manager</span> 인증 이벤트 중 ID(예: 사용자가 온사이트, 인앱 등)입니다. 인증됨 ID를 사용하여 이 ID를 저장하는 다른 소스의 데이터를 온보드 데이터로 사용할 수 있습니다. 또한 여러 장치 ID를 <span class="wintitle"> 프로필 링크</span>. </p> <p>이 옵션은 데이터 소스의 이름을 별칭으로 바꿀 수 있는 텍스트 필드를 표시합니다. 별칭을 사용하는 경우 이 새 이름은 데이터 소스 이름을 재정의하고 <span class="wintitle"> 인증된 프로필 옵션</span> 언제 <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 프로필 병합 규칙 만들기</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 장치 그래프로 사용</span></b> </p> </td> 
   <td colname="col2"> <p>다른 사용자에게 제공할 수 있는 장치 그래프로 데이터 소스를 만듭니다 <span class="keyword"> Audience Manager</span> 고객. 이 옵션을 선택하기 전에 <span class="keyword"> Audience Manager</span> 이 고객이 누구인지를 설명합니다. <span class="wintitle"> 데이터 소스</span> 와 공유해야 합니다. 컨설턴트는 내부 프로세스를 통해 그러한 회사를 제공해야 합니다. </p> <p>이 옵션은 데이터 소스의 이름을 별칭으로 바꿀 수 있는 텍스트 필드를 표시합니다. 별칭을 사용하는 경우 이 새 이름은 데이터 소스 이름을 재정의하고 <span class="wintitle"> 장치 옵션</span> 언제 <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 프로필 병합 규칙 만들기</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 특정 Audience Manager 고객과 연결된 방문자 또는 장치 ID 공유</span></b> </p> </td> 
   <td colname="col2"> <p>교차 장치 데이터 소스에는 장치 그래프의 ID가 포함되어 있습니다. 장치 그래프는 하나 이상에 매핑되는 ID의 컬렉션입니다 <span class="keyword"> Audience Manager</span> 클러스터에 ID를 추가합니다. 이 클러스터는 일반적으로 개인 또는 보다 큰 가족 그룹을 나타냅니다. "데이터 공급자"로 나열된 계정에만 사용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Audience Manager 플랫폼에서 연결된 방문자 또는 장치 ID 공유</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 소스에는 다른 간에 공유할 수 있는 방문자 또는 장치 ID가 포함되어 있습니다 <span class="keyword"> Experience Cloud</span> 솔루션. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 비활성 고객 ID에 대한 데이터 유지</span></b> </p> </td> 
   <td colname="col2"> <p>비활성 고객 ID에 대해 데이터 유지 기간을 설정할 수 있습니다. 이는 Audience Manager이 고객 ID를 Audience Manager 플랫폼에서 마지막으로 본 후 데이터베이스에 유지하는 시간을 결정합니다.</p> <p>기본값은 24개월(720일)입니다. 설정할 수 있는 최소값은 1개월이고 최대값은 5년입니다. 모든 개월 수를 30일로 계산합니다.</p> <p>Audience Manager은 비활성 고객 ID에 대해 설정한 데이터 유지에 따라 일주일에 한 번 비활성 고객 ID를 삭제하는 프로세스를 실행합니다.</p> <p>Audience Manager은 비활성 고객 ID에 대해 설정한 데이터 유지에 따라 일주일에 한 번 비활성 고객 ID를 삭제하는 프로세스를 실행합니다.</p> <p><b>참고</b>: 이 컨트롤은 장치 간 데이터 소스에만 사용할 수 있습니다. 또한, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> 교차 장치 데이터 소스 만들기 </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 고유한 트레이트 통합 코드</span></b> </p> </td> 
   <td colname="col2"> <p>동일한 데이터 소스의 두 트레이트에 동일한 통합 코드가 없다는 것을 적용하려고 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 고유한 세그먼트 통합 코드</span></b> </p> </td> 
   <td colname="col2"> <p>동일한 데이터 소스의 두 세그먼트에 동일한 통합 코드가 없도록 하려고 합니다. </p> </td> 
  </tr>
 </tbody>
</table>
