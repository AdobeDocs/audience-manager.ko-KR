---
description: 활동 사용량 보고는 Audience Manager 인스턴스에 대한 활동 사용량을 보고 추적하는 데 도움이 되므로 실제 사용량을 계약 약정과 비교할 수 있습니다.
keywords: 활동, 사용, 보고, 약정
seo-description: Activity Usage Reporting helps you view and track the activity usage for your Audience Manager instance, so you can compare your actual usage to your contractual commitment.
seo-title: Activity Usage Reporting
solution: Audience Manager
title: 활동 사용 보고
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## 개요 {#overview}

[!UICONTROL Activity Usage Report]는 Audience Manager 인스턴스의 활동 사용을 보고 추적하는 데 도움이 되며, 사용자의 활동 사용이 계약 약정과 비교하여 어떤지 알 수 있습니다.

또한 레코드 보관 및 사용자 지정 분석을 위해 필요할 때마다 [!UICONTROL Activity Usage Report]을(를) 다운로드할 수 있습니다.

## 고려 사항 {#considerations}

[!UICONTROL Activity Usage Report]은(는) [관리자 권한](edit-account-settings.md)을 가진 모든 Audience Manager 사용자가 사용할 수 있습니다.

>[!IMPORTANT]
>
>[!UICONTROL Activity Usage Report]은(는) Audience Manager 인스턴스의 활동 사용 통계를 보여 줍니다. 활동 사용과 관련된 청구 문의는 Adobe 담당자에게 문의하십시오.

## 사용 사례 {#use-cases}

[!UICONTROL Activity Usage Report]에는 두 가지 기본 사용 사례가 있습니다.

* **활동 사용 약정에 대한 실제 인스턴스 활동 사용량 추적**: 대부분의 고객은 Audience Manager 인스턴스당 월간 예상 활동 약정을 가지고 있으며, 이는 모든 인스턴스에 대해 연간 활동 약정으로 누적됩니다. 이 보고서는 청구 보고서가 아니지만 커밋된 활동 사용량을 초과하는지 여부에 대한 유용한 지침을 제공할 수 있습니다.
* **구현 변경에 대한 유효성 검사**: [!DNL Adobe Analytics] 서버측 전달 설정 또는 [!DNL Adobe Target] 서버 호출 설정 변경과 같이 최근 구현을 업데이트한 경우 이 보고서를 통해 새 활동 볼륨이 예상 활동 볼륨과 일치하는지 여부를 확인할 수 있습니다.

## [!UICONTROL Activity Usage Report] 사용 {#using}

[!UICONTROL Activity Usage Report]을(를) 보려면 Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** > **[!UICONTROL Usage]**(으)로 이동하십시오.

![aur-ui](assets/aur-ui.png)

그런 다음 **[!UICONTROL Reporting Interval]** 필터를 사용하여 보고서를 생성할 시간 간격을 선택합니다. 30일, 60일, 90일 또는 사용자 지정 날짜 범위 중에서 선택할 수 있습니다.

보고서가 로드되면 선택한 기간 동안 [!UICONTROL Activities]의 분류를 볼 수 있습니다.

[!UICONTROL Activities]은(는) Audience Manager을 통한 모든 온사이트 및 오프사이트 상호 작용의 합계를 다음 범주로 분할합니다.

* **[!UICONTROL Server Calls]**: 웹 사이트, 서버, 이메일, 모바일 애플리케이션 또는 기타 시스템에서 Audience Manager에게 전송된 데이터 수집 또는 검색 이벤트입니다.
* **[!UICONTROL Pixel Calls] (이전 이름: [!UICONTROL Impression Server Calls])**: Audience Manager에 대해 수행된 광고(예: 타깃팅 플랫폼의 노출 볼륨) 또는 이메일 노출 호출에서 수집된 데이터. 쿼리 문자열에 `d_event` 매개 변수가 있어야 합니다.
* **[!UICONTROL On-Boarded Records]**: 고유한 CRM(고객 관계 관리 시스템) 또는 기타 오프라인 데이터 파일에서 수집한 고유한 레코드(예: 콜센터 레코드, 장치 ID 및 외부 데이터 공급자의 사용자 지정 데이터 피드)입니다.
* **[!UICONTROL Log File Records]**: 타깃팅 플랫폼에서 Audience Manager으로 수집된 로그 파일의 고유 레코드.

>[!NOTE]
>
>고유한 레코드는 Audience Manager 고객을 대신하여 Adobe이 저장한 파일에 있는 데이터의 각 개별 레코드를 정의합니다.

또한 [!UICONTROL Activity Usage Trends] 그래프 형식을 사용하여 두 종류의 그래프 사이를 전환할 수 있습니다.

![aur-ui-graphs](assets/aur-ui-graphs.png)

타임라인의 특정 날짜 위에 커서를 놓으면 해당 날짜에 대한 세부 사용량을 볼 수도 있습니다.

![마우스 오버](assets/aur-hover.png)

## [!UICONTROL Activity Usage Reports] 내보내기 {#export}

Audience Manager 활동 사용 수준에 대한 더 나은 개요를 보려면 포함하려는 레코드 유형에 따라 [!UICONTROL Activity Usage Report]을(를) 내보낼 수 있습니다.

![aur-export](assets/aur-export.png)

**[!UICONTROL Onboarded Records Breakdown]** 및 **[!UICONTROL Onsite Server Calls Breakdown]** 보고서는 이러한 활동에 사용할 수 있는 소스 데이터에 대한 가장 세부적인 통찰력을 제공합니다. 이러한 분류로 인한 볼륨은 구현을 기반으로 합니다.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

이 보고서에는 데이터 소스별로 분류된 온보딩된 레코드가 포함되어 있습니다.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

이 보고서에는 [!UICONTROL Analytics], [!UICONTROL Target] 및 [!UICONTROL Other] 원본 세 곳에서 발생한 서버 호출 분류가 포함되어 있습니다.

* **[!UICONTROL Analytics]**: 서버측 전달을 포함하여 모든 [!UICONTROL Adobe Analytics] 인스턴스에서 Audience Manager으로 전달되는 청구 가능한 서버 호출입니다. 보조 서버 호출 또는 중복 서버 호출 (여러 보고서 세트에서 서버측 전달의 경우와 같이)은 청구 가능 활동이 아니므로 이 분류에 포함되지 않습니다.
* **[!UICONTROL Target]**: 서버 간 통합의 일부로 Audience Manager 세그먼트 데이터를 검색하기 위해 [!UICONTROL Adobe Target]에서 Audience Manager으로 보내는 서버측 호출입니다.
* **[!UICONTROL Other]**: 다른 웹 사이트 또는 시스템의 호출(파트너 사이트, 직접 서버 호출 등), [!DNL SDK], [!DNL DIL], 이벤트 호출 및 [!DNL DCS] 호출을 통한 모바일 브라우저/앱 호출을 포함합니다. 또한 서버 간 통합이 아닌 쿠키 통합으로 설정된 경우 [!DNL Target]의 호출도 포함합니다.
