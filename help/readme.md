---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# 지침

**참고: 이 페이지 (또는 Readme. md 페이지) 는 고객 대면 설명서에 게시되지 않습니다.**

## TOC

+ `TOC.md` 사용자 안내서의 루트에서 이 솔루션에 대한 안내서에 포함된 주제 구성을 제공합니다.
+ Each user guide will have its own unique `TOC.md`, in which you can order all the pages/topics as necessary.
+ The first page of all user guides is `overview.md`.

## 사용 안내서

+ The introduction to the user guide is called `overview.md`
+ 사용자 안내서의 각 주제에는 고유한 디렉토리가 있습니다.
   + If there is a topic in the guide called *Implementation*, the corresponding directory is `/implementation`
+ All image assets are stored in `/assets` at the root of the user guide.
   + `/assets` 디렉토리의 모든 이미지가 현지화됩니다.
   + `/no-localize` 디렉토리에 있는 모든 이미지는 현지화되지 않습니다. 특정 자산이 불필요하게 재생되지 않는 LOC 버전을 확인하는 데 사용할 수 있습니다.

## 사용 안내서 수준 메타 데이터

+ Meta data which describes the user guide is stored in the `TOC.md`. 여기에는 다음 항목이 포함되어 있습니다.
   + 제품 - 제품/기능의 이름.
   + 클라우드 - 이 제품이 속한 클라우드.
   + 대상 - 안내서가 타깃팅된 대상 또는 관문자입니다.
   + 사용자 안내서 - 사용자 안내서의 이름입니다.

## 페이지 수준 메타 데이터

+ 문서를 설명하는 데 필요한 메타 데이터는 각 개별 페이지의 일부로 저장됩니다. 여기에는 다음 항목이 포함되어 있습니다.
   + 제목 - 페이지의 제목입니다.
   + 설명 - 페이지에 대한 설명입니다.
   + seo-title - SEO 대체 제목.
   + seo-description - SEO 목적의 대체 제목입니다.
   + short-title - (선택적 필드).
   + 색인 - 예/아니요 - 페이지가 Adobe의 검색 플랫폼으로 인덱싱됩니다.
   + Translate - Yes/No - 이 페이지가 현지화될 것입니다.
   + 버전 - 주로 AEM 및 캠페인에 사용되며 제품 버전을 나타냅니다.
   + private-feature-pack - 주로 AEM에 사용됩니다.
   + 베타 - 베타 버전입니까?
   + 리디렉션 - 새 페이지에 대한 참조를 만드는 데 사용할 수 있습니다.
   + doc-type: 참조 (기본값)/문제 해결/개발자/자습서/kb/백서를 참조하십시오.

## 추가 정보

For more publishing instructions, style guides, samples and other resources, please visit the [Collaborative Documentation Repo](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
