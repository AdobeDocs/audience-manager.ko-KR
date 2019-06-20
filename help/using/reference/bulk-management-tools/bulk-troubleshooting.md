---
description: 워크시트에서 오류를 반환하거나 벌크 요청이 실패하면 수행할 작업입니다.
seo-description: 워크시트에서 오류를 반환하거나 벌크 요청이 실패하면 수행할 작업입니다.
seo-title: 일괄 관리 도구에 대한 문제 해결 팁
solution: Audience Manager
title: 일괄 관리 도구에 대한 문제 해결 팁
uuid: 550908 A 1-E 24 E -4 F 31-954 B -7132 C 0 C 8 DC 3 E
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Troubleshooting Tips for Bulk Management Tools{#troubleshooting-tips-for-bulk-management-tools}

워크시트에서 오류를 반환하거나 벌크 요청이 실패하면 수행할 작업입니다.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*는에서* 지원되지 [!DNL Audience Manager]않습니다. 이 도구는 편의를 위해 제공되며 편의를 위해 제공됩니다. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [UI에](../../features/administration/administration-overview.md) 할당된 RBAC 그룹 권한이 [!DNL Audience Manager] 에서 [!UICONTROL Bulk Management Tools]인정됩니다.

대량의 네트워크 트래픽, 서버 사용 및 대용량 데이터 세트와 같은 요인은 벌크 요청이 실패하거나 시간 초과될 수 있습니다. 문제가 발생하면 워크시트에서 데이터 쓰기를 중단하고 오류 메시지를 표시합니다. 이러한 경우 다음을 수행해야 합니다.

* 오류 메시지를 읽습니다.
* 문제를 해결합니다.
* 이미 업데이트된 모든 행을 삭제합니다.
* 일괄 요청을 다시 시도하십시오.

## Long delays or unresponsive behavior {#delays-behavior}

다음 표에는 워크시트와 함께 벌크 요청을 수행할 때 발생할 수 있는 몇 가지 일반적인 문제가 나와 있습니다. 권장되는 솔루션으로 이러한 문제를 해결해 보십시오. 권장 솔루션으로 인해 문제가 해결되지 않으면 작업을 저장하고 컴퓨터를 다시 시작한 다음 다른 애플리케이션을 실행하거나 작업 없이 요청을 다시 시도해야 합니다.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 문제 </th> 
   <th colname="col2" class="entry"> 솔루션 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>긴 지연 시간</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>호환성 모드 해제</b>: Microsoft Excel의 호환 모드에서 다른 워크시트가 열려 있는지 확인합니다. 호환성 모드는 런타임을 증가시킬 수 있습니다. 이 모드에서 열었던 스프레드시트를 모두 닫고 일괄 요청을 다시 시도하십시오. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>시스템 리소스</b>: 시스템 리소스가 제한된 경우 지연 시간이 길어질 수 있습니다. 일괄 요청하기 전에 다른 프로그램을 모두 닫으십시오. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>응답 없음</b> </td> 
   <td colname="col2">작업 버튼을 클릭하면 아무것도 일어나지 않습니다. 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">선택 작업에 적합한 헤더 세트가 있는지 확인합니다. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">복사한 헤더에 올바른 워크시트를 사용하고 있는지 확인하십시오. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">일괄 작업에서 사용할 데이터의 위치를 확인합니다. 모든 헤더가 A 열, 1 행에서 시작됩니다. 모든 데이터는 열 A, 행 2 (헤더 바로 아래) 에서 시작하여 해당 헤더에 적용됩니다. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

