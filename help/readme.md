---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# 지침

**참고: 이 페이지(또는 readme.md 페이지)는 고객 대면 설명서에 게시되지 않습니다**

## 목차

+ `TOC.md` 사용 안내서의 루트에 있는 는 이 솔루션에 대한 안내서에 포함된 주제 구성을 제공합니다.
+ 각 사용 안내서에는 고유한 항목이 있습니다 `TOC.md`, 필요에 따라 모든 페이지/주제를 정렬할 수 있습니다.
+ 모든 사용 안내서의 첫 페이지는 다음과 같습니다. `overview.md`.

## 사용 안내서

+ 사용 안내서 소개는 라고 합니다. `overview.md`
+ 사용 안내서의 각 주제에는 고유한 디렉토리가 있습니다.
   + 안내서에 다음 주제가 있는 경우 *구현*, 해당 디렉터리는 입니다. `/implementation`
+ 모든 이미지 자산은에 저장됩니다. `/assets` 사용 안내서의 루트에 있습니다.
   + 의 모든 이미지 `/assets` 디렉토리가 현지화됩니다.
   + 에 있는 모든 이미지 `/no-localize` 디렉터리가 현지화되지 않습니다. loc 버전에서 특정 자산이 불필요하게 재생되지 않는지 확인하는 데 사용할 수 있습니다.

## 사용 안내서 수준 메타데이터

+ 사용 안내서를 설명하는 메타데이터는에 저장됩니다 `TOC.md`. 여기에는 다음 항목이 포함되어 있습니다.
   + product - 제품/기능의 이름.
   + cloud - 이 제품이 속한 클라우드.
   + audience - 안내서가 타깃팅된 대상 또는 원형.
   + user-guide - 사용 안내서의 이름.

## 페이지 수준 메타데이터

+ 문서를 설명하는 데 필요한 메타데이터는 각 개별 페이지의 일부로 저장됩니다. 여기에는 다음 항목이 포함되어 있습니다.
   + title - 페이지의 제목입니다.
   + description - 페이지에 대한 설명.
   + seo-title - seo 대체 제목.
   + seo-description - SEO 목적의 대체 제목.
   + short-title - (선택 필드).
   + index - yes / no - 페이지가 Adobe의 검색 플랫폼으로 인덱싱됨.
   + translate - yes / no - 이 페이지가 현지화됨.
   + version - 주로 AEM 및 Campaign에 사용되며 제품 버전을 나타냅니다.
   + private-feature-pack - 주로 AEM에 사용됨.
   + beta - 제품이 베타 버전입니까?
   + 리디렉션 - 필요한 경우 새 페이지에 대한 참조를 만드는 데 사용할 수 있습니다.
   + doc-type: 참조(기본값) / 문제 해결 / 개발자 / 튜토리얼 / kb / 백서.

## 추가 정보

자세한 게시 지침, 스타일 안내서, 샘플 및 기타 리소스는 [공동 작업 문서 리포지토리](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
