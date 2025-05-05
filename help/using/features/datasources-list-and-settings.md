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
source-wordcount: '1070'
ht-degree: 0%

---

# [!UICONTROL Data Sources] 목록 및 설정 {#data-sources-list-and-settings}

현재 구성된 [!UICONTROL data sources]의 목록을 보고 새 [!UICONTROL data sources]을(를) 추가하고 기존 [!UICONTROL data sources]을(를) 편집하세요.

[!DNL API] 메서드를 사용하여 [!UICONTROL data sources]을(를) 관리할 수도 있습니다. 자세한 내용은 [데이터 Source API 메서드](../api/rest-api-main/aam-api-data-sources.md)를 참조하십시오.

## [!UICONTROL Data Sources] 목록 보기 {#list-view}

[!UICONTROL Data Sources] 대시보드는 데이터 원본 관리를 위한 중앙 집중식 작업 영역입니다.

[!UICONTROL Data Sources] 대시보드(**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**)에는 다음과 같은 기능이 포함되어 있습니다.

* 각 데이터 원본의 설명, 상태 및 [!UICONTROL Inbound], [!UICONTROL Outbound], 둘 다 또는 [!UICONTROL Shared Provider]인지 여부를 포함하여 기존 [!UICONTROL data sources]을(를) 모두 봅니다.
* 이름으로 [!UICONTROL data sources]을(를) 검색합니다.
* [!UICONTROL data sources]을(를) 만들고, 편집하고, 삭제합니다.

## [!DNL Data Source] 설정 및 메뉴 옵션 {#settings-menu-options}

[!UICONTROL Data Source] 관리 인터페이스의 여러 섹션에 있는 설정이 [!DNL data source]을(를) 식별하고, 사용 또는 공유 방법을 결정하고, [!UICONTROL Onboarding Status Report]에 대한 오류 보고를 사용하도록 설정합니다.

## [!DNL Data Source] 세부 정보 {#details}

[!UICONTROL Data Source Details] 섹션에는 텍스트 필드 외에도 아래에 나열된 컨트롤과 옵션이 포함되어 있습니다.

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> 쿠키</span></b>: 장치를 식별하는 쿠키 ID입니다. 데이터 소스가 웹 브라우저이거나 익명 데이터 또는 한 사람과 연결할 수 없는 데이터로 작업할 때 이 옵션을 선택합니다. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> 장치 Advertising ID</span></b>: 모바일 장치 식별자입니다. 데이터 소스가 모바일 디바이스 또는 인터넷 사용 디바이스인 경우 이 옵션을 선택합니다. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> 교차 장치</span></b>: 고객이 제공한 인증된 ID입니다. 다음을 만들려는 경우 이 옵션을 선택합니다. 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">장치 간 데이터 원본이며 <span class="wintitle"> 프로필 병합 규칙을 만듭니다</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B"><span class="keyword"> Audience Manager</span>과(와) 통합된 타사 장치 그래프에서 제공하는 링크를 사용하는 데이터 원본입니다. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 정의</span></b> </p> </td> 
   <td colname="col2"> <p><b><span class="uicontrol"> ID 정의</span></b> 옵션은 데이터 원본과 <span class="keyword"> Audience Manager</span> UUID(사용자 ID) 및 <span class="keyword"> Audience Manager</span>과(와) 통합된 서드파티 장치 그래프에 의해 연결된 장치의 관계를 정의합니다. 옵션은 다음과 같습니다. </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol">명:</span></b> 한 사람을 정의하는 데 사용되는 ID입니다. 이 ID는 여러 <span class="keyword"> Audience Manager</span> ID에 매핑될 수 있습니다. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> 세대:</span></b> 사용자 그룹을 정의하는 데 사용되는 ID입니다. 이 ID는 여러 Audience Manager ID에 매핑될 수 있습니다. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[데이터 내보내기 제어](../features/data-export-controls.md)는 [!UICONTROL data source] 및 [!UICONTROL destination]에 적용할 수 있는 선택적 분류 규칙입니다. 이 옵션을 사용하면 해당 작업이 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우 [!UICONTROL destination]에 데이터를 보내지 못합니다. [!UICONTROL Data Export Controls]을(를) 사용하지 않는 경우 이 섹션을 건너뜁니다.

>[!IMPORTANT]
>
>[!UICONTROL destination]에 일치하는 내보내기 레이블을 설정하지 않으면 내보내기 제한이 작동하지 않습니다.

