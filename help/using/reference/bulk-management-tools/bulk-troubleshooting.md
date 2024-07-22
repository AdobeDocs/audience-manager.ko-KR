---
description: 워크시트가 오류를 반환하거나 대량 요청이 실패할 경우 수행할 작업.
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: 벌크 관리 도구 문제 해결 팁
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# 벌크 관리 도구 문제 해결 팁{#troubleshooting-tips-for-bulk-management-tools}

워크시트가 오류를 반환하거나 대량 요청이 실패할 경우 수행할 작업.

>[!IMPORTANT]
>
>Bulk Management Tools는 공식적으로 지원되는 Adobe 제품이 아닙니다. 고객 지원 센터를 통한 문제 해결 및 지원은 사안별로 처리됩니다.

<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[!DNL Audience Manager] UI에 할당된 [RBAC 그룹 권한](../../features/administration/administration-overview.md)이(가) [!UICONTROL Bulk Management Tools]에서 허용됩니다.

네트워크 트래픽이 많거나, 서버 사용량 및 대용량 데이터 세트와 같은 요인으로 인해 대량 요청이 실패하거나 시간 초과가 발생할 수 있습니다. 문제가 있는 경우 워크시트가 데이터 쓰기를 중지하고 오류 메시지를 표시합니다. 이 경우 다음을 수행해야 합니다.

* 오류 메시지를 읽습니다.
* 문제를 해결합니다.
* 이미 업데이트된 행을 모두 삭제합니다.
* 대량 요청을 다시 시도하십시오.

## 인증 오류, 긴 지연 또는 응답하지 않는 비헤이비어 {#delays-behavior}

다음 표에는 워크시트로 대량 요청을 할 때 발생할 수 있는 몇 가지 일반적인 문제가 나열되어 있습니다. 권장 솔루션으로 이러한 문제를 해결해 보십시오. 권장 솔루션으로 문제가 해결되지 않으면 작업을 저장하고 컴퓨터를 다시 시작한 다음 다른 응용 프로그램을 실행하거나 사용하지 않고 요청을 다시 시도하십시오.

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
    <b>최신 버전의 Microsoft Excel로 업데이트</b>: 새 버전의 Microsoft Excel을 릴리스하고 이전 버전을 사용하는 경우 벌크 관리 워크시트에 인증 오류가 발생할 수 있습니다. 최신 버전의 Microsoft Excel로 업데이트하여 인증 오류를 해결합니다.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>긴 지연</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>호환성 모드 해제</b>: Microsoft Excel의 호환성 모드에서 다른 워크시트가 열려 있는지 확인하십시오. 호환 모드는 실행 시간을 늘릴 수 있습니다. 이 모드에서 열려 있는 스프레드시트를 닫고 대량 요청을 다시 시도하십시오. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>시스템 리소스</b>: 제한된 시스템 리소스는 긴 지연에 기여합니다. 일괄 요청하기 전에 다른 프로그램을 모두 닫아 보십시오. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>응답 없음</b> </td> 
   <td colname="col2">작업 버튼을 클릭해도 아무 일도 발생하지 않는 경우: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">선택 작업에 적합한 헤더 세트가 있는지 확인합니다. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">복사한 헤더에 올바른 워크시트를 사용하고 있는지 확인합니다. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">대량 작업에 사용할 데이터의 위치를 확인합니다. 모든 헤더는 열 A, 행 1에서 시작합니다. 모든 데이터는 열 A, 행 2(헤더 바로 아래)에서 시작하는 해당 헤더에 삽입됩니다. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 오류 메시지

경우에 따라 일괄 변경 시 오류 메시지를 받을 수 있습니다. 오류 메시지를 해석하려면 API 설명서에서 [정의된 응답 코드](/help/using/api/rest-api-main/aam-api-getting-started.md)를 참조하십시오.
