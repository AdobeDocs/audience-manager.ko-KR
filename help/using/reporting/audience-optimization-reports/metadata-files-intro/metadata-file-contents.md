---
description: 이러한 사양에 따라 대상 최적화 메타데이터 파일의 컨텐츠를 포맷합니다.
seo-description: 이러한 사양에 따라 대상 최적화 메타데이터 파일의 컨텐츠를 포맷합니다.
seo-title: 메타데이터 파일에 대한 컨텐츠 형식
solution: Audience Manager
title: 메타데이터 파일에 대한 컨텐츠 형식
uuid: 9ba44738-3e17-4 파섹
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 메타데이터 파일에 대한 컨텐츠 형식{#content-format-for-metadata-files}

이러한 사양에 따라 대상 최적화 메타데이터 파일의 컨텐츠를 포맷합니다.

## 구문 {#syntax}

다음 구문은 메타데이터 파일에서 형식이 올바른 내용의 구조를 정의합니다. Note, *italics* indicates a variable placeholder.

**** 구문: *콘텐츠 ID* | *이름* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

세 번째 열 **1** 은 기술적으로 상위 ID이며 기존 필드입니다. 값은 항상 **-1로**&#x200B;설정해야 합니다.

>[!NOTE]
>
>차원당 하나의 메타데이터 파일이 필요하므로 버킷에 여러 메타데이터 파일이 필요합니다. 차원은 메타데이터 파일에 대한 [이름 지정 규칙에 설명되어 있습니다](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**^a(control-A 또는 ASCII 001)로 파일 항목 구분**

메타데이터 파일에서 컨텐츠를 분리하려면 `^a` (control-A 또는 ASCII 001)을 사용합니다. 이러한 문자는 인쇄되지 않는 문자이므로 위의 구문 예는 표시 목적으로만 파이프 "|"을 표시합니다.

필요한 경우 예제 파일(20181105_ [0_1)을 다운로드할 수 있습니다](assets/20181105_0_1.zip). 필요한 구분 기호가 이미 포함되어 있으므로 원하는 편집기를 사용하여 편집하고 실제 메타데이터 컨텐츠에 따라 조정할 수 있습니다.

>[!IMPORTANT]
>
>메타데이터 파일에 머리글 행을 추가하지 마십시오.

## 예 {#examples}

메타데이터 파일에서 컨텐츠를 구성하는 방법을 살펴보겠습니다. 이 구조의 일부는 차원에 따라 다릅니다. 차원은 메타데이터 파일에 대한 [이름 지정 규칙에 설명되어 있습니다](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

이 예에서 파일 제목은 20180921_0_1이고 파일의 세 열은 다음과 같습니다.캠페인 ID, 이름 및 상위 ID.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**크리에이티브**

이 예에서 파일 제목은 20180827_0_2이고 파일의 세 열은 다음과 같습니다.크리에이티브 ID, 이름 및 상위 ID.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**사이트**

이 예에서 파일 제목은 20180921_0_5이고 파일의 세 열은 다음과 같습니다.사이트 ID, 이름 및 상위 ID.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
