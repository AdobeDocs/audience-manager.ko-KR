---
description: Audience Manager 계정의 모든 속성에서 지역 변수를 사용하는 사용자를 타겟팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍에 대해 설명합니다.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: 플랫폼 수준 키가 포함된 Geotargeting
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 2de7aba53e3c88d31270f2acb4fa29389f940312
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# 플랫폼 수준 키가 포함된 Geotargeting {#geotargeting-with-platform-level-keys}

Audience Manager 계정의 모든 속성에서 지역 변수를 사용하는 사용자를 타겟팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍에 대해 설명합니다.

<!-- c_tb_platform_vars.xml -->

## 플랫폼 수준 변수의 목적 {#platform-variables}

플랫폼 수준 변수를 사용하면 특정 사이트에서 전달된 데이터를 가져와 [!DNL Audience Manager] 계정의 모든 속성에서 타깃팅에 사용할 수 있습니다. 이러한 변수는 아래와 같이 [이 접두사로 추가된 키를 사용하여 ](../../reference/key-value-pairs-explained.md)키-값 쌍`d_`으로 형성됩니다.

## 플랫폼 수준 키에 값 추가 {#adding-values}

일부 플랫폼 수준 키의 경우 직접 값을 지정할 수 있습니다. 다른 사용자와 함께 키는 이벤트 호출 시 전달된 해당 [!DNL IP] 주소와 연결됩니다. 두 경우 모두 [!UICONTROL Trait Builder]에서 특성을 작성할 때 값을 지정해야 합니다.

## 사용자 정의 플랫폼 수준 키 {#user-defined-keys}

키-값 쌍을 정의 및 수집하는 프로세스가 이미 있거나 설정 중인 경우 이 옵션을 활용합니다. IP 주소로 미리 정의된 키를 사용하려면 다음 섹션으로 이동하십시오. 사용자 정의 키의 경우 다음 키-값 쌍으로 트레이트를 작성할 때 값을 지정합니다.

| 키 | 타깃팅용 |
|---|---|
| `d_zx` | 우편 번호(예: `d_zx=10022`). |

## IP 주소로 정의된 플랫폼 수준 키 {#keys-ip-address}

[Digital Envoy](https://www.digitalenvoy.com/)와(과) 함께 아래 키에 대한 인구 통계학적 및 지리적 데이터를 가져오고 업데이트합니다. 이 키의 값은 [!DNL IP] 주소를 해당 지리적 및 인구 통계학적 데이터에 일치시켜 결정됩니다. 그러나 [!UICONTROL Trait Builder]에서 키-값 쌍을 만들 때는 값 매개 변수를 입력해야 합니다.

| 키 | 타깃팅용 |
|--- |--- |
| d_area_code | [북미 지역 코드](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  예: <ul><li>**트레이트**: d_area_code=801</li><li>**트레이트 이름**: 유타</li></ul> |
| d_city | 도시와 도시. [도시 목록](assets/d_city.txt)을 다운로드합니다.  예: <ul><li>트레이트: d_city=bonn</li><li>트레이트 이름: 본</li></ul> **팁**: 다른 국가에서 이름이 같은 두 도시를 대상으로 하지 않도록 `d_city`을(를) `d_country`과(와) 함께 사용할 수 있습니다. `d_postal_code`을(를) 사용하여 타깃팅에서 더 구체적일 수 있습니다. |
| d_country | 값은 ISO 국가 코드에 해당합니다. 검색 가능한 코드 목록은 [ISO 온라인 검색 플랫폼](https://www.iso.org/obp/ui/#home)을 참조하십시오. <br>  영국에 대한 타겟팅은 ISO 3166을 준수하지 않는 유일한 특수 사례입니다. 영국에서 타깃팅에 &quot;GB&quot; 대신 &quot;UK&quot;를 사용해야 합니다.  네덜란드 앤틸레스를 타깃으로 코드 &quot;AN&quot;은 2010년부터 더 이상 사용되지 않습니다. 그 지역은 5개의 별도 영토 단위로 해체되었다. 함축된 의미는 네덜란드 안틸레스에서 타깃팅의 경우 &quot;AN&quot;을 사용하지 말고 &quot;CW&quot;, &quot;SX&quot;, &quot;BQ&quot;에 국가 코드를 조합하여 사용해야 한다는 것입니다.  예: <br>  트레이트: d_country=CZ <br>  트레이트 이름: 체코 공화국 <br>  트레이트: d_country=UK <br>  트레이트 이름: 영국 <br>  트레이트: d_country=CW 또는 d_country=SX 또는 d_country=BQ <br>  트레이트 이름: 네덜란드령 앤틸리스 |
| d_dma_code | 대도시 지역 DMA 코드. [DMA 영역 목록](assets/DMAregions.csv)(.csv 형식)을 다운로드합니다.  예: <ul><li>트레이트: d_dma_code=807</li><li>트레이트 이름: San Francisco</li></ul> |
| d_lat | 위도(예: d_lat=40.75). [위도 목록](assets/d_lat.txt)을 다운로드합니다. |
| d_long | 경도(예: d_long=73.98). [경도 목록](assets/d_long.txt)을 다운로드합니다. |
| d_postal_code | ZIP 코드(확장 +4 코드 제외). [우편 번호 목록](assets/d_postal_code.txt)을 다운로드합니다.  예: <ul><li>트레이트: d_postal_code=84004 </li><li>트레이트 이름: Alpine</li></ul> |
| d_state | 미국 주의 2문자 약어입니다. [상태 코드 목록](assets/d_state.txt)을 다운로드합니다.  예: <ul><li>트레이트: d_state=NY </li><li>트레이트 이름: 뉴욕</li></ul>d_state에는 다른 국가의 다른 상태에 대해 반복된 값이 포함되어 있습니다. 예를 들어 d_state == &quot;on&quot;은 온타리오(캐나다), 온도(나이지리아), 오샤나(나미비아) 등 여러 주와 일치합니다. 보다 구체적인 지리 기반의 타깃팅을 위해 이 신호를 d_country와 같은 다른 신호와 결합하는 것이 좋습니다. |
| d_region | 지역 영숫자 ID. [지역 목록](assets/Country_RegionCodes_City.csv)을 다운로드합니다.  그런 다음 이 목록을 사용하여 지역 ID를 지역 이름과 일치시킬 수 있습니다. |
| d_isp | ISP/조직. [ISP 목록](assets/d_isp.txt)을 다운로드하십시오. |

[모든 위치 기반 신호](assets/all.txt) 목록은 다음 순서로 위의 모든 신호를 포함합니다. `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [주요 변수의 접두사 요구 사항](../../features/traits/trait-variable-prefixes.md)

