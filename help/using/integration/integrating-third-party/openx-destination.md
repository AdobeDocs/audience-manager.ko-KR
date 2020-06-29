---
description: OpenX를 대상으로 설정하고 Audience Manager 세그먼트 데이터를 해당 플랫폼에 보냅니다.
seo-description: OpenX를 대상으로 설정하고 Audience Manager 세그먼트 데이터를 해당 플랫폼에 보냅니다.
seo-title: OpenX를 Audience Manager 대상으로 사용
solution: Audience Manager
title: OpenX를 Audience Manager 대상으로 사용
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%

---


# OpenX를 Audience Manager 대상으로 사용{#openx-as-an-audience-manager-destination}

대상으로 설정하고 Audience Manager 세그먼트 데이터 [!DNL OpenX] 를 해당 플랫폼에 보냅니다.

>[!NOTE]
>
>온사이트 및 서버 타깃팅만

## OpenX 대상 요구 사항 {#openx-requirements}

코드 배치 표준, 지원되는 키-값 형식, 보고서 및 전송되는 세그먼트 데이터 유형에 대한 설명입니다 [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Audience Manager 대상으로 설정하기 전에 다음 [!DNL OpenX] 을 검토하십시오.

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library]코드를 사이트에 배포해야 합니다.[!UICONTROL DIL]데이터 수집, 통합, 쿠키 값 읽기 및 페이지 데이터 복구를 위한 특수 코드를 작성할 필요가 없습니다.
* **`get_aamCookie`함수:**Audience Manager 사용자 ID 및 쿠키 데이터를 캡처하는 코드입니다. 이 코드[를](../../features/destinations/get-aam-cookie-code.md)페이지 상단 또는`<head>`코드 블록 내에 배치합니다.
* **배달 로그를 Audience Manager으로 전송:** 세그먼트 배달 보고서(선택 사항)를 원하는 경우 노출 수준 배달 데이터가 포함된 일별 로그를 Audience Manager에 제공합니다. 데이터는 원시 형식일 수 있지만 각 레코드에는 Audience Manager이 포함되어야 합니다 `UUID`. Audience Manager은 이것을 수령하거나 받을 수 있다 [!DNL FTP].

### 키-값 데이터: 형식 요구 사항

Audience Manager은 키-값 쌍의 형태로 데이터를 전송합니다. 다음 사양에 따라 키-값 쌍을 만듭니다.

* 서문 키 `c.` (예: `c.color` 또는 `c.price`)
* 일련 번호가 할당된 값을 쉼표(예:,)로 단일 키에 `c.color = red, green, blue`연결합니다.
* 앰퍼샌드와 여러 개의 키-값 쌍을 `c.color=red & c.price = 100 & c.condition = new`구분합니다.
* 키 이름에는 악센트 부호와 구두점 표시 또는 기타 기호와 같은 특수 문자가 포함될 수 없습니다.

### 자격이 있는 세그먼트만 OpenX로 전송됩니다.

전달된 데이터 양은 특정 사용자가 [!DNL OpenX] 자격을 얻은 세그먼트 수에 따라 다릅니다. 예를 들어 100개의 Audience Manager 세그먼트를 설정했다고 가정해 봅시다. 사이트 방문자가 5개 자격을 얻는 경우 5개의 세그먼트만 [!DNL OpenX] 전송됩니다(100개 중 전부가 아님).

## OpenX 대상 만들기 {#openx-destination}

Audience Manager에 대한 쿠키 대상 [!DNL OpenX] 을 만듭니다.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) 입니다. [!UICONTROL Destination Builder] 는 이러한 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager 대상 기능은 *대상 데이터 > 대상에 있습니다*. 시작하려면 을( **[!UICONTROL Add New Destination]** 를) 클릭하고 아래 단계를 따르십시오.

### 1단계: 기본 정보

섹션을 완료하려면 [!UICONTROL Basic Information] 다음을 수행하십시오.

1. 대상의 이름을 지정합니다.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. 를 **[!UICONTROL Next]** 클릭하고 [!UICONTROL Configuration] 및 [!UICONTROL Segment Mappings] 섹션으로 이동합니다.

### 2단계: 구성 정보

섹션을 완료하려면 [!UICONTROL Configuration] 다음을 수행하십시오.

1. **쿠키 이름:** 쿠키에 대해 간단한 설명형 이름을 제공합니다.
1. **쿠키 도메인:** 사용자 현재 페이지의 도메인에 쿠키를 설정하려면 비워 두십시오. 도메인을 지정하려면 이름에 다음과 같은 마침표를 붙입니다 `.mydomain.com`.
1. 섹션에서 키 옵션을 [!UICONTROL Data Format] 선택합니다.
1. 키가 직렬화된 값과 함께 데이터를 사용하는 경우 컨트롤을 **[!UICONTROL Serialize]** 선택하고 일련 구분 기호(직렬화된 값을 구분하는 문자)를 지정합니다.
1. 섹션 **[!UICONTROL Save]** 을 클릭하고 [!UICONTROL Segment Mappings] 확장합니다.

### 3단계: 세그먼트 매핑

쿠키 대상에 세그먼트를 추가하려면:

1. **세그먼트 찾기:** 이 [!UICONTROL Segment Mappings] 섹션에는 세그먼트를 찾는 데 도움이 되는 두 개의 검색 도구가 제공됩니다. 세그먼트를 찾으려면
   * 옵션 1: 검색 필드에 세그먼트 이름을 입력하기 시작합니다. 필드는 텍스트를 기반으로 자동으로 업데이트됩니다. 사용할 세그먼트를 찾은 **[!UICONTROL Add]** 다음 을 클릭합니다.
   * 옵션 2: 이름 또는 저장소 위치별로 세그먼트를 검색할 수 있는 창을 열려면 을 클릭합니다 **[!UICONTROL Browse All Segments]** . 완료되면 을 **[!UICONTROL Add Selected Segments]** 클릭합니다.
1. **매핑 추가:** 매핑 팝업에서 매핑 필드에 세그먼트 ID를 입력하고 을 클릭합니다 **[!UICONTROL Save]**.
1. 클릭 **[!UICONTROL Done]**.

## OpenX 설치 {#openx-code-setup}

Audience Manager 세그먼트 데이터 [!DNL OpenX] 에서 작동하도록 설정을 수정합니다.

<!-- aam-openx-code.xml -->

설정하려면 [!DNL OpenX]:

* 사이트 전체에 [!UICONTROL DIL] 코드를 설치합니다.
* Audience Manager [!DNL OpenX] 에서 쿠키 대상으로 만듭니다.
* 페이지 맨 위에 `get_aamCookie` 함수를 배치하여 코드 블록 내에 `<head>` 배치하는 것이 좋습니다. 이 `get_aamCookie` 코드는 [여기에서 사용할 수 있습니다](../../features/destinations/get-aam-cookie-code.md).
* 함수를 호출하고 대상을 설정할 때 제공한 쿠키 이름을 포함하도록 광고 태그를 `get_aamCookie` [!DNL OpenX] 수정합니다. 예를 들어, 쿠키 이름을 지정한 경우 `test_cookie`광고 태그는 쿠키 이름 `get_aamCookie` 을 호출하고 참조해야 합니다.
* 광고 태그는 아래 예와 유사할 수 있습니다.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

를 포함해야 `xid=` 합니다. 광고 호출 중에 전달된 실제 고유 사용자 ID([!UICONTROL UUID])가 들어 있습니다.

전체 광고 호출은 다음과 비슷합니다.

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
