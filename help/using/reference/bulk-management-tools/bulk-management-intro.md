---
description: 벌크 관리 도구를 사용하면 한 번의 작업으로 여러 개체를 한 번에 만들고 관리할 수 있습니다. 벌크 관리 도구를 사용하여 데이터 소스, 파생된 신호, 대상, 폴더, 세그먼트 및 트레이트를 사용할 수 있습니다.
keywords: baaam;BAAAM;다운로드 baaam
seo-description: 벌크 관리 도구를 사용하면 한 번의 작업으로 여러 개체를 한 번에 만들고 관리할 수 있습니다. 벌크 관리 도구를 사용하여 데이터 소스, 파생된 신호, 대상, 폴더, 세그먼트 및 트레이트를 사용할 수 있습니다.
seo-title: 벌크 관리 시작
solution: Audience Manager
title: 벌크 관리 시작
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 4%

---

# 벌크 관리 시작{#getting-started-with-bulk-management}

[!DNL Bulk Management Tools]을 사용하면 한 번의 작업으로 여러 개체를 한 번에 만들고 관리할 수 있습니다. [!DNL Bulk Management Tools]을(를) 사용하여 [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments] 및 [!UICONTROL traits]에서 작업할 수 있습니다.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[RBAC 그룹 ](../../features/administration/administration-overview.md) 권한은  [!DNL Audience Manager] 사용자 인터페이스에 할당된 권한을 [!UICONTROL Bulk Management Tools] 유지합니다.

## 개요 {#overview}

이 기능은 [!DNL Audience Manager] API에 대한 안전하고 인증된 호출을 수행하는 매크로가 포함된 [!DNL Microsoft Excel] 스프레드시트를 사용합니다. API는 일괄 변경할 수 있는 메서드 및 서비스를 제공합니다. API를 사용하기 위해 코드를 작성하거나 API를 사용하여 작업하는 방법을 모르셔도 됩니다. 워크시트에는 특정 대량 변경 기능을 수행하는 열 머리글과 탭이 있습니다. 일괄적으로 변경하려면 미리 정의된 헤더를 특정 워크시트에 추가하고 일괄 변경할 정보를 제공한 다음 작업 단추를 클릭하기만 하면 됩니다. 워크시트와 API는 나머지 작업을 자동으로 수행합니다.

## 다운로드 {#download}

최신 워크시트 **[여기](assets/BAAAM_V2_20200502.xlsm)**&#x200B;를 다운로드합니다.

## 사전 요구 사항 {#prereqs}

[!DNL Bulk Management Tools]을(를) 사용하려면 다음이 필요합니다.

* [!DNL Experience Cloud] 로그인. 고객으로서 이러한 자격 증명이 이미 있어야 합니다.
* [!DNL Bulk Management Tools] 워크시트. [작업 ](assets/BAAAM_V2_20200502.xlsm) 세트를 다운로드하여 최신 버전을 다운로드하십시오.
* [!DNL Microsoft Excel] 64 [!DNL macOS] 비트에서  [!DNL Microsoft Windows]실행 최신 버전의 [!DNL Microsoft Excel]을 사용하는 것이 좋습니다.
* 워크시트를 열 때 [!DNL Bulk Management Tools]이(가) 작동하려면 **매크로 사용**&#x200B;이(가) 필요합니다.

## 인증 요구 사항 및 옵션 {#auth-reqs}

벌크 변경 시 인증이 필요합니다. 작업을 수행하려면 먼저 로그인해야 합니다. 워크시트는 API 호출을 생성하므로 사용자 계정에 인증하도록 구성해야 합니다.

**API 인증 요구 사항**

2019년 10월에 릴리스된 두 번째 버전의 [!DNL Bulk Management Tools]에서는 인증 프로세스를 단순화합니다. 이 버전의 인증 단계는 아래에 요약되어 있습니다.

1. 스프레드시트를 열고 **[!UICONTROL Config]** 시트로 이동합니다.
2. 시트에 설명된 단계를 따릅니다.
   ![](assets/baaam-authentication.png)
3. 단계를 완료한 후 일괄 변경을 수행할 수 있습니다.

벌크 변경 시 변경 작업을 수행할 수 있는 권한이 있는지 확인해야 하지만 API 인증은 자동입니다.

**도메인 인증 옵션**

도메인 인증은 벌크 요청을 테스트하거나 프로덕션 계정에 직접 적용할 수 있는 옵션을 제공합니다. 베타 환경을 일괄 변경해도 제작 계정에 영향을 주지 않습니다. 프로덕션 변경은 즉시 적용됩니다. 벌크 관리 시트를 사용하여 다음 환경에서 작업할 수 있습니다.

* 베타
* 프로덕션

## 작업 및 작업 {#actions-ops}

[!UICONTROL Bulk Management Tools] 워크시트는 인증 단추, 작업 탭, 작업 단추 및 **[!UICONTROL Headers]** 탭으로 구성됩니다. **[!UICONTROL Headers]** 탭에는 작업 탭에서 사용하는 사전 서식이 지정된 열 머리글이 포함되어 있습니다. 작업 탭에는 선택한 일괄 작업을 수행하는 매크로가 포함되어 있습니다. 일괄 작업을 수행하려면 헤더 세트를 해당 작업 탭에 복사하고 헤더 데이터를 입력한 다음 작업 단추를 클릭합니다.

[인증](#auth-reqs) 후 작업 단추를 클릭하여 시작합니다.

![](assets/baaam-worksheet.png)

아래 표에는 수행할 수 있는 작업과 [!UICONTROL Bulk Management Tools] 워크시트로 조작할 수 있는 항목이 나열됩니다.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 작업 </th> 
   <th colname="col2" class="entry"> 개체 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>일괄 작업은 워크시트 하단의 탭에 나타나며 다음을 포함합니다. </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">요청 </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">업데이트 </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">선택 사항에서 </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">예상 </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">삭제 </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>일괄적으로 변경할 수 있는 개체는 <b><span class="uicontrol"> 헤더</span></b> 탭 아래에 있으며 다음을 포함합니다. </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 데이터 소스</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> 파생된 신호</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> 대상</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> 모델</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> 특성 폴더 </a> 및 세그먼트 폴더 </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> 세그먼트</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> 트레이트</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**일괄 작업 예**

한 번에 여러 트레이트를 만드는 방법을 살펴보겠습니다. 벌크 작업에서 여러 트레이트를 만들려면 다음을 수행합니다.

1. **[!UICONTROL Headers]** 탭을 클릭하고 [!UICONTROL Create a Trait] 옵션 아래의 모든 레이블을 복사합니다.
2. **[!UICONTROL Create]** 탭을 클릭하고 1행, A 열 중에서 시작하는 레이블을 붙여 넣습니다.
3. 각 열 헤더와 관련된 정보를 입력하고 **[!UICONTROL Create Traits]**&#x200B;을 클릭합니다. 이 작업은 인증을 확인하라는 메시지를 표시합니다. 인증을 확인한 후 일괄 작업이 실행됩니다. 작업 상태 알림을 보려면 워크시트의 왼쪽 아래 모서리를 선택합니다.


>[!NOTE]
>
>큰 요청을 사용하여 작업할 때 워크시트가 응답하지 않아 비활성 상태인 것 같습니다. 이런 경우에는 그냥 내버려두세요. 벌크 요청이 완료되면 워크시트가 반응형으로 바뀝니다. 워크시트가 긴 시간 동안 응답하지 않으면 [문제 해결 섹션](../../reference/bulk-management-tools/bulk-troubleshooting.md)을 참조하십시오.
