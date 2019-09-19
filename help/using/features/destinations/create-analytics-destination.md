---
description: Audience Analytics를 통해 Audience Manager 세그먼트를 Analytics에 보낼 수 있습니다. 이 기능을 사용하려면 Analytics 대상을 만들고 세그먼트를 Audience Manager의 대상에 매핑합니다.
seo-description: Audience Analytics를 통해 Audience Manager 세그먼트를 Analytics에 보낼 수 있습니다. 이 기능을 사용하려면 Analytics 대상을 만들고 세그먼트를 Audience Manager의 대상에 매핑합니다.
seo-title: Analytics 대상 구성
solution: Audience Manager
title: Analytics 대상 구성
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Analytics 대상 구성

## 요구 사항 {#requirements}

대상 [분석을 참조하십시오](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## 기본 분석 대상 및 새 분석 대상

| Analytics 대상 유형 | 설명 |
|---|---|
| 기본값 | 이 기본 대상의 이름은 편집할 수 있는 "Adobe Analytics"입니다. 매핑된 보고서 세트 ID 파섹 <br>  계정에 다음이 있는 경우 Audience Manager가 자동으로 하나의 대상을 만듭니다. <br>  <ul><li>대상 분석 설명서에 설명된 요구 [사항을](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) 충족했습니다.</li><li>Analytics의 [보고서 세트](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) .</li><li>[보고서 세트를 조직에](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)매핑했습니다.</li></ul> |
| 신규 | 새 Analytics 대상을 만들려면 대상 데이터 &gt; 대상 &gt; 새 대상 만들기로 이동하여 아래 설명된 각 섹션에 대한 단계를 수행합니다. |

## 1단계:기본 정보 제공

이 섹션에는 Analytics 대상 생성 프로세스를 시작하는 필드 및 옵션이 포함되어 있습니다. 이 섹션을 완료하려면

1. 기본 **정보를** 클릭하여 컨트롤을 표시합니다.
1. 대상의 이름을 지정합니다. 약어와 특수 문자는 사용하지 마십시오.
1. *(선택 사항)* 대상을 설명합니다. 간결한 설명은 대상에 대한 자세한 정보를 정의하거나 제공하는 효과적인 방법입니다.
1. *(선택 사항)* 플랫폼 **목록에서** 기본값을 모두(All)로 **설정합니다**. 현재 이러한 옵션은 아무 작업도 하지 않습니다. 나중에 추가될 수 있는 기능을 지원하도록 설계되었습니다.
1. 카테고리 **목록에서** Adobe Experience Cloud **를 선택합니다**.
1. 유형 **목록에서** Adobe Analytics를 **선택합니다**.
1. 저장을 **클릭하여** 구성 설정으로 이동하거나 데이터 내보내기 **레이블을** 클릭하여 내보내기 컨트롤을 대상에 적용합니다.

>[!NOTE]
>
>Analytics 대상의 경우 **기본적으로 대상 매핑** 자동 채우기 확인란 및 **세그먼트 ID** 옵션이선택됩니다. 이러한 설정은 변경할 수 없습니다.

![기초 정보](assets/basicinformation.png)

## 2단계:데이터 내보내기 컨트롤 구성

이 섹션에는 데이터 내보내기 컨트롤을 [Analytics](/help/using/features/data-export-controls.md) 대상에 적용하는 옵션이 포함되어 있습니다. 데이터 내보내기 컨트롤을 사용하지 않으면 이 단계를 건너뜁니다. 이 섹션을 완료하려면

1. 데이터 **내보내기 컨트롤을** 클릭하여 컨트롤을 표시합니다.
1. 대상에 적용된 데이터 내보내기 컨트롤에 해당하는 레이블을 선택합니다(대상에 데이터 [내보내기 레이블 추가 참조](/help/using/features/destinations/add-data-export-labels.md) ). Analytics 대상의 경우 기본적으로 PII 확인란이 선택됩니다.
1. **저장**&#x200B;을 클릭합니다.

![내보내기 제어](assets/exportControls.png)

## 3단계:보고서 세트 매핑

구성 섹션에는 서버측 전달에 대해 활성화된 분석 보고서 세트가 나열됩니다. 여러 Analytics 대상이 있는 경우 이러한 대상에 할당된 보고서 세트는 상호 배타적이고 Audience Manager에 의해 집행됩니다. 이 섹션을 완료하려면

1. 구성을 **클릭하여** 컨트롤을 표시합니다.
1. 세그먼트를 보낼 보고서 세트를 하나 이상 선택합니다.
1. **저장**&#x200B;을 클릭합니다.

![reportsuite](assets/reportSuites.png)

## 4단계:세그먼트 매핑

이 섹션에서는 세그먼트를 자동으로 또는 수동으로 매핑할 수 있는 옵션을 제공합니다.

| 매핑 옵션 | 설명 |
|---|---|
| 모든 현재 및 향후 세그먼트 자동 매핑 | 기본적으로 이 기능은 방문자가 적격한 모든 세그먼트를 히트별로 Analytics로 전송합니다. <br>  방문자가 단일 히트에서 150개 이상의 Audience Manager 세그먼트에 속한 경우, 가장 최근에 자격을 갖춘 150개의 세그먼트만 Analytics로 전송되고 나머지 목록은 잘립니다. 세그먼트 목록이 잘렸음을 나타내는 추가 플래그가 Analytics로 전송됩니다. 이 작업은 대상자 이름 차원에 "대상자 제한에 도달함"으로 표시되고 대상 ID 차원에 "1"로 표시됩니다. 자세한 내용은 [FAQ를](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) 참조하십시오. <br>  또한 이 옵션은 세그먼트 빌더의 대상 가용성에 영향을 [줍니다](/help/using/features/segments/segment-builder.md). 예를 들어 세그먼트가 Analytics 대상에 자동으로 매핑되는 경우 세그먼트 빌더의 [대상 매핑](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) 섹션에서 해당 대상을 선택할 수 없습니다. Analytics 대상이 회색으로 표시되고 대상 브라우저의 유형 열에 "Analytics"가 표시됩니다. |
| 수동으로 세그먼트 매핑 | 이 옵션은 Analytics로 보낼 세그먼트를 선택할 수 있는 검색 및 검색 컨트롤을 표시합니다. <br>  세그먼트를 검색하려면 <br>  <ol><li>검색 필드에 세그먼트 이름 또는 ID를 입력합니다.</li><li>Click <b>Add.</b></li><li>세그먼트를 계속 검색하고 추가하거나 완료를 <b>클릭합니다</b>.</li></ol><br>  세그먼트를 찾으려면 <ol><li>모든 <b>세그먼트</b>찾아보기를 클릭합니다. 이렇게 하면 사용 가능한 세그먼트 목록이 표시됩니다.</li><li>목록에서 사용할 세그먼트의 확인란을 선택하고 선택한 세그먼트 <b>추가를 클릭합니다</b>.</li><li>매핑 <b>추가</b> 창에서 저장을 클릭합니다. 베타 릴리스 중에는 매핑, 시작 또는 종료 날짜를 변경할 수 없습니다.</li><li>계속해서 세그먼트를 찾아 추가하거나 완료를 <b>클릭합니다</b>.</li></ol> ![세그먼트](assets/mapSegments.png) |

## 다음 단계

대상을 만들고 저장한 후 Analytics에서 해당 데이터로 작업할 수 있습니다. 하지만 선택한 보고서 세트에서 데이터를 사용할 수 있으려면 몇 시간이 걸릴 수 있습니다. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).
