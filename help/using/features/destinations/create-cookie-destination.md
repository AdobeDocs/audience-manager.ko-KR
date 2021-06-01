---
description: 쿠키 대상은 사용자 브라우저의 쿠키에 데이터를 반환하고 기록합니다. 쿠키에는 페이지에 대한 액세스 권한이 있는 다른 플랫폼에서 읽을 수 있는 데이터가 포함되어 있습니다. 다음 지침에 따라 [!UICONTROL Destination Builder]을 사용하여 쿠키 대상을 만듭니다.
seo-description: 쿠키 대상은 사용자 브라우저의 쿠키에 데이터를 반환하고 기록합니다. 쿠키에는 페이지에 대한 액세스 권한이 있는 다른 플랫폼에서 읽을 수 있는 데이터가 포함되어 있습니다. 다음 지침에 따라 [!UICONTROL Destination Builder]을 사용하여 쿠키 대상을 만듭니다.
seo-title: 쿠키 대상 구성
solution: Audience Manager
title: 쿠키 대상 구성
feature: 대상 기본 사항
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 3%

---

# 쿠키 대상 구성 {#create-cookie-destination}

쿠키 대상은 사용자 브라우저의 쿠키에 데이터를 반환하고 기록합니다. 쿠키에는 페이지에 대한 액세스 권한이 있는 다른 플랫폼에서 읽을 수 있는 데이터가 포함되어 있습니다. 다음 지침에 따라 [!UICONTROL Destination Builder]을 사용하여 쿠키 대상을 만듭니다.

<!-- create-cookie-destination.xml -->

새 쿠키 대상을 만들려면 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 로 이동하여 아래 설명된 대로 섹션을 완료합니다.

## 기본 정보 {#basic-information}

이 섹션에는 쿠키 대상 만들기 프로세스를 시작하는 필드 및 옵션이 포함되어 있습니다. 이 섹션을 완료하려면

1. **[!UICONTROL Basic Information]** 을 클릭하여 컨트롤을 표시합니다.
2. 대상에 이름을 지정합니다. 약자 및 특수 문자는 사용하지 마십시오.
3. *(선택 사항)* 대상을 설명합니다. 간결한 설명은 대상에 대한 자세한 정보를 정의하거나 제공하는 효과적인 방법입니다.
4. **[!UICONTROL Category]** 목록에서 **[!UICONTROL Custom]** 을 선택합니다.
5. **[!UICONTROL Environment]** 목록에서 **[!UICONTROL Browser]** 을 선택합니다. Android 또는 iOS 앱과 같은 기본 모바일 환경에 대한 쿠키 대상을 구성할 수 없습니다.
6. **[!UICONTROL Type]** 목록에서 **[!UICONTROL Cookie]** 를 클릭합니다.
7. *(선택 사항)* 을  **[!UICONTROL Auto-fill Destination Mapping]**&#x200B;선택합니다. 옵션은 다음과 같습니다.
   * **[!UICONTROL Segment ID]**:자동으로 세그먼트 ID를 추가하여 대상에 전송합니다.
   * **[!UICONTROL Integration Code Value]**:세그먼트 통합 코드를 자동으로 추가하여 대상 매핑에 전송합니다. 통합 코드는 고객이 만들고 사용하는 고유 식별자입니다. 최대 255자로 제한됩니다.
8. **[!UICONTROL Next]** 을 클릭하여 [!UICONTROL Configuration] 설정으로 이동하거나 **[!UICONTROL Data Export Labels]** 를 클릭하여 내보내기 컨트롤을 대상에 적용합니다.

## 데이터 내보내기 레이블 {#data-export-labels-cookies}

이 섹션에는 [데이터 내보내기 컨트롤](../../features/data-export-controls.md)을 쿠키 대상에 적용하는 옵션이 포함되어 있습니다. 데이터 내보내기 컨트롤을 사용하지 않는 경우 이 단계를 건너뜁니다. 이 섹션을 완료하려면

1. **[!UICONTROL Data Export Labels]** 을 클릭하여 컨트롤을 표시합니다.
2. 대상에 적용된 데이터 내보내기 컨트롤에 해당하는 레이블을 선택합니다(자세한 내용은 [대상에 내보내기 레이블 추가](/help/using/features/destinations/add-data-export-labels.md) 참조).
3. 클릭 **[!UICONTROL Save]**.

## 구성 {#configuration}

이 섹션에는 대상에 대한 쿠키를 설정할 수 있는 필드와 옵션이 포함되어 있습니다.

>[!NOTE]
>
>[!DNL Audience Manager] 대상 쿠키에 작성된 데이터를 인코딩합니다. 예를 들어 공백은 `%20` 로 인코딩되고 세미콜론은 `%3B` 로 인코딩됩니다.

이 섹션을 완료하려면

1. **[!UICONTROL Configuration]** 을 클릭하여 컨트롤을 표시합니다
1. 쿠키 이름을 지정합니다. 약자 및 특수 문자는 사용하지 마십시오.
1. 데이터 형식 옵션을 선택합니다. 이러한 옵션을 사용하면 세그먼트 데이터를 대상으로 보내는 키-값 쌍에 대한 구분 기호와 구분자를 선택할 수 있습니다. 서식 옵션은 다음과 같습니다.
   * **단일 키:**  키-값 쌍에 키를 설정할 수 있도록 해줍니다. 아래 [!UICONTROL Segment Mappings] 섹션에서 세그먼트를 선택하면 값이 설정됩니다.
   * **다중 키:** 키-값 쌍에 대한 키 및 값을 설정할 수 있도록 해줍니다. 아래 세그먼트 매핑 섹션에서 세그먼트를 선택하면 키-값 쌍을 만듭니다.
이러한 데이터 요소에 대한 자세한 내용은 [표준 및 일련 키-값 쌍](../../features/destinations/key-value-pairs.md)을 참조하십시오.
1. 클릭 **[!UICONTROL Save]**.

다른 모든 설정은 선택 사항입니다. **[!UICONTROL Cookie Domain]** 및 **[!UICONTROL Publish data to]** 설정에 대한 자세한 내용은 [쿠키 대상에 대한 선택적 설정](/help/using/features/destinations/cookie-destination-options.md)을 참조하십시오.

## 세그먼트 매핑 {#segments-mapping}

이 섹션에서는 세그먼트를 검색하고 대상에 추가할 수 있습니다. 이 섹션을 완료하려면

1. **[!UICONTROL Segment Mappings]** 을 클릭하여 컨트롤을 표시합니다.
1. **[!UICONTROL Search and Add Segments]** 상자에서 세그먼트 이름을 입력하거나 **[!UICONTROL Browse All Segments]** 을 클릭하여 사용 가능한 세그먼트 목록을 찾습니다.
1. 사용할 세그먼트를 찾으면 **[!UICONTROL Add Selected Segments]** 을 클릭합니다. 세그먼트를 추가하면 [!UICONTROL Edit Mapping] 창이 열립니다.
1. [!UICONTROL Edit Mapping] 대화 상자에서 다음을 수행합니다.
   * **[!UICONTROL Mapping]** 위의 구성 섹션에 지정된 키에 대한 값을 설정할 수 있도록 해줍니다.
   * **[!UICONTROL Publish from]** 대상에 대한 시작 및 종료 날짜를 설정할 수 있도록 해줍니다. 종료 날짜가 비어 있으면 대상이 만료되지 않습니다.
1. 클릭 **[!UICONTROL Save]**.
1. 클릭 **[!UICONTROL Done]**.