옵션은 다음과 같습니다.

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] 설정 {#data-source-settings}

[!UICONTROL Data Source Settings]에는 아래 나열된 컨트롤 및 옵션이 포함되어 있습니다. 이러한 설정 중 일부에는 데이터 소스를 수정하기 위해 선택할 수 있는 추가 하위 옵션과 메뉴 항목이 있습니다.

### [!UICONTROL Inbound Data Source] 설정

데이터 원본이 인바운드 데이터를 받도록 디자인된 경우 **[!UICONTROL Inbound]** 확인란을 선택하십시오. **[!UICONTROL Inbound]** 확인란을 선택하면 아래에 설명된 2개의 추가 컨트롤 그룹이 표시됩니다.

>[!NOTE]
>
>**[!UICONTROL Inbound]** 확인란은 아래에 설명된 [!UICONTROL data source] 컨트롤을 표시하거나 숨기는 용도로만 사용됩니다. **[!UICONTROL Inbound]** 옵션을 선택 취소해도 데이터 수집에는 아무런 영향을 주지 않습니다. 이 옵션을 선택하더라도 온보딩된 데이터가 처리됩니다.

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
   <td colname="col2"> <p><b><span class="uicontrol"> Inbound</span></b> 옵션에는 ID 유형이 필요합니다. 옵션은 다음과 같습니다. </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> 고객 ID</span></b>: 고객 ID로 인바운드 데이터를 식별합니다. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>: <span class="keyword"> Audience Manager</span> ID로 인바운드 데이터를 식별합니다. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: <span class="keyword"> Experience Cloud</span> ID로 인바운드 데이터를 식별합니다. <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=ko" format="https" scope="external"> 쿠키와 Experience Cloud ID</a>을(를) 참조하십시오. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 파일 형식 문제 해결</span></b> </p> </td> 
   <td colname="col2"> <p>인바운드 파일 처리 문제를 해결해야 하는 경우 <b><span class="uicontrol"> 파일 오류 샘플링 사용</span></b>을 선택합니다. 이 기능은 파일 형식 및 구문 오류를 보여 주는 오류 샘플 보고서를 생성합니다. </p> <p>오류 보고 및 오류 샘플링에 대한 자세한 내용은 <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> 온보딩 상태 보고서: 정보</a>을(를) 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 기타 [!UICONTROL Data Source] 설정

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 설정 </th> 
   <th colname="col2" class="entry"> 다음과 같은 경우 선택 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 아웃바운드</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 소스는 대상으로 데이터를 전송합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 공유 활성화됨</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 소스는 다른 파트너와 공유할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 인증된 프로필로 사용</span></b> </p> </td> 
   <td colname="col2"> <p>교차 장치 데이터 소스에는 인증된 ID가 포함되어 있습니다. 인증 이벤트(예: 사용자가 온사이트, 인앱 등에 로그인) 중에 인증된 ID가 수집되고 <span class="keyword"> Audience Manager</span> ID에 동기화됩니다. 인증된 ID는 이 ID를 저장하는 다른 소스의 데이터를 온보딩하는 데 사용할 수 있습니다. <span class="wintitle"> 프로필 링크</span>에서 여러 장치 ID를 연결하는 데 사용할 수도 있습니다. </p> <p>이 옵션은 별칭을 사용하여 데이터 소스의 이름을 바꿀 수 있는 텍스트 필드를 노출합니다. 별칭을 사용하는 경우, 이 새 이름은 데이터 원본 이름을 무시하고 <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule">에서 프로필 병합 규칙을 만들 때 <span class="wintitle"> 인증된 프로필 옵션</span>에 나타납니다</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 장치 그래프로 사용</span></b> </p> </td> 
   <td colname="col2"> <p>다른 <span class="keyword"> Audience Manager</span> 고객에게 제공할 수 있는 장치 그래프로 데이터 원본을 만듭니다. 이 옵션을 선택하기 전에 <span class="keyword"> Audience Manager</span> 컨설턴트에게 이 <span class="wintitle"> 데이터 Source</span>을(를) 공유할 고객을 알려주십시오. 컨설턴트는 내부 프로세스를 통해 해당 회사를 프로비저닝해야 합니다. </p> <p>이 옵션은 별칭을 사용하여 데이터 소스의 이름을 바꿀 수 있는 텍스트 필드를 노출합니다. 별칭을 사용하는 경우 이 새 이름은 데이터 원본 이름을 재정의하며 <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule">에서 프로필 병합 규칙을 만들 때 <span class="wintitle"> 장치 옵션</span>에 나타납니다</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 연결된 방문자 또는 장치 ID를 특정 Audience Manager 고객과 공유</span></b> </p> </td> 
   <td colname="col2"> <p>교차 장치 데이터 소스에는 장치 그래프의 ID가 포함되어 있습니다. Device Graph는 클러스터에 하나 이상의 <span class="keyword"> Audience Manager</span> ID에 매핑되는 ID의 컬렉션입니다. 이 클러스터는 일반적으로 1인 이상의 가구 그룹을 나타냅니다. "데이터 공급자"로 나열된 계정에만 사용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Audience Manager 플랫폼에서 연결된 방문자 또는 장치 ID를 공유합니다</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 원본에 다른 <span class="keyword"> Experience Cloud</span> 솔루션에서 공유할 수 있는 방문자 또는 장치 ID가 있습니다. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> 비활성 고객 ID에 대한 <b><span class="uicontrol"> 데이터 유지</span></b> </p> </td> 
   <td colname="col2"> <p>비활성 고객 ID에 대한 데이터 보존 기간을 설정할 수 있습니다. Audience Manager이 고객 ID를 Audience Manager 플랫폼에서 마지막으로 본 후 데이터베이스에 유지하는 기간을 결정합니다.</p> <p>기본값은 24개월(720일)입니다. 설정할 수 있는 최소값은 1개월이고 최대값은 5년입니다. 모든 달은 30일로 계산됩니다.</p> <p>Audience Manager은 비활성 고객 ID에 대해 설정한 데이터 유지에 따라 일주일에 한 번 비활성 고객 ID를 삭제하는 프로세스를 실행합니다.</p> <p>Audience Manager은 비활성 고객 ID에 대해 설정한 데이터 유지에 따라 일주일에 한 번 비활성 고객 ID를 삭제하는 프로세스를 실행합니다.</p> <p><b>참고</b>: 이 컨트롤은 장치 간 데이터 원본에만 사용할 수 있습니다. <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> 교차 장치 데이터 만들기 Source </a>도 참조하세요.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 고유 트레이트 통합 코드</span></b> </p> </td> 
   <td colname="col2"> <p>동일한 데이터 소스의 두 트레이트에 동일한 통합 코드가 없도록 하려는 경우 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 고유한 세그먼트 통합 코드</span></b> </p> </td> 
   <td colname="col2"> <p>동일한 데이터 소스의 두 세그먼트에 동일한 통합 코드가 없도록 하려는 경우 </p> </td> 
  </tr>
 </tbody>
</table>
