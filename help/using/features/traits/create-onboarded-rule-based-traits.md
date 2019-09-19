---
description: 규칙 기반 및 온보드 트레이트 생성 프로세스에 대한 설정 단계 및 기능에 대해 설명합니다.
keywords: 트레이트 만들기;트레이트 만들기
seo-description: 규칙 기반 및 온보드 트레이트 생성 프로세스에 대한 설정 단계 및 기능에 대해 설명합니다.
seo-title: 규칙 기반 트레이트 또는 온보드 트레이트 만들기
solution: Audience Manager
title: 규칙 기반 트레이트 또는 온보드 트레이트 만들기
uuid: 4243e09f-1f96-44 파섹
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# 규칙 기반 트레이트 또는 온보드 트레이트 만들기 {#create-rules-based-or-onboarded-traits}

및 트레이트 생성 프로세스에 대한 설정 단계 및 기능에 대해 [!UICONTROL rules-based] [!UICONTROL onboarded] 설명합니다.

<!-- c_tb_rules_traits.xml -->

## 트레이트에 대한 기본 정보 {#basics}

에서 [!UICONTROL Trait Builder]설정을 [!UICONTROL Basic Information] 사용하여 새 트레이트를 만들거나 기존 트레이트를 편집할 수 있습니다. 규칙 기반, 온보드 및 알고리즘 트레이트에 대한 설정은 동일합니다. [!UICONTROL Basic Information] 새 트레이트를 만들려면 이름(특수 문자 제외), 데이터 소스를 입력하고 저장소 폴더를 선택합니다. 다른 [!UICONTROL Basic Information] 필드는 선택 사항입니다.

<!-- c_tb_basics.xml -->

### 정의된 기본 정보 필드

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
   <td colname="col2"> <p>특성 이름입니다. 필수 여부. </p> <p>최대 길이:255자. </p> <p> <p>참고:트레이트의 이름을 지정할 때는 다음 특수 문자를 사용하지 마십시오. 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">쉼표 </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">대시 </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">하이픈 </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">탭 </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">세로 막대 또는 파이프 기호 </li> 
      </ul> </p> </p> <p>이렇게 하면 <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 인바운드 데이터 파일 전송을</a>설정할 때 처리 오류가 줄어듭니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 설명</span></b> </td> 
   <td colname="col2"> 트레이트의 목적이나 기능을 설명하는 데 도움이 되는 몇 마디. 선택 사항입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 이벤트 유형</span></b> </td> 
   <td colname="col2"> 유형 또는 카테고리에 트레이트를 할당합니다. 일반적으로 함수에 따라(예: 전환, 사이트 방문자, 파트너, 페이지 보기 등). 선택 사항입니다. <p> 전환 트레이트를 만드는 방법에 대한 자세한 내용은 Audience Manager에서 <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">전환 트레이트 만들기 비디오를</a>참조하십시오. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 데이터 소스</span></b> </td> 
   <td colname="col2"> 트레이트를 특정 데이터 공급자에 연결합니다. 필수 여부. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 통합 코드</span></b> </td> 
   <td colname="col2"> 내부 비즈니스 프로세스에서 사용하는 ID, SKU 또는 기타 값에 대한 필드입니다. 선택 사항입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 댓글</span></b> </td> 
   <td colname="col2"> 특성에 대한 일반 참고 사항 선택 사항입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 저장 위치</span></b> </td> 
   <td colname="col2"> 트레이트가 속한 저장소 폴더를 결정합니다. 필수 여부. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 데이터 카테고리</span></b> </td> 
   <td colname="col2"> 일반적으로 인식되는 범주에 따라 트레이트를 분류합니다. <p>참고: 트레이트는 단일 카테고리에만 속합니다. 선택 사항입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 특성 만료 간격 설정 {#set-expiration-interval}

에서 [!UICONTROL Trait Builder]트레이트에 대한 실시간( [!UICONTROL Advanced Options][!DNL TTL]) 간격을 설정할 수 있도록 해줍니다. [!DNL TTL] 자격 있는 방문자가 트레이트에 남아 있는 일 수를 정의합니다(120일은 기본값). 0으로 설정하면 트레이트 멤버십이 만료되지 않습니다.

<!-- t_tb_ttl.xml -->

### 트레이트의 TTL 설정

1. 섹션을 [!UICONTROL Advanced Options] 확장하고 숫자를 입력하여 트레이트에 대한 [!DNL TTL] 값을 설정합니다.
2. 클릭 **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORELIKE_THIS]
>
>* [세그먼트 시간 설명](../../features/traits/segment-ttl-explained.md)

