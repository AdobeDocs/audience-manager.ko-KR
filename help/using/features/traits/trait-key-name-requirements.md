---
description: 이 문서에서는 키-값 쌍의 키 변수에 사용되는 이름 지정 규칙에 대해 설명합니다.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: 주요 변수의 이름 요구 사항
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
TQID: 'https://experienceleague.adobe.com/OEw-vhgEQtUfiyA4FzKp7rnxeFOZh2nL3r1-YudPAhc'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b89b323a-1e91-40b1-8d20-96b5b726d55a
    internal-label: Audience management
subfeature_v2:
  - id: b1ecf375-97f8-4f5a-a937-6129552209be
    internal-label: Traits
topic_v2:
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 0%
---
# 주요 변수의 이름 요구 사항 {#name-requirements-for-key-variables}

이 문서에서는 키-값 쌍의 키 변수에 사용되는 이름 지정 규칙에 대해 설명합니다.

## 키 이름 지정 요구 사항

<!-- c_tb_key_name_requirements.xml -->

[!UICONTROL Expression Builder]에서 키-값 쌍의 키 변수 이름은 임의의 자릿수 뒤에 1개 이상의 문자, 대시, 밑줄 및 추가 자릿수로 구성될 수 있습니다.

* 올바른 키 이름: `price123`, `123price`, `price-123`, `c_price123`.

* 잘못된 키 이름: `123`, `price!123`.

## `c_`(으)로 키 변수 접두사 사용

이벤트 호출 URL에서 데이터를 보내는 매개 변수가 해당 구문을 사용하는 경우 `c_` 접두사가 *always*&#x200B;입니다.
