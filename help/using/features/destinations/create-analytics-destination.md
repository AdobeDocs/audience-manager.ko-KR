---
description: Audience Analytics를 통해 Audience Manager 세그먼트를 Analytics에 보낼 수 있습니다. 이 기능을 사용하려면 Analytics 대상을 만들고 세그먼트를 Audience Manager의 대상에 매핑합니다.
seo-description: Audience Analytics를 통해 Audience Manager 세그먼트를 Analytics에 보낼 수 있습니다. 이 기능을 사용하려면 Analytics 대상을 만들고 세그먼트를 Audience Manager의 대상에 매핑합니다.
seo-title: Analytics 대상 구성
solution: Audience Manager
title: Analytics 대상 구성
translation-type: tm+mt
source-git-commit: 3179b9007e102f7031cc4cc9e0da64f77cfa3eeb

---


# Analytics 대상 구성

## 요구 사항 {#requirements}

[대상 분석을 참조하십시오](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## 기본 Analytics 대상 및 새 Analytics 대상

| Analytics 대상 유형 | 설명 |
|---|---|
| 기본값 | 이 기본 대상의 이름은 편집할 수 있는 &quot;Adobe Analytics&quot; 입니다. 매핑된 보고서 세트 ID는 Audience Manager 트레이트나 세그먼트에 대한 폴더 저장소에 표시됩니다. <br>Audience Manager는 계정이 다음과 같은 경우에 자동으로 하나의 대상을 만듭니다. <br> <ul><li>[대상 분석](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) 설명서에 설명된 요구 사항을 충족했습니다.</li><li>A [report suite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[보고서 세트를 조직에](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)매핑했습니다.</li></ul> |
| 신규 | 새 Analytics 대상을 만들려면 대상 데이터 &gt; 대상 &gt; 새 대상 만들기를 클릭하고 아래 설명된 각 섹션에 대한 단계를 따르십시오. |

## 1 단계: 기본 정보 제공

이 섹션에는 Analytics 대상 만들기 프로세스를 시작하는 필드 및 옵션이 포함되어 있습니다. 이 섹션을 완료하려면:

1. Click **Basic Information** to expose the controls.
2. 대상의 이름을 지정합니다. 약자 및 특수 문자를 사용하지 마십시오.
3. *(선택 사항)* 대상을 설명합니다. 간결한 설명은 대상에 대한 자세한 정보를 정의하거나 제공하는 효과적인 방법입니다.
4. *(선택 사항)* **플랫폼** 목록에서 기본 설정을 모두 [ **모두**] 로 설정합니다. 현재 이러한 옵션은 아무 작업도 수행하지 않습니다. 나중에 추가할 수 있는 기능을 지원하도록 설계되었습니다.
5. **범주** 목록에서 **Adobe Experience Cloud** 를 선택합니다.
6. **유형** 목록에서 **Adobe Analytics** 를 선택합니다.
7. **저장을** 클릭하여 구성 설정으로 이동하거나 **데이터 내보내기 레이블을** 클릭하여 대상에 내보내기 컨트롤을 적용합니다.

>[!NOTE]
>
>For an Analytics destination, the **Auto-fill Destination Mappping** check box and **Segment ID** option are selected by default. 이러한 설정은 변경할 수 없습니다.

![Basicinformation](assets/basicinformation.png)

## 2 단계: 데이터 내보내기 컨트롤 구성

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. 데이터 내보내기 컨트롤을 사용하지 않으면 이 단계를 건너뜁니다. 이 섹션을 완료하려면:

1. Click **Data Export Controls** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Data Export Labels to a Destination](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) ). Analytics 대상의 경우 기본적으로 PII 확인란이 선택됩니다.
3. **저장** 을 클릭합니다.

![Exportcontrols](assets/exportControls.png)

## 3 단계: 보고서 세트 매핑

구성 섹션에는 서버측 전달을 위해 활성화된 Analytics 보고서 세트가 나열됩니다. Analytics 대상이 여러 개 있는 경우, 이러한 대상에 할당된 보고서 세트는 Audience Manager에 의해 상호 배타적이고 적용됩니다. 이 섹션을 완료하려면:

1. Click **Configuration** to expose the controls.
2. 세그먼트를 보낼 하나 이상의 보고서 세트를 선택합니다.
3. **저장** 을 클릭합니다.

![Reportsuites](assets/reportSuites.png)

## 4 단계: 세그먼트 매핑

이 섹션에서는 세그먼트를 자동 또는 수동으로 매핑할 수 있는 옵션을 제공합니다.

| 매핑 옵션 | 설명 |
|---|---|
| 현재와 미래의 모든 세그먼트를 자동으로 매핑 | 기본적으로 선택된 이 기능은 방문자가 히트별로 자격을 갖춘 모든 세그먼트를 Analytics로 전송합니다. <br>방문자가 하나의 히트에서 150 개 이상의 Audience Manager 세그먼트에 속하는 경우 나머지 목록은 잘리지만 가장 최근에 자격을 갖춘 세그먼트만 Analytics로 전송됩니다. 세그먼트 목록이 잘렸음을 나타내는 추가 플래그가 Analytics에 전송됩니다. 이 작업은 대상 이름 차원에서 &quot;대상 제한 도달&quot; 로 표시되고 대상 ID 차원에서 &quot;1&quot; 로 표시됩니다. See the [FAQ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) for details. <br>또한 이 옵션은 세그먼트 빌더의 [대상 가용성에 영향을](/help/using/features/segments/segment-builder.md)줍니다. For example, if a segment is mapped automatically to an Analytics destination, that destination is not available for selection in the [destination mappings](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) section of Segment Builder. Analytics 대상이 회색으로 표시되고 대상 브라우저의 유형 열에 &quot;Analytics&quot; 가 표시됩니다. |
| 수동으로 세그먼트 매핑 | 이 옵션은 Analytics로 보낼 세그먼트를 선택할 수 있는 검색 및 탐색 컨트롤을 표시합니다. <br>세그먼트를 검색하려면 다음을 수행하십시오. <br> <ol><li>검색 필드에 세그먼트 이름이나 ID를 입력합니다.</li><li><b>추가를 클릭합니다.</b></li><li>Continue to search and add segments or click <b>Done</b>.</li></ol><br>세그먼트를 찾아보려면 다음을 수행하십시오. <ol><li>Click <b>Browse all segments</b>. 사용 가능한 세그먼트 목록이 표시됩니다.</li><li>From the list, select the check box of the segment you want to use and click <b>Add selected segments</b>.</li><li>Click <b>Save</b> in the Add Mappings window. 베타 릴리스 중에는 매핑, 시작 또는 종료 날짜를 변경할 수 없습니다.</li><li>Continue to browse and add segments or click <b>Done</b>.</li></ol> |

![Mapsegments](assets/mapSegments.png)

## 다음 단계

대상을 만들고 저장한 후 Analytics에서 해당 데이터를 사용할 수 있습니다. 하지만 선택한 보고서 세트에서 데이터를 사용할 수 있으려면 몇 시간이 걸릴 수 있습니다. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).



