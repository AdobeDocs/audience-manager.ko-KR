---
description: 모델 빌더에서 알고리즘 모델을 만들 수 있는 필수 단계와 선택 단계에 대해 설명합니다.
keywords: algo how works
seo-description: 모델 빌더에서 알고리즘 모델을 만들 수 있는 필수 단계와 선택 단계에 대해 설명합니다.
seo-title: 알고리즘 모델 만들기
solution: Audience Manager
title: 알고리즘 모델 만들기
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: 35bad7e676aa1d4143f5d114a1eff85d6aba5f1d

---


# 유사 모델 만들기 {#create-an-algorithmic-model}

를 만들 수 있는 필수 단계와 선택 단계에 대해 [!UICONTROL Look-Alike Model]설명합니다.

## 모델 빌더 섹션

[!UICONTROL Model Builder] 은 [!UICONTROL Basic Information] 및 [!UICONTROL Configuration] 섹션으로 구성됩니다. 모델을 만들려면 이 두 섹션에서 필요한 필드를 완성합니다. 모델을 저장하여 알고리즘을 시작합니다. [!DNL Audience Manager] 첫 번째 데이터 실행이 완료된 후 자동으로 알림을 보냅니다. 이메일을 받은 후 트레이트 빌더로 이동하여 [알고리즘 트레이트를](../../features/traits/about-trait-builder.md) 만들 수 있습니다.

>[!NOTE]
>
>* 모델링 프로세스는 모델을 만들고 해당 모델로 트레이트를 만들지 않는 경우에만 실행됩니다.
>* 의미 있는 양의 정보가 포함된 데이터 소스를 기반으로 모델을 구축할 수 있습니다. 데이터가 부족한 모델은 실행되지만 결과를 반환하지 않습니다.
>* *다른 알고리즘 특성이나 세그먼트로 모델을 만들지 마십시오* .
>* 자동 이메일 알림은 첫 번째 데이터 실행 후 한 번만 전송됩니다.


## 모델 작성

아래 절차에 따라 [!UICONTROL Look-Alike Model]다음을 빌드하십시오.

1. > **[!UICONTROL Audience Data]** 로 **[!UICONTROL Models]** 이동하고 **[!UICONTROL Add New]** [!UICONTROL Look-Alike Modeling] 섹션에서 을 클릭합니다.
   ![유사 추가](assets/look-alike-add.png)
1. 기본 [정보](../../features/algorithmic-models/create-model.md#basic-information) 섹션에서
   * 모델의 이름을 지정합니다.
   * *(선택 사항)* 모델에 대한 간단한 설명을 제공합니다.
   * 모델의 상태를 **[!UICONTROL Active]** 또는 으로 **[!UICONTROL Inactive]**설정합니다. 비활성 모델은 실행되지 않으며 데이터를 생성하지 않습니다.
      ![유사 기본](assets/look-alike-basic.png)
1. 구성 [섹션에서](../../features/algorithmic-models/create-model.md#configuration) 다음을 수행합니다.
   * 를 **[!UICONTROL Browse All Traits]** 클릭하거나 **[!UICONTROL Browse All Segments]** 클릭하여 모델링할 트레이트 또는 세그먼트를 선택합니다. 이름, ID, 설명 또는 데이터 소스별로 트레이트를 검색합니다. 검색 중에 폴더를 클릭하여 해당 폴더 및 하위 폴더로 결과를 제한합니다. 트레이트를 트레이트 유형([!UICONTROL Folder Trait], [!UICONTROL Rule-based][!UICONTROL Onboarded]및 [!UICONTROL Algorithmic]인구 유형) 또는 인구 유형([장치 ID 및](../../reference/ids-in-aam.md) 크로스 장치 ID [)별로 필터링할](../../reference/ids-in-aam.md)수도 있습니다.
      ![browse traits](assets/browse-traits.png)
   * 30, 60 또는 90일 룩백 기간을 선택합니다. 그러면 모델의 시간 범위가 설정됩니다.
   * 기본적으로 [!UICONTROL TraitWeight] 알고리즘이 선택됩니다.
   * 목록에서 데이터 소스를 [!UICONTROL Available Data] 선택합니다.
   * 완료되면 을 **[!UICONTROL Save]** 클릭합니다.
      ![유사 구성](assets/look-alike-configuration.png)

## 알고리즘 모델에 대한 기본 정보 {#basic-information}

<!-- r_model_basic.xml -->

에서 [!UICONTROL Model Builder]설정을 [!UICONTROL Basic Information] 사용하여 새 모델을 만들거나 기존 모델을 편집할 수 있습니다. 새 모델을 만들려면 이름을 입력하고 [!UICONTROL Configuration] 설정으로 이동합니다. 설명 필드는 선택 사항입니다.

| 필드 | 설명 |
|---|---|
| **[!UICONTROL Name]** | 기능이나 목적을 설명하는 짧고 논리적인 이름을 모델에 지정합니다. 약자, 특수 문자 및 강조 표시를 사용하지 마십시오. |
| **[!UICONTROL Description]** | 모델에 대한 추가 설명 정보를 위한 필드입니다. |
| **[!UICONTROL Status]** | 모델을 활성화 또는 비활성화합니다(기본적으로 활성). |

## 구성 {#configuration}

에서 [!UICONTROL Model Builder]이 [!UICONTROL Configuration] 섹션에서 모델에 트레이트 또는 세그먼트를 추가할 수 있습니다. 이 섹션에서 기준 트레이트 또는 세그먼트, 룩백 기간 및 첫 번째 및 타사 데이터 소스의 데이터를 선택합니다.

<!-- r_model_configuration.xml -->

### 전제 조건

먼저 [!UICONTROL Basic Information] 섹션의 필수 필드를 완료합니다.

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 필드 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>기준 요소 트레이트 또는 세그먼트 선택(1)</b> </p> </td> 
   <td colname="col2"> <p>트레이트 또는 세그먼트 단추를 클릭하여 모든 트레이트 또는 세그먼트 목록을 봅니다. 선택한 세그먼트나 트레이트는 시스템 알고리즘이 모델링에 사용하는 기준이 됩니다. </p> <p> <p><b>참고</b>: 온보드 트레이트, 규칙 기반 트레이트 또는 세그먼트를 기준선으로 선택합니다. 그렇지 않으면 모델이 실행되지 않습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>뒤로 보기 기간 선택(2)</b> </p> </td> 
   <td colname="col2"> <p>모델의 시간 범위를 설정합니다. 선택한 항목에 따라 알고리즘은 이전 30일, 60일 또는 90일의 데이터를 포함하고 평가합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>알고리즘 선택(3)</b> </p> </td> 
   <td colname="col2"> <p>현재 Model Builder는 독점적인 특성 가중치 <span class="keyword"> 알고리즘에서만</span> 작동합니다. <span class="keyword"> Audience</span> Manager는 이후 릴리스에 다른 알고리즘 기능을 추가할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>데이터 소스에서 모델 데이터 선택(4)</b> </p> </td> 
   <td colname="col2"> <p>모델에서 사용할 첫 번째 및 타사 데이터 소스를 선택할 수 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>제외(5)</b> </p> </td> 
   <td colname="col2"> <p>모델링을 위해 선택한 데이터 소스에서 트레이트를 제외할 수 있습니다. 제외 <span class="wintitle"> 목록을 사용하고 알고리즘 모델을</span> <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> 읽습니다.트레이트 제외를</a> 참조하십시오. </p> </td>
  </tr> 
 </tbody>
</table>

아래 비디오를 시청하여 퍼스트 파티 유사 모델을 만드는 방법을 살펴보십시오. 그러면 전환자와 비슷한 방문자를 더 많이 찾을 수 있습니다.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [특성 가중치 이해](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

