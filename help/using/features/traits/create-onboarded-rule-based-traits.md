---
description: 규칙 기반 및 온보드 추적형 트레이트 작성 프로세스에 대한 설정 및 기능에 대해 설명합니다.
keywords: 트레이트 만들기; 트레이트 제작
seo-description: 규칙 기반 및 온보드 추적형 트레이트 작성 프로세스에 대한 설정 및 기능에 대해 설명합니다.
seo-title: 규칙 기반 또는 온보드 트레이트를 만듭니다.
solution: Audience Manager
title: 규칙 기반 또는 온보드 트레이트를 만듭니다.
uuid: 4243 E 09 F -1 F 96-443 A -864 A-D 6 E 6918079 FA
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Rules-Based or Onboarded Traits {#create-rules-based-or-onboarded-traits}

[!UICONTROL rules-based] 및 [!UICONTROL onboarded] 특성 작성 과정과 관련된 설정 및 기능에 대해 설명합니다.

<!-- c_tb_rules_traits.xml -->

## Basic Information for Traits {#basics}

In [!UICONTROL Trait Builder], the [!UICONTROL Basic Information] settings let you create new, or edit existing traits. The [!UICONTROL Basic Information] settings are the same for rules-based, onboarded and algorithmic traits. 새 트레이트를 만들려면 이름 (특수 문자 제외) 와 데이터 소스를 제공하고 저장소 폴더를 선택합니다. Other [!UICONTROL Basic Information] fields are optional.

<!-- c_tb_basics.xml -->

### 기본 정보 필드 정의

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 인터페이스 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">이름</span></b> </td> 
   <td colname="col2"> <p>트레이트 이름. 필수 여부. </p> <p>최대 길이: 255 자. </p> <p> <p>참고: 트레이트를 지정할 때 다음과 같은 특수 문자를 사용하지 마십시오. 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">쉼표 </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">대시 </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">하이픈 </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">탭 </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">세로 막대 또는 파이프 기호 </li> 
      </ul> </p> </p> <p>This helps reduce processing errors when you set up an <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> inbound data file transfer</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 설명</span></b> </td> 
   <td colname="col2"> 특성 또는 기능을 설명하는 데 도움이 되는 몇 가지 단어. 선택 사항입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 이벤트 유형</span></b> </td> 
   <td colname="col2"> 일반적으로 함수 (예: 전환, 사이트 방문자, 파트너, 페이지 보기 등) 에 따라 유형 또는 카테고리에 트레이트를 할당합니다. 선택 사항입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 데이터 소스</span></b> </td> 
   <td colname="col2"> 트레이트를 특정 데이터 공급자에 연결합니다. 필수 여부. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 통합 코드</span></b> </td> 
   <td colname="col2"> 내부 업무 처리 과정에서 사용되는 ID, SKU 또는 기타 값에 대한 필드입니다. 선택 사항입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 댓글</span></b> </td> 
   <td colname="col2"> 트레이트에 대한 일반 노트입니다. 선택 사항입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 저장 위치</span></b> </td> 
   <td colname="col2"> 속성이 속한 저장소 폴더를 결정합니다. 필수 여부. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 데이터 카테고리</span></b> </td> 
   <td colname="col2"> 일반적으로 인식되는 카테고리에 따라 트레이트를 분류합니다. <p>참고: 트레이트는 단일 카테고리에만 속합니다. 선택 사항입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Set a Trait Expiration Interval {#set-expiration-interval}

In [!UICONTROL Trait Builder], the [!UICONTROL Advanced Options] lets you set a time-to-live ([!DNL TTL]) interval for a trait. [!DNL TTL] 자격이 있는 방문자가 트레이트에 머무는 일 수를 정의합니다 (기본값은 120 일). 0로 설정하면 트레이트 멤버십이 만료되지 않습니다.

<!-- t_tb_ttl.xml -->

### 트레이트 TTL 설정

1. [!UICONTROL Advanced Options] 섹션을 확장하고 숫자를 입력하여 트레이트 [!DNL TTL] 값을 설정합니다.
1. 클릭 **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_ like_ this]
>
>* [세그먼트 작업 시간 설명](../../features/traits/segment-ttl-explained.md)

