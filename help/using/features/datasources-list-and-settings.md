---
description: 현재 구성된 데이터 소스 목록을 보고 새 데이터 소스를 추가하고 기존 소스를 편집합니다.
seo-description: 현재 구성된 데이터 소스 목록을 보고 새 데이터 소스를 추가하고 기존 소스를 편집합니다.
seo-title: 데이터 소스 목록 및 설정
solution: Audience Manager
title: 데이터 소스 목록 및 설정
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# 데이터 소스 목록 및 설정 {#data-sources-list-and-settings}

현재 구성된 데이터 소스 목록을 보고 새 데이터 소스를 추가하고 기존 소스를 편집합니다.

<!-- c_datasources.xml -->

메서드를 사용하여 데이터 소스를 관리할 수도 [!DNL API] 있습니다. 자세한 내용은 데이터 소스 [API 메서드를 참조하십시오](../api/rest-api-main/aam-api-data-sources.md).

## 데이터 소스 목록 보기 {#list-view}

대시보드는 데이터 소스를 관리하기 위한 중앙 관리 작업 공간입니다. [!UICONTROL Data Sources]

<!-- c_datasources_list.xml -->

대시보드( [!UICONTROL Data Sources] &gt;**[!UICONTROL Audience Data]** **[!UICONTROL Data Sources]**)에는 다음과 같은 유용한 기능과 도구가 포함되어 있습니다.

* 각 데이터 소스의 설명, 상태 및 해당 데이터 소스, [!UICONTROL Inbound][!UICONTROL Outbound]둘 다 또는 [!UICONTROL Shared Provider]해당 여부를 포함하여 모든 기존 데이터 소스를 볼 수 있습니다.
* 이름별로 데이터 소스를 검색합니다.
* 데이터 소스 만들기, 편집 및 삭제

## 데이터 소스 설정 및 메뉴 옵션 {#settings-menu-options}

관리 인터페이스의 서로 다른 섹션에 있는 설정은 데이터 소스를 식별하고, 데이터 소스를 어떻게 사용 또는 공유할지 결정하고, 오류 보고를 활성화할 수 [!UICONTROL Data Source] [!UICONTROL Onboarding Status Report]있습니다.

## 데이터 소스 세부 사항 {#details}

<!-- datasource-settings-definitions.xml -->

텍스트 필드 외에도, [!UICONTROL Data Source Details] 섹션에는 아래에 나열된 컨트롤과 옵션이 포함되어 있습니다.

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> 쿠키</span></b>:장치를 식별하는 쿠키 ID입니다. 데이터 소스가 웹 브라우저이거나 단일 사용자와 연결할 수 없는 익명 데이터 또는 데이터로 작업할 때 이 옵션을 선택합니다. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> 장치 광고 ID</span></b>:모바일 장치 식별자입니다. 데이터 소스가 모바일 장치 또는 인터넷 사용 장치인 경우 이 옵션을 선택합니다. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> 크로스 디바이스</span></b>:고객이 제공한 인증된 ID. 만들 때 이 옵션을 선택합니다. 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">크로스 디바이스 데이터 소스 및 프로필 병합 <span class="wintitle"> 규칙을 만듭니다</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Audience Manager와 통합된 Adobe Experience Cloud <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Device Co-op</a> 또는 다른 타사 디바이스 그래프에서 제공하는 링크를 사용하는 데이터 <span class="keyword"> 소스입니다</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 정의</span></b> </p> </td> 
   <td colname="col2"> <p>ID <b><span class="uicontrol"> 정의</span></b> 옵션은 데이터 소스가 Audience Manager <span class="keyword"> 사용자 ID(UUID)</span> 및 Adobe Experience <span class="keyword"> Cloud Device Co-op</span> 또는 Audience Manager와 통합된 다른 타사 <span class="keyword"> 장치 그래프로 연결된 관련 장치와 Audience Manager</span>사용자 ID와의 관계를 정의합니다. 옵션은 다음과 같습니다. </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"></span></b> 사람:단일 개인을 정의하는 데 사용되는 ID입니다. 이 ID는 여러 Audience Manager ID에 매핑할 <span class="keyword"> 수</span> 있습니다. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"></span></b> 일반:사람 그룹을 정의하는 데 사용되는 ID입니다. 이 ID는 여러 Audience Manager ID에 매핑할 수 있습니다. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 데이터 내보내기 제어 {#export-controls}

[데이터 내보내기](../features/data-export-controls.md) 컨트롤은 데이터 소스 및 대상에 적용할 수 있는 선택적 분류 규칙입니다. 이러한 동작을 통해 데이터 개인 정보 보호 또는 사용 계약을 위반할 경우 데이터가 대상으로 전송되지 않도록 합니다. 사용하지 않는 경우 이 섹션을 건너뜁니다 [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>대상에 일치하는 내보내기 레이블을 설정하지 않으면 내보내기 제한이 작동하지 않습니다.

옵션은 다음과 같습니다.

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

에는 [!UICONTROL Data Source Settings] 아래 나열된 컨트롤과 옵션이 포함되어 있습니다. 이러한 설정 중 일부에는 데이터 소스를 수정하도록 선택할 수 있는 추가 하위 옵션과 메뉴 항목이 있습니다.

### 인바운드 데이터 소스 설정

데이터 소스가 인바운드 데이터를 수신하도록 설계된 경우 **[!UICONTROL Inbound]** 확인란을 선택합니다. 확인란을 선택하면 아래에 설명된 두 개의 추가 컨트롤 그룹이 표시됩니다. **[!UICONTROL Inbound]**

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
   <td colname="col2"> <p>인바운드 <b><span class="uicontrol"> 옵션에는</span></b> ID 유형이 필요합니다. 옵션은 다음과 같습니다. </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> 고객 ID</span></b>:고객 ID로 인바운드 데이터를 식별합니다. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>:Audience Manager ID를 사용하여 인바운드 <span class="keyword"> 데이터를</span> 식별합니다. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>:Experience Cloud ID를 사용하여 인바운드 <span class="keyword"> 데이터를</span> 식별합니다. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 파일 형식 문제 해결</span></b> </p> </td> 
   <td colname="col2"> <p>인바운드 <b><span class="uicontrol"> 파일 처리 문제를 해결해야 할 때 파일 오류 샘플링</span></b> 활성화를 선택합니다. 이 기능은 파일 형식 및 구문 오류를 보여주는 오류 샘플 보고서를 생성합니다. </p> <p>온보딩 <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> 상태 보고서를 참조하십시오.오류</a> 보고 및 오류 샘플링에 대한 정보를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 기타 데이터 소스 설정

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
   <td colname="col2"> <p>데이터 소스는 데이터를 대상으로 전송합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 공유 사용</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 소스는 다른 파트너와 공유할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 인증된 프로필로 사용</span></b> </p> </td> 
   <td colname="col2"> <p>크로스 장치 데이터 소스에 인증된 ID가 포함되어 있습니다. 인증된 ID는 인증 이벤트 <span class="keyword"> 동안</span> 수집되어 Audience Manager ID에 동기화됩니다(예: 사용자가 온사이트, 인앱 등). 인증된 ID를 사용하여 이 ID를 저장하는 다른 소스의 온보드 데이터를 사용할 수 있습니다. 또한 프로필 링크에서 여러 장치 ID를 연결하는 데 사용할 수 <span class="wintitle"> 있습니다</span>. </p> <p>이 옵션은 데이터 소스의 이름을 별칭으로 바꿀 수 있는 텍스트 필드를 표시합니다. 별칭을 사용하는 경우 이 새 이름은 데이터 소스 이름을 대체하며 프로필 병합 규칙을 <span class="wintitle"> 만들 때</span> 인증된 <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 프로필 옵션에</a>나타납니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 장치 그래프로 사용</span></b> </p> </td> 
   <td colname="col2"> <p>다른 Audience Manager 고객에게 제공할 수 있는 데이터 소스를 장치 그래프로 <span class="keyword"> 만듭니다</span> . 이 옵션을 선택하기 전에 Audience Manager <span class="keyword"> 컨설턴트에게</span> 이 데이터 소스를 <span class="wintitle"> 공유해야</span> 하는 고객에게 알려주십시오. 컨설턴트가 내부 절차를 통해 해당 회사들을 프로비저닝해야 할 것입니다. </p> <p>이 옵션은 데이터 소스의 이름을 별칭으로 바꿀 수 있는 텍스트 필드를 표시합니다. 별칭을 사용하는 경우 이 새 이름은 데이터 소스 이름을 대체하며 프로필 병합 규칙을 <span class="wintitle"> 만들 때 장치</span> 옵션에 <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 나타납니다</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 특정 Audience Manager 고객과 연결된 방문자 또는 장치 ID 공유</span></b> </p> </td> 
   <td colname="col2"> <p>장치 간 데이터 소스에는 장치 그래프의 ID가 포함되어 있습니다. 장치 그래프는 하나 이상의 Audience Manager ID를 클러스터에 매핑하는 <span class="keyword"> ID의</span> 모음입니다. 이 클러스터는 일반적으로 개인 또는 보다 큰 가족 그룹을 나타냅니다. "데이터 공급자"로 나열된 계정에서만 사용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Audience Manager 플랫폼에서 연결된 방문자 또는 장치 ID 공유</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 소스에는 다른 Experience Cloud 솔루션에서 공유할 수 있는 방문자 또는 장치 ID가 <span class="keyword"> 포함되어</span> 있습니다. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 비활성 고객 ID에 대한 데이터 유지</span></b> </p> </td> 
   <td colname="col2"> <p>비활성 고객 ID에 대한 데이터 보존 기간을 설정할 수 있습니다. Audience Manager 플랫폼에서 고객 ID가 마지막으로 표시된 후 Audience Manager가 데이터베이스에 고객 ID를 유지하는 시간을 결정합니다.</p> <p>기본값은 24개월(720일)입니다. 설정할 수 있는 최소 값은 1개월이고 최대 값은 5년입니다. 모든 달은 30일로 계산합니다.</p> <p>Audience Manager는 비활성 고객 ID에 대해 설정한 데이터 유지에 따라 일주일에 한 번 비활성 고객 ID를 삭제하는 프로세스를 실행합니다.</p> <p>Audience Manager는 비활성 고객 ID에 대해 설정한 데이터 유지에 따라 일주일에 한 번 비활성 고객 ID를 삭제하는 프로세스를 실행합니다.</p> <p><b>참고</b>:이 컨트롤은 장치 간 데이터 소스에서만 사용할 수 있습니다. 장치 간 <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> 데이터 소스 만들기를 참조하십시오 </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 고유 트레이트 통합 코드</span></b> </p> </td> 
   <td colname="col2"> <p>동일한 데이터 소스의 두 트레이트에 동일한 통합 코드가 없도록 설정하려고 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 고유 세그먼트 통합 코드</span></b> </p> </td> 
   <td colname="col2"> <p>동일한 데이터 소스의 두 세그먼트에 동일한 통합 코드가 없도록 설정하려고 합니다. </p> </td> 
  </tr>
 </tbody>
</table>
