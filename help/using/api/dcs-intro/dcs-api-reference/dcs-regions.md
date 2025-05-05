---
description: DCS를 호출하려면 지역 DCS 서버 호스트 이름이 필요합니다. DCS가 사이트 방문자와 지리적으로 가까운 데이터 센터에 정보를 저장하기 때문입니다. 쿼리를 잘못된 DCS로 보내면 쿼리가 작동하지만, 이러한 호출은 비효율적이고 응답을 지연시킬 수 있습니다. DCS 요청을 만들려면 지역 ID를 해당 지역 호스트 이름과 일치시키고 적절한 호스트 이름으로 쿼리를 만듭니다.
seo-description: The regional DCS server host name is required to make calls to the DCS. This is because the DCS stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong DCS, but these calls are inefficient and can delay the response. To make a DCS request, match the region ID to its corresponding regional host name and form your query with the proper host name.
seo-title: DCS Region IDs, Locations, and Host Names
solution: Audience Manager
title: DCS 지역 ID, 위치 및 호스트 이름
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---

# DCS 지역 ID, 위치 및 호스트 이름 {#dcs-region-ids-locations-and-host-names}

[!DNL DCS]을(를) 호출하려면 지역 [!DNL DCS] 서버 호스트 이름이 필요합니다. 이는 [!DNL DCS]이(가) 사이트 방문자와 지리적으로 가까운 데이터 센터에 정보를 저장하기 때문입니다. 쿼리를 잘못된 [!DNL DCS] (으)로 보내면 쿼리가 작동하지만 이러한 호출은 비효율적이며 응답을 지연시킬 수 있습니다. [!DNL DCS] 요청을 수행하려면 지역 ID를 해당 지역 호스트 이름과 일치시키고 올바른 호스트 이름으로 쿼리를 만듭니다.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS 지역 ID(dcs_region) </th> 
   <th colname="col2" class="entry"> 지역(및 위치) </th> 
   <th colname="col3" class="entry"> 호스트 이름 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>동남아시아(싱가포르) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 4 </p> </td> 
   <td colname="col2"> <p>남아메리카(상파울루, 브라질) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>유럽(더블린, 아일랜드) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>미국 동부(버지니아, 미국) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>남태평양/오세아니아(시드니, 오스트레일리아) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>미국 서부(오레곤, 미국) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>아시아(도쿄, 일본) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID 12 </p> </td> 
   <td colname="col2"> <p>인도 </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL API] 메서드를 사용하여 사용 가능한 [!DNL DCS] 영역의 목록을 가져올 수도 있습니다. [DCS 지역 API 메서드](../../../api/rest-api-main/aam-api-dcs-regions.md)를 참조하십시오.
