---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# 지침

**참고:이 페이지(또는 모든 readme.md 페이지)는 고객 대면 문서에 게시되지 않습니다.**

## TOC

+ `TOC.md` 사용 안내서의 루트에서 이 솔루션의 안내서에 포함된 항목의 구성을 제공합니다.
+ 각 사용자 안내서에는 고유한 `TOC.md`항목이 있으며, 이 안내서는 필요한 경우 모든 페이지/항목을 주문할 수 있습니다.
+ 모든 사용자 안내서의 첫 번째 페이지는 `overview.md`입니다.

## 사용 안내서

+ 사용 안내서 소개는 `overview.md`
+ 사용 안내서의 각 항목에는 고유한 디렉토리가 있습니다.
   + 구현이라는 안내서에 주제가 있으면 *해당*&#x200B;디렉토리는 `/implementation`
+ 모든 이미지 에셋은 사용자 안내서의 `/assets` 루트에 저장됩니다.
   + 디렉토리의 모든 이미지가 `/assets` 현지화됩니다.
   + 디렉토리에 있는 모든 이미지는 현지화되지 않습니다(놀라운 기능!). `/no-localize` 이 기능은 loc 버전에서 특정 자산이 불필요하게 재생되지 않도록 하는 데 사용할 수 있습니다.

## 사용자 안내서 수준 메타 데이터

+ 사용자 안내서를 설명하는 메타 데이터는 에 저장됩니다 `TOC.md`. 여기에는 다음 항목이 포함되어 있습니다.
   + 제품 - 제품/기능의 이름입니다.
   + cloud - 이 제품이 속한 클라우드
   + 대상 - 대상이 되는 대상 또는 전형
   + 사용 안내서 - 사용 안내서의 이름입니다.

## 페이지 수준 메타 데이터

+ 문서를 설명하는 데 필요한 메타 데이터는 각 개별 페이지의 일부로 저장됩니다. 여기에는 다음 항목이 포함되어 있습니다.
   + title - 페이지의 제목.
   + 설명 - 페이지 설명입니다.
   + seo-title - seo alternative title.
   + seo-description - SEO 목적을 위한 대체 제목.
   + short-title - (선택적 필드).
   + index - yes / no - will be indexed by Adobe's search platform.
   + translate - yes / no - this page is localized.
   + 버전 - 주로 AEM 및 Campaign에 사용되며 제품 버전을 나타냅니다.
   + private-feature-pack - 주로 AEM에 사용됩니다.
   + 베타 - 이 제품이 베타 버전입니까?
   + 리디렉션 - 필요한 경우 새 페이지에 대한 참조를 만드는 데 사용할 수 있습니다.
   + doc-type:참조(기본값) / 문제 해결 / 개발자 / 자습서 / kb / 백서를 참조하십시오.

## 추가 정보

추가 게시 지침, 스타일 가이드, 샘플 및 기타 리소스를 보려면 협업 [설명서 보고서를 참조하십시오.](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
