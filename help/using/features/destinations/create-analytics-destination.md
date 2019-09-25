---
description: Audience Analytics를 통해 Audience Manager 세그먼트를 Analytics에 보낼 수 있습니다. 이 기능을 사용하려면 Analytics 대상을 만들고 세그먼트를 Audience Manager의 대상에 매핑합니다.
seo-description: Audience Analytics를 통해 Audience Manager 세그먼트를 Analytics에 보낼 수 있습니다. 이 기능을 사용하려면 Analytics 대상을 만들고 세그먼트를 Audience Manager의 대상에 매핑합니다.
seo-title: Analytics 대상 구성
solution: Audience Manager
title: Analytics 대상 구성
translation-type: tm+mt
source-git-commit: fa39d070be9ec9f07e9da31de3efd151dd2c6cf1

---


# Configure an Analytics Destination

## 요구 사항 {#requirements}

Analytics 대상을 구성하려면 Audience Manager 사용자에게 관리 권한이 있어야 합니다. 관리 [안내서에서](/help/using/features/administration/administration-overview.md#create-users) 사용자 만들기를 참조하십시오. Analytics 대상을 만들려면 `CREATE_DESTINATIONS` 와일드카드 [사용 권한을](/help/using/features/administration/administration-overview.md#wild-card-permissions) 가지면 충분하지 않습니다.
추가 요구 사항은 Audience Analytics의 전제 [조건을 참조하십시오](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## 기본 분석 대상 및 새 분석 대상

| Analytics 대상 유형 | 설명 |
|---|---|
| 기본값 | 이 기본 대상의 이름은 편집할 수 있는 "Adobe Analytics"입니다. 매핑된 보고서 세트 ID 파섹 <br>  계정에 다음이 있는 경우 Audience Manager가 자동으로 하나의 대상을 만듭니다. <br>  <ul><li>대상 분석 설명서에 설명된 요구 [사항을](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) 충족했습니다.</li><li>Analytics의 [보고서 세트](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) .</li><li>[Mapped a report suite to an organization](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| 신규 | 새 Analytics 대상을 만들려면 대상 데이터 &gt; 대상 &gt; 새 대상 만들기로 이동하여 아래 설명된 각 섹션에 대한 단계를 수행합니다. |

## 1단계:기본 정보 제공

이 섹션에는 Analytics 대상 생성 프로세스를 시작하는 필드 및 옵션이 포함되어 있습니다. 이 섹션을 완료하려면

1. 기본 **정보를** 클릭하여 컨트롤을 표시합니다.
2. 대상의 이름을 지정합니다. 약어와 특수 문자는 사용하지 마십시오.
3. *(선택 사항)* 대상을 설명합니다. 간결한 설명은 대상에 대한 자세한 정보를 정의하거나 제공하는 효과적인 방법입니다.
4. *(선택 사항)* 플랫폼 **목록에서** 기본값을 모두(All)로 **설정합니다**. 현재 이러한 옵션은 아무 작업도 하지 않습니다. 나중에 추가될 수 있는 기능을 지원하도록 설계되었습니다.
5. 카테고리 **목록에서** Adobe Experience Cloud **를 선택합니다**.
6. 유형 **목록에서** Adobe Analytics를 **선택합니다**.
7. 저장을 **클릭하여** 구성 설정으로 이동하거나 데이터 내보내기 **레이블을** 클릭하여 내보내기 컨트롤을 대상에 적용합니다.

>[!NOTE]
>
>Analytics 대상의 경우 **기본적으로 대상 매핑** 자동 채우기 확인란 및 **세그먼트 ID** 옵션이선택됩니다. 이러한 설정은 변경할 수 없습니다.

![기초 정보](assets/basicinformation.png)

## 2단계:데이터 내보내기 컨트롤 구성

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. Skip this step if you do not use data export controls. To complete this section:

1. Click Data Export Controls to expose the controls.****
1. Select a label that corresponds to the data export control applied to the destination (see Add Data Export Labels to a Destination ). [](/help/using/features/destinations/add-data-export-labels.md) For Analytics destinations, the PII check box is selected by default.
1. **저장**&#x200B;을 클릭합니다.

![exportcontrols](assets/exportControls.png)

## Step 3: Map Report Suites

The Configuration section lists your Analytics Report Suites that have been enabled for server-side forwarding. If you have multiple Analytics destinations, the report suites assigned to these destinations will be mutually exclusive and enforced by Audience Manager. To complete this section:

1. Click Configuration to expose the controls.****
1. Select one (or more) report suites that you want to send segments to.
1. **저장**&#x200B;을 클릭합니다.

![reportsuites](assets/reportSuites.png)

## 4단계:세그먼트 매핑

This section provides options that let you map segments automatically or manually.

| 매핑 옵션 | 설명 |
|---|---|
| 모든 현재 및 향후 세그먼트 자동 매핑 | 기본적으로 이 기능은 방문자가 적격한 모든 세그먼트를 히트별로 Analytics로 전송합니다. <br>  If a visitor belongs to more than 150 Audience Manager segments on a single hit, only the 150-most recently qualified segments are sent to Analytics, while the remaining list is truncated. 세그먼트 목록이 잘렸음을 나타내는 추가 플래그가 Analytics로 전송됩니다. 이 작업은 대상자 이름 차원에 "대상자 제한에 도달함"으로 표시되고 대상 ID 차원에 "1"로 표시됩니다. 자세한 내용은 [FAQ를](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) 참조하십시오. <br>  또한 이 옵션은 세그먼트 빌더의 대상 가용성에 영향을 [줍니다](/help/using/features/segments/segment-builder.md). 예를 들어 세그먼트가 Analytics 대상에 자동으로 매핑되는 경우 세그먼트 빌더의 [대상 매핑](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) 섹션에서 해당 대상을 선택할 수 없습니다. Analytics 대상이 회색으로 표시되고 대상 브라우저의 유형 열에 "Analytics"가 표시됩니다. |
| 수동으로 세그먼트 매핑 | 이 옵션은 Analytics로 보낼 세그먼트를 선택할 수 있는 검색 및 검색 컨트롤을 표시합니다. <br>  세그먼트를 검색하려면 <br>  <ol><li>검색 필드에 세그먼트 이름 또는 ID를 입력합니다.</li><li>Click <b>Add.</b></li><li>세그먼트를 계속 검색하고 추가하거나 완료를 <b>클릭합니다</b>.</li></ol><br>  세그먼트를 찾으려면 <ol><li>모든 <b>세그먼트</b>찾아보기를 클릭합니다. 이렇게 하면 사용 가능한 세그먼트 목록이 표시됩니다.</li><li>목록에서 사용할 세그먼트의 확인란을 선택하고 선택한 세그먼트 <b>추가를 클릭합니다</b>.</li><li>매핑 <b>추가</b> 창에서 저장을 클릭합니다. 베타 릴리스 중에는 매핑, 시작 또는 종료 날짜를 변경할 수 없습니다.</li><li>계속해서 세그먼트를 찾아 추가하거나 완료를 <b>클릭합니다</b>.</li></ol> ![세그먼트](assets/mapSegments.png) |

## 다음 단계

대상을 만들고 저장한 후 Analytics에서 해당 데이터로 작업할 수 있습니다. 하지만 선택한 보고서 세트에서 데이터를 사용할 수 있으려면 몇 시간이 걸릴 수 있습니다. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).
