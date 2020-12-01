---
description: 이 문서에서는 키-값 쌍에서 키 변수가 사용하는 이름 지정 규칙에 대해 설명합니다.
seo-description: 이 문서에서는 키-값 쌍에서 키 변수가 사용하는 이름 지정 규칙에 대해 설명합니다.
seo-title: 주요 변수의 이름 요구 사항
solution: Audience Manager
title: 주요 변수의 이름 요구 사항
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 12%

---


# 주요 변수의 이름 요구 사항 {#name-requirements-for-key-variables}

이 문서에서는 키-값 쌍에서 키 변수가 사용하는 이름 지정 규칙에 대해 설명합니다.

## 키에 대한 이름 지정 요구 사항

<!-- c_tb_key_name_requirements.xml -->

[!UICONTROL Expression Builder]에서 키-값 쌍의 키 변수 이름은 1자 이상, 대시, 밑줄 및 추가 자리로 구성될 수 있습니다.

* 유효한 키 이름:`price123`, `123price`, `price-123`, `c_price123`.

* 잘못된 키 이름:`123`, `price!123`.

## 키 변수 접두사가 `c_`

이벤트 호출 URL에서 데이터를 보내는 매개 변수가 해당 구문을 사용하는 경우 `c_` 접두사는 *항상*&#x200B;입니다.