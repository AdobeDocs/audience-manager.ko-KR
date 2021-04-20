---
description: 이러한 사양에 따라 Audience Optimization 메타데이터 파일의 이름을 지정합니다.
seo-description: 이러한 사양에 따라 Audience Optimization 메타데이터 파일의 이름을 지정합니다.
seo-title: 메타데이터 파일에 대한 이름 지정 규칙
solution: Audience Manager
title: 메타데이터 파일에 대한 이름 지정 규칙
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: Log Files
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 10%

---

# 메타데이터 파일에 대한 이름 지정 규칙{#naming-conventions-for-metadata-files}

이러한 사양에 따라 Audience Optimization 메타데이터 파일의 이름을 지정합니다.

## 구문 및 ID 카테고리 {#syntax}

다음 구문은 올바른 형식의 메타데이터 파일 이름의 구조를 정의합니다. 참고: *기울임체*&#x200B;는 변수 자리 표시자를 나타냅니다. 다른 요소는 상수이며 변경되지 않습니다.

**구문:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*메타데이터* 파일(.txt 또는 기타)에는 파일 확장자를 사용하지 마십시오.

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* 중간 구성 요소 **0**&#x200B;은(는) 엄밀히 말해 레거시 필드인 상위 ID입니다. 값은 항상 **0**&#x200B;으로 설정해야 합니다.
* 하위 ID는 차원에 따라 1에서 10 사이의 값을 가질 수 있습니다. 아래를 참조하십시오.

## 하위 ID 차원 {#child-dimension}

메타데이터 파일 이름에서 자식 ID는 파일의 데이터 유형을 분류하고 이를 계층 구조에 배치하는 식별자입니다. 파일 이름에 다음 카테고리 ID로 하위 ID에 태그를 지정할 수 있습니다.

1. 캠페인
1. 크리에이티브
1. 배치
1. Exchange
1. 사이트
1. 광고주([데이터 소스](../../../features/manage-datasources.md#details)에서 통합 코드를 사용하는 경우)
1. 삽입 순서(IO)
1. 수직(예: &quot;컴퓨터&quot;, &quot;자동차&quot;, &quot;부동산&quot; 등과 같은 특정 산업 또는 비즈니스 부문)
1. 전술
1. 사업부 또는 브랜드

## 예 {#example}

크리에이티브 메타데이터 파일의 경우 파일 이름은 20190115_0_2일 수 있습니다.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
