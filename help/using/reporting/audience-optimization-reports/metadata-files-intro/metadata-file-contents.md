---
description: 이러한 사양에 따라 대상 최적화 메타데이터 파일의 내용을 포맷합니다.
seo-description: 이러한 사양에 따라 대상 최적화 메타데이터 파일의 내용을 포맷합니다.
seo-title: 메타데이터 파일에 대한 컨텐츠 형식
solution: Audience Manager
title: 메타데이터 파일에 대한 컨텐츠 형식
uuid: 9 ba 44738-3 e 17-40 c 7-9 e 8 c -5 abd 8361 e 16 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Content Format for Metadata Files{#content-format-for-metadata-files}

이러한 사양에 따라 대상 최적화 메타데이터 파일의 내용을 포맷합니다.

## 구문 {#syntax}

다음 구문은 메타데이터 파일에서 형식이 잘 구성된 컨텐츠의 구조를 정의합니다. *기울임꼴은* 변수 자리 표시자를 나타냅니다.

**구문:***컨텐츠 ID* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

The third column **-1** is technically the Parent ID, which is a legacy field. The value should always be set as **-1**.

>[!NOTE]
>
>차원당 하나의 메타데이터 파일이 필요하므로 버킷에서 여러 메타데이터 파일이 필요합니다. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**^ A (Control-A 또는 ASCII 001) 와 파일 항목 구분**

Use `^a` (control-A or ASCII 001) to separate content in your metadata files. 이것이 인쇄되지 않는 문자이므로 위의 구문의 예는 파이프 "|" 표시 목적으로만 제공됩니다.

If needed, you may download the example file - [20181105_0_1](assets/20181105_0_1.zip). 파일의 압축을 풀고 편집기에서 편집하고 실제 메타데이터 컨텐츠에 따라 조정하면 필요한 구분 기호가 이미 포함되어 있습니다.

>[!IMPORTANT]
>
>메타데이터 파일에 머리글 행을 추가하지 마십시오.

## 예 {#examples}

메타데이터 파일에서 컨텐츠를 구조화하는 방법을 살펴보겠습니다. 이 구조의 일부는 차원에 따라 다릅니다. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

이 예에서 파일 제목은 20180921_ 0_ 1 이며 파일의 열은 다음과 같습니다. 캠페인 ID, 이름 및 상위 ID.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**크리에이티브**

이 예에서 파일 제목은 20180827_ 0_ 2 이며 파일의 열은 다음과 같습니다. 크리에이티브 ID, 이름 및 상위 ID.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**사이트**

이 예에서 파일 제목은 20180921_ 0_ 5 이며 파일의 열은 다음과 같습니다. 사이트 ID, 이름 및 상위 ID.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
