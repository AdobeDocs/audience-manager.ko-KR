---
description: 특성 자격 조건 또는 특성 구현은 트레이트 유형에 따라 Audience Manager에서 다르게 처리됩니다. 특성 자격 조건에 대한 자세한 내용은 아래 표를 참조하십시오.
keywords: 특성 자격 조건; 특성 구현; 고유한 특성 실현; UTR; 총 특성 수TTP
seo-description: 특성 자격 조건 또는 특성 구현은 트레이트 유형에 따라 Audience Manager에서 다르게 처리됩니다. 특성 자격 조건에 대한 자세한 내용은 아래 표를 참조하십시오.
seo-title: 트레이트 자격 참조
solution: Audience Manager
title: 트레이트 자격 참조
uuid: 07 E 0 A 639-2 FB 2-45 D 8-BAD 7-10 FB 46 B 08 BA 9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# 트레이트 자격 참조 {#trait-qualification-reference}

특성 자격 조건 또는 특성 구현은 트레이트 유형에 따라 Audience Manager에서 다르게 처리됩니다. 특성 자격 조건에 대한 자세한 내용은 아래 표를 참조하십시오.

## Trait Qualification by Trait Type {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 트레이트 유형 </th> 
   <th colname="col2" class="entry"> 자격 조건 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>규칙 기반의 트레이트 </p> </td> 
   <td colname="col2"> <p>특성 자격 조건은 사용자가 브라우저에서 트레이트를 적용받을 수 있으므로 실시간으로 발생합니다. Your users will start qualifying for a rule-based trait approximately 4 hours after you <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> create the trait</a> in the UI. </p> <p>Rule-based traits allow you to use <a href="../../features/segments/recency-and-frequency.md"> recency and frequency</a> controls for ad frequency capping and other use cases. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>온보드 트레이트릿 </p> </td> 
   <td colname="col2"> <p>Trait qualification happens after an inbound file is processed, i.e. the inbound file is <a href="../../faq/faq-inbound-data-ingestion.md"> imported into Audience Manager</a> and that is when the trait qualification happens. </p> <p> 온보드 트레이트에 대해 사용자 프로필에 대한 최대 자격 조건은 1 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>알고리즘 트레이트 </p> </td> 
   <td colname="col2"> <p>알고리즘 트레이트에 대한 사용자 프로파일의 최대 자격 조건은 1 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>폴더 특징 </p> </td> 
   <td colname="col2"> <p>폴더 트레이트는 포함된 트레이트에 대한 트레이트 자격 조건을 요약합니다. </p> <p><a href="../../features/traits/about-folder-traits.md"> 폴더 특성 읽기: About</a> for more information. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>활성 고객 특성 및 데이터 소스 동기화 특성 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 활성 대상</span> 트레이트에는 <span class="wintitle"> Audience Manager</span> 계정의 관리 아래에 있는 모든 장치가 포함되어 있습니다. </p> <p><span class="wintitle"> 데이터 소스 동기화된 트레이트는</span> 데이터 소스와 연결된 모든 사용자를 추적합니다. </p> <p><a href="../../features/traits/client-activity-synced-audience-traits.md"> 적극적인 고객 특성 및 데이터 소스에 동기화된 트레이트에</a>대한 자세한 내용을 살펴보십시오. </p> </td>
  </tr>
 </tbody>
</table>

## Unique Trait Realizations and Total Trait Population {#unique-trait-realizations}

![](assets/utr-ttp1.png)

The **[!UICONTROL Unique Trait Realizations]** count the number of your visitors that have added the trait to their profile, within different time ranges.

The **[!UICONTROL Total Trait Population]** represents the number of your visitors that have this trait on their profile.

이런 식으로 숫자를 생각해 보십시오. In the image above, from the [Trait Details](../../features/traits/trait-details-page.md) view, 181 represents the number of active devices, that visited your properties yesterday. The [!UICONTROL Total Trait Population] of 1,595 represents the amount of users currently qualified for this trait. [!UICONTROL Total Trait Population] 그림은 세그멘테이션/타깃팅에 사용할 수 있는 총 사용자 수를 보여주기 위한 것입니다. 일반적으로 사용자는 120 일간 트레이트의 일부로 남아 있습니다.

Because we run two different computational jobs to calculate the two populations, the [!UICONTROL Total Trait Population] always lags behind the [!UICONTROL Unique Trait Realizations] by 24 hours. In the graph above, you can see 175 [!UICONTROL Unique Trait Realizations] and a [!UICONTROL Total Trait Population] of 6 for February 11. The 175 profiles are added to the [!UICONTROL Total Trait Population] on the following day.

To further drive the point home, if you experienced a spike of 10,000 visitors right now, they would show up in tomorrow's [!UICONTROL Unique Trait Realizations], but would only show up 24 hours later in the [!UICONTROL Total Trait Population].

## Trait Qualification Limit {#trait-qualification-limit}

We enforce a limit of 150,000 trait qualifications for each user profile, whether it is an authenticated profile ( [DPUUID](../../reference/ids-in-aam.md)) or a device ID ( [UUID](../../reference/ids-in-aam.md)). Note that while the DPUUIDs are unique to a specific instance of [!DNL Audience Manager], UUIDs are shared across the [!DNL Audience Manager] platform. For [!UICONTROL UUID]s, we impose a fairness policy when storing trait qualifications. An algorithm ensures that an equal share of the [!UICONTROL UUID] profile is made available for every instance of [!DNL Audience Manager].
