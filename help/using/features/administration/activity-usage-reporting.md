---
description: 활동 사용량 보고를 사용하면 Audience Manager 인스턴스에 대한 활동 사용량을 보고 추적할 수 있으므로 실제 사용량을 계약 약정과 비교할 수 있습니다.
keywords: activity, usage, reporting, commitment
seo-description: 활동 사용량 보고를 사용하면 Audience Manager 인스턴스에 대한 활동 사용량을 보고 추적할 수 있으므로 실제 사용량을 계약 약정과 비교할 수 있습니다.
seo-title: 활동 사용량 보고
solution: Audience Manager
title: 활동 사용량 보고
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# 활동 사용량 보고

## 개요 {#overview}

이 [!UICONTROL Activity Usage Report] 보고서는 Audience Manager 인스턴스의 활동 사용을 보고 추적하는 데 도움이 되며, 사용자의 활동 사용이 계약 약정과 어떻게 비교되는지 명확하게 알려줍니다.

또한 필요할 때마다 기록 보관 및 사용자 지정 분석을 위해 [!UICONTROL Activity Usage Report] 언제든지 다운로드할 수 있습니다.

## 고려 사항 {#considerations}

이 [!UICONTROL Activity Usage Report] 기능은 [관리자 권한이](edit-account-settings.md)있는 모든 Audience Manager 사용자가 사용할 수 있습니다.

>[!IMPORTANT]
>
>이 [!UICONTROL Activity Usage Report] 보고서는 Audience Manager 인스턴스의 활동 사용 통계를 보여줍니다. 귀하의 활동 사용과 관련된 대금 청구 문의는 Adobe 담당자에게 문의하십시오.

## 사용 사례 {#use-cases}

두 가지 주요 사용 사례가 [!UICONTROL Activity Usage Report]있습니다.

* **활동 사용 약정에**&#x200B;대해 실제 인스턴스 활동 사용 추적:대부분의 고객은 Audience Manager 인스턴스당 월별 예상 활동 약정을 보유하고 있으며, 이 약정은 모든 인스턴스에 걸쳐 연간 활동 약정에 누적됩니다. 이 보고서는 청구 보고서가 아니지만, 귀하가 커밋된 활동 사용을 초과하는지 여부에 대한 유용한 지침을 제공할 수 있습니다.
* **구현 변경**&#x200B;확인:Analytics 서버측 전달 설정 또는 Target 서버 호출 설정 변경과 같은 최근 구현을 업데이트한 경우 이 보고서를 통해 새 활동 볼륨이 예상 활동 볼륨과 일치하는지 확인할 수 있습니다.

## 활동 사용량 보고서 사용 {#using}

Audience [!UICONTROL Activity Usage Report]Manager 계정에 로그인한 다음 **[!UICONTROL Administration]** > **[!UICONTROL Usage]**&#x200B;로 이동합니다.

![aur-ui](assets/aur-ui.png)

그런 다음 필터를 사용하여 **[!UICONTROL Reporting Interval]** 보고서를 생성할 시간 간격을 선택합니다. 30, 60, 90일 또는 사용자 지정 날짜 범위 중에서 선택할 수 있습니다.

보고서가 로드되면 선택한 기간 [!UICONTROL Activities] 동안의 분류를 볼 수 있습니다.

[!UICONTROL Activities] audience Manager를 사용하여 모든 온사이트 및 오프사이트 상호 작용의 총계를 정의하고, 다음 카테고리로 분할합니다.

* **[!UICONTROL Server Calls]**:웹 사이트, 서버, 이메일, 모바일 애플리케이션 또는 기타 시스템에서 Audience Manager로 전송되는 모든 데이터 수집 또는 검색 이벤트
* **[!UICONTROL Pixel Calls](이전 명칭[!UICONTROL Impression Server Calls]**:타깃팅 플랫폼의 임프레션 볼륨 등 광고 또는 Audience Manager에 대한 이메일 임프레션 호출에서 수집된 데이터 쿼리 문자열에 매개 변수가 있어야`d_event`합니다.
* **[!UICONTROL On-Boarded Records]**:고객 관계 관리 시스템(CRM) 또는 기타 오프라인 데이터 파일(예: 콜 센터 레코드, 디바이스 ID, 외부 데이터 공급자의 사용자 지정 데이터 피드)에서 수집되는 고유 레코드
* **[!UICONTROL Log File Records]**:타깃팅 플랫폼에서 Audience Manager로 인제스트된 로그 파일의 고유 레코드.

>[!NOTE]
>
>고유 레코드는 Audience Manager 고객을 대신하여 Adobe가 저장한 파일의 각 데이터 레코드를 정의합니다.

또한 그래프 유형을 사용하여 두 유형의 그래프 간을 전환할 수 있습니다. [!UICONTROL Activity Usage Trends]

![aur-ui 그래프](assets/aur-ui-graphs.png)

타임라인에서 특정 날짜 위로 커서를 가져가면 해당 날짜에 대한 자세한 사용을 확인할 수 있습니다.

![aur-hover](assets/aur-hover.png)

## 활동 사용량 보고서 내보내기 {#export}

Audience Manager 활동 사용 수준에 대한 더 나은 개요를 보려면 포함할 레코드 유형을 [!UICONTROL Activity Usage Report] 기반으로 내보내면 됩니다.

![aur-export](assets/aur-export.png)

이 **[!UICONTROL Onboarded Records Breakdown]** 및 **[!UICONTROL Onsite Server Calls Breakdown]** 보고서는 이러한 활동에 사용할 수 있는 소스 데이터에 대한 가장 세부적인 통찰력을 제공합니다. 이러한 분류로 인한 볼륨은 구현에 따라 다릅니다.

### 온보드 레코드 분류 {#onboarded-breakdown}

이 보고서에는 데이터 소스별로 분류된 온보드 레코드가 포함되어 있습니다.

### 온사이트 서버 호출 분류 {#onsite-breakdown}

이 보고서에는 세 가지 소스의 서버 호출 분류가 포함되어 있습니다. [!UICONTROL Analytics]및 [!UICONTROL Target]를 [!UICONTROL Other]참조하십시오.

* **[!UICONTROL Analytics]**:서버 측 전달을 포함하여 모든 Adobe Analytics 인스턴스에서 Audience Manager로 전달된 과금 가능한 서버 호출입니다. 보조 서버 호출 또는 중복 서버 호출(여러 보고서 세트의 서버측 전달의 경우)은 청구 가능한 활동이 아니므로 이 분류에는 포함되지 않습니다.
* **[!UICONTROL Target]**:서버 간 통합의 일부로 Audience Manager 세그먼트 데이터를 검색하기 위해 Adobe Target에서 Audience Manager에 대한 서버측 호출입니다.
* **[!UICONTROL Other]**:다른 웹 사이트 또는 시스템(파트너 사이트, 직접 서버 호출 등), 모바일 브라우저/앱 호출( [!DNL SDK]이벤트 [!DNL DIL]호출 및 [!DNL DCS] 호출을 통한 호출)을 포함합니다. 또한 쿠키 통합으로 설정된 [!DNL Target] 경우(서버 간 통합이 아니라) 호출을 포함합니다.
