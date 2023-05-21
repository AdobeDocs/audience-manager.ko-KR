---
description: Open Ad Server를 대상으로 설정하고 Audience Manager 데이터를 해당 플랫폼으로 전송합니다.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS를 Audience Manager 대상으로 사용
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 4%

---

# OAS를 Audience Manager 대상으로 사용 {#oas-as-an-audience-manager-destination}

설정 [!DNL Open Ad Server] 를 대상으로 하여 해당 플랫폼으로 Audience Manager 데이터를 전송합니다.

## OAS 대상 요구 사항 {#oas-requirements}

코드 배치, 지원되는 키-값 형식, 보고서 및 로 전송되는 세그먼트 데이터의 유형에 대한 표준 [!DNL OAS].

<!-- aam-oas-requirements.xml -->

이 대상 유형에는 다음이 필요합니다.

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] 인벤토리에 코드를 배포해야 합니다. [!UICONTROL DIL] 를 사용하면 데이터 수집, 통합, 쿠키 값 읽기 및 페이지 데이터 복구를 위해 특수 코드를 작성할 필요가 없습니다.
* **`get_aamCookie`함수:** Audience Manager 사용자 ID 및 쿠키 데이터를 캡처하는 코드입니다. 위치 [이 코드](../../features/destinations/get-aam-cookie-code.md) 페이지 상단 또는 `<head>` 코드블록.
* **Audience Manager에 게재 로그 보내기:** 세그먼트 게재 보고서가 필요하면 Audience Manager에게 노출 수준 게재 데이터가 포함된 일별 로그를 제공합니다. 데이터는 원시 형식일 수 있지만 각 레코드에는 Audience Manager이 포함되어야 합니다 [!UICONTROL UUID]. Audience Manager은 를 통해 이러한 파일을 받거나 받을 수 있습니다. [!DNL FTP].

### 쿠키 형식 및 키-값 데이터

Audience Manager은 다음과 같이 세그먼트 데이터를 브라우저 쿠키에 보낼 수 있습니다.

* 단일 키 (`x=1&x=2`);
* 여러 키(`x=1&x=2&y=3&y=4`);
* 직렬화된 값 (`x=1,2,3`);
* 개별 키-값 쌍을 구분하는 데 사용되는 표준 값 구분 기호입니다.

### 적격 세그먼트만 OAS로 전송됩니다.

에 전달된 금액 데이터 [!DNL OAS] 특정 사용자가 사용할 수 있는 세그먼트 수에 따라 다릅니다. 예를 들어 100개의 Audience Manager 세그먼트를 설정한다고 가정해 보겠습니다. 사이트 방문자가 이 중 5개에 대한 자격이 있는 경우 해당 5개의 세그먼트만 OAS로 전송됩니다(100개 모두는 아님).

>[!MORELIKETHIS]
>
>* [get_aamCookie 코드](../../features/destinations/get-aam-cookie-code.md)
>* [키-값 쌍 설명](../../reference/key-value-pairs-explained.md)


## OAS 대상 만들기 {#oas-dest-setup}

에 대한 쿠키 기반 대상 만들기 [!DNL OAS] Audience Manager.

<!-- aam-oas-destination-setup.xml -->

Audience Manager에서 *대상* 다른 시스템(광고 서버, [!DNL DSP], 광고 네트워크 등) 입니다. [!UICONTROL Destination Builder] 는 이러한 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager 대상 기능은에 있습니다. *대상 데이터 > 대상*. 시작하려면 다음을 클릭하십시오. **[!UICONTROL Add New Destination]** 을(를) 클릭하고 아래 단계를 수행합니다.

### 1단계: 기본 정보

다음을 완료하려면 [!UICONTROL Basic Information] 섹션:

1. 대상 이름을 지정합니다.
1. 선택 **[!UICONTROL "Cookie"]** 다음에서 [!UICONTROL Type] 드롭다운 목록입니다.
1. 클릭 **[!UICONTROL Save]** 다음으로 이동: [!UICONTROL Configuration] 및 [!UICONTROL Segment Mappings] 섹션.

### 2단계: 구성 정보

다음을 완료하려면 [!UICONTROL Configuration] 섹션:

1. **쿠키 이름:** 쿠키를 설명하는 간단한 이름을 입력합니다.
1. **쿠키 도메인:** 사용자의 현재 페이지 도메인에 쿠키를 설정하려면 비워 둡니다. 도메인을 지정하려면 이름 앞에 마침표를 붙입니다. `.mydomain.com`.
1. 에서 키 옵션을 선택합니다. [!UICONTROL Data Format] 섹션.
1. 키가 직렬화된 값과 함께 데이터를 사용하는 경우 **[!UICONTROL Serialize]** 일련 구분 기호(serialized 값을 구분하는 문자)를 제어하고 지정합니다.
1. 클릭 **[!UICONTROL Save]** 및 확장 [!UICONTROL Segment Mappings] 섹션.

### 3단계: 세그먼트 매핑

쿠키 대상에 세그먼트를 추가하려면 다음 작업을 수행하십시오.

1. **세그먼트 찾기:** 다음 [!UICONTROL Segment Mappings] 섹션은 세그먼트를 찾는 데 도움이 되는 두 가지 검색 도구를 제공합니다. 세그먼트를 찾으려면
   * 옵션 1: 검색 필드에 세그먼트 이름을 입력하십시오. 필드는 텍스트에 따라 자동으로 업데이트됩니다. 클릭 **[!UICONTROL Add]** 사용할 세그먼트를 찾으면
   * 옵션 2: 클릭 **[!UICONTROL Browse All Segments]** 이름 또는 저장소 위치별로 세그먼트를 검색할 수 있는 창을 엽니다. 클릭 **[!UICONTROL Add Selected Segments]** 완료 시.
1. **매핑 추가:** 매핑 팝에서 매핑 필드에 세그먼트 ID를 입력하고 를 클릭합니다 **[!UICONTROL Save]**.
1. 클릭 **[!UICONTROL Done]**.

## OAS 설정 {#oas-code-setup}

수정 [!DNL OAS] Audience Manager 세그먼트 데이터로 작업할 설정입니다.

<!-- aam-oas-code.xml -->

설정하려면 [!DNL OAS]

* 설치 [!UICONTROL DIL] 코드를 사이트에 게시합니다.
* Audience Manager에서 OAS를 쿠키 대상으로 만듭니다.
* 배치 `get_aamCookie` 페이지 맨 위에서 작동합니다. 이상적으로는 `<head>` 코드블록. 다음 `get_aamCookie` 코드를 사용할 수 있음 [여기](../../features/destinations/get-aam-cookie-code.md).
* 광고 태그를 수정하여 `get_aamCookie` 함수 및 를 설정할 때 제공한 쿠키 이름을 포함합니다. [!DNL OAS] 대상. 예를 들어, 쿠키 이름을 지정한 경우 `test_cookie`, 그러면 광고 태그가 를 호출해야 합니다. `get_aamCookie` 쿠키 이름을 참조합니다.
* 광고 태그는 아래 예제와 유사할 수 있습니다.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

다음을 포함해야 합니다. `u=` 변수를 채우는 방법에 따라 페이지를 순서대로 표시합니다. 실제 고유 사용자 ID([!UICONTROL UUID]광고 호출 중에 가 전달되었습니다.
