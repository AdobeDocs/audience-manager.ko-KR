---
description: DCS를 호출하려면 지역 DCS 서버 호스트 이름이 필요합니다. 이것은 DCS가 사이트 방문자와 지리적으로 가까운 데이터 센터에 정보를 저장하기 때문입니다. 쿼리를 잘못된 DCS로 보내면 쿼리가 작동하지만 이러한 호출은 비효율적이며 응답이 지연될 수 있습니다. DCS 요청을 하려면 지역 ID를 해당 지역 호스트 이름과 일치시키고 올바른 호스트 이름으로 쿼리를 형성합니다.
seo-description: DCS를 호출하려면 지역 DCS 서버 호스트 이름이 필요합니다. 이것은 DCS가 사이트 방문자와 지리적으로 가까운 데이터 센터에 정보를 저장하기 때문입니다. 쿼리를 잘못된 DCS로 보내면 쿼리가 작동하지만 이러한 호출은 비효율적이며 응답이 지연될 수 있습니다. DCS 요청을 하려면 지역 ID를 해당 지역 호스트 이름과 일치시키고 올바른 호스트 이름으로 쿼리를 형성합니다.
seo-title: DCS 지역 ID, 위치 및 호스트 이름
solution: Audience Manager
title: DCS 지역 ID, 위치 및 호스트 이름
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 9%

---


# DCS 지역 ID, 위치 및 호스트 이름 {#dcs-region-ids-locations-and-host-names}

[!DNL DCS]을(를) 호출하려면 지역 [!DNL DCS] 서버 호스트 이름이 필요합니다. 이것은 [!DNL DCS]이 사이트 방문자와 지리적으로 가까운 데이터 센터에 정보를 저장하기 때문입니다. 쿼리를 잘못된 [!DNL DCS]으로 보낸 경우 사용할 수 있지만 이러한 호출은 비효율적이며 응답이 지연될 수 있습니다. [!DNL DCS] 요청을 하려면 지역 ID를 해당 지역 호스트 이름과 일치시키고 올바른 호스트 이름으로 쿼리를 형성하십시오.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS 영역 ID(dcs_region) </th> 
   <th colname="col2" class="entry"> 지역(및 위치) </th> 
   <th colname="col3" class="entry"> 호스트 이름 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>동남아시아(싱가포르) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>남미(상파울루, 브라질) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>유럽(더블린, 아일랜드) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>미국 동부(버지니아, 미국) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>남태평양/오세아니아(오스트레일리아 시드니) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>미국 서부(미국 오리건 주) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>아시아(일본 도쿄) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>인도 </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL API] 메서드를 사용하여 사용 가능한 [!DNL DCS] 지역 목록을 가져올 수도 있습니다. [DCS 영역 API 메서드](../../../api/rest-api-main/aam-api-dcs-regions.md)를 참조하십시오.