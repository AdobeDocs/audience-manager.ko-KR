---
description: Audience Manager 계정의 모든 속성에 지리적 변수를 사용하여 사용자를 타깃팅하는 데 사용할 수 있는 공통 플랫폼 수준 키-값 쌍에 대해 설명합니다.
seo-description: Audience Manager 계정의 모든 속성에 지리적 변수를 사용하여 사용자를 타깃팅하는 데 사용할 수 있는 공통 플랫폼 수준 키-값 쌍에 대해 설명합니다.
seo-title: 플랫폼 수준 키로 지리 기반 타겟팅
solution: Audience Manager
title: 플랫폼 수준 키로 지리 기반 타겟팅
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---


# 플랫폼 수준 키로 지리 기반 타겟팅 {#geotargeting-with-platform-level-keys}

Audience Manager 계정의 모든 속성에 지리적 변수를 사용하여 사용자를 타깃팅하는 데 사용할 수 있는 공통 플랫폼 수준 키-값 쌍에 대해 설명합니다.

<!-- c_tb_platform_vars.xml -->

## 플랫폼 수준 변수의 목적 {#platform-variables}

플랫폼 수준 변수를 사용하면 특정 사이트에서 전달된 데이터를 가져와서 [!DNL Audience Manager] 계정의 모든 속성에 대해 타깃팅할 수 있도록 할 수 있습니다. 이러한 변수는 `d_`이(가) 키를 접두사로 사용한 [키-값 쌍](../../reference/key-value-pairs-explained.md)에 의해 만들어집니다.

## 플랫폼 수준 키에 값 추가 {#adding-values}

일부 플랫폼 수준 키의 경우 값을 직접 지정할 수 있습니다. 다른 키와 함께 키는 이벤트 호출에서 전달된 해당 [!DNL IP] 주소와 연결됩니다. 두 경우 모두 [!UICONTROL Trait Builder]에서 트레이트를 작성할 때 값을 지정해야 합니다.

## 사용자 정의 플랫폼 수준 키 {#user-defined-keys}

다음 키-값 쌍으로 트레이트를 작성할 때 값을 지정합니다.

| 키 | 타깃팅용 |
|---|---|
| `d_zx` | 우편 번호(예: `d_zx=10022`). |

## IP 주소로 정의되는 플랫폼 수준 키 {#keys-ip-address}

Adobe는 [Digital Envoy](https://www.digitalenvoy.com/)와 함께 아래 키에 대한 인구 통계학적 및 지리적 데이터를 입수하고 업데이트합니다. 이러한 키에 대한 값은 해당 지역 및 인구 통계 데이터에 [!DNL IP] 주소를 일치시켜 결정됩니다. 하지만 [!UICONTROL Trait Builder]에서 키-값 쌍을 만들 때는 값 매개 변수를 입력해야 합니다.

| 키 | 타깃팅용 |
|--- |--- |
| d_area_code | [북아메리카 지역 코드](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  예: <ul><li>**특성**:d_area_code=801</li><li>**특성 이름**:유타</li></ul> |
| d_city | 도시와 도시 [도시 목록](assets/d_city.txt)을 다운로드합니다.  예: <ul><li>특성: d_city=bonn</li><li>특성 이름:본</li></ul> **팁**:서로 다른 국가에서 이름이 같은 두 도시 `d_city` 를 타깃팅하지 않도록  `d_country` 함께 사용할 수 있습니다. `d_postal_code`을 사용하여 타깃팅에서 더 구체적으로 지정할 수 있습니다. |
| d_country | 값은 ISO 국가 코드에 해당합니다. 검색 가능한 코드 목록은 [ISO 온라인 브라우징 플랫폼](https://www.iso.org/obp/ui/#home)을 참조하십시오. <br>  영국에 대한 타깃팅은 ISO 3166에 따르지 않는 유일한 특별한 경우입니다. 영국에서 타깃팅하기 위해 &quot;GB&quot; 대신 &quot;UK&quot;를 사용해야 합니다.  네덜란드령 앤틸리스 대상 코드인 &quot;AN&quot;은 2010년부터 더 이상 사용되지 않습니다. 그 지역은 5개의 독립된 영토 부대로 해체되었다. 즉 네덜란드 앤틸리스 대상 타깃팅을 할 때 &quot;AN&quot;을 사용하지 말고 &quot;CW&quot;, &quot;SX&quot;, &quot;BQ&quot;의 국가 코드를 조합해야 합니다.  예: <br>  특성: d_country=CZ <br>  특성 이름:체코 <br>  특성: d_country=UK <br>  특성 이름:영국 <br>  특성: d_country=CW OR d_country=SX OR d_country=BQ <br>  특성 이름:네덜란드령 앤틸리스 |
| d_dma_code | 수도권 DMA 코드. [DMA 영역 목록](assets/DMAregions.csv) (.csv 형식)을 다운로드합니다.  예: <ul><li>특성: d_dma_code=807</li><li>특성 이름:샌프란시스코</li></ul> |
| d_lat | 위도(예: d_lat=40.75). [위도 목록](assets/d_lat.txt)을 다운로드합니다. |
| d_long | 경도(예: d_long=73.98). [긴 목록](assets/d_long.txt)을 다운로드합니다. |
| d_postal_code | ZIP 코드(확장 +4 코드 제외). [우편 번호 목록](assets/d_postal_code.txt)을 다운로드합니다.  예: <ul><li>특성: d_postal_code=84004 </li><li>특성 이름:알파인</li></ul> |
| d_state | 미국 주의 2자 약어. [상태 코드 목록](assets/d_state.txt)을 다운로드합니다.  예: <ul><li>특성: d_state=NY </li><li>특성 이름:뉴욕</li></ul>d_state에는 다른 국가의 여러 상태에 대한 반복되는 값이 포함되어 있습니다. 예를 들어 d_state == &quot;on&quot;은 여러 상태와 일치합니다.온타리오(캐나다), 온도(나이지리아), 오샤나(나미비아). 보다 구체적인 지리 기반의 타깃팅을 위해 d_country와 같은 다른 지표와 이 신호를 결합하는 것이 좋습니다. |
| d_region | 지역 영숫자 ID. [지역 목록](assets/Country_RegionCodes_City.csv)을 다운로드합니다.  그런 다음 이 목록을 사용하여 지역 ID를 지역 이름에 일치시킬 수 있습니다. |
| d_isp | ISP/조직 [ISP 목록](assets/d_isp.txt)을 다운로드합니다. |

[모든 위치 기반 신호 목록](assets/all.txt)은 위의 모든 신호를 다음 순서로 포함합니다.`d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [주요 변수의 접두사 요구 사항](../../features/traits/trait-variable-prefixes.md)

