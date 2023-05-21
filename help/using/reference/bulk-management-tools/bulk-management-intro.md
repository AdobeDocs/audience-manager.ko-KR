---
description: 벌크 관리 도구를 사용하면 한 번의 작업으로 여러 개체를 한 번에 만들고 관리할 수 있습니다. 대량 관리 도구를 사용하여 데이터 소스, 파생된 신호, 대상, 폴더, 세그먼트 및 트레이트로 작업할 수 있습니다.
keywords: baaam;BAAAM;baaam 다운로드
seo-description: The Bulk Management Tools let you create and manage multiple objects at once with single operation. You can use Bulk Management Tools to work with data sources, derived signals, destinations, folders, segments, and traits.
seo-title: Getting Started With Bulk Management
solution: Audience Manager
title: 벌크 관리 시작
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: 911eab2d661907c6f1e2ffc08603d994bd346395
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 3%

---

# 벌크 관리 시작{#getting-started-with-bulk-management}

다음 [!DNL Bulk Management Tools] 을 사용하면 한 번의 작업으로 여러 개체를 한 번에 만들고 관리할 수 있습니다. 다음을 사용할 수 있습니다. [!DNL Bulk Management Tools] 로 작업하기 [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments], 및 [!UICONTROL traits].

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[RBAC 그룹 권한](../../features/administration/administration-overview.md) 에 할당됨 [!DNL Audience Manager] 사용자 인터페이스가 [!UICONTROL Bulk Management Tools].

## 개요 {#overview}

이 기능은 [!DNL Microsoft Excel] 에 대한 안전하고 인증된 호출을 수행하는 매크로가 포함된 스프레드시트 [!DNL Audience Manager] API. API는 대량으로 변경할 수 있는 메서드 및 서비스를 제공합니다. 사용하기 위해 API를 코딩하거나 작업하는 방법을 알 필요가 없습니다. 이 워크시트에는 특정 일괄 변경 기능을 수행하는 열 머리글과 탭이 있습니다. 일괄 변경을 수행하려면 사전 정의된 헤더를 특정 워크시트에 추가하고, 일괄 변경할 정보를 제공하고 작업 버튼을 클릭하기만 하면 됩니다. 워크시트와 API가 나머지 작업을 수행합니다.

## 다운로드 {#download}

최신 워크시트 다운로드 **[여기](assets/BAAAM_V2_20210609.xlsm)** (2021년 6월에 마지막으로 업데이트됨).

## 사전 요구 사항 {#prereqs}

을(를) 사용하려면 [!DNL Bulk Management Tools], 다음이 필요합니다.

* 사용자 [!DNL Experience Cloud] 로그인합니다. 고객은 이미 이러한 자격 증명을 가지고 있어야 합니다.
* 다음 [!DNL Bulk Management Tools] 워크시트입니다. [워크시트 다운로드](assets/BAAAM_V2_20200502.xlsm) 최신 버전을 다운로드하십시오.
* [!DNL Microsoft Excel] 실행 중 [!DNL macOS] 또는 64비트 [!DNL Microsoft Windows]. 최신 버전의 를 사용하는 것이 좋습니다. [!DNL Microsoft Excel].
* 워크시트를 열 때 다음을 수행해야 합니다. **매크로 활성화** 대상: [!DNL Bulk Management Tools] 일 때문에.

## 인증 요구 사항 및 옵션 {#auth-reqs}

벌크 변경에는 인증이 필요합니다. 작업을 수행하기 전에 로그인해야 합니다. 워크시트가 API를 호출하므로 사용자 계정을 인증하도록 구성해야 합니다.

**API 인증 요구 사항**

의 두 번째 버전 [!DNL Bulk Management Tools]2019년 10월에 릴리스된 는 인증 프로세스를 간소화합니다. 이 버전의 인증 단계는 아래에 요약되어 있습니다.

1. 스프레드시트를 열고 로 이동합니다. **[!UICONTROL Config]** 시트.
2. 시트에 설명된 단계를 수행합니다.
   ![](assets/baaam-authentication.png)
3. 단계를 완료한 후 일괄 변경할 권한이 있습니다.

일괄 변경 시 변경할 권한이 있는지 확인해야 하지만 API 인증은 자동으로 수행됩니다.

**도메인 인증 옵션**

도메인 인증은 대량 요청을 테스트하거나 프로덕션 계정에 직접 적용할 수 있는 옵션을 제공합니다. Beta 환경을 대량으로 변경해도 프로덕션 계정에는 영향을 주지 않습니다. 프로덕션 변경 사항은 즉시 적용됩니다. 벌크 관리 시트를 사용하여 다음 환경에서 작업할 수 있습니다.

* 베타
* 프로덕션

## 작업 및 작업 {#actions-ops}

다음 [!UICONTROL Bulk Management Tools] 워크시트는 인증 버튼, 작업 탭, 작업 버튼 및 **[!UICONTROL Headers]** 탭. 다음 **[!UICONTROL Headers]** 탭에는 작업 탭에서 사용하는 미리 서식이 지정된 열 머리글이 포함되어 있습니다. 작업 탭에는 선택한 일괄 작업을 수행하는 매크로가 포함되어 있습니다. 대량 작업을 수행하려면 헤더 집합을 해당 작업 탭에 복사하고 헤더 데이터를 입력한 다음 작업 단추를 누릅니다.

다음 이후 [인증](#auth-reqs)시작하려면 작업 버튼을 클릭하십시오.

![](assets/baaam-worksheet.png)

아래 표에는 수행할 수 있는 작업과 [!UICONTROL Bulk Management Tools] 워크시트.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 작업 </th> 
   <th colname="col2" class="entry"> 오브젝트 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>대량 작업은 워크시트 하단의 탭에 표시되며 다음을 포함합니다. </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">요청 </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">업데이트 </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">선택 사항에서 </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">예상 </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">삭제 </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>대량으로 변경할 수 있는 객체는 <b><span class="uicontrol"> 헤더</span></b> 탭으로 다음을 포함합니다. </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 데이터 소스</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> 파생 신호</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> 대상</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> 모델</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> 트레이트 폴더</a> 및 세그먼트 폴더 </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> 세그먼트</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> 트레이트</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**대량 작업 예**

예를 들어 한 번에 여러 트레이트를 만드는 방법을 살펴보겠습니다. 일괄 작업으로 여러 트레이트를 생성하려면 다음을 수행합니다.

1. 다음을 클릭합니다. **[!UICONTROL Headers]** 을(를) 탭하고 아래의 모든 레이블 복사 [!UICONTROL Create a Trait] 옵션을 선택합니다.
2. 다음을 클릭합니다. **[!UICONTROL Create]** 1행, A열부터 레이블을 탭하고 붙여 넣습니다.
3. 각 열 헤더와 관련된 정보를 입력하고 클릭 **[!UICONTROL Create Traits]**. 이 작업은 인증을 확인하라는 메시지를 표시합니다. 인증을 확인한 후 벌크 작업이 실행됩니다. 작업 상태 알림에 대한 워크시트의 왼쪽 아래 모서리를 확인합니다.


>[!NOTE]
>
>큰 요청으로 작업할 때 워크시트가 응답하지 않고 비활성 상태로 표시될 수 있습니다. 이런 경우에는 그냥 내버려둬. 벌크 요청이 완료되면 워크시트가 응답합니다. 워크시트가 오랫동안 응답하지 않으면 [문제 해결 섹션](../../reference/bulk-management-tools/bulk-troubleshooting.md).
