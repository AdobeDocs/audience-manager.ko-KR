---
description: 워크시트가 오류를 반환하거나 벌크 요청이 실패할 때 수행할 작업
seo-description: 워크시트가 오류를 반환하거나 벌크 요청이 실패할 때 수행할 작업
seo-title: 일괄 관리 도구 문제 해결 팁
solution: Audience Manager
title: 일괄 관리 도구 문제 해결 팁
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
translation-type: tm+mt
source-git-commit: 994b12fd442a08da3b606dabca1f9382a7bd6f74

---


# 일괄 관리 도구 문제 해결 팁{#troubleshooting-tips-for-bulk-management-tools}

워크시트가 오류를 반환하거나 벌크 요청이 실패할 때 수행할 작업



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>는 에서 [!UICONTROL Bulk Management Tools] 지원되지 *않습니다* . [!DNL Audience Manager] 이 도구는 편의를 위해 제공되는 무료 도구입니다. 일괄 변경의 경우 Audience Manager API를 [대신 사용하는 것이](../../api/rest-api-main/aam-api-getting-started.md) 좋습니다. [UI에 할당된 RBAC 그룹 권한은](../../features/administration/administration-overview.md) 에서 [!DNL Audience Manager] 적용됩니다 [!UICONTROL Bulk Management Tools].

대량의 네트워크 트래픽, 서버 사용량 및 대규모 데이터 세트와 같은 요인으로 인해 벌크 요청이 실패하거나 시간 초과될 수 있습니다. 문제가 발생하면 워크시트는 데이터 쓰기를 중단하고 오류 메시지를 표시합니다. 이러한 경우 다음을 수행해야 합니다.

* 오류 메시지를 확인합니다.
* 문제 해결
* 이미 업데이트된 모든 행을 삭제합니다.
* 일괄 요청을 다시 시도하십시오.

## 인증 오류, 긴 지연 또는 응답 없는 동작 {#delays-behavior}

다음 표에는 워크시트에 벌크 요청을 할 때 발생할 수 있는 몇 가지 일반적인 문제가 나와 있습니다. 권장 솔루션을 사용하여 이러한 문제를 해결해 보십시오. 권장 솔루션이 문제를 해결하지 못하는 경우 작업을 저장하고 컴퓨터를 다시 시작한 후 다른 응용 프로그램을 실행하거나 작업하지 않고 요청을 다시 시도하십시오.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 문제 </th> 
   <th colname="col2" class="entry"> 솔루션 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>인증 오류</b> </td> 
   <td colname="col2"> 
    <b>최신 버전의 Microsoft Excel로 업데이트</b>:새 버전의 Microsoft Excel이 릴리스되고 이전 버전을 사용 중인 경우 벌크 관리 워크시트에서 인증 오류가 발생할 수 있습니다. 최신 버전의 Microsoft Excel로 업데이트하여 인증 오류를 해결하십시오.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>긴 지연 시간</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>호환성 모드</b>해제:다른 워크시트가 Microsoft Excel의 호환성 모드로 열려 있는지 확인합니다. 호환성 모드를 사용하면 런타임이 늘어날 수 있습니다. 이 모드에서 열려 있는 스프레드시트를 모두 닫고 벌크 요청을 다시 시도하십시오. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>시스템 리소스</b>:시스템 리소스가 제한되어 오래 지체됩니다. 일괄 요청하기 전에 다른 프로그램을 모두 닫으십시오. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>응답 없음</b> </td> 
   <td colname="col2">작업 단추를 클릭하면 아무 일도 발생하지 않습니다. 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">선택 작업에 적합한 헤더 세트가 있는지 확인합니다. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">복사한 헤더에 적합한 워크시트를 사용하고 있는지 확인합니다. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">일괄 작업에 사용할 데이터의 위치를 확인합니다. 모든 헤더는 열 A, 행 1에서 시작됩니다. 모든 데이터는 A 열, 2행(머리글 바로 아래)에서 시작하는 해당 헤더로 이동합니다. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 오류 메시지

경우에 따라 벌크 변경 시 오류 메시지가 표시될 수 있습니다. 오류 메시지를 해석하려면 API [설명서에 정의된](/help/using/api/rest-api-main/aam-api-getting-started.md) 응답 코드를 참조하십시오.

