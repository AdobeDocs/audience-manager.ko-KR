---
description: URL 대상은 페이지에서 대상에 대한 픽셀 호출을 만듭니다. 다음 지침에 따라 대상 빌더로 URL 대상을 만듭니다.
seo-description: URL 대상은 페이지에서 대상에 대한 픽셀 호출을 만듭니다. 다음 지침에 따라 대상 빌더로 URL 대상을 만듭니다.
seo-title: URL 대상 구성
solution: Audience Manager
title: URL 대상 구성
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 3%

---



# 구성 [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] 는 페이지에서 사용자 페이지로 픽셀 호출을 만듭니다 [!DNL destination]. 다음 지침에 따라 와 함께 [!DNL URL] 를 [!DNL destination] 만듭니다 [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

새 [!DNL URL] 를 만들려면 아래 [!DNL destination]에 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 설명된 대로 섹션으로 이동하여 해당 섹션을 완료합니다.

## 기본 정보 {#basic-info}

이 섹션에는 작성 프로세스를 시작하는 필드 및 옵션이 [!DNL URL destination] 포함되어 있습니다. 이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Basic Information]** 클릭합니다.
2. 이름을 [!DNL destination]지정합니다. 약자와 특수 문자는 사용하지 마십시오.
3. *(선택 사항)* 을 [!DNL destination]설명합니다. 간결한 설명은 한 항목에 대한 자세한 정보를 정의하거나 제공하는 효과적인 방법입니다 [!DNL destination].
4. 목록에서 **[!UICONTROL Category]** 선택합니다 **[!UICONTROL Custom]**.
5. 목록에서 **[!UICONTROL Environment]** 트리거할 환경을 선택합니다 [!DNL URL destination].
6. 목록에서 **[!UICONTROL Type]** 을 클릭합니다 **[!UICONTROL URL]**.
7. *(선택 사항)* 아이콘을 선택합니다 **[!UICONTROL Auto-fill Destination Mapping]**. 옵션은 다음과 같습니다.
   * **[!UICONTROL Segment ID]**: 세그먼트 ID를 자동으로 추가하고 이 ID를 [!DNL destination]
   * **[!UICONTROL Integration Code Value]**: 세그먼트 통합 코드를 자동으로 추가하여 대상 매핑에 보냅니다. 통합 코드는 고객이 만들고 사용하는 고유 식별자입니다. 최대 255자로 제한됩니다.
8. 을 **[!UICONTROL Next]** 클릭하여 [!UICONTROL Configuration] 설정으로 이동하거나 을 클릭하여 내보내기 제어 **[!UICONTROL Data Export Labels]** 를 에 적용합니다 [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

이 섹션에는 [데이터 내보내기 컨트롤을 대상에](../../features/data-export-controls.md) 적용하는 옵션이 [!DNL URL] 포함되어 있습니다. 데이터 내보내기 컨트롤을 사용하지 않으면 이 단계를 건너뜁니다. 이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Data Export Labels]** 클릭합니다.
2. 대상에 적용된 데이터 내보내기 컨트롤에 해당하는 레이블을 선택합니다(자세한 내용은 대상에 [내보내기 레이블 추가 참조](/help/using/features/destinations/add-data-export-labels.md) ).
3. 클릭 **[!UICONTROL Save]**.

## 구성 {#configure-base-data}

이 섹션에는 문자열로 전달된 기본 [!DNL URL] 및 데이터 구분 기호를 설정할 수 있는 옵션이 [!DNL URL] 포함되어 있습니다. 이 섹션은 선택 사항입니다. 이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Configuration]** 클릭합니다.
1. *(선택 사항)* 확인란을 **[!UICONTROL Serialize]** 선택합니다.
이렇게 하면 각 세그먼트에 대해 별도의 호출을 하지 않고 세그먼트를 [!DNL destination] 순차적으로 보낼 수 있습니다. 정리를 사용하면 데이터 전송을 효율적으로 수행할 수 있습니다. 이 확인란을 선택하면 URL 및 구분 기호 필드가 표시됩니다. 자세한 내용은 [표준 및 직렬 키-값 쌍을 참조하십시오](../../features/destinations/key-value-pairs.md).
1. 선택하는 경우 **[!UICONTROL Serialize]**&#x200B;아래 설명된 URL 및 구분 기호 필드도 구성해야 합니다.

| 필드 | 설명 |
|--- |--- |
| [!UICONTROL Base URL] | 변경되지 않는 표준 `HTTP` 의 기본 부분 [!DNL URL] . 또한 기본 URL에 자리 `%ALIAS%` 표시자 매크로를 [](../../features/destinations/destination-macros.md#destination-macros-defined) 배치해야 합니다. 예: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 변경되지 않는 보안 `HTTPS` 의 기본 부분 [!DNL URL] . 또한 기본 URL에 자리 `%ALIAS%` 표시자 매크로를 [](../../features/destinations/destination-macros.md#destination-macros-defined) 배치해야 합니다. 예: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | 문자열에서 세그먼트 변수를 구분하는 [!DNL URL] 기호입니다. 보통 쉼표나 세미콜론입니다. 대상 파트너로부터 이 정보를 얻으십시오. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

이 섹션에서는 세그먼트를 검색하고 추가할 수 있습니다 [!UICONTROL destination]. 이 섹션을 완료하려면

1. 컨트롤을 표시하려면 **[!UICONTROL Segment Mappings]** 클릭합니다.
1. 상자에 세그먼트 **[!UICONTROL Search and Add Segments]** 이름을 입력하거나 사용 가능한 세그먼트 목록을 **[!UICONTROL Browse All Segments]** 클릭합니다.
1. 사용할 세그먼트를 찾을 **[!UICONTROL Add Selected Segments]** 때 을 클릭합니다. 세그먼트를 추가하면 창이 [!UICONTROL Edit Mapping] 열립니다.
1.  [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: 세그먼트에서 사용하는 키-값 쌍을 제공합니다.
   * **[!UICONTROL Start Date]** 및 **[!UICONTROL End Date]**&#x200B;시작 및 종료 날짜를 선택합니다 [!DNL destination]. 종료 날짜가 비어 있으면 만료되지 [!DNL destination] 않습니다.
1. 클릭 **[!UICONTROL Done]**.