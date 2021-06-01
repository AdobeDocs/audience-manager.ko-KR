---
description: Audience Manager이 데이터 파트너에게 세그먼트 정보를 전송하는 경우 숫자 ID를 사용하여 이러한 개체를 식별합니다. 데이터 파트너로서, 이 정보를 고객과 공유(또는 직접 작업)할 때 실제 이름과 설명은 보고서, 대시보드 또는 기타 사용자 인터페이스(UI)에서 고객에게 더 나은 경험을 제공합니다. 데이터 파트너는 이 섹션에 설명된 수동 또는 자동화된 방법을 사용하여 고객에게 친숙한 이름을 제공할 수 있습니다.
seo-description: Audience Manager이 데이터 파트너에게 세그먼트 정보를 전송하는 경우 숫자 ID를 사용하여 이러한 개체를 식별합니다. 데이터 파트너로서, 이 정보를 고객과 공유(또는 직접 작업)할 때 실제 이름과 설명은 보고서, 대시보드 또는 기타 사용자 인터페이스(UI)에서 고객에게 더 나은 경험을 제공합니다. 데이터 파트너는 이 섹션에 설명된 수동 또는 자동화된 방법을 사용하여 고객에게 친숙한 이름을 제공할 수 있습니다.
seo-title: 세그먼트 메타데이터 검색
solution: Audience Manager
title: 세그먼트 메타데이터 검색
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: 세그먼트
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 2%

---

# 세그먼트 메타데이터 검색 {#retrieving-segment-metadata}

Audience Manager이 데이터 파트너에게 세그먼트 정보를 전송하는 경우 숫자 ID를 사용하여 이러한 개체를 식별합니다. 데이터 파트너로서, 이 정보를 고객과 공유(또는 직접 작업)할 때 실제 이름과 설명은 보고서, 대시보드 또는 기타 사용자 인터페이스([!DNL UI])에서 고객에게 더 나은 경험을 제공합니다. 데이터 파트너는 이 섹션에 설명된 수동 또는 자동화된 방법을 사용하여 고객에게 친숙한 이름을 제공할 수 있습니다.

## 수동 메서드 {#manual-method}

데이터 파트너인 경우 수동 프로세스를 통해 고객으로부터 대상 메타데이터를 가져오는 데 익숙할 것입니다. 여기에는 전자 메일에 첨부된 파일 또는 고객이 이 목적으로 빌드하고 유지 관리한 [!DNL UI]을 통해 해당 데이터를 추가할 수 있습니다. 이러한 프로세스는 작동하지만 종종 번거롭고 시간이 많이 소요되며 수동 데이터 입력 작업이 필요할 수 있습니다. 이러한 메서드는 통합을 빠르게 실행하고 실행하는 데 종종 사용되지만, 장기적으로 최상의 고객 경험을 제공하지는 않습니다. 또는 [!DNL Audience Manager] [!DNL API] 을 사용하여 세그먼트 메타데이터를 자동으로 가져올 수도 있습니다.

## 자동화된 메서드 {#automated-method}

[!DNL Audience Manager] 은 세그먼트 메타데이터를  [자동으로 검색할 수 ](../../api/rest-api-main/rest-api-main.md) 있는 REST API 세트를 제공합니다. [!DNL API] 을 사용하면 [!DNL Audience Manager] 데이터를 처리하고 새 세그먼트 ID를 찾을 때마다 예약된 간격으로 또는 자동으로 세그먼트 메타데이터를 검색하는 작업을 만들 수 있습니다. 자세한 내용은 아래 단계를 참조하십시오.

### 1단계:Audience Manager API 검토

[REST API 시작하기](../../api/rest-api-main/aam-api-getting-started.md) 섹션에는 일반 요구 사항, 인증, 사용 가능한 메서드 등에 대한 정보가 포함되어 있습니다. 이 곳은 이전에 [!DNL Audience Manager] [!DNL API]과 작업하지 않은 경우 시작하기 좋은 장소입니다.

### 2단계:OAuth2 액세스 자격 증명 요청

[!DNL API] 호출을 하려면 클라이언트 ID와 암호가 필요합니다. 통합 설정 프로세스 중에 통합 전문가에게 클라이언트 ID와 암호를 얻을 수 있습니다. [!DNL amsupport@adobe.com]에 [!UICONTROL Audience Manager Customer Care]에 이메일 요청을 보낼 수도 있습니다.

### 3단계:각 통합 고객으로부터 고객별 정보 수집

각 통합 고객에게 다음 사항을 요청합니다.

* 사용자 이름:특정 통합과 관련된 대상에 대한 읽기 전용 권한이 있는 제한된 사용자용입니다.
* 암호:사용자 암호입니다.
* 대상 ID:특정 서버 간 통합을 위해 생성된 대상에 연결된 ID(정수)입니다.

### 4단계:API 호출을 사용하여 세그먼트 메타데이터 검색

이전 단계를 완료한 후 `GET` 메서드를 사용하여 세그먼트 메타데이터를 검색할 수 있습니다. 샘플 요청 및 응답에 대해서는 [반환 대상 매핑](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings)을 참조하십시오. 이 호출은 [!DNL JSON] 개체에서 키-값 쌍으로 형식이 지정된 세그먼트 데이터를 반환합니다. 응답에서 반환되는 중요한 세그먼트 속성 중 일부는 다음 표에 나와 있습니다.

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
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 세그먼트 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>세그먼트 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>세그먼트를 간략하게 설명하는 일부 텍스트입니다. </p> </td> 
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
