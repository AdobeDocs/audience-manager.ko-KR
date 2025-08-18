---
description: Open Ad Server를 대상으로 설정하고 Audience Manager 데이터를 해당 플랫폼으로 전송합니다.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS as a Audience Manager 대상
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 0%

---

# OAS as a Audience Manager 대상 {#oas-as-an-audience-manager-destination}

[!DNL Open Ad Server]을(를) 대상으로 설정하고 해당 플랫폼으로 Audience Manager 데이터를 보냅니다.

## OAS 대상 요구 사항 {#oas-requirements}

코드 배치, 지원되는 키-값 형식, 보고서 및 [!DNL OAS]&#x200B;(으)로 전송되는 세그먼트 데이터의 유형에 대한 표준입니다.

<!-- aam-oas-requirements.xml -->

이 대상 유형에는 다음이 필요합니다.

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] 코드를 인벤토리에 배포해야 합니다. [!UICONTROL DIL]을(를) 사용하면 데이터 수집, 통합, 쿠키 값 읽기 및 페이지 데이터 복구를 위해 특수 코드를 작성할 필요가 없습니다.
* **`get_aamCookie`함수:** Audience Manager 사용자 ID 및 쿠키 데이터를 캡처하는 코드입니다. [이 코드](../../features/destinations/get-aam-cookie-code.md)을(를) 페이지 맨 위나 `<head>` 코드 블록 내부에 배치합니다.
* **Audience Manager에 게재 로그 보내기:** 세그먼트 게재 보고서(선택 사항)를 원하는 경우 노출 수준 게재 데이터가 포함된 일별 로그를 Audience Manager에 제공하십시오. 데이터는 원시 형식일 수 있지만 각 레코드에는 Audience Manager [!UICONTROL UUID]이(가) 포함되어야 합니다. Audience Manager은 [!DNL FTP]을(를) 통해 이러한 파일을 받거나 받을 수 있습니다.

### 쿠키 형식 및 키-값 데이터

Audience Manager은 다음과 같이 세그먼트 데이터를 브라우저 쿠키에 보낼 수 있습니다.

* 단일 키(`x=1&x=2`);
* 여러 키(`x=1&x=2&y=3&y=4`);
* 직렬화된 값(`x=1,2,3`);
* 개별 키-값 쌍을 구분하는 데 사용되는 표준 값 구분 기호입니다.

### 적격 세그먼트만 OAS로 전송됩니다.

[!DNL OAS]에 전달되는 양 데이터는 특정 사용자가 사용할 수 있는 세그먼트 수에 따라 다릅니다. 예를 들어 100개의 Audience Manager 세그먼트를 설정한다고 가정합니다. 사이트 방문자가 이 중 5개에 대한 자격이 있는 경우 해당 5개의 세그먼트만 OAS로 전송됩니다(100개 모두는 아님).

>[!MORELIKETHIS]
>
>* [get_aamCookie 코드](../../features/destinations/get-aam-cookie-code.md)
>* [키-값 쌍 설명](../../reference/key-value-pairs-explained.md)

## OAS 대상 만들기 {#oas-dest-setup}

Audience Manager에서 [!DNL OAS]에 대한 쿠키 기반 대상을 만듭니다.

<!-- aam-oas-destination-setup.xml -->

Audience Manager에서 *대상*&#x200B;은(는) 데이터를 공유할 다른 시스템(광고 서버, [!DNL DSP], 광고 네트워크 등)입니다. [!UICONTROL Destination Builder]은(는) 이러한 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager 대상 기능은 *대상 데이터 > 대상*&#x200B;에 있습니다. 시작하려면 **[!UICONTROL Add New Destination]**&#x200B;을(를) 클릭하고 아래 단계를 따르십시오.

### 1단계: 기본 정보

[!UICONTROL Basic Information] 섹션을 완료하려면

1. 대상 이름을 지정합니다.
1. **[!UICONTROL "Cookie"]** 드롭다운 목록에서 [!UICONTROL Type] 선택.
1. **[!UICONTROL Save]**&#x200B;을(를) 클릭하고 [!UICONTROL Configuration] 및 [!UICONTROL Segment Mappings] 섹션으로 이동합니다.

### 2단계: 구성 정보

[!UICONTROL Configuration] 섹션을 완료하려면

1. **쿠키 이름:** 쿠키에 대해 짧고 설명적인 이름을 제공합니다.
1. **쿠키 도메인:** 사용자의 현재 페이지에 있는 도메인에 쿠키를 설정하려면 비워 둡니다. 도메인을 지정하려면 `.mydomain.com`과(와) 같이 이름 접두사에 마침표를 붙입니다.
1. [!UICONTROL Data Format] 섹션에서 키 옵션을 선택하십시오.
1. 키가 serialize된 값과 함께 데이터를 사용하는 경우 **[!UICONTROL Serialize]** 컨트롤을 선택하고 serialize 구분 기호(serialize된 값을 구분하는 문자)를 지정합니다.
1. **[!UICONTROL Save]**&#x200B;을(를) 클릭하고 [!UICONTROL Segment Mappings] 섹션을 확장합니다.

### 3단계: 세그먼트 매핑

쿠키 대상에 세그먼트를 추가하려면 다음 작업을 수행하십시오.

1. **세그먼트 찾기:** [!UICONTROL Segment Mappings] 섹션에서는 세그먼트를 찾는 데 도움이 되는 두 가지 검색 도구를 제공합니다. 세그먼트를 찾으려면
   * 옵션 1: 검색 필드에 세그먼트 이름을 입력하십시오. 필드는 텍스트에 따라 자동으로 업데이트됩니다. 사용할 세그먼트를 찾으면 **[!UICONTROL Add]**&#x200B;을(를) 클릭합니다.
   * 옵션 2: **[!UICONTROL Browse All Segments]**&#x200B;을(를) 클릭하여 이름 또는 저장소 위치별로 세그먼트를 검색할 수 있는 창을 엽니다. 완료되면 **[!UICONTROL Add Selected Segments]**&#x200B;을(를) 클릭합니다.
1. **매핑 추가:** 매핑 팝업에서 매핑 필드에 세그먼트 ID를 입력하고 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.
1. **[!UICONTROL Done]** 아이콘을 클릭합니다.

## OAS 설정 {#oas-code-setup}

Audience Manager 세그먼트 데이터를 사용하도록 [!DNL OAS] 설정을 수정하십시오.

<!-- aam-oas-code.xml -->

[!DNL OAS] 설정

* 사이트에 [!UICONTROL DIL] 코드를 설치합니다.
* Audience Manager에서 OAS를 쿠키 대상으로 만듭니다.
* `get_aamCookie` 함수를 페이지의 맨 위에 배치합니다. `<head>` 코드 블록 내에 이상적으로 배치하십시오. `get_aamCookie` 코드는 [여기](../../features/destinations/get-aam-cookie-code.md)에서 사용할 수 있습니다.
* 광고 태그를 수정하여 `get_aamCookie` 함수를 호출하고 [!DNL OAS] 대상을 설정할 때 제공한 쿠키 이름을 포함하십시오. 예를 들어 쿠키 이름을 `test_cookie`로 지정한 경우 광고 태그는 `get_aamCookie`을(를) 호출하고 쿠키 이름을 참조해야 합니다.
* 광고 태그는 아래 예제와 유사할 수 있습니다.

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

`u=` 변수를 포함해야 합니다. 광고 호출 중에 전달된 실제 고유 사용자 ID([!UICONTROL UUID])가 있습니다.
