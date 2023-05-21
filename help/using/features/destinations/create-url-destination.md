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
source-wordcount: '486'
ht-degree: 3%

---

# 구성 [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] 페이지에서 로 픽셀 호출 [!DNL destination]. 다음 지침에 따라 [!DNL URL] [!DNL destination] 포함 [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

새로 만들려면 [!DNL URL] [!DNL destination]로 이동합니다. **[!UICONTROL Audience Data > Destinations > Create New Destination]** 아래에 설명된 대로 섹션을 완료합니다.

## 기본 정보 {#basic-info}

이 섹션에는 를 시작하는 필드와 옵션이 포함되어 있습니다. [!DNL URL destination] 생성 프로세스. 이 섹션을 완료하려면

1. 클릭 **[!UICONTROL Basic Information]** 컨트롤을 노출합니다.
2. 이름 지정 [!DNL destination]. 약어 및 특수 문자를 사용하지 마십시오.
3. *(선택 사항)* 설명 [!DNL destination]. 간결한 설명은 다음에 대한 추가 정보를 정의하거나 제공하는 효과적인 방법입니다. [!DNL destination].
4. 다음에서 **[!UICONTROL Category]** 목록, 선택 **[!UICONTROL Custom]**.
5. 다음에서 **[!UICONTROL Environment]** 목록에서 를 트리거할 환경을 선택합니다. [!DNL URL destination].
6. 다음에서 **[!UICONTROL Type]** 목록, 클릭 **[!UICONTROL URL]**.
7. *(선택 사항)* 선택 **[!UICONTROL Auto-fill Destination Mapping]**. 옵션은 다음과 같습니다.
   * **[!UICONTROL Segment ID]**: 세그먼트 ID를 자동으로 추가하여 로 보냅니다. [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: 세그먼트 통합 코드를 대상 매핑에 자동으로 추가하고 전송합니다. 통합 코드는 고객이 만들고 사용하는 고유 식별자입니다. 최대 255자로 제한됩니다.
8. 클릭 **[!UICONTROL Next]** 로 이동 [!UICONTROL Configuration] 설정 또는 클릭 **[!UICONTROL Data Export Labels]** 에 내보내기 컨트롤을 적용하려면 [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

이 섹션에는 적용되는 옵션이 포함되어 있습니다. [데이터 내보내기 제어](../../features/data-export-controls.md) (으)로 [!DNL URL] 대상. 데이터 내보내기 컨트롤을 사용하지 않는 경우 이 단계를 건너뜁니다. 이 섹션을 완료하려면

1. 클릭 **[!UICONTROL Data Export Labels]** 컨트롤을 노출합니다.
2. 대상에 적용된 데이터 내보내기 제어에 해당하는 레이블을 선택합니다(참조) [대상에 내보내기 레이블 추가](/help/using/features/destinations/add-data-export-labels.md) 을 참조하십시오.
3. 클릭 **[!UICONTROL Save]**.

## 구성 {#configure-base-data}

이 섹션에는 기준을 설정할 수 있는 옵션이 포함되어 있습니다 [!DNL URL] 및 데이터 구분 기호 전달자 [!DNL URL] 문자열. 이 섹션은 선택 사항입니다. 이 섹션을 완료하려면

1. 클릭 **[!UICONTROL Configuration]** 컨트롤을 노출합니다.
1. *(선택 사항)* 다음 항목 선택 **[!UICONTROL Serialize]** 확인란.
세그먼트를 로 보낼 수 있습니다. [!DNL destination] 각 세그먼트를 별도로 호출하지 않고 순차적으로 호출합니다. 직렬화를 사용하면 데이터를 효율적으로 전송할 수 있습니다. 이 확인란을 선택하면 URL 및 구분 기호 필드가 표시됩니다. 자세한 내용은 [표준 및 일련 키-값 쌍](../../features/destinations/key-value-pairs.md).
1. 다음을 선택하는 경우 **[!UICONTROL Serialize]**&#x200B;아래에 설명된 URL 및 구분 기호 필드도 구성해야 합니다.

| 필드 | 설명 |
|--- |--- |
| [!UICONTROL Base URL] | 표준의 기본 부분 `HTTP` [!DNL URL] 그것은 변하지 않는다. 또한 `%ALIAS%`  [자리 표시자 매크로](../../features/destinations/destination-macros.md#destination-macros-defined) 기본 URL에서 예: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 보안의 기본 부분 `HTTPS` [!DNL URL] 그것은 변하지 않는다. 또한 `%ALIAS%`   [자리 표시자 매크로](../../features/destinations/destination-macros.md#destination-macros-defined) 기본 URL에서 예: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | 에서 세그먼트 변수를 구분하는 기호 [!DNL URL] 문자열. 이는 보통 쉼표 또는 세미콜론입니다. 대상 파트너로부터 이 정보를 가져옵니다. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

이 섹션에서는 세그먼트를 검색하고 추가할 수 있습니다. [!UICONTROL destination]. 이 섹션을 완료하려면

1. 클릭 **[!UICONTROL Segment Mappings]** 컨트롤을 노출합니다.
1. 다음에서 **[!UICONTROL Search and Add Segments]** 상자에서 세그먼트 이름을 입력하거나 **[!UICONTROL Browse All Segments]** 사용 가능한 세그먼트 목록을 검색합니다.
1. 클릭 **[!UICONTROL Add Selected Segments]** 사용할 세그먼트를 찾을 때. 세그먼트를 추가하면 [!UICONTROL Edit Mapping] 창.
1.  [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: 세그먼트에서 사용하는 키-값 쌍을 제공합니다.
   * **[!UICONTROL Start Date]** 및 **[!UICONTROL End Date]**: 의 시작 및 종료 날짜를 선택합니다. [!DNL destination]. 종료 날짜가 비어 있으면 [!DNL destination] 만료되지 않습니다.
1. 클릭 **[!UICONTROL Done]**.
