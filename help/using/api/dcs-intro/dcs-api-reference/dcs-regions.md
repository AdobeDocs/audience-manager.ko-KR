---
description: DCS를 호출하려면 지역 DCS 서버 호스트 이름이 필요합니다. DCS는 지리적으로 사이트 방문자와 가까운 데이터 센터에 정보를 저장하기 때문입니다. 잘못된 DCS로 전송하는 경우 쿼리가 작동하지만 이러한 호출은 비효율적이며 응답을 지연시킬 수 있습니다. DCS 요청을 수행하려면 해당 지역 ID와 해당 지역 호스트 이름을 일치시키고 쿼리를 적절한 호스트 이름으로 구성합니다.
seo-description: DCS를 호출하려면 지역 DCS 서버 호스트 이름이 필요합니다. DCS는 지리적으로 사이트 방문자와 가까운 데이터 센터에 정보를 저장하기 때문입니다. 잘못된 DCS로 전송하는 경우 쿼리가 작동하지만 이러한 호출은 비효율적이며 응답을 지연시킬 수 있습니다. DCS 요청을 수행하려면 해당 지역 ID와 해당 지역 호스트 이름을 일치시키고 쿼리를 적절한 호스트 이름으로 구성합니다.
seo-title: DCS 영역 ID, 위치 및 호스트 이름
solution: Audience Manager
title: DCS 영역 ID, 위치 및 호스트 이름
uuid: AD 150 FFE -4583-472 B-AC 8 B-FB 900 A 7966 E 4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS Region IDs, Locations, and Host Names {#dcs-region-ids-locations-and-host-names}

The regional [!UICONTROL DCS] server host name is required to make calls to the [!UICONTROL DCS]. This is because the [!UICONTROL DCS] stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong [!UICONTROL DCS], but these calls are inefficient and can delay the response. [!UICONTROL DCS] 요청을 하려면 해당 지역 ID와 해당 지역 호스트 이름을 일치시키고 적절한 호스트 이름으로 쿼리를 구성합니다.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS 영역 ID (dcs_ region) </th> 
   <th colname="col2" class="entry"> 지역 (및 위치) </th> 
   <th colname="col3" class="entry"> 호스트 이름 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>동남 아시아 (싱가포르) </p> </td> 
   <td colname="col3"> <p> <code> apse. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>남아메리카 (상파울루, 브라질) </p> </td> 
   <td colname="col3"> <p> <code> sae. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>유럽 (더블린, 아일랜드) </p> </td> 
   <td colname="col3"> <p> <code> irl 1. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>미국 동부 (버지니아 주) </p> </td> 
   <td colname="col3"> <p> <code> use. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>남태평양/오세아니아 (오스트레일리아 시드니) </p> </td> 
   <td colname="col3"> <p> <code> apse 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>미국 서부 (오레곤 주) </p> </td> 
   <td colname="col3"> <p> <code> usw 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>아시아 (일본, 일본) </p> </td> 
   <td colname="col3"> <p> <code> tyo 3. demdex. net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>인도 </p> </td> 
   <td colname="col3"> <p> <code> ind 1. demdex. net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL API] 메서드를 사용하여 사용 가능한 [!UICONTROL DCS] 지역 목록을 가져올 수도 있습니다. [DCS 영역 API 방법을 참조하십시오](../../../api/rest-api-main/aam-api-dcs-regions.md).