---
description: Audience Manager 계정의 모든 속성에서 지리적 변수로 사용자를 타깃팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍을 설명합니다.
seo-description: Audience Manager 계정의 모든 속성에서 지리적 변수로 사용자를 타깃팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍을 설명합니다.
seo-title: 플랫폼 수준 키가 포함된 지리 기반의 타깃팅
solution: Audience Manager
title: 플랫폼 수준 키가 포함된 지리 기반의 타깃팅
uuid: C 7 E 4 CBFE-E 564-404 E-A 565-BBE 5 FD 2 FB 519
translation-type: tm+mt
source-git-commit: c5c57423bcba8d4b3974a04c46dc7c7afc7484a0

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Audience Manager 계정의 모든 속성에서 지리적 변수로 사용자를 타깃팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍을 설명합니다.

<!-- c_tb_platform_vars.xml -->

## Purpose of Platform-level Variables {#platform-variables}

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Adding Values to Platform Level Keys {#adding-values}

일부 플랫폼 수준 키에 대해 직접 값을 지정할 수 있습니다. With others, the keys are associated with corresponding [!DNL IP] addresses passed in on an event call. In either case, you still need to specify the value when building traits in [!UICONTROL Trait Builder].

## User Defined Platform-Level Keys {#user-defined-keys}

다음 키-값 쌍으로 특성을 작성할 때 값을 지정합니다.

| 키 | 타깃팅 |
|---|---|
| `d_zx` | ZIP code (e.g., `d_zx=10022`). |

## Platform Level Keys Defined by IP Address {#keys-ip-address}

[Digital Envoy](https://www.digitalenvoy.com/) 와 협력하여 아래 키에 대한 인구 통계학적 데이터와 지리학적 데이터를 입수하고 업데이트합니다. The values for these keys are determined by matching [!DNL IP] addresses to corresponding geographic and demographic data. However, you'll still have to enter the value parameter when creating the key-value pair in [!UICONTROL Trait Builder].

| 키 | 타깃팅 |
|--- |--- |
| d_ area_ code | [북미 지역 코드](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes). 예: <ul><li>**특성**: D_ AREA_ CODE = 801</li><li>**특성 이름**: 유타</li></ul> |
| d_ city | 도시 및 도시. [도시 목록을 다운로드합니다](assets/d_city.txt). 예: <ul><li>특성: d_ city = bonn</li><li>특성 이름: Bonn</li></ul> **팁**: `d_city` 와 함께 사용하면 `d_country` 다른 국가에서 이름이 같은 두 개의 도시를 타깃팅하지 않을 수 있습니다. You can be even more specific in your targeting by using `d_postal_code`. |
| d_ country | 값은 ISO 국가 코드에 해당합니다. For a searchable list of codes, see the [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>ISO 3166를 준수하지 않는 유일한 특별 사례는 영국의 타깃팅입니다. 영국에서 타깃팅하려면 "GB" 대신 "uk" 를 사용해야 합니다. 네덜란드령 앤틸리스를 공략하기 위해 코드 "AN" 는 2010 년부터 더 이상 사용되지 않습니다. 이 영역은 5 개의 별도 영토로 해체되었습니다. 즉, 네덜란드령 안틸레스 타깃팅을 위해서는 "an" 를 사용해서는 안 되지만 "cw", "sx" 및 "bq" 에 대한 국가 코드의 조합을 사용해서는 안됩니다. For example:  <br>  Trait:  d_country=CZ  <br>  Trait Name: Czech Republic <br>  Trait:  d_country=UK <br>  Trait Name: United Kingdom  <br>  Trait:  d_country=CW OR d_country=SX OR d_country=BQ  <br>  Trait Name: Netherlands Antilles |
| d_ dma_ code | 대도시 지역 DMA 코드. [DMA 영역 목록](assets/DMAregions.csv) (. csv 형식) 를 다운로드합니다. 예: <ul><li>특성: D_ DMA_ CODE = 807</li><li>특성 이름: 샌프란시스코</li></ul> |
| d_ lat | 위도 (예: D_ Lat = 40.75). [위도 목록을 다운로드합니다](assets/d_lat.txt). |
| d_ long | 경도 (예: d_ long = 73.98). [경도 목록을 다운로드합니다](assets/d_long.txt). |
| d_ postal_ code | 우편 번호 (확장 +4 코드 제외). [우편 번호 목록을 다운로드합니다](assets/d_postal_code.txt). 예: <ul><li>특성: d_ postal_ code = 84004 </li><li>특성 이름: 알파인</li></ul> |
| d_ state | 미국 주에 대한 2 자 약어. [상태 코드 목록을 다운로드합니다](assets/d_state.txt). 예: <ul><li>특성: d_ state = ny </li><li>특성 이름: 뉴욕</li></ul>d_ state는 국가마다 다른 상태에 대해 반복 값을 포함합니다. 예를 들어 d_ state = = "on" 는 여러 상태와 일치합니다. 온타리오 (캐나다), 온도 (나이지리아), 오샤나 (나미비아) 더 구체적인 지리 기반의 타깃팅을 위해 D_ Country와 같은 다른 사람과 이 신호를 결합하는 것이 좋습니다. |
| D_ region | 지역별 영숫자 ID. [지역 목록을 다운로드합니다](assets/Country_RegionCodes_City.csv). 그런 다음 이 목록을 사용하여 지역 ID와 지역 이름을 비교할 수 있습니다. |
| d_ ISP | ISP/조직. [ISP 목록을 다운로드합니다](assets/d_isp.txt). |

[모든 위치 기반 신호](assets/all.csv) 목록은 위의 모든 신호를 순서대로 포함합니다. `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_ like_ this]
>
>* [주요 변수의 접두사 요구 사항](../../features/traits/trait-variable-prefixes.md)

