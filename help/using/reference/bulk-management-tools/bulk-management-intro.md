---
description: 일괄 관리 도구를 사용하면 한 번에 여러 개체를 만들고 관리할 수 있습니다. 일괄 관리 도구를 사용하여 데이터 소스, 파생된 신호, 대상, 폴더, 세그먼트 및 트레이트를 사용할 수 있습니다.
keywords: Baaam; Baaam
seo-description: 일괄 관리 도구를 사용하면 한 번에 여러 개체를 만들고 관리할 수 있습니다. 일괄 관리 도구를 사용하여 데이터 소스, 파생된 신호, 대상, 폴더, 세그먼트 및 트레이트를 사용할 수 있습니다.
seo-title: 일괄 관리 시작하기
solution: Audience Manager
title: 일괄 관리 시작하기
uuid: 4 BC 6 AE 0 A -315 C -4 CE 7-A 68 E-CC 0 C 6 C 6 AA 2 F 1
translation-type: tm+mt
source-git-commit: 349cc962c993b361e2dea00ba693337391b87e5e

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

일괄 관리 도구를 사용하면 한 번에 여러 개체를 만들고 관리할 수 있습니다. 일괄 관리 도구를 사용하여 데이터 소스, 파생된 신호, 대상, 폴더, 세그먼트 및 트레이트를 사용할 수 있습니다.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*는에서* 지원되지 [!DNL Audience Manager]않습니다. 이 도구는 편의를 위해 제공되며 편의를 위해 제공됩니다. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [UI에](../../features/administration/administration-overview.md) 할당된 RBAC 그룹 권한이 [!DNL Audience Manager] 에서 [!UICONTROL Bulk Management Tools]인정됩니다.

## 개요 {#overview}

This feature uses a Microsoft Excel spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs. API는 일괄적으로 변경할 수 있는 메서드 및 서비스를 제공합니다. Adobe API를 사용하여 코딩 또는 작업하는 방법을 익히지 않아도 됩니다. 워크시트에는 특정 벌크 변경 기능을 수행하는 열 머리글과 탭이 포함되어 있습니다. 일괄 변경을 수행하려면 미리 정의된 헤더를 특정 워크시트에 추가하고 변경할 정보를 제공하고 작업 단추를 클릭합니다. 워크시트와 API는 나머지 작업을 자동으로 수행합니다.

## 전제 조건 {#prereqs}

To use the [!DNL Bulk Management Tools], you need the following:

* Your [!DNL Audience Manager] user name and password. 고객은 이미 이러한 자격 증명을 가지고 있어야 합니다.
* API 클라이언트 ID 및 비밀 키. 계정 관리자가 이러한 정보를 제공할 수 있습니다.
* [!UICONTROL Bulk Management Tools] 워크시트. **[최신 버전을 얻으려면 워크시트를](assets/BAAAM_August_2018.xlsm)** 다운로드하십시오.

* Microsoft Excel running on [!DNL Windows] or in a [!DNL Microsoft Windows] virtual machine running on [!DNL macOS X]. You must use 32-bit Excel for the [!UICONTROL Bulk Management Tools] to work.

## Actions and operations {#actions-ops}

[!UICONTROL Bulk Management Tools] 이 워크시트는 작업 탭, 작업 단추 및 **[!UICONTROL Headers]** 탭으로 구성됩니다. **[!UICONTROL Headers]** 탭에는 작업 탭에서 사용하는 사전 형식 열 헤더가 포함되어 있습니다. 작업 탭에는 선택한 일괄 작업을 수행하는 매크로가 포함됩니다. 일괄 작업을 수행하려면 헤더 세트를 적절한 작업 탭에 복사하고 헤더 데이터를 입력한 다음 작업 단추를 클릭합니다.

스프레드시트를 열고 작업 버튼을 클릭하여 시작합니다.

![](assets/bamwrkbk.png)

The table below lists the operations you can perform and items you can manipulate with the [!UICONTROL Bulk Management Tools] worksheets.

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
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">estimate </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">삭제 </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>The objects you can change in bulk are located under the <b><span class="uicontrol"> Headers</span></b> tab and include: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Data Sources</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> 파생 신호</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> 대상</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> 특성 폴더</a> 및 세그먼트 폴더 </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> 세그먼트</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> 트레이트</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**일괄 작업 예**

예를 들어 한 번에 여러 트레이트를 만드는 방법을 살펴보겠습니다. 일괄 작업에서 여러 특성을 만들려면 다음을 수행하십시오.

1. **[!UICONTROL Headers]** 탭을 클릭하고 [!UICONTROL Create a Trait] 옵션 아래에 있는 모든 레이블을 복사합니다.

2. **[!UICONTROL Create]** 탭을 클릭하고 1 행 열 A에서 시작하는 레이블을 붙여넣습니다.
3. Provide information related to each column header and click **[!UICONTROL Create Traits]**. 이렇게 하면 로그인하라는 메시지가 표시됩니다. Your bulk job runs after you successfully authenticate (see the [authentication requirements](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) below). 작업 상태 알림에 대해 워크시트의 왼쪽 아래 모서리를 확인합니다.

>[!NOTE]
>
>대규모 요청으로 작업할 때 워크시트는 응답하지 않아 비활성 상태가 될 수 있습니다. 이러한 경우 그냥 두기만 하면 됩니다. 벌크 요청이 완료되면 워크시트는 응답하게 됩니다. If the worksheet does not respond for a long period of time, see the [troubleshooting section](../../reference/bulk-management-tools/bulk-troubleshooting.md).

## Authentication requirements and options {#auth-reqs}

벌크 변경은 인증이 필요합니다. 작업을 선택하면 워크시트는 로그인하라는 메시지를 표시합니다. 워크시트에서 API 호출을 하기 때문에 비밀 키를 읽도록 구성해야 합니다. **[!UICONTROL Domain]** 이 필드를 사용하면 스테이징/테스트 환경 또는 라이브 프로덕션 계정에서 벌크 변경을 수행할 수 있습니다.

![](assets/bamauth.png)

**API 인증 요구 사항**

API 인증을 설정하려면 다음을 수행해야 합니다.

* 비밀 키를 복사하여 텍스트 (.txt) 파일로 저장합니다.
* 텍스트 파일의 이름을 API 클라이언트 ID로 지정합니다. 예를 들어 클라이언트 ID가 &quot;bulk-user&quot; 인 경우 &quot;bulk-user. txt&quot; 라는 파일에 키를 저장합니다.
* 비밀 키와 워크시트를 같은 폴더에 저장합니다.

일괄적으로 변경할 때 사용자 이름, 암호, 클라이언트 ID 및 도메인을 입력해야 하지만 API 인증은 자동으로 이루어집니다.

**도메인 인증 옵션**

도메인 인증은 벌크 요청을 테스트하거나 프로덕션 계정에 직접 적용하는 옵션을 제공합니다. 테스트 환경을 대량으로 변경해도 프로덕션 계정은 영향을 받지 않습니다. 제작 변경 사항은 즉시 적용됩니다. **[!UICONTROL Domain]** 필드는 작업할 환경에 따라 다음 주소를 수락합니다.

* 테스트: `api-beta.demdex.com`
* 프로덕션: `api.demdex.com`

>[!MORE_ like_ this]
>
>* [일괄 관리 워크시트 다운로드](assets/BAAAM_August_2018.xlsm)

