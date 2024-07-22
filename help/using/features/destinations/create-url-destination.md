---
description: URL 대상은 페이지에서 대상으로 픽셀 호출을 수행합니다. 다음 지침에 따라 대상 빌더로 URL 대상을 만듭니다.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: URL 대상 구성
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# [!DNL URL Destination] 구성 {#configure-url-destination}

[!DNL URL destination]이(가) 페이지에서 [!DNL destination](으)로 픽셀 호출을 합니다. 다음 지침에 따라 [!UICONTROL Destination Builder]을(를) 사용하여 [!DNL URL] [!DNL destination]을(를) 만듭니다.

<!-- create-url-destination.xml -->

새 [!DNL URL] [!DNL destination]을(를) 만들려면 **[!UICONTROL Audience Data > Destinations > Create New Destination]**(으)로 이동하여 아래 설명에 따라 섹션을 완료하십시오.

## 기본 정보 {#basic-info}

이 섹션에는 [!DNL URL destination] 만들기 프로세스를 시작하는 필드와 옵션이 포함되어 있습니다. 이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Basic Information]**&#x200B;을(를) 클릭합니다.
2. [!DNL destination] 이름을 지정합니다. 약어 및 특수 문자를 사용하지 마십시오.
3. *(선택 사항)*&#x200B;에서 [!DNL destination]을(를) 설명합니다. 간결한 설명은 [!DNL destination]에 대한 자세한 정보를 정의하거나 제공하는 효과적인 방법입니다.
4. **[!UICONTROL Category]** 목록에서 **[!UICONTROL Custom]**&#x200B;을(를) 선택합니다.
5. **[!UICONTROL Environment]** 목록에서 [!DNL URL destination]을(를) 트리거할 환경을 선택합니다.
6. **[!UICONTROL Type]** 목록에서 **[!UICONTROL URL]**&#x200B;을(를) 클릭합니다.
7. *(선택 사항)* **[!UICONTROL Auto-fill Destination Mapping]**&#x200B;을(를) 선택하십시오. 옵션은 다음과 같습니다.
   * **[!UICONTROL Segment ID]**: 세그먼트 ID를 자동으로 추가하여 [!DNL destination]에 보냅니다.
   * **[!UICONTROL Integration Code Value]**: 세그먼트 통합 코드를 대상 매핑에 자동으로 추가하고 전송합니다. 통합 코드는 고객이 만들고 사용하는 고유 식별자입니다. 최대 255자로 제한됩니다.
8. **[!UICONTROL Next]**&#x200B;을(를) 클릭하여 [!UICONTROL Configuration] 설정으로 이동하거나 **[!UICONTROL Data Export Labels]**&#x200B;을(를) 클릭하여 [!DNL destination]에 내보내기 컨트롤을 적용합니다.

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

이 섹션에는 [!DNL URL] 대상에 [데이터 내보내기 컨트롤](../../features/data-export-controls.md)을 적용하는 옵션이 포함되어 있습니다. 데이터 내보내기 컨트롤을 사용하지 않는 경우 이 단계를 건너뜁니다. 이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Data Export Labels]**&#x200B;을(를) 클릭합니다.
2. 대상에 적용된 데이터 내보내기 컨트롤에 해당하는 레이블을 선택합니다(자세한 내용은 [대상에 내보내기 레이블 추가](/help/using/features/destinations/add-data-export-labels.md) 참조).
3. **[!UICONTROL Save]** 아이콘을 클릭합니다.

## 구성 {#configure-base-data}

이 섹션에는 [!DNL URL] 문자열에서 전달된 기본 [!DNL URL] 및 데이터 구분 기호를 설정할 수 있는 옵션이 포함되어 있습니다. 이 섹션은 선택 사항입니다. 이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Configuration]**&#x200B;을(를) 클릭합니다.
1. *(선택 사항)* **[!UICONTROL Serialize]** 확인란을 선택합니다.
이렇게 하면 각 세그먼트를 별도로 호출하지 않고 세그먼트를 [!DNL destination]에 순차적으로 보낼 수 있습니다. 직렬화를 사용하면 데이터를 효율적으로 전송할 수 있습니다. 이 확인란을 선택하면 URL 및 구분 기호 필드가 표시됩니다. 자세한 내용은 [표준 및 일련 키-값 쌍](../../features/destinations/key-value-pairs.md)을 참조하세요.
1. **[!UICONTROL Serialize]**&#x200B;을(를) 선택하는 경우 아래 설명된 URL 및 구분 기호 필드도 구성해야 합니다.

| 필드 | 설명 |
|--- |--- |
| [!UICONTROL Base URL] | 변경되지 않는 표준 `HTTP` [!DNL URL]의 기본 부분입니다. 또한 기본 URL에 `%ALIAS%` [자리 표시자 매크로](../../features/destinations/destination-macros.md#destination-macros-defined)를 배치해야 합니다. 예: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 변경되지 않는 보안 `HTTPS` [!DNL URL]의 기본 부분입니다. 또한 `%ALIAS%`을(를) 배치해야 합니다.   기본 URL의 [자리 표시자 매크로](../../features/destinations/destination-macros.md#destination-macros-defined). 예: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | [!DNL URL] 문자열에서 세그먼트 변수를 구분하는 기호입니다. 이는 보통 쉼표 또는 세미콜론입니다. 대상 파트너로부터 이 정보를 가져옵니다. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

이 섹션에서는 세그먼트를 검색하고 [!UICONTROL destination]에 추가할 수 있습니다. 이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Segment Mappings]**&#x200B;을(를) 클릭합니다.
1. **[!UICONTROL Search and Add Segments]** 상자에서 세그먼트 이름을 입력하거나 **[!UICONTROL Browse All Segments]**&#x200B;을(를) 클릭하여 사용 가능한 세그먼트 목록을 찾아봅니다.
1. 사용할 세그먼트를 찾으면 **[!UICONTROL Add Selected Segments]**&#x200B;을(를) 클릭합니다. 세그먼트를 추가하면 [!UICONTROL Edit Mapping] 창이 열립니다.
1. [!UICONTROL Edit Mapping]에서:
   * **[!UICONTROL Mappings]**: 세그먼트에서 사용하는 키-값 쌍을 제공합니다.
   * **[!UICONTROL Start Date]** 및 **[!UICONTROL End Date]**: [!DNL destination]의 시작 및 종료 날짜를 선택하십시오. 종료 날짜가 비어 있으면 [!DNL destination]이(가) 만료되지 않습니다.
1. **[!UICONTROL Done]** 아이콘을 클릭합니다.
