---
description: 규칙 기반 및 온보드 트레이트 생성 프로세스에 대한 설정 단계 및 기능에 대해 설명합니다.
keywords: create trait;create traits
seo-description: 규칙 기반 및 온보드 트레이트 생성 프로세스에 대한 설정 단계 및 기능에 대해 설명합니다.
seo-title: 규칙 기반 또는 온보딩된 트레이트 만들기
solution: Audience Manager
title: 규칙 기반 또는 온보딩된 트레이트 만들기
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 8%

---


# 원하는 대로 페이지 애플리케이션을 만들거나  [!UICONTROL Rules-Based][!UICONTROL Onboarded Traits]{#create-rules-based-or-onboarded-traits}

[!UICONTROL rules-based] 및 [!UICONTROL onboarded] 특성 생성 프로세스에 적용되는 설정 단계 및 기능에 대해 설명합니다.

<!-- c_tb_rules_traits.xml -->

## 트레이트 {#basics}에 대한 기본 정보

[!UICONTROL Trait Builder]에서 [!UICONTROL Basic Information] 설정을 사용하여 새로 만들거나 기존 [!UICONTROL traits]을 편집할 수 있습니다. [!UICONTROL Basic Information] 설정은 [!UICONTROL rules-based], [!UICONTROL onboarded] 및 [!UICONTROL algorithmic traits]에 대해 동일합니다. 새 [!UICONTROL trait]을(를) 만들려면 이름(특수 문자 제외), [!UICONTROL data source]을 입력하고 [!UICONTROL storage folder]를 선택합니다. 다른 [!UICONTROL Basic Information] 필드는 선택 사항입니다.

<!-- c_tb_basics.xml -->

![생성](assets/create-trait.png)

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
   <td colname="col1"> <b><span class="uicontrol"> 이름 </span></b> </td> 
   <td colname="col2"> <p>특성 이름입니다. 필수 여부. </p> <p>최대 길이:255자. </p> <p> <p>참고:트레이트의 이름을 지정할 때는 다음 특수 문자를 사용하지 마십시오. 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">쉼표 </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">대시 </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">하이픈 </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">탭 </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">세로 막대 또는 파이프 기호 </li> 
      </ul> </p> </p> <p>이렇게 하면 <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 인바운드 데이터 파일 전송</a>을 설정할 때 처리 오류를 줄이는 데 도움이 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 설명</span></b> </td> 
   <td colname="col2"> 특징의 목적이나 기능을 설명하는 몇 마디. 선택 사항입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 데이터 소스</span></b> </td> 
   <td colname="col2"> 트레이트를 특정 데이터 공급자와 연결합니다. 필수 여부. <p>첫 번째 드롭다운 메뉴를 사용하여 Audience Manager 데이터 소스, Adobe Analytics 보고서 세트 또는 둘 다 필터링합니다. 그런 다음 두 번째 드롭다운 메뉴를 사용하여 데이터 소스를 선택합니다.</p><p> Adobe Analytics 보고서 세트를 사용하지 않는 경우 데이터 소스 유형 선택기가 비활성화되어 Audience Manager 데이터 소스만 기본값으로 설정됩니다.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 이벤트 유형</span></b> </td> 
   <td colname="col2"> 유형 또는 카테고리에 트레이트를 할당합니다. 일반적으로 함수(예: 전환, 사이트 방문자, 파트너, 페이지 보기 등)에 해당합니다. 선택 사항입니다. <p> 전환 트레이트를 만드는 방법을 알아보려면 Audience Manager 비디오<a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">에서 전환 트레이트 만들기를 참조하십시오.</a> </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 통합 코드</span></b> </td> 
   <td colname="col2"> 내부 비즈니스 프로세스에서 사용하는 ID, SKU 또는 기타 값에 대한 필드입니다. 선택 사항입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 댓글</span></b> </td> 
   <td colname="col2"> 특성에 대한 일반적인 노트입니다. 선택 사항입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 저장 위치</span></b> </td> 
   <td colname="col2"> 트레이트가 속한 저장소 폴더를 결정합니다. 필수 여부. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 데이터 범주</span></b> </td> 
   <td colname="col2"> 일반적으로 이해되는 범주에 따라 트레이트를 분류합니다. <p>참고: 트레이트는 단일 카테고리에만 속합니다. 선택 사항입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Trait] 만료 간격 {#set-expiration-interval} 설정

[!UICONTROL Trait Builder]에서 [!UICONTROL Advanced Options]에서는 [!UICONTROL trait]에 대한 실시간 시간([!DNL TTL]) 간격을 설정할 수 있습니다. [!DNL TTL] 자격 조건을 갖춘 방문자가 남은 일 수를  [!UICONTROL trait] 정의합니다(120일은 기본값임). 0으로 설정하면 [!UICONTROL trait] 멤버십이 만료되지 않습니다.

<!-- t_tb_ttl.xml -->

### [!UICONTROL trait]에 대한 TTL 설정

1. [!UICONTROL Advanced Options] 섹션을 확장하고 번호를 입력하여 [!UICONTROL trait]에 대한 [!DNL TTL] 값을 설정합니다.
1. 클릭 **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [세그먼트별 라이브 설명](../../features/traits/segment-ttl-explained.md)

