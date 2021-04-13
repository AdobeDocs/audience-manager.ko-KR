---
description: Open Ad Server를 대상으로 설정하고 Audience Manager 데이터를 해당 플랫폼에 보냅니다.
seo-description: Open Ad Server를 대상으로 설정하고 Audience Manager 데이터를 해당 플랫폼에 보냅니다.
seo-title: OAS를 Audience Manager 대상으로 사용
solution: Audience Manager
title: OAS를 Audience Manager 대상으로 사용
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: 타사 통합
exl-id: cf919c27-691f-424b-be83-040f03e34455
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 4%

---

# OAS를 Audience Manager 대상으로 사용 {#oas-as-an-audience-manager-destination}

[!DNL Open Ad Server]을(를) 대상으로 설정하고 Audience Manager 데이터를 해당 플랫폼에 보냅니다.

## OAS 대상 요구 사항 {#oas-requirements}

코드 배치 표준, 지원되는 키-값 형식, 보고서 및 [!DNL OAS]에 전송된 세그먼트 데이터의 유형에 대한 내용입니다.

<!-- aam-oas-requirements.xml -->

이 대상 유형에는 다음이 필요합니다.

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] 코드를 인벤토리에 배포해야 합니다. [!UICONTROL DIL] 데이터 수집, 통합, 쿠키 값 읽기 및 페이지 데이터 복구에 대한 특수 코드를 작성할 필요가 없습니다.
* **`get_aamCookie`함수:** Audience Manager 사용자 ID 및 쿠키 데이터를 캡처하는 코드입니다. [이 코드](../../features/destinations/get-aam-cookie-code.md)을(를) 페이지 위쪽이나 `<head>` 코드블록 내에 배치합니다.
* **Audience Manager에 배달 로그 보내기:** 세그먼트 배달 보고서를 원하는 경우(선택 사항) 노출 수준 배달 데이터가 포함된 일별 로그를 Audience Manager에 제공합니다. 데이터는 원시 형식일 수 있지만 각 레코드에는 Audience Manager [!UICONTROL UUID]이(가) 포함되어야 합니다. Audience Manager은 [!DNL FTP]을 통해 이러한 항목을 선택하거나 받을 수 있습니다.

### 쿠키 형식 및 키-값 데이터

Audience Manager은 다음과 같이 세그먼트 데이터를 브라우저 쿠키로 보낼 수 있습니다.

* 단일 키(`x=1&x=2`);
* 여러 키(`x=1&x=2&y=3&y=4`);
* 직렬화된 값(`x=1,2,3`);
* 개별 키-값 쌍을 구분하는 데 사용되는 표준 값 구분 기호.

### 자격이 있는 세그먼트만 OAS로 전송됩니다.

[!DNL OAS]에 전달된 데이터 양은 특정 사용자가 등록한 세그먼트 수에 따라 다릅니다. 예를 들어 100개의 Audience Manager 세그먼트를 설정했다고 가정해 보십시오. 사이트 방문자가 5개 중 자격을 얻으면 5개의 세그먼트만 OAS로 전송됩니다(100개 세그먼트 모두 아님).

>[!MORELIKETHIS]
>
>* [get_aamCookie 코드](../../features/destinations/get-aam-cookie-code.md)
>* [키-값 쌍 설명](../../reference/key-value-pairs-explained.md)


## OAS 대상 {#oas-dest-setup} 만들기

Audience Manager에서 [!DNL OAS]에 대한 쿠키 기반 대상을 만듭니다.

<!-- aam-oas-destination-setup.xml -->

Audience Manager에서 *destination*&#x200B;은 다른 모든 시스템(광고 서버, [!DNL DSP], 광고 네트워크 등)입니다. 입니다. [!UICONTROL Destination Builder] 는 이러한 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager 대상 기능은 *대상 데이터 > 대상*&#x200B;에 있습니다. 시작하려면 **[!UICONTROL Add New Destination]**&#x200B;을 클릭하고 아래 단계를 따르십시오.

