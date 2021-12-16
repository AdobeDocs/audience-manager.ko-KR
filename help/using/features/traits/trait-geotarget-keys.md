---
description: Audience Manager 계정의 모든 속성에서 지리적 변수를 사용하여 사용자를 타깃팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍에 대해 설명합니다.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: 플랫폼 수준 키로 지리 기반 타겟팅
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 366589d51601f438999bfdc6a10c306eb1186742
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 3%

---

# 플랫폼 수준 키로 지리 기반 타겟팅 {#geotargeting-with-platform-level-keys}

Audience Manager 계정의 모든 속성에서 지리적 변수를 사용하여 사용자를 타깃팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍에 대해 설명합니다.

<!-- c_tb_platform_vars.xml -->

## 플랫폼 수준 변수의 목적 {#platform-variables}

플랫폼 수준 변수를 사용하면 특정 사이트에서 전달된 데이터를 가져와 의 모든 속성에서 타겟팅할 수 있습니다 [!DNL Audience Manager] 계정이 필요합니다. 이러한 변수는 [키 값 쌍](../../reference/key-value-pairs-explained.md) 접두사가 있는 키 `d_` 아래와 같이 표시됩니다.

## 플랫폼 수준 키에 값 추가 {#adding-values}

일부 플랫폼 수준 키의 경우 값을 직접 지정할 수 있습니다. 다른 키와 함께 키는 해당 와 연결됩니다 [!DNL IP] 이벤트 호출 시 전달된 주소. 어느 경우에나 트레이트를 작성할 때 값을 지정해야 합니다 [!UICONTROL Trait Builder].

## 사용자 정의 플랫폼 수준 키 {#user-defined-keys}

키-값 쌍을 정의하고 수집하는 프로세스를 이미 가지고 있거나 설정하고 있는 경우 이 옵션을 활용하십시오. IP 주소로 미리 정의된 키를 사용하려면 다음 섹션을 계속 진행합니다. 사용자 정의 키의 경우 다음 키-값 쌍으로 트레이트를 작성할 때 값을 지정합니다.

| 키 | 타겟 |
|---|---|
| `d_zx` | 우편 번호(예: `d_zx=10022`). |

## IP 주소로 정의된 플랫폼 수준 키 {#keys-ip-address}

우리는 [Digital Envoy](https://www.digitalenvoy.com/) 를 클릭하여 아래 키에 대한 인구 통계학 및 지역 데이터를 가져와 업데이트합니다. 이러한 키의 값은 일치로 결정됩니다 [!DNL IP] 해당 지역 및 인구 통계 데이터에 대한 주소. 그러나 키-값 쌍을 만들 때 값 매개 변수를 입력해야 합니다. [!UICONTROL Trait Builder].

| 키 | 타겟 |
|--- |--- |
| d_area_code | [북미 지역 코드](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  예: <ul><li>**트레이트**: d_area_code=801</li><li>**트레이트 이름**: 유타</li></ul> |
| d_city | 도시와 도시들. 다운로드 [도시 목록](assets/d_city.txt).  예: <ul><li>트레이트: d_city=bonn</li><li>트레이트 이름: 본</li></ul> **팁**: 다음을 사용할 수 있습니다 `d_city` 결합 `d_country` 다른 국가에서 이름이 같은 두 도시를 목표로 하지 않는 것이 확실합니다. 를 사용하여 타깃팅에서 보다 구체적으로 지정할 수 있습니다 `d_postal_code`. |
| d_country | 값은 ISO 국가 코드에 해당합니다. 검색 가능한 코드 목록을 보려면 [ISO 온라인 검색 플랫폼](https://www.iso.org/obp/ui/#home). <br>  영국에 대한 타깃팅은 ISO 3166에 따르지 않는 유일한 특별한 경우입니다. 영국에서 타깃팅하려면 &quot;GB&quot; 대신 &quot;UK&quot;를 사용해야 합니다.  네덜란드 항원을 대상으로 하기 위해 &quot;AN&quot; 코드는 2010년부터 더 이상 사용되지 않습니다. 그 지역은 5개의 분리된 영토 단위로 해산되었다. 함축된 의미는 네덜란드 항소에서 타깃팅하기 위해 &quot;AN&quot;을 사용하지 말고 &quot;CW&quot;, &quot;SX&quot; 및 &quot;BQ&quot;에 대한 국가 코드의 조합을 사용하라는 것입니다.  예:  <br>  트레이트: d_country=CZ  <br>  트레이트 이름: 체코 <br>  트레이트: d_country=UK <br>  트레이트 이름: 영국  <br>  트레이트: d_country=CW OR d_country=SX OR d_country=BQ  <br>  트레이트 이름: 네덜란드령 앤틸리스 |
| d_dma_code | 수도권 DMA 코드. 다운로드 [DMA 영역 목록](assets/DMAregions.csv) (.csv 형식).  예: <ul><li>트레이트: d_dma_code=807</li><li>트레이트 이름: 샌프란시스코</li></ul> |
| d_lat | 위도(예: d_lat=40.75). 다운로드 [위도 목록](assets/d_lat.txt). |
| d_long | 경도(예: d_long=73.98). 다운로드 [긴 목록](assets/d_long.txt). |
| d_postal_code | 우편 번호(확장 +4 코드 제외)입니다. 다운로드  [우편 번호 목록](assets/d_postal_code.txt).  예: <ul><li>트레이트: d_postal_code=84004 </li><li>트레이트 이름: 알파인</li></ul> |
| d_state | 미국 주용 2자의 약어입니다. 다운로드 [상태 코드 목록](assets/d_state.txt).  예: <ul><li>트레이트: d_state=NY </li><li>트레이트 이름: 뉴욕</li></ul>d_state에는 여러 국가의 다른 상태에 대해 반복되는 값이 포함되어 있습니다. 예를 들어 d_state == &quot;on&quot;은 여러 상태를 일치시킵니다. 온타리오(캐나다), 온도(나이지리아), 오샤나(나미비아). 보다 구체적인 지리 기반의 타깃팅을 위해 d_country와 같은 다른 사용자와 이 신호를 결합하는 것이 좋습니다. |
| d_region | 지역 영숫자 ID. 다운로드 [지역 목록](assets/Country_RegionCodes_City.csv).  그런 다음 이 목록을 사용하여 지역 ID와 지역 이름을 일치시킬 수 있습니다. |
| d_isp | ISP/조직. 다운로드 [ISP 목록](assets/d_isp.txt). |

목록 [모든 위치 기반 신호](assets/all.txt) 위의 모든 신호를 다음 순서로 포함합니다. `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [주요 변수의 접두사 요구 사항](../../features/traits/trait-variable-prefixes.md)

