---
description: Open Ad Server를 대상으로 설정하고 Audience Manager 데이터를 해당 플랫폼으로 전송합니다.
seo-description: Open Ad Server를 대상으로 설정하고 Audience Manager 데이터를 해당 플랫폼으로 전송합니다.
seo-title: Audience Manager 대상으로 OAS 사용
solution: Audience Manager
title: Audience Manager 대상으로 OAS 사용
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Audience Manager 대상으로 OAS 사용 {#oas-as-an-audience-manager-destination}

대상으로 [!DNL Open Ad Server] 설정하고 Audience Manager 데이터를 해당 플랫폼으로 보냅니다.

## OAS 대상 요구 사항 {#oas-requirements}

코드 배치 표준, 지원되는 키-값 형식, 보고서 및 전송된 세그먼트 데이터 유형에 대한 [!DNL OAS]표준.

<!-- aam-oas-requirements.xml -->

이 대상 유형에는 다음이 필요합니다.

* **[!UICONTROL DIL]** :코드는 [!UICONTROL Data Integration Library] 인벤토리에 배포해야 합니다. [!UICONTROL DIL] 데이터 수집, 통합, 쿠키 값 읽기 및 페이지 데이터 복구에 대한 특수 코드를 작성할 필요가 없습니다.
* **`get_aamCookie`** 함수:Audience Manager 사용자 ID 및 쿠키 데이터를 캡처하는 코드입니다. 이 [코드를](../../features/destinations/get-aam-cookie-code.md) 페이지 위쪽이나 `<head>` 코드 블록에 배치합니다.
* **** Audience Manager로 배달 로그 보내기:세그먼트 배달 보고서를 원하는 경우(선택 사항), Audience Manager에 노출 수준 배달 데이터가 포함된 일별 로그를 제공합니다. 데이터는 원시 형식일 수 있지만 각 레코드에는 Audience Manager가 포함되어야 합니다 [!UICONTROL UUID]. Adobe Audience Manager는 이 기능을 통해 수신하거나 가져올 수 [!DNL FTP]있습니다.

### 쿠키 형식 및 키-값 데이터

Audience Manager는 다음과 같이 세그먼트 데이터를 브라우저 쿠키로 보낼 수 있습니다.

* 단일 키(`x=1&x=2`);
* 다중 키(`x=1&x=2&y=3&y=4`);
* 직렬화된 값(`x=1,2,3`);
* 개별 키-값 쌍을 구분하는 데 사용되는 표준 값 구분 기호.

### 자격이 있는 세그먼트만 OAS로 전송됩니다.

전달된 데이터 양은 특정 사용자가 자격을 얻은 세그먼트 수에 [!DNL OAS] 따라 다릅니다. 예를 들어 100개의 Audience Manager 세그먼트를 설정했다고 가정해 봅시다. 사이트 방문자가 5개의 자격을 갖춘 경우 이 5개의 세그먼트만 OAS로 전송됩니다(100개 중 전부가 아님).

>[!MORELIKETHIS]
>
>* [get_aamCookie 코드](../../features/destinations/get-aam-cookie-code.md)
>* [키-값 쌍 설명](../../reference/key-value-pairs-explained.md)


## OAS 대상 만들기 {#oas-dest-setup}

Audience Manager에서 쿠키 기반 대상을 [!DNL OAS] 만듭니다.

<!-- aam-oas-destination-setup.xml -->

Audience Manager에서 *대상은* 다른 시스템(광고 서버, [!DNL DSP]광고 네트워크 등)입니다. 데이터를 공유할 수 있습니다. [!UICONTROL Destination Builder] 에서는 이러한 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager 대상 기능은 대상 데이터 *&gt; 대상에 있습니다*. 시작하려면 을 클릭하고 아래 단계를 **[!UICONTROL Add New Destination]** 따르십시오.

### 1단계: 기본 정보

섹션을 완료하려면 [!UICONTROL Basic Information] 다음을 수행하십시오.

1. 대상의 이름을 지정합니다.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. 을 **[!UICONTROL Save]** 클릭하고 [!UICONTROL Configuration] 및 [!UICONTROL Segment Mappings] 섹션으로 이동합니다.

### 2단계:구성 정보

섹션을 완료하려면 [!UICONTROL Configuration] 다음을 수행하십시오.

1. **** 쿠키 이름:쿠키에 사용할 간단한 설명 이름을 제공합니다.
1. **** 쿠키 도메인:사용자 현재 페이지의 도메인에 쿠키를 설정하려면 비워 둡니다. 도메인을 지정하려면 이름 앞에 이와 같은 마침표를 붙입니다 `.mydomain.com`.
1. 섹션에서 주요 옵션을 [!UICONTROL Data Format] 선택합니다.
1. 키가 직렬화된 값과 함께 데이터를 사용하는 경우 **[!UICONTROL Serialize]** 컨트롤을 선택하고 일련 구분 기호(직렬화된 값을 구분하는 문자)를 지정합니다.
1. 을 **[!UICONTROL Save]** 클릭하고 [!UICONTROL Segment Mappings] 섹션을 확장합니다.

### 3단계:세그먼트 매핑

쿠키 대상에 세그먼트를 추가하려면:

1. **** 세그먼트 찾기:이 [!UICONTROL Segment Mappings] 섹션에서는 세그먼트를 찾는 데 도움이 되는 두 개의 검색 도구를 제공합니다. 세그먼트를 찾으려면
   * 옵션 1:검색 필드에 세그먼트 이름을 입력합니다. 필드는 텍스트를 기반으로 자동으로 업데이트됩니다. 사용할 세그먼트를 **[!UICONTROL Add]** 찾으면 클릭합니다.
   * 옵션 2:이름이나 저장소 위치별로 세그먼트를 검색할 수 있는 창을 **[!UICONTROL Browse All Segments]** 열려면 을 클릭합니다. Click **[!UICONTROL Add Selected Segments]** when done.
1. **** 매핑 추가:매핑 팝업에서 매핑 필드에 세그먼트 ID를 입력하고 을 **[!UICONTROL Save]**&#x200B;클릭합니다.
1. 클릭 **[!UICONTROL Done]**.

## OAS 설정 {#oas-code-setup}

Audience Manager 세그먼트 데이터와 연동되도록 [!DNL OAS] 설정을 수정합니다.

<!-- aam-oas-code.xml -->

설정하려면 [!DNL OAS]

* 사이트 전체에 [!UICONTROL DIL] 코드를 설치합니다.
* Audience Manager에서 쿠키 대상으로 OAS를 만듭니다.
* 페이지 맨 위에 `get_aamCookie` 함수를 배치하여 코드 `<head>` 블록 내에 배치하는 것이 좋습니다. 코드는 `get_aamCookie` 여기에서 [](../../features/destinations/get-aam-cookie-code.md)사용할 수 있습니다.
* 광고 태그를 수정하여 `get_aamCookie` 함수를 호출하고 [!DNL OAS] 대상을 설정할 때 제공한 쿠키 이름을 포함합니다. 예를 들어, 쿠키 이름을 `test_cookie``get_aamCookie` 지정한 경우 광고 태그는 쿠키 이름을 호출하고 참조해야 합니다.
* 광고 태그는 아래 예와 유사할 수 있습니다.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

반드시 `u=` 변수를 포함해야 합니다. 광고 호출 중에 전달된 실제 고유 사용자 ID([!UICONTROL UUID])가 들어 있습니다.
