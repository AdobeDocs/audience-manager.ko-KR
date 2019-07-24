---
description: 중복 보고서가 백만 개의 레코드 제한에 도달하는 경우 이 보고서에 대한 .csv 파일을 요청할 수 있습니다. " 예기치 않은 오류가 발생했습니다 "메시지가 표시되는 경우 보고서가 이 제한에 도달했을 수 있습니다. 자체 데이터베이스 시스템에서 가져와 작업할 수 있는 압축된. csv 파일을 요청하려면 고객 지원 센터에 문의하십시오. 파일은 세그먼트 간, 세그먼트 간 및 특성 겹침 보고서에 사용할 수 있습니다.
seo-description: 중복 보고서가 백만 개의 레코드 제한에 도달하는 경우 이 보고서에 대한 .csv 파일을 요청할 수 있습니다. " 예기치 않은 오류가 발생했습니다 "메시지가 표시되는 경우 보고서가 이 제한에 도달했을 수 있습니다. 자체 데이터베이스 시스템에서 가져와 작업할 수 있는 압축된. csv 파일을 요청하려면 고객 지원 센터에 문의하십시오. 파일은 세그먼트 간, 세그먼트 간 및 특성 겹침 보고서에 사용할 수 있습니다.
seo-title: 중복 보고서에 대한 CSV 파일
solution: Audience Manager
title: 중복 보고서에 대한 CSV 파일
uuid: 047 e 440 e -00 c 5-4 d 06-a 809-51 d 776326 cd 6
translation-type: tm+mt
source-git-commit: d13b32999c5af4d20f33a92dfa805d7fe0babb2d

---


# 중복 보고서에 대한 CSV 파일{#csv-files-for-overlap-reports}

중복 보고서가 백만 개의 레코드 제한에 도달하는 경우 이 보고서에 대한 .csv 파일을 요청할 수 있습니다. " 예기치 않은 오류가 발생했습니다 "메시지가 표시되는 경우 보고서가 이 제한에 도달했을 수 있습니다. 자체 데이터베이스 시스템에서 가져와 작업할 수 있는 압축된. csv 파일을 요청하려면 고객 지원 센터에 문의하십시오. 파일은 세그먼트 간, 세그먼트 간 및 특성 겹침 보고서에 사용할 수 있습니다.

## File Name Metadata {#file-name-metadata}

