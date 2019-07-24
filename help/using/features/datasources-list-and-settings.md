---
description: 현재 구성된 데이터 소스 목록을 보고, 새 Data Sources를 추가하고, 기존 소스를 편집합니다.
seo-description: 현재 구성된 데이터 소스 목록을 보고, 새 Data Sources를 추가하고, 기존 소스를 편집합니다.
seo-title: Data Sources 목록 및 설정
solution: Audience Manager
title: Data Sources 목록 및 설정
uuid: 280 a 6 ACD-FEF 0-4737-A 96 D -9 E 22 FBC 8 BFAF
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Data Sources List and Settings {#data-sources-list-and-settings}

현재 구성된 데이터 소스 목록을 보고, 새 Data Sources를 추가하고, 기존 소스를 편집합니다.

<!-- c_datasources.xml -->

You can also manage data sources using [!DNL API] methods. For more information, see [Data Source API Methods](../api/rest-api-main/aam-api-data-sources.md).

## Data Sources List View {#list-view}

[!UICONTROL Data Sources] 대시보드는 데이터 소스를 관리하기 위한 중앙 작업 공간입니다.

<!-- c_datasources_list.xml -->

[!UICONTROL Data Sources] 대시보드&#x200B;**[!UICONTROL Audience Data]** (&gt; **[!UICONTROL Data Sources]**) 에는 다음과 같은 기능이 포함되어 있습니다.

* See all your existing data sources, including each data source's description, status, and whether it is [!UICONTROL Inbound], [!UICONTROL Outbound], both, or a [!UICONTROL Shared Provider].
* 이름별로 Data Sources를 검색합니다.
* 데이터 소스를 만들고, 편집하고, 삭제합니다.

## Data Source Settings and Menu Options {#settings-menu-options}

[!UICONTROL Data Source] 관리 인터페이스의 다른 섹션에 있는 설정은 데이터 소스를 식별하고, 사용 또는 공유 방식을 결정하고, 에 대한 오류 보고를 활성화할 수 있도록 해줍니다 [!UICONTROL Onboarding Status Report].

## Data Source Details {#details}

<!-- datasource-settings-definitions.xml -->

In addition to text fields, the [!UICONTROL Data Source Details] section contains the controls and options listed below.

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> 쿠키</span></b>: 장치를 식별하는 쿠키 ID. 데이터 소스가 웹 브라우저인 경우 또는 한 사람과 연결할 수 없는 익명의 데이터 또는 데이터를 사용하여 작업하는 경우 이 옵션을 선택합니다. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> 장치 광고 ID</span></b>: 모바일 장치 식별자입니다. 데이터 소스가 모바일 장치 또는 인터넷 지원 장치인 경우 이 옵션을 선택합니다. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> 크로스 디바이스</span></b>: 고객이 제공한 인증 ID 입니다. 만들려는 경우 이 옵션을 선택합니다. 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">A cross-device data source and build a <span class="wintitle"> Profile Merge Rule</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">A data source that uses links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 정의</span></b> </p> </td> 
   <td colname="col2"> <p><b><span class="uicontrol"> ID 정의</span></b> 옵션은 데이터 소스와의 관계 (UUID) <span class="keyword"> 와</span> <span class="keyword"> Adobe Experience Cloud Device Co-op</span> 또는 Audience Manager와 <span class="keyword"> 통합된 다른 타사 장치 그래프로 연결된 관련 장치 간의 관계를 정의합니다</span>. 옵션은 다음과 같습니다. </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> 사람:</span></b> 단일 사람을 정의하는 데 사용되는 ID 입니다. This ID can be mapped to multiple <span class="keyword"> Audience Manager</span> IDs. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> 제품군:</span></b> 사용자 그룹을 정의하는 데 사용되는 ID 입니다. 이 ID는 여러 Audience Manager ID에 매핑할 수 있습니다. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 데이터 내보내기 제어 {#export-controls}

[데이터 내보내기 컨트롤은](../features/data-export-controls.md) 데이터 소스 및 대상에 적용할 수 있는 선택적 분류 규칙입니다. 이러한 행위는 해당 행동이 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우에 사용자가 대상에 데이터를 전송하지 못하도록 합니다. Skip this section if you do not use [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>대상에 일치하는 내보내기 레이블을 설정하지 않으면 내보내기 제한 사항이 작동하지 않습니다.

옵션은 다음과 같습니다.

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

The [!UICONTROL Data Source Settings] contains the controls and options listed below. 이러한 설정 중에는 데이터 소스를 수정하기 위해 선택할 수 있는 추가 하위 옵션과 메뉴 항목이 있습니다.

### 인바운드 데이터 소스 설정

Select the **[!UICONTROL Inbound]** check box when your data source is designed to receive inbound data. **[!UICONTROL Inbound]** 확인란을 선택하면 아래 설명된 2 개의 추가 컨트롤 그룹이 표시됩니다.

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
   <td colname="col2"> <p><b><span class="uicontrol"> 인바운드</span></b> 옵션을 사용하려면 ID 유형이 필요합니다. 옵션은 다음과 같습니다. </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> 고객 ID</span></b>: 고객 ID로 인바운드 데이터를 식별합니다. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>: <span class="keyword"> Audience Manager</span> ID를 사용하여 인바운드 데이터를 식별합니다. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: <span class="keyword"> Experience Cloud</span> ID를 사용하여 인바운드 데이터를 식별합니다. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> 쿠키 및 Experience Cloud ID를 참조하십시오</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 파일 포맷 문제 해결</span></b> </p> </td> 
   <td colname="col2"> <p>Select <b><span class="uicontrol"> Enable file error sampling</span></b> when you need to troubleshoot problems with inbound file processing. 이 기능은 파일 형식 및 구문 오류를 보여주는 오류 샘플 보고서를 생성합니다. </p> <p><a href="../reporting/onboarding-status-report.md#onboarding-status-about"> 온보딩 상태 보고서를 참조하십시오. 오류</a> 보고 및 오류 샘플링에 대한 정보를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 기타 데이터 소스 설정

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 설정 </th> 
   <th colname="col2" class="entry"> 선택할 시기 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 아웃바운드</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 소스는 대상에 데이터를 보냅니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 공유 활성화됨</span></b> </p> </td> 
   <td colname="col2"> <p>데이터 소스는 다른 파트너와 공유할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 인증된 프로필로 사용</span></b> </p> </td> 
   <td colname="col2"> <p>크로스 장치 데이터 소스에 인증된 ID가 포함되어 있습니다. An Authenticated ID is collected and synced to an <span class="keyword"> Audience Manager</span> ID during an authentication event (e.g, a user logs in on-site, in-app, etc.). 인증된 ID는 이 ID를 저장하는 다른 소스의 보드 데이터에 사용할 수 있습니다. It can also be used to link multiple device IDs in <span class="wintitle"> Profile Link</span>. </p> <p>이 옵션은 별칭으로 데이터 소스의 이름을 변경할 수 있는 텍스트 필드를 표시합니다. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Authenticated Profile Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 장치 그래프로 사용</span></b> </p> </td> 
   <td colname="col2"> <p>Creates a data source as a device graph which you can provide to other <span class="keyword"> Audience Manager</span> customers. Before you select this option, tell with your <span class="keyword"> Audience Manager</span> consultant which customers this <span class="wintitle"> Data Source</span> should be shared with. 컨설턴트는 내부 프로세스를 통해 해당 회사를 프로비저닝해야 합니다. </p> <p>이 옵션은 별칭으로 데이터 소스의 이름을 변경할 수 있는 텍스트 필드를 표시합니다. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Device Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 특정 Audience Manager 고객과 연관된 방문자 또는 장치 ID 공유</span></b> </p> </td> 
   <td colname="col2"> <p>크로스 디바이스 데이터 소스에는 장치 그래프의 ID가 포함됩니다. A device graph is a collection of IDs which map to one or more <span class="keyword"> Audience Manager</span> IDs to a cluster. 이 클러스터는 일반적으로 개인 또는 더 큰 가족 그룹을 나타냅니다. " 데이터 공급자 "로 나열된 계정에만 사용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Audience Manager 플랫폼에서 연관된 방문자 또는 장치 ID 공유</span></b> </p> </td> 
   <td colname="col2"> <p>Your data source contains visitor or device IDs that can be shared across other <span class="keyword"> Experience Cloud</span> solutions. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 비활성 고객 ID에 대한 데이터 유지</span></b> </p> </td> 
   <td colname="col2"> <p>비활성 고객 ID의 데이터 유지 기간을 설정할 수 있습니다. Audience Manager 플랫폼에서 마지막으로 본 후 Audience Manager가 고객 ID를 데이터베이스에 유지하는 기간을 결정합니다.</p> <p>기본값은 24 개월 (720 일) 입니다. 설정할 수 있는 최소 값은 1 개월이며 최대 값은 5 년입니다. Adobe는 모든 달을 30 일로 계산합니다.</p> <p>Audience Manager는 비활성 고객 ID에 대해 설정한 데이터 보존에 따라 일주일에 한 번 비활성 고객 ID를 삭제하는 프로세스를 실행합니다.</p> <p>Audience Manager는 비활성 고객 ID에 대해 설정한 데이터 보존에 따라 일주일에 한 번 비활성 고객 ID를 삭제하는 프로세스를 실행합니다.</p> <p><b></b>참고: 이 컨트롤은 장치 간 Data Sources 에서만 사용할 수 있습니다. See also, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 고유한 특성 통합 코드</span></b> </p> </td> 
   <td colname="col2"> <p>동일한 데이터 소스의 두 특성에 동일한 통합 코드가 없는 경우를 적용하려고 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 고유한 세그먼트 통합 코드</span></b> </p> </td> 
   <td colname="col2"> <p>동일한 데이터 소스의 두 세그먼트에 동일한 통합 코드가 없는 경우를 적용하려고 합니다. </p> </td> 
  </tr>
 </tbody>
</table>
