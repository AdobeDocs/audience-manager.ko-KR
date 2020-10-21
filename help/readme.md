---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# 지침

**참고:이 페이지(또는 모든 readme.md 페이지)는 고객 대면 설명서에 게시되지 않습니다**

## TOC

+ `TOC.md` 사용자 안내서의 루트에서 이 솔루션에 대한 안내서에 포함된 항목의 구성을 제공합니다.
+ 각 사용자 안내서는 고유한 고유 `TOC.md`를 가지며, 필요한 경우 모든 페이지/항목을 주문할 수 있습니다.
+ 모든 사용자 안내서의 첫 번째 페이지는 다음과 같습니다 `overview.md`.

## 사용 안내서

+ 사용자 안내서 소개 `overview.md`
+ 사용 안내서의 각 항목에는 고유한 디렉토리가 있습니다.
   + Implementation이라는 안내서에 *주제가*&#x200B;있으면 해당 디렉터리는 `/implementation`
+ 모든 이미지 에셋은 사용자 안내서 `/assets` 의 루트에 저장됩니다.
   + 디렉토리의 모든 이미지가 `/assets` 현지화됩니다.
   + 디렉토리의 모든 이미지는 `/no-localize` 현지화되지 않습니다(놀라운 기능!). 특정 자산이 불필요하게 재생되지 않도록 하는 데 사용할 수 있습니다.

## 사용 안내서 수준 메타 데이터

+ 사용자 안내서를 설명하는 메타 데이터는 `TOC.md` 여기에는 다음 항목이 포함되어 있습니다.
   + product - product/capability의 이름입니다.
   + cloud - 이 제품이 속한 cloud.
   + audience - 가이드가 타깃팅되는 대상 또는 전형
   + user-guide - user guide의 이름입니다.

## 페이지 수준 메타 데이터

+ 문서를 설명하는 데 필요한 메타 데이터는 각 개별 페이지의 일부로 저장됩니다. 여기에는 다음 항목이 포함되어 있습니다.
   + title - 페이지의 제목.
   + description - page.
   + seo-title - seo alternative title.
   + seo-description - SEO 목적으로 사용할 대체 제목입니다.
   + 짧은 제목 - (선택적 필드)
   + index - yes / no - 페이지가 Adobe 검색 플랫폼으로 인덱싱됩니다.
   + 번역 - 예 / 아니요 - 이 페이지가 현지화됩니까?
   + 버전 - 제품 버전을 나타내는 데 주로 AEM 및 Campaign에 사용됩니다.
   + private-feature-pack - 주로 AEM에 사용됩니다.
   + 베타 - 베타 버전입니까?
   + 리디렉션 - 필요한 경우 새 페이지에 대한 참조를 만드는 데 사용할 수 있습니다.
   + doc-type:참조(기본값) / 문제 해결 / developer / tutorial / kb / 백서

## 추가 정보

게시 지침, 스타일 가이드, 샘플 및 기타 리소스를 자세히 알아보려면 [공동 작업 설명서 보고서를 참조하십시오](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
