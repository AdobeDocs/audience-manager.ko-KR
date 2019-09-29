---
description: 이 문서에서는 Audience Manager의 GDPR(General Data Protection Regulation)과 관련된 기술을 다루고 GDPR 요청을 Audience Manager에 제출하는 방법을 설명합니다.
seo-description: 이 문서에서는 Audience Manager의 GDPR(General Data Protection Regulation)과 관련된 기술을 다루고 GDPR 요청을 Audience Manager에 제출하는 방법을 설명합니다.
seo-title: Audience Manager에서의 GDPR
solution: Audience Manager
title: Audience Manager에서의 GDPR
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 98914987331ce31bc8d3e67647d5b8273b287d4c

---


# Audience Manager에서의 GDPR{#gdpr-in-audience-manager}

이 문서에서는 Audience Manager의 GDPR(General Data Protection Regulation)과 관련된 기술을 다루고 GDPR 요청을 Audience Manager에 제출하는 방법을 설명합니다.

## Experience Cloud의 GDPR 설명서 {#gdpr-documentation}

Adobe는 Audience Manager 세부 사항을 읽기 전에 아래에 연계된 유럽 GDPR(General Data Protection Regulation)에 대한 Experience Cloud 자료를 살펴보는 것이 좋습니다.

* [GDPR 및 비즈니스](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [GDPR 백서](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [GDPR 용어](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

아래 섹션에서는 Audience Manager에 대한 GDPR의 의미와 Audience Manager에 GDPR 요청을 제출하는 방법에 대해 설명합니다.

## GDPR 요청 유형 및 GDPR 요청 수행 방법 {#types-of-gdpr-requests}

Audience Manager 고객인 경우 GDPR 클라이언트 서비스 UI를 통해 또는 GDPR API를 **[통해 고객 데이터에 액세스하고 삭제할](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** 수 있는 개별 GDPR 요청을 제출할 **[수 있습니다](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)**. You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). 질문이 있는 경우 고객 지원 센터(gdprsupport@adobe.com)에 문의하십시오.

## 데이터 액세스 {#access-data}

Adobe는 접수 후 30일 이내에 GDPR 고객의 요청을 존중해야 한다는 귀하의 약속을 이해합니다. 이러한 이유로 Adobe는 데이터 액세스 요청을 가능한 한 빨리 처리하도록 시도합니다.

**요청**

GDPR 클라이언트 서비스 UI를 통해 **[또는 GDPR API를](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** 호출하여 데이터 액세스 요청을 기록할 **[수](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** 있습니다( `access` 작업 참조). 두 경우 모두 데이터 액세스 요청을 제출할 Audience Manager 식별자가 있는 JSON을 업로드해야 합니다. Experience Cloud GDPR 설명서에서 **[](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** 형식이 올바른 JSON이 어떻게 보이는지 살펴보십시오(특히 페이지에서 "POST 요청 형식" 검색). 또는 샘플 JSON을 **[다운로드할 수 있습니다](assets/access_request.json)**.

**응답**

데이터 요청에 대한 응답에는 해당 데이터 소스 이름과 함께 총 트레이트 및 세그먼트 수, 트레이트 유형, 트레이트 및 세그먼트 설명이 포함됩니다. 액세스 응답에는 퍼스트 파티 데이터와 함께 데이터 컨트롤러에 액세스할 수 있는 제2자 및 제3자 데이터도 포함됩니다. 크로스 장치 CRM ID 또는 고객 쿠키 ID와 [!UICONTROL declared IDs] 같은 것이 GDPR 요청으로 전송되면 Audience Manager는 모든 연결된 장치의 액세스 응답을 포함합니다(선언된 ID당 최대 100개의 장치).

**응답 상태**

응답에 Audience Manager의 오류가 있으면 응답에 오류 코드로 표시됩니다. 반환된 오류에 대한 자세한 정보를 찾을 수 있는 오류 코드 [](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)목록이 있습니다.

**응답 예**

샘플 액세스 응답은 아래 응답과 비슷합니다. 이 예에서는 데이터 주체의 ID가 쿠키 ID입니다. 이들은 여러 트레이트에 대해 자격을 갖추었으며 몇 개의 세그먼트에 속합니다. 쿠키 ID가 모바일 ID에 연결되어 있습니다. 이 예에는 휴대폰에 대한 메타데이터도 포함되어 있습니다.

```
{
  "id": "45338264191156397602180946733455975613",
  "namespace": {
    "id": 0,
    "integration code": "",
    "data provider name": "Demdex, Inc",
    "type": "COOKIE"
  },
  "warnings": [{
    "title": "Device Data",
    "description": "Contains data from all users of this device"
  }],
  "data": {
    "traits": [{
      "name": "Website Visitors",
      "type": "1st party",
      "description": "All Active Visitors",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Interested in Italian Holidays",
      "type": "1st party",
      "description": "Query string contains holidays/bella_italia",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Lifestyle>Recreational>Garden Party",
      "type": "3rd party",
      "description": "Survey respondents that have expressed an interest in hosting garden parties",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:36"
    }],
    "segments": [{
      "name": "test",
      "description": "Interested in Photography",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "false"
    }, {
      "name": "Traveler and Frequent Flier",
      "description": "",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }, {
      "name": "Interested in Sports",
      "description": "",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }]
  },
  "links": [{
    "id": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2",
    "namespace": {
      "id": 20914,
      "integration code": "DSID_20914",
      "data provider name": "Google",
      "type": "MOBILE"
    },
    "linking datetime": "2018-04-10 17:00:37"
  }],
  "deviceMetadata": {
    "hardware": "Mobile Phone",
    "manufacturer": "Samsung",
    "marketing name": "Galaxy S8 Plus",
    "model": "",
    "os name": "Android",
    "os version": "7.0",
    "vendor": "Samsung"
  }
}
```

아래 표에는 데이터 액세스 응답에서 반환된 모든 필드에 대한 설명이 위에 표시된 순서대로 나와 있습니다.

<table id="table_DF08231257F64588B98BD71A088C50DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>필드 </p> </th> 
   <th colname="col2" class="entry"> <p>설명 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ID</code> </p> </td> 
   <td colname="col2"> <p>다음에 오는 데이터의 사용자 ID입니다. GDPR 데이터 액세스 요청에서 제공한 ID 또는 제공된 선언된 ID 중 하나에 연결된 ID입니다. The ID types are described in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>데이터 소스라고도 합니다. See the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ID</code> </p> </td> 
   <td colname="col2"> <p>네임스페이스/데이터 소스의 ID입니다. See <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (IDs)</a> for all the accepted values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 통합 코드 </code> </p> </td> 
   <td colname="col2"> <p>통합 코드는 데이터 소스의 친숙한 이름이며 데이터 소스 ID를 사용하는 것보다 데이터 소스를 손쉽게 추적할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 데이터 공급자 이름 </code> </p> </td> 
   <td colname="col2"> <p>The name of the owner of the data source. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">For first party data, this is the customer's own company name. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">For second party data, this is the name of the partner company. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">For third party data, this is the name of the data partner. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>GDPR 데이터 액세스를 요청한 ID의 유형입니다. Accepted types are listed in the  Audience Manager Identifiers section.<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> warnings</code> </p> </td> 
   <td colname="col2"> <p>Warnings return further information related to the data access request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 제목 </code> </p> </td> 
   <td colname="col2"> <p>Brief information about the warning. </p> <p>The two warnings you may receive are: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Device Data </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Incomplete request </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 설명 </code> </p> </td> 
   <td colname="col2"> <p>A more detailed description of the warning you received: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">장치 데이터 - 이 장치의 모든 사용자의 데이터를 포함합니다. </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">요청이 완료되지 않음 - Audience Manager 데이터 검색이 완료되지 않았습니다. 일부 정보가 누락되었을 수 있습니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data </code> </p> </td> 
   <td colname="col2"> <p>이 사용자 ID와 연결된 트레이트 및 세그먼트. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>사용자 ID와 연결된 트레이트입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 이름</code> </p> </td> 
   <td colname="col2"> <p>트레이트의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>트레이트 유형입니다. 가능한 값은 다음과 같습니다. </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>자사</i> 트레이트를 위한 퍼스트 파티 </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>파트너에 속한 트레이트를 위한 제2자</i> . 자세한 내용은 <a href="../../overview/data-types-collected.md#second-party-data"> 제휴 데이터</a> 문서를 참조하십시오. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Audience</i> Marketplace를 통해 데이터 파트너의 트레이트를 타사에서 얻을 수 <a href="../../features/audience-marketplace/audience-marketplace.md"> 있습니다</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 설명</code> </p> </td> 
   <td colname="col2"> <p>트레이트의 목적이나 기능을 설명하는 데 도움이 되는 몇 마디. 선택 필드입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 데이터 내보내기 제어</code> </p> </td> 
   <td colname="col2"> <p>이 트레이트의 데이터 소스에 적용된 <a href="../../features/data-export-controls.md"> 데이터 내보내기 컨트롤입니다</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 데이터 공급자 이름</code> </p> </td> 
   <td colname="col2"> <p>이 트레이트가 속한 데이터 원본 소유자의 이름입니다. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">자사 데이터의 경우 고객의 회사 이름입니다. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">제휴 데이터의 경우 파트너 회사의 이름입니다. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">타사 데이터의 경우, 데이터 파트너의 이름입니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 마지막 실현</code> </p> </td> 
   <td colname="col2"> <p>데이터 주체가 이 트레이트에 대해 마지막으로 자격을 가졌던 정확한 시간입니다. 날짜 형식은 YYYY-MM-DD입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 세그먼트 </code> </p> </td> 
   <td colname="col2"> <p>이 사용자가 속한 세그먼트. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 이름</code> </p> </td> 
   <td colname="col2"> <p>세그먼트의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 설명</code> </p> </td> 
   <td colname="col2"> <p>이 세그먼트를 설명하는 데 도움이 되는 몇 가지 단어 선택 필드입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 데이터 내보내기 제어</code> </p> </td> 
   <td colname="col2"> <p>이 세그먼트의 데이터 소스에 적용된 <a href="../../features/data-export-controls.md"> 데이터 내보내기 제어</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 데이터 공급자 이름</code> </p> </td> 
   <td colname="col2"> <p>이 세그먼트가 속한 데이터 소스의 소유자의 이름입니다. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">자사 데이터의 경우 고객의 회사 이름입니다. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">제휴 데이터의 경우 파트너 회사의 이름입니다. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">타사 데이터의 경우, 데이터 파트너의 이름입니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>The exact time that the Data Subject last qualified for this segment. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> active</code> </p> </td> 
   <td colname="col2"> <p>Indicates whether the Data Subject is currently qualified for this segment. Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> links </code> </p> </td> 
   <td colname="col2"> <p>Additional ID that this ID has been linked to. Information is returned on: </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (data source) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">통합 코드 </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">데이터 공급자 이름 </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID 유형 </li> 
     </ul> </p> <p>All these fields are described in the first rows of this table. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> linking datetime</code> </p> </td> 
   <td colname="col2"> <p>The exact time that an ID sync event made the link between IDs. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> device metadata </code> </p> </td> 
   <td colname="col2"> <p>Information about the device. This information includes the fields below. 모든 장치 유형에 대해 일부 필드가 반환되는 것은 아닙니다. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>하드웨어 정보 </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>Device manufacturer </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>장치의 마케팅 이름 </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>장치 모델 </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>장치의 운영 체제(OS) 이름 </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>OS 버전 </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>디바이스 공급업체 </p> </li> 
     </ul> </p> <p> <p>참고:다음 중 하나를 제출하면 장치 메타데이터만 반환됩니다. 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">모바일 ID </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Audience Manager ID </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud ID </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 데이터 삭제 {#delete-data}

Adobe는 접수 후 30일 이내에 GDPR 고객의 요청을 존중해야 한다는 귀하의 약속을 이해합니다. 이러한 이유로, 가능한 한 빨리 데이터 삭제 요청을 처리하도록 시도합니다.

**요청**

GDPR 클라이언트 서비스 UI를 통해 **[또는 GDPR API를](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** 호출하여 데이터 삭제 요청을 기록할 **[수](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** 있습니다( `delete` 작업 참조). 두 경우 모두 데이터 액세스 요청을 제출할 Audience Manager 식별자가 있는 JSON을 업로드해야 합니다. Experience Cloud GDPR 설명서에서 [](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 형식이 올바른 JSON이 어떻게 보이는지 살펴보십시오(특히 페이지에서 "POST 요청 형식" 검색). 또는 샘플 JSON을 **[다운로드할 수 있습니다](assets/delete_request.json)**.

**응답**

데이터 삭제 요청에 대한 응답으로 각 Audience Manager 식별자와 연결된 트레이트 및 세그먼트를 삭제합니다. 또한 데이터 주체의 각 Audience Manager 식별자는 Audience Manager의 추가 데이터 수집에서 영구적으로 제외되며 해당 Id 매핑이 제거됩니다. 교차 장치 CRM Id 또는 고객 쿠키 ID와 같은 선언된 ID가 GDPR 요청으로 전송되면 Audience Manager는 연결된 모든 장치(선언된 ID당 최대 100개의 장치)에서 필요한 삭제 작업을 수행합니다.

## 옵트아웃 요청 {#opt-out-request}

옵트아웃 요청은 옵트아웃 관리에 대한 설명서를 [참조하십시오](../../overview/data-security-and-privacy/opt-out-management.md).

## Audience Manager 식별자(ID) {#aam-ids}

Adobe Audience Manager에 GDPR 요청을 제출할 때 아래에 나열된 식별자(ID) 중 하나를 포함해야 합니다. ID 형식에 대한 자세한 내용은 Audience Manager ID [색인에서 확인할 수 있습니다](../../reference/ids-in-aam.md).

### Adobe Audience Manager 고유 사용자 ID

**사용자 ID**:aam_uuid

**정의**:Adobe Audience Manager 고유 사용자 ID

**Namespace ID**: 0

>[!NOTE]
>
>CORE 네임스페이스를 사용할 수도 있습니다. 두 번째 JSON 예를 참조하십시오.

**Example in JSON:**

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

### Adobe Experience Cloud ID

**User ID: mid**

**Definition**: Adobe Experience Cloud ID, formerly known as Visitor ID or Marketing Cloud ID

**Namespace ID**: 4

>[!NOTE]
>
>You can also use the ECID namespace. See the second JSON example.

**Example in JSON:**

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

### Customer ID

**User ID: cid**

**Definition: Customer ID, such as a cookie you set for anonymous site visitors or a CRM ID from an offline system or a hashed username**

**Namespace ID: Customer-specific.** Please find it from your Audience Manager instance.

**Example in JSON:**

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

### 모바일 광고 ID

**User ID: d_cid**

**정의**:모바일 광고 ID.
>[!IMPORTANT]
>
> Mobile SDK를 사용 중인 경우, 전체 GDPR 액세스 및 삭제 응답을 위해 모바일 광고 ID와 함께 Experience Cloud ID(MID)를 전송해야 합니다.

**네임스페이스 ID**:

* IDFA: 20915
* GAID:2091년 4월

**JSON의 예**:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

### 통합 코드

**사용자 ID**: d_cid_ic

**정의**:데이터 소스에 대한 통합 코드입니다. Adobe Experience Cloud Privacy Core Service에 대한 API 요청에서 데이터 소스 ID/네임스페이스 ID 대신 사용할 수 있습니다.

**네임스페이스 ID**:해당 사항 없음

JSON의 예:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
