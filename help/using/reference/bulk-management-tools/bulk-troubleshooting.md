---
description: 워크시트에서 오류를 반환하거나 벌크 요청이 실패할 경우 수행할 작업
seo-description: 워크시트에서 오류를 반환하거나 벌크 요청이 실패할 경우 수행할 작업
seo-title: 벌크 관리 도구 문제 해결 팁
solution: Audience Manager
title: 벌크 관리 도구 문제 해결 팁
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 5%

---

# 벌크 관리 도구 문제 해결 팁{#troubleshooting-tips-for-bulk-management-tools}

워크시트에서 오류를 반환하거나 벌크 요청이 실패할 경우 수행할 작업



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[RBAC 그룹 ](../../features/administration/administration-overview.md) 권한 [!DNL Audience Manager] 이 UI에 할당되어  [!UICONTROL Bulk Management Tools]있습니다.

대량 네트워크 트래픽, 서버 사용량 및 대규모 데이터 세트와 같은 요인으로 인해 대량 요청이 실패하거나 시간 초과될 수 있습니다. 문제가 발생하면 워크시트에서 데이터 쓰기를 중단하고 오류 메시지를 표시합니다. 이런 경우 다음을 수행해야 합니다.

* 오류 메시지를 읽습니다.
* 문제를 해결합니다.
* 이미 업데이트된 모든 행을 삭제합니다.
* 벌크 요청을 다시 시도하십시오.

## 인증 오류, 긴 지연 또는 응답하지 않는 동작 {#delays-behavior}

다음 표에는 워크시트를 사용하여 벌크 요청을 수행할 때 발생할 수 있는 몇 가지 일반적인 문제가 나와 있습니다. 권장 솔루션으로 이러한 문제를 해결하려고 합니다. 권장 솔루션에서 문제를 해결하지 못하면 작업을 저장하고 컴퓨터를 다시 시작한 다음 다른 응용 프로그램을 시작하거나 사용하지 않고 요청을 다시 시도하십시오.

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
    <b>최신 버전의 Microsoft Excel로 업데이트</b>:새 버전의 Microsoft Excel을 릴리스하고 이전 버전을 사용하는 경우 벌크 관리 워크시트에서 인증 오류가 발생할 수 있습니다. 인증 오류를 해결하려면 최신 버전의 Microsoft Excel로 업데이트하십시오.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>긴 지연</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>호환성 모드 해제</b>:Microsoft Excel의 호환성 모드에서 열려 있는 다른 워크시트가 있는지 확인합니다. 호환성 모드는 런타임 속도를 높일 수 있습니다. 이 모드에서 열려 있을 수 있는 스프레드시트를 모두 닫고 벌크 요청을 다시 시도하십시오. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>시스템 리소스</b>:시스템 리소스가 제한되므로 지연 시간이 오래 걸립니다. 대량 요청을 수행하기 전에 다른 프로그램을 모두 닫으십시오. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>응답 없음</b> </td> 
   <td colname="col2">작업 버튼을 클릭하면 아무 일도 발생하지 않습니다. 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">선택 작업에 올바른 헤더 세트가 있는지 확인합니다. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">복사된 헤더에 올바른 워크시트를 사용하고 있는지 확인합니다. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">대량 작업에 사용할 데이터의 위치를 확인합니다. 모든 헤더는 열 A, 행 1에서 시작합니다. 모든 데이터는 열 A, 행 2(머리글 바로 아래)에서 시작하는 해당 헤더로 이동합니다. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 오류 메시지

벌크 변경 시 오류 메시지가 표시되는 경우가 있습니다. 오류 메시지를 해석하려면 API 설명서에서 [정의된 응답 코드](/help/using/api/rest-api-main/aam-api-getting-started.md)를 참조하십시오.