### 1단계:기본 정보

[!UICONTROL Basic Information] 섹션을 완료하려면 다음을 수행하십시오.

1. 대상의 이름을 지정합니다.
1. [!UICONTROL Type] 드롭다운 목록에서 **[!UICONTROL "Cookie"]**&#x200B;을 선택합니다.
1. **[!UICONTROL Save]**&#x200B;을 클릭하고 [!UICONTROL Configuration] 및 [!UICONTROL Segment Mappings] 섹션으로 이동합니다.

### 2단계:구성 정보

[!UICONTROL Configuration] 섹션을 완료하려면 다음을 수행하십시오.

1. **쿠키 이름:** 쿠키에 대해 간단한 설명형 이름을 제공합니다.
1. **쿠키 도메인:** 사용자 현재 페이지의 도메인에 쿠키를 설정하려면 비워 둡니다. 도메인을 지정하려면 `.mydomain.com`과 같은 마침표로 이름을 접두사로 지정합니다.
1. [!UICONTROL Data Format] 섹션에서 키 옵션을 선택합니다.
1. 키가 직렬화된 값과 함께 데이터를 사용하는 경우 **[!UICONTROL Serialize]** 컨트롤을 선택하고 일련 구분 기호(직렬화된 값을 구분하는 문자)를 지정합니다.
1. **[!UICONTROL Save]**&#x200B;을 클릭하고 [!UICONTROL Segment Mappings] 섹션을 확장합니다.

### 3단계:세그먼트 매핑

쿠키 대상에 세그먼트를 추가하려면:

1. **세그먼트 찾기:** 이  [!UICONTROL Segment Mappings] 섹션은 세그먼트를 찾는 데 도움이 되는 2개의 검색 도구를 제공합니다. 세그먼트를 찾으려면:
   * 옵션 1:검색 필드에 세그먼트 이름을 입력하기 시작합니다. 이 필드는 텍스트를 기반으로 자동으로 업데이트됩니다. 사용할 세그먼트를 찾으면 **[!UICONTROL Add]**&#x200B;을 클릭합니다.
   * 옵션 2:이름 또는 저장소 위치별로 세그먼트를 검색할 수 있는 창을 열려면 **[!UICONTROL Browse All Segments]**&#x200B;을 클릭합니다. 완료되면 **[!UICONTROL Add Selected Segments]**&#x200B;을 클릭합니다.
1. **매핑 추가: 매핑** 팝업에서 매핑 필드에 세그먼트 ID를 입력하고 을  **[!UICONTROL Save]**&#x200B;클릭합니다.
1. 클릭 **[!UICONTROL Done]**.

## OAS 설정 {#oas-code-setup}

Audience Manager 세그먼트 데이터로 작업하려면 [!DNL OAS] 설정을 수정합니다.

<!-- aam-oas-code.xml -->

[!DNL OAS]을 설정하려면

* 사이트에 [!UICONTROL DIL] 코드를 설치합니다.
* Audience Manager에서 쿠키 대상으로 OAS를 만듭니다.
* `get_aamCookie` 함수를 페이지 맨 위에, 가장 좋은 방법은 `<head>` 코드블록 내에 배치합니다. `get_aamCookie` 코드는 [여기](../../features/destinations/get-aam-cookie-code.md)에서 사용할 수 있습니다.
* 광고 태그를 수정하여 `get_aamCookie` 함수를 호출하고 [!DNL OAS] 대상을 설정할 때 제공한 쿠키 이름을 포함합니다. 예를 들어 쿠키 이름을 `test_cookie`으로 지정한 경우 광고 태그는 `get_aamCookie`을 호출하고 쿠키 이름을 참조해야 합니다.
* 광고 태그는 아래 예와 비슷합니다.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

`u=` 변수를 포함해야 합니다. 광고 호출 동안 전달된 실제 고유 사용자 ID([!UICONTROL UUID])가 들어 있습니다.
