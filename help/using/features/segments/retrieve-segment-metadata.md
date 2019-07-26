---
description: Audience Manager가 데이터 파트너에게 세그먼트 정보를 보내면 숫자 ID로 이러한 개체를 식별합니다. 데이터 파트너로서, 고객과 이 정보를 공유하거나 직접 작업할 때 실제 이름과 설명은 보고서, 대시보드 또는 기타 유저 인터페이스 (UI) 의 고객에게 더 나은 경험을 제공합니다. 데이터 파트너는 이 섹션에 설명된 수동 방식 또는 자동화된 방법을 통해 고객에게 이러한 친근한 이름을 제공할 수 있습니다.
seo-description: Audience Manager가 데이터 파트너에게 세그먼트 정보를 보내면 숫자 ID로 이러한 개체를 식별합니다. 데이터 파트너로서, 고객과 이 정보를 공유하거나 직접 작업할 때 실제 이름과 설명은 보고서, 대시보드 또는 기타 유저 인터페이스 (UI) 의 고객에게 더 나은 경험을 제공합니다. 데이터 파트너는 이 섹션에 설명된 수동 방식 또는 자동화된 방법을 통해 고객에게 이러한 친근한 이름을 제공할 수 있습니다.
seo-title: 세그먼트 메타데이터 검색
solution: Audience Manager
title: 세그먼트 메타데이터 검색
uuid: 719 E 2 C 41-8788-4 E 8 A -967 A-E 367421 F 9 F 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Retrieving Segment Metadata {#retrieving-segment-metadata}

Audience Manager가 데이터 파트너에게 세그먼트 정보를 보내면 숫자 ID로 이러한 개체를 식별합니다. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces ([!DNL UI]). 데이터 파트너는 이 섹션에 설명된 수동 방식 또는 자동화된 방법을 통해 고객에게 이러한 친근한 이름을 제공할 수 있습니다.

## Manual method {#manual-method}

데이터 파트너는 수동 프로세스를 통해 고객의 메타데이터를 가져오는 데 익숙해질 수 있습니다. This could include files attached to emails or from customers adding that data through a [!DNL UI] you've built and maintained for this purpose. 이러한 프로세스는 작동하지만 번거롭고 시간이 많이 소요되며 수동으로 데이터를 입력해야 할 수도 있습니다. 이러한 메서드는 통합을 빠르게 시작하고 실행하는 데 도움이 되지만, 장기적으로 최상의 고객 경험을 제공하지 않습니다. As an alternative, you can use the [!DNL Audience Manager] [!DNL API] to get segment metadata automatically.

## Automated method {#automated-method}

[!DNL Audience Manager] 세그먼트 메타데이터를 자동으로 검색할 수 있는 [REST API](../../api/rest-api-main/rest-api-main.md) 세트를 제공합니다. With the [!DNL API], you can create jobs that retrieve segment metadata at scheduled intervals or automatically, whenever you process [!DNL Audience Manager] data and find a new segment ID. 자세한 내용은 아래 단계를 참조하십시오.

### 1 단계: Audience Manager API 검토

The [Getting Started with REST APIs](../../api/rest-api-main/aam-api-getting-started.md) section contains information about general requirements, authentication, available methods, etc. This is a good place to begin if you haven't worked with the [!DNL Audience Manager] [!DNL API] before.

### 2 단계: OAuth 2 액세스 자격 증명 요청

You need a client ID and secret to make [!DNL API] calls. 통합 설정 프로세스 중에 통합 전문가로부터 클라이언트 ID와 암호를 얻을 수 있습니다. You can also send an email request to [!UICONTROL Audience Manager Customer Care] at [!DNL amsupport@adobe.com].

### 3 단계: 각 통합 고객의 고객별 정보 수집

통합된 각 고객에게 다음 사항을 요청합니다.

* 사용자 이름: 특정 통합과 연관된 대상에 대한 읽기 전용 권한을 가진 제한된 사용자를 위한 것입니다.
* 암호: 사용자 암호입니다.
* 대상 ID: 특정 서버-서버 간 통합에 대해 생성된 대상과 연결된 ID (정수) 입니다.

### 4 단계: API 호출을 사용하여 세그먼트 메타데이터 검색

After completing the previous steps, you can use a `GET` method to retrieve segment metadata. For a sample request and response, see [Return Destination Mappings](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). This call returns segment data formatted as key-value pairs in a [!DNL JSON] object. 응답에서 반환된 중요한 세그먼트 속성 중 일부가 다음 표에 나열되어 있습니다.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Destinationmappingid</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 세그먼트 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementname</code> </p> </td> 
   <td colname="col2"> <p>세그먼트 이름. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementdescription</code> </p> </td> 
   <td colname="col2"> <p>세그먼트를 간략하게 설명하는 일부 텍스트입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementstatus</code> </p> </td> 
   <td colname="col2"> <p>세그먼트 매핑의 현재 상태입니다. 반환된 상태 옵션은 다음과 같습니다. </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> 활성</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> 비활성</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> 삭제됨</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>