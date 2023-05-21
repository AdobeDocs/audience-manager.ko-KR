---
description: Audience Manager이 데이터 파트너에게 세그먼트 정보를 보내면 숫자 ID로 이러한 개체를 식별합니다. 데이터 파트너로서, 이 정보를 고객과 공유(또는 직접 작업)하면 실제 이름과 설명이 보고서, 대시보드 또는 기타 UI(사용자 인터페이스)에서 고객에게 더 나은 경험을 제공합니다. 데이터 파트너는 이 섹션에 설명된 수동 또는 자동화된 방법을 통해 고객에게 친숙한 이름을 제공할 수 있습니다.
seo-description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-title: Retrieving Segment Metadata
solution: Audience Manager
title: 세그먼트 메타데이터 검색
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 1%

---

# 세그먼트 메타데이터 검색 {#retrieving-segment-metadata}

Audience Manager이 데이터 파트너에게 세그먼트 정보를 보내면 숫자 ID로 이러한 개체를 식별합니다. 데이터 파트너로서 이 정보를 고객과 공유(또는 직접 작업)하면 실제 이름과 설명이 보고서, 대시보드 또는 기타 사용자 인터페이스에서 고객에게 더 나은 경험을 제공합니다([!DNL UI]). 데이터 파트너는 이 섹션에 설명된 수동 또는 자동화된 방법을 통해 고객에게 친숙한 이름을 제공할 수 있습니다.

## 수동 방법 {#manual-method}

데이터 파트너는 수작업 프로세스를 통해 고객으로부터 대상 메타데이터를 가져오는 데 익숙할 것입니다. 이메일에 첨부된 파일이나 를 통해 해당 데이터를 추가한 고객이 첨부할 수도 있습니다. [!DNL UI] 이 목적을 위해 빌드하고 유지 관리했습니다. 이러한 프로세스는 작동하지만 번거롭고 시간이 많이 소요되며 수동으로 데이터를 입력해야 할 수 있습니다. 이러한 방법은 통합이 빠르게 실행되고 준비되는 데 도움이 되지만 장기적인 관점에서 최상의 고객 경험을 제공하지는 않습니다. 또는 다음을 사용할 수 있습니다 [!DNL Audience Manager] [!DNL API] 세그먼트 메타데이터를 자동으로 가져옵니다.

## 자동화된 메서드 {#automated-method}

[!DNL Audience Manager] 다음을 제공합니다. [REST API](../../api/rest-api-main/rest-api-main.md) 이를 통해 세그먼트 메타데이터를 자동으로 검색할 수 있습니다. 포함 [!DNL API], 예약된 간격으로 또는 처리할 때마다 자동으로 세그먼트 메타데이터를 검색하는 작업을 만들 수 있습니다 [!DNL Audience Manager] 데이터를 확인하고 새 세그먼트 ID를 찾습니다. 자세한 내용은 아래 단계를 참조하십시오.

### 1단계: Audience Manager API 검토

다음 [REST API 시작](../../api/rest-api-main/aam-api-getting-started.md) 섹션에는 일반 요구 사항, 인증, 사용 가능한 방법 등에 대한 정보가 포함되어 있습니다. 이 작업을 수행하지 않았다면 시작하기 좋은 위치입니다. [!DNL Audience Manager] [!DNL API] 전.

### 2단계: OAuth2 액세스 자격 증명 요청

클라이언트 ID와 암호를 입력해야 합니다. [!DNL API] 호출. 통합 설정 프로세스 중에 통합 전문가로부터 클라이언트 ID와 암호를 받을 수 있습니다. 다음으로 이메일 요청을 보낼 수도 있습니다. [!UICONTROL Audience Manager Customer Care] 위치: [!DNL amsupport@adobe.com].

### 3단계: 각 통합 고객으로부터 고객별 정보 수집

각 통합 고객에게 다음 사항을 요청하십시오.

* 사용자 이름: 특정 통합과 연관된 대상에 대해 읽기 전용 권한이 있는 제한된 사용자를 위한 것입니다.
* 암호: 사용자 암호입니다.
* 대상 ID: 특정 서버 간 통합을 위해 생성된 대상과 연결된 ID(정수)입니다.

### 4단계: API 호출로 세그먼트 메타데이터 검색

이전 단계를 완료한 후 `GET` 세그먼트 메타데이터를 검색하는 방법입니다. 샘플 요청 및 응답은 다음을 참조하십시오. [대상 매핑 반환](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). 이 호출은 의 키-값 쌍으로 형식이 지정된 세그먼트 데이터를 반환합니다. [!DNL JSON] 개체. 응답에서 반환되는 몇 가지 중요한 세그먼트 속성은 다음 표에 나열되어 있습니다.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingId</code> </p> </td> 
   <td colname="col2"> <p>다음 <span class="keyword"> Audience Manager</span> 세그먼트 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>세그먼트 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>세그먼트를 간단히 설명하는 일부 텍스트입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>세그먼트 매핑의 현재 상태입니다. 반환된 상태 옵션은 다음과 같습니다. </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
