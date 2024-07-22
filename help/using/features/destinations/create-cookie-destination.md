---
description: 쿠키 대상은 사용자 브라우저의 쿠키에 데이터를 반환하고 씁니다. 쿠키에는 페이지에 액세스할 수 있는 다른 플랫폼에서 읽을 수 있는 데이터가 포함되어 있습니다. [!UICONTROL Destination Builder]을(를) 사용하여 쿠키 대상을 만들려면 다음 지침을 따르십시오.
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: 쿠키 대상 구성
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---

# 쿠키 대상 구성 {#create-cookie-destination}

쿠키 대상은 사용자 브라우저의 쿠키에 데이터를 반환하고 씁니다. 쿠키에는 페이지에 액세스할 수 있는 다른 플랫폼에서 읽을 수 있는 데이터가 포함되어 있습니다. [!UICONTROL Destination Builder]을(를) 사용하여 쿠키 대상을 만들려면 다음 지침을 따르십시오.

<!-- create-cookie-destination.xml -->

새 쿠키 대상을 만들려면 **[!UICONTROL Audience Data > Destinations > Create New Destination]**(으)로 이동하여 아래 설명에 따라 섹션을 완료하십시오.

## 기본 정보 {#basic-information}

이 섹션에는 쿠키 대상 생성 프로세스를 시작하는 필드와 옵션이 포함되어 있습니다. 이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Basic Information]**&#x200B;을(를) 클릭합니다.
2. 대상 이름을 지정합니다. 약어 및 특수 문자를 사용하지 마십시오.
3. *(선택 사항)* 대상을 설명합니다. 간결한 설명은 대상에 대한 자세한 정보를 정의하거나 제공하는 효과적인 방법입니다.
4. **[!UICONTROL Category]** 목록에서 **[!UICONTROL Custom]**&#x200B;을(를) 선택합니다.
5. **[!UICONTROL Environment]** 목록에서 **[!UICONTROL Browser]**&#x200B;을(를) 선택합니다. Android 또는 iOS 앱과 같은 기본 모바일 환경에 대한 쿠키 대상을 구성할 수 없습니다.
6. **[!UICONTROL Type]** 목록에서 **[!UICONTROL Cookie]**&#x200B;을(를) 클릭합니다.
7. *(선택 사항)* **[!UICONTROL Auto-fill Destination Mapping]**&#x200B;을(를) 선택하십시오. 옵션은 다음과 같습니다.
   * **[!UICONTROL Segment ID]**: 세그먼트 ID를 대상에 자동으로 추가하고 보냅니다.
   * **[!UICONTROL Integration Code Value]**: 세그먼트 통합 코드를 대상 매핑에 자동으로 추가하고 전송합니다. 통합 코드는 고객이 만들고 사용하는 고유 식별자입니다. 최대 255자로 제한됩니다.
8. **[!UICONTROL Next]**&#x200B;을(를) 클릭하여 [!UICONTROL Configuration] 설정으로 이동하거나 **[!UICONTROL Data Export Labels]**&#x200B;을(를) 클릭하여 대상에 내보내기 컨트롤을 적용합니다.

## 데이터 내보내기 레이블 {#data-export-labels-cookies}

이 섹션에는 쿠키 대상에 [데이터 내보내기 제어](../../features/data-export-controls.md)를 적용하는 옵션이 포함되어 있습니다. 데이터 내보내기 컨트롤을 사용하지 않는 경우 이 단계를 건너뜁니다. 이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Data Export Labels]**&#x200B;을(를) 클릭합니다.
2. 대상에 적용된 데이터 내보내기 제어에 해당하는 레이블을 선택합니다(자세한 내용은 [대상에 내보내기 레이블 추가](/help/using/features/destinations/add-data-export-labels.md) 참조).
3. **[!UICONTROL Save]** 아이콘을 클릭합니다.

## 구성 {#configuration}

이 섹션에는 대상에 대한 쿠키를 설정할 수 있는 필드와 옵션이 포함되어 있습니다.

>[!NOTE]
>
>[!DNL Audience Manager]은(는) 대상 쿠키에 기록된 데이터를 인코딩합니다. 예를 들어 공백은 `%20`(으)로 인코딩되고 세미콜론은 `%3B`(으)로 인코딩됩니다.

이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Configuration]**&#x200B;을(를) 클릭하십시오.
1. 쿠키의 이름을 지정합니다. 약어 및 특수 문자를 사용하지 마십시오.
1. 데이터 형식 옵션을 선택합니다. 이러한 옵션을 사용하면 세그먼트 데이터를 대상으로 전송하는 키-값 쌍에 대해 구분 기호와 구분 기호를 선택할 수 있습니다. 형식 옵션은 다음과 같습니다.
   * **단일 키:** 키-값 쌍의 키를 설정할 수 있습니다. 아래 [!UICONTROL Segment Mappings] 섹션에서 세그먼트를 선택한 후 값을 설정합니다.
   * **다중 키:** 키-값 쌍의 키와 값을 설정할 수 있습니다. 아래 세그먼트 매핑 섹션에서 세그먼트를 선택하면 키-값 쌍을 만듭니다.
이러한 데이터 요소에 대한 자세한 내용은 [표준 및 일련 키-값 쌍](../../features/destinations/key-value-pairs.md)을 참조하십시오.
1. **[!UICONTROL Save]** 아이콘을 클릭합니다.

다른 모든 설정은 선택 사항입니다. **[!UICONTROL Cookie Domain]** 및 **[!UICONTROL Publish data to]** 설정에 대한 자세한 내용은 [쿠키 대상에 대한 선택적 설정](/help/using/features/destinations/cookie-destination-options.md)을 참조하십시오.

## 세그먼트 매핑 {#segments-mapping}

이 섹션에서는 세그먼트를 검색하고 대상에 추가할 수 있습니다. 이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Segment Mappings]**&#x200B;을(를) 클릭합니다.
1. **[!UICONTROL Search and Add Segments]** 상자에서 세그먼트 이름을 입력하거나 **[!UICONTROL Browse All Segments]**&#x200B;을 클릭하여 사용 가능한 세그먼트 목록을 찾아봅니다.
1. 사용할 세그먼트를 찾으면 **[!UICONTROL Add Selected Segments]**&#x200B;을(를) 클릭합니다. 세그먼트를 추가하면 [!UICONTROL Edit Mapping] 창이 열립니다.
1. [!UICONTROL Edit Mapping] 대화 상자에서:
   * **[!UICONTROL Mapping]**&#x200B;을(를) 사용하면 위의 구성 섹션에 지정된 키의 값을 설정할 수 있습니다.
   * **[!UICONTROL Publish from]**&#x200B;을(를) 사용하면 대상의 시작 및 종료 날짜를 설정할 수 있습니다. 종료 날짜가 비어 있으면 대상이 만료되지 않습니다.
1. **[!UICONTROL Save]** 아이콘을 클릭합니다.
1. **[!UICONTROL Done]** 아이콘을 클릭합니다.
