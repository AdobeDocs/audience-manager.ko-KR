---
description: 트레이트 자격 또는 트레이트 실현은 트레이트 유형에 따라 Audience Manager에서 다르게 처리됩니다. 트레이트 자격에 대한 자세한 내용은 아래 표를 참조하십시오.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: 트레이트 자격 또는 트레이트 실현은 트레이트 유형에 따라 Audience Manager에서 다르게 처리됩니다. 트레이트 자격에 대한 자세한 내용은 아래 표를 참조하십시오.
seo-title: 트레이트 자격 참조
solution: Audience Manager
title: 트레이트 자격 참조
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 2f8662aba70254e550bc15417463c3c06492a9d5

---


# 트레이트 자격 참조 {#trait-qualification-reference}

트레이트 자격 또는 트레이트 실현은 트레이트 유형에 따라 Audience Manager에서 다르게 처리됩니다. 트레이트 자격에 대한 자세한 내용은 아래 표를 참조하십시오.

## 특성 유형별 트레이트 자격 {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 특성 유형 </th> 
   <th colname="col2" class="entry"> 자격 조건 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>규칙 기반 트레이트 </p> </td> 
   <td colname="col2"> <p>트레이트 자격은 사용자가 브라우저에서 트레이트를 이용할 수 있으므로 실시간으로 발생합니다. 사용자는 UI에서 트레이트를 <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> 만든 후 약 4시간 후에 규칙 기반 트레이트에 대한 자격을</a> 시작합니다. </p> <p>규칙 기반 트레이트를 사용하면 <a href="../../features/segments/recency-and-frequency.md"> 최근 및 빈도</a> 컨트롤을 사용하여 광고 빈도 제한 및 기타 사용 사례를 수행할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>온보드 트레이트 </p> </td> 
   <td colname="col2"> <p>트레이트 자격은 인바운드 파일이 처리된 후에 발생합니다. 즉, 인바운드 파일을 Audience Manager <a href="../../faq/faq-inbound-data-ingestion.md"> 로</a> 가져오며 이는 트레이트 자격 증명이 발생한 때입니다. 처리를 위해 인바운드 파일을 업로드하기 전에 온보드 트레이트를 만든 후 약 4시간을 기다려야 합니다.  </p> <p> 온보드 트레이트의 경우 사용자 프로필의 최대 자격 조건은 1입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>알고리즘 트레이트 </p> </td> 
   <td colname="col2"> <p>알고리즘 방식의 트레이트의 경우 사용자 프로필의 최대 자격 조건은 1입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>폴더 트레이트 </p> </td> 
   <td colname="col2"> <p>폴더 트레이트는 포함된 트레이트의 특성 자격을 합산합니다. </p> <p>폴더 <a href="../../features/traits/about-folder-traits.md"> 트레이트 읽기:정보</a> . </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>활성 고객 트레이트 및 데이터 소스 동기화된 트레이트 </p> </td> 
   <td colname="col2"> <p>활성 <span class="wintitle"> 대상</span> 트레이트에는 Audience Manager 계정에서 관리 중인 모든 장치가 <span class="wintitle"> 포함됩니다</span> . </p> <p><span class="wintitle"> 데이터 소스 동기화된</span> 트레이트는 데이터 소스와 연관된 모든 사용자를 추적합니다. </p> <p>활성 고객 트레이트 및 <a href="../../features/traits/client-activity-synced-audience-traits.md"> 데이터 소스 동기화된 트레이트에 대한 자세한 내용을 살펴보십시오</a>. </p> </td>
  </tr>
 </tbody>
</table>

## 고유 트레이트 실현과 총 트레이트 인구 {#unique-trait-realizations}

![](assets/utr-ttp1.png)

프로필에 트레이트를 추가한 방문자 수를 다른 시간 범위 내에서 **[!UICONTROL Unique Trait Realizations]** 카운트합니다.

이 **[!UICONTROL Total Trait Population]** 트레이트가 프로필에 있는 방문자 수를 나타냅니다.

이런 식으로 숫자를 생각해 보세요. 위의 이미지에서 트레이트 세부 사항 [보기에서](../../features/traits/trait-details-page.md) 181은 어제 속성을 방문한 활성 장치의 수를 나타냅니다. 1,595 [!UICONTROL Total Trait Population] 는 현재 이 트레이트에 대해 자격이 있는 사용자의 양을 나타냅니다. 이 [!UICONTROL Total Trait Population] 수치는 세그멘테이션/타깃팅에 사용할 수 있는 총 사용자 수를 보여주기 위한 것입니다. 일반적으로 사용자는 120일 동안 트레이트의 일부로 유지됩니다.

우리는 두 개의 다른 계산 작업을 실행하여 두 개의 인구를 계산하기 때문에, [!UICONTROL Total Trait Population] 항상 24 [!UICONTROL Unique Trait Realizations] 시간 정도 뒤쳐집니다. 위의 그래프에서 2월 11일에 대해 175 [!UICONTROL Unique Trait Realizations] 와 [!UICONTROL Total Trait Population] 6을 볼 수 있습니다. 175개의 프로필이 다음날 [!UICONTROL Total Trait Population] 에 추가됩니다.

더 나아가 그 점을 집까지 향하기 위해, 당신이 지금 10,000명의 방문자를 경험한다면, 그들은 내일 [!UICONTROL Unique Trait Realizations]에 나타날 것이지만, 그것은 단지 24시간 후에 [!UICONTROL Total Trait Population]나타날 것입니다.

## 트레이트 자격 제한 {#trait-qualification-limit}

인증된 프로필(DPUUID) 또는 디바이스 ID(UUID)인지 여부에 따라 각 사용자 프로필에 대해 [150,](../../reference/ids-in-aam.md)000개의 트레이트 자격 [](../../reference/ids-in-aam.md)제한을 적용합니다. DPUUID는 특정 인스턴스에 고유하지만 [!DNL Audience Manager]UUID는 [!DNL Audience Manager] 플랫폼에서 공유됩니다. 관건은 [!UICONTROL UUID]트레이트 자격을 저장할 때 공정성이 있다는 것이다. 알고리즘은 모든 인스턴스에 대해 동일한 [!UICONTROL UUID] 프로필 공유를 사용할 수 있도록 [!DNL Audience Manager]합니다.
