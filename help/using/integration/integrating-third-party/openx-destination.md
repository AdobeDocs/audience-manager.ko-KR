---
description: OpenX를 대상으로 설정하고 Audience Manager 세그먼트 데이터를 해당 플랫폼으로 전송합니다.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX를 Audience Manager 대상으로 사용
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 2%

---

# OpenX를 Audience Manager 대상으로 사용{#openx-as-an-audience-manager-destination}

설정 [!DNL OpenX] 를 대상으로 하고 Audience Manager 세그먼트 데이터를 해당 플랫폼으로 보냅니다.

>[!NOTE]
>
>온사이트 광고 서버 타깃팅만 해당.

## OpenX 대상 요구 사항 {#openx-requirements}

코드 배치, 지원되는 키-값 형식, 보고서 및 로 전송되는 세그먼트 데이터의 유형에 대한 표준 [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

설정하기 전에 다음 사항을 검토하십시오 [!DNL OpenX] Audience Manager 대상:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] 사이트에 코드를 배포해야 합니다. [!UICONTROL DIL] 를 사용하면 데이터 수집, 통합, 쿠키 값 읽기 및 페이지 데이터 복구를 위해 특수 코드를 작성할 필요가 없습니다.
* **`get_aamCookie`함수:** Audience Manager 사용자 ID 및 쿠키 데이터를 캡처하는 코드입니다. 위치 [이 코드](../../features/destinations/get-aam-cookie-code.md) 페이지 상단 또는 `<head>` 코드블록.
* **Audience Manager에 게재 로그 보내기:** 세그먼트 게재 보고서가 필요하면 Audience Manager에게 노출 수준 게재 데이터가 포함된 일별 로그를 제공합니다. 데이터는 원시 형식일 수 있지만 각 레코드에는 Audience Manager이 포함되어야 합니다 `UUID`. Audience Manager은 를 통해 이러한 파일을 받거나 받을 수 있습니다. [!DNL FTP].

### 키-값 데이터: 형식 요구 사항

Audience Manager은 데이터를 키-값 쌍의 형태로 전송합니다. 다음 사양에 따라 키-값 쌍을 만듭니다.

* 키를 앞에 놓기 `c.` (예: `c.color` 또는 `c.price`).
* 단일 키에 첨부된 직렬화된 값을 쉼표로 구분합니다(예: `c.color = red, green, blue`).
* 여러 키-값 쌍을 앰퍼샌드로 구분합니다(예: `c.color=red & c.price = 100 & c.condition = new`).
* 키 이름에는 악센트 및 구두점 기호나 기타 기호와 같은 특수 문자가 포함되어서는 안 됩니다.

### 적격한 세그먼트만 OpenX로 전송됩니다.

에 전달된 금액 데이터 [!DNL OpenX] 특정 사용자가 사용할 수 있는 세그먼트 수에 따라 다릅니다. 예를 들어 100개의 Audience Manager 세그먼트를 설정한다고 가정해 보겠습니다. 사이트 방문자가 이 중 5개에 대한 자격이 있는 경우 해당 5개의 세그먼트만 [!DNL OpenX] (100개 중 일부만).

## OpenX 대상 만들기 {#openx-destination}

에 대한 쿠키 대상 만들기 [!DNL OpenX] Audience Manager.

<!-- aam-openx-destination.xml -->

Audience Manager에서 *대상* 다른 시스템(광고 서버, [!DNL DSP], 광고 네트워크 등) 입니다. [!UICONTROL Destination Builder] 는 이러한 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager 대상 기능은에 있습니다. *대상 데이터 > 대상*. 시작하려면 다음을 클릭하십시오. **[!UICONTROL Add New Destination]** 을(를) 클릭하고 아래 단계를 수행합니다.

### 1단계: 기본 정보

다음을 완료하려면 [!UICONTROL Basic Information] 섹션:

1. 대상 이름을 지정합니다.
1. 선택 **[!UICONTROL "Cookie"]** 다음에서 [!UICONTROL Type] 드롭다운 목록입니다.
1. 클릭 **[!UICONTROL Next]** 다음으로 이동: [!UICONTROL Configuration] 및 [!UICONTROL Segment Mappings] 섹션.

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

## OpenX 설정 {#openx-code-setup}

수정 [!DNL OpenX] Audience Manager 세그먼트 데이터로 작업할 설정입니다.

<!-- aam-openx-code.xml -->

설정하려면 [!DNL OpenX]:

* 설치 [!UICONTROL DIL] 코드를 사이트에 게시합니다.
* 만들기 [!DNL OpenX] Audience Manager에서 쿠키 대상으로 사용됩니다.
* 배치 `get_aamCookie` 페이지 맨 위에서 작동합니다. 이상적으로는 `<head>` 코드블록. 다음 `get_aamCookie` 코드를 사용할 수 있음 [여기](../../features/destinations/get-aam-cookie-code.md).
* 광고 태그를 수정하여 `get_aamCookie` 함수 및 를 설정할 때 제공한 쿠키 이름을 포함합니다. [!DNL OpenX] 대상. 예를 들어, 쿠키 이름을 지정한 경우 `test_cookie`, 그러면 광고 태그가 를 호출해야 합니다. `get_aamCookie` 쿠키 이름을 참조합니다.
* 광고 태그는 아래 예제와 유사할 수 있습니다.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

다음을 포함해야 합니다. `xid=` . 실제 고유 사용자 ID([!UICONTROL UUID]광고 호출 중에 가 전달되었습니다.

전체 형식의 광고 호출은 다음과 유사할 수 있습니다.

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