다음 표 목록은 겹친. csv 파일에서 파일 이름 지정 규칙과 파일 확장명에 대해 설명합니다. In the examples, *italics* indicates a variable placeholder.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 메타데이터 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>파일 익스텐션 </p> </td> 
   <td colname="col2"> <p>Overlap report files are gzip compressed and have a <code> .gz</code> file extension. You must add the <code> .csv</code> extension to the file after decompression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>파일 이름 </p> </td> 
   <td colname="col2"> <p>파일 이름 구문: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Segment-to-segment files: <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Segment-to-trait files: <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Trait-to-trait files: <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>날짜 범위 </p> </td> 
   <td colname="col2"> <p>보고서의 날짜 범위는 다음을 포함하는 5 자리 ID 입니다. </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 7 일 보고서의</code> 경우 70000 입니다. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30 일 보고서의</code> 경우 30000 입니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>여러 파일 </p> </td> 
   <td colname="col2"> <p>보고서에 여러 파일이 포함된 경우 파일 이름의 마지막 숫자가 증가합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>예 </p> </td> 
   <td colname="col2"> <p>단일 보고서의 파일 이름 예: </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Single, 7-day file: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Single, 30-day file: <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>여러 파일이 있는 보고서의 파일 이름 예: </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Contents {#file-contents}

파일에서 문자열 데이터는 큰 따옴표로 묶습니다. 아래 모의 데이터를 참조하십시오. 이 값이 잘려서 화면에 맞게 잘렸습니다.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Segment-to-Segment Report Records {#segment-segment-records}

[세그먼트 간 겹침 보고서의 데이터 파일에는 다음 레코드가](segment-segment-overlap-report.md) 포함됩니다.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 레이블 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ id 1</code> </p> </td> 
   <td colname="col2"> <p>기준 세그먼트와 비교할 세그먼트의 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ name 1</code> </p> </td> 
   <td colname="col2"> <p>기준 세그먼트와 비교할 세그먼트 이름. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ id 2</code> </p> </td> 
   <td colname="col2"> <p>기준선 세그먼트의 ID. 기준 세그먼트는 다른 세그먼트와 비교할 세그먼트입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ name 2</code> </p> </td> 
   <td colname="col2"> <p>다른 세그먼트와 비교할 기준 세그먼트의 이름. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Rangeid</code> </p> </td> 
   <td colname="col2"> <p>7 일 및 30 일 룩백 간격에 대한 보고서를 얻을 수 있습니다. <code> Rangeid</code> 는 아래 표시된 시간 간격에 해당합니다. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>일 7 일 </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>일: 30 일 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Datethru</code> </p> </td> 
   <td colname="col2"> <p>보고서의 처리 날짜입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ uniques 1</code> </p> </td> 
   <td colname="col2"> <p>기준 세그먼트와 비교할 세그먼트에 있는 고유 사용자의 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ uniques 2</code> </p> </td> 
   <td colname="col2"> <p>기준선 세그먼트에 있는 고유 사용자의 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ uniques</code> </p> </td> 
   <td colname="col2"> <p>기준선 세그먼트와 비교를 위해 선택한 다른 세그먼트 간의 고유 사용자 겹침 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>기준선 세그먼트와 비교를 위해 선택한 다른 세그먼트 간에 고유한 사용자의 % 겹침. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment-to-Trait Report Records {#segment-trait-records}

[세그먼트에 특성 겹침 보고서의 데이터 파일에는 다음 레코드가](segment-trait-overlap-report.md) 포함됩니다.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 레이블 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ id</code> </p> </td> 
   <td colname="col2"> <p>특성 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ name</code> </p> </td> 
   <td colname="col2"> <p>특성 이름. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_ type</code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 ID 입니다. ID 에는 다음이 포함됩니다. </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 자사</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 타사</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Dataprovider</code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Rangeid</code> </p> </td> 
   <td colname="col2"> <p>7 일 및 30 일 룩백 간격에 대한 보고서를 얻을 수 있습니다. <code> Rangeid</code> 는 아래 표시된 시간 간격에 해당합니다. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>일 7 일 </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>일: 30 일 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Datethru</code> </p> </td> 
   <td colname="col2"> <p>보고서의 처리 날짜입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ uniques</code> </p> </td> 
   <td colname="col2"> <p>선택한 세그먼트에서 고유한 사용자 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ uniques</code> </p> </td> 
   <td colname="col2"> <p>트레이트 고유 사용자 수입니다. UI 보고서에서 열맵 결과의 특성 위로 마우스를 가져가면 팝업 창에 이 숫자가 표시됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ uniques</code> </p> </td> 
   <td colname="col2"> <p>선택한 세그먼트와 특성 간에 공유되는 고유한 사용자의 수입니다. UI 보고서에서 열맵 결과의 특성 위로 마우스를 가져가면 팝업 창에 이 숫자가 표시됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ uniques_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>트레이트 및 세그먼트 간에 겹치는 고유한 사용자의 %. UI 보고서에서 열맵 결과의 특성 위로 마우스를 가져가면 팝업 창에 이 숫자가 표시됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ uniques_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>세그먼트와 트레이트 사이에 겹치는 고유 사용자의 %. UI 보고서에서 열맵 결과의 특성 위로 마우스를 가져가면 팝업 창에 이 숫자가 표시됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait-to-Trait Report Records {#trait-trait-records}

[특성 특성 겹침 보고서의 데이터 파일에는 다음 레코드가](trait-trait-overlap-report.md) 포함됩니다.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 레이블 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ trait_ id</code> </p> </td> 
   <td colname="col2"> <p>기준선 트레이트와 비교할 트레이트 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ trait_ name</code> </p> </td> 
   <td colname="col2"> <p>기준선 트레이트와 비교할 트레이트 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ id</code> </p> </td> 
   <td colname="col2"> <p>기준선 특성 ID. 기준선 트레이트 (Baseline Trait) 는 다른 트레이트와 비교할 트레이트입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ name</code> </p> </td> 
   <td colname="col2"> <p>다른 트레이트와 비교할 기준선 트레이트 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_ type</code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 ID 입니다. ID 에는 다음이 포함됩니다. </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 자사</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 타사</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Dataprovider</code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Rangeid</code> </p> </td> 
   <td colname="col2"> <p>7 일 및 30 일 룩백 간격에 대한 보고서를 얻을 수 있습니다. <code> Rangeid</code> 는 아래 표시된 시간 간격에 해당합니다. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>일 7 일 </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>일: 30 일 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Datethru</code> </p> </td> 
   <td colname="col2"> <p>보고서의 처리 날짜입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ trait_ uniques</code> </p> </td> 
   <td colname="col2"> <p>선택한 트레이트 사이에 공유되는 고유한 사용자의 수입니다. UI 보고서에서 열맵 결과의 특성 위로 마우스를 가져가면 팝업 창에 이 숫자가 표시됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ uniques</code> </p> </td> 
   <td colname="col2"> <p>기본 트레이트의 고유 사용자 수입니다. UI 보고서에서 열맵 결과의 특성 위로 마우스를 가져가면 팝업 창에 이 숫자가 표시됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ uniques</code> </p> </td> 
   <td colname="col2"> <p>선택한 트레이트 사이에 공유되는 고유한 사용자의 수입니다. UI 보고서에서 열맵 결과의 특성 위로 마우스를 가져가면 팝업 창에 이 숫자가 표시됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ trait_ uniques_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>선택한 트레이트 사이에 겹치는 고유한 사용자의 %. UI 보고서에서 열맵 결과의 특성 위로 마우스를 가져가면 팝업 창에 이 숫자가 표시됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ uniques_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>선택한 특성 사이에 겹치는 고유 사용자의 %. UI 보고서에서 열맵 결과의 특성 위로 마우스를 가져가면 팝업 창에 이 숫자가 표시됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
