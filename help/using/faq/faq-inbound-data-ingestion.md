---
description: 오프라인 데이터를 Audience Manager로 가져오는 방법에 대한 FAQ입니다.
keywords: ftp or s3;s3 or ftp
seo-description: 오프라인 데이터를 Audience Manager로 가져오는 방법에 대한 FAQ입니다.
seo-title: 인바운드 고객 데이터 통합 FAQ
solution: Audience Manager
title: 인바운드 고객 데이터 통합 FAQ
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: f2f3e40e7866c7610de520952f5dfd65823554f3

---


# 인바운드 고객 데이터 통합 FAQ{#inbound-customer-data-ingestion-faq}

오프라인 데이터를 Audience Manager로 가져오는 방법에 대한 FAQ입니다.

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**입사 절차를 요약해주시겠어요?**

온보딩 프로세스는 설명된 배치 데이터 전송 [프로세스에 설명된 두 가지 핵심 구성 요소로 구성됩니다](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md). 여기에는 다음이 포함됩니다.

* ID 동기화
* 인바운드 데이터 파일( [!DNL .sync] 파일 또는 [!DNL .overwrite] 파일)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

다음은 설명서를 검토한 후 도움이 될 수 있는 질문과 대답 목록입니다.

>[!NOTE]
>
>이 섹션의 예는 간결성 및 데모를 위해 단순화하거나 단축되었습니다. 파일 형식 및 구문에 대한 자세한 사양은 인바운드 데이터 통합 문서를 참조하십시오.

<br> 

**배포 프로세스를 요약할 수 있습니까?**

다음 사항을 권장합니다.

* 데이터 제공업체와 협력하여 [!DNL Adobe] 사양에 따라 일일 인바운드 데이터 파일의 형식을 지정합니다.
* 형식 확인을 위해 테스트 데이터 파일을 [!DNL Adobe] 로 전송합니다.
* 컨설턴트와 협력하여 데이터 파일의 내용을 해석하는 데 적합한 분류법을 만듭니다. [!DNL Adobe]
* 스테이징/개발 환경에서 ID 동기화가 데이터 공급자의 방문자 ID를 제대로 선택하여 [!DNL Audience Manager] 서버에 실시간으로 전송되도록 구성되었는지 확인합니다.
* 프로덕션에 DIL/ID 동기화 배포 ID 동기화는 Adobe 컨설턴트가 DIL 코드 내에 모듈로 이미 구성됩니다.
* 프로덕션 데이터 파일을 로 [!DNL Audience Manager]전송합니다. ID 동기화 매핑에 대한 종속성이 있는 경우 코드가 프로덕션으로 들어가는 즉시 데이터 파일 전송을 시작할 수 있지만 프로덕션 코드 배포 후 최대 1주까지의 데이터 전송을 시작하는 것이 적절할 수 있습니다.

<br> 

**압축 또는 암호화된 파일을 전송하려면 어떤 FTP 모드를 사용해야 합니까?**

인바운드 [데이터 전송 파일에 대한 파일 압축을 참조하십시오](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**[!DNL Audience Manager]코드를 프로덕션에 배포하기 전에 인바운드 데이터 파일([!DNL .sync]또는[!DNL .overwrite]파일)을 업로드할 수 있습니까?**

* 데이터 공급자가 크로스 장치 [타깃팅에 프로필](../features/profile-merge-rules/merge-rules-overview.md) 링크를 사용하도록 구성된 경우 ID 동기화 직후 타깃팅에 사용할 수 있는 데이터는 일치하는 [!DNL Audience Manager] 방문자 ID를 식별합니다.

* 데이터 공급자가 이 [!UICONTROL Profile Link] 기능을 사용하도록 구성되지 않은 경우, 이전에 동기화되었거나 [!DNL Audience Manager] [!DNL Audience Manager] 방문자 ID에 대응한 인바운드 데이터 파일에서 방문자 ID에 대한 데이터만 처리합니다.

데이터 공급자가 사용하도록 구성되지 않은 다음 사용 사례를 [!UICONTROL Profile Merge]고려하십시오.

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>사례 1</b> </p> </td> 
   <td colname="col2"> <p>월요일에 CRM 데이터베이스에서 방문자 ABC로 식별된 방문자가 로그인하고 클라이언트측 ID 동기화를 시작합니다. <span class="keyword"> Audience Manager</span> 는 방문자 ABC와 Audience Manager <span class="keyword"> 방문자 123의</span> 매핑을 저장합니다. </p> <p>화요일, CRM 데이터베이스는 데이터 파일(.sync<span class="filepath"> )을</span>다음 레코드와 함께 Audience Manager <span class="keyword"> </span>서버로 전송합니다. </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>이 경우 Audience Manager <span class="keyword"></span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">저장된 ID 동기화 매핑에서 방문자 ABC를 인식합니다. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> 트레이트와 방문자 123 <code> male</code> 프로필을 <code> luxury_shopper</code> 연결합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>사례 2</b> </p> </td> 
   <td colname="col2"> <p>월요일, CRM 데이터베이스는 데이터 파일(.sync<span class="filepath"> )을 Audience Manager</span>서버로 푸시하여 <span class="keyword"></span> 다음 레코드를 저장합니다. </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience</span> Manager에 이 방문자(또는 관련 방문자 ID)의 레코드가 없으므로 이 레코드가 처리되지 않습니다. </p> <p>화요일에 방문자 DEF가 로그인합니다. 이 작업은 해당 방문자에 대한 첫 번째 클라이언트측 ID 동기화를 시작합니다. 이 작업은 방문자 DEF를 Audience Manager ID <span class="keyword"> 456에</span> 매핑합니다. 하지만 이 방문자는 프로필과 연결된 CRM 데이터를 가지고 있지 않습니다. 따라서 Audience Manager <span class="keyword"> 는</span> 다시 돌아가 이전 파일을 다시 처리하지 않습니다. </p> <p>수요일에는 CRM 데이터베이스가 다른 데이터 파일을 Audience <span class="keyword"> Manager</span> 서버로 푸시합니다. </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>이 경우 Audience Manager <span class="keyword"></span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">저장된 ID 동기화 매핑에서 방문자 DEF를 인식합니다. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">트레이트 <code> female</code>및 <code> paris</code>방문자 456 프로필을 <code> wine_enthusiast</code> 연결합니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>사례 3</b> </p> </td> 
   <td colname="col2"> <p>월요일에 Audience Manager <span class="keyword"> 서버는</span> 다음 레코드가 있는 두 개의 파일을 받습니다. </p> <p> <code> .sync</code> 다음을 포함하는 파일: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> 다음을 포함하는 파일: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience</span> Manager는 이전 ID 동기화에서 방문자 JKL의 매핑된 레코드를 ID 789로 보유합니다. </p> <p>이 경우 Audience Manager <span class="keyword"></span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">저장된 ID 동기화 매핑에서 방문자 JKL을 인식합니다. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">트레이트와 방문자 ID <code> female</code> 789 <code> wine_enthusiast</code> 의 프로필을 연결합니다. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">방문자 GHI에 대한 트레이트 연결을 무시합니다. 방문자 ID가 현재 배치에만 동기화되었기 때문입니다. 트레이트를 방문자 GHI와 연결하려면 이후 <code> .overwrite</code> 파일에 트레이트를 포함해야 합니다. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

<br> 

**파일을 언제 전송해야 합니까?**

[!DNL Audience Manager] 하루 종일 여러 번 파일을 확인하고 처리합니다. 언제든지 데이터 업로드

<br> 

**업로드된 파일의 데이터를 타깃팅하는 데 얼마나 걸립니까?**

데이터는 48시간 후에 타깃팅할 수 있습니다. 또한 &quot;성공적인 업로드&quot; 이메일을 데이터를 사용할 수 있다는 설명으로 해석하지 마십시오. 즉, 파일을 [!DNL Audience Manager] 선택하고 첫 번째 처리 단계를 완료한 것입니다.

<br> 

**파일을 얼마나 자주 전송해야 하며 전체 또는 증분 파일이어야 합니까?**

새 방문자와 데이터가 변경된 방문자에 대해 매일 증분 파일을 보내는 것이 좋습니다. 많은 [!DNL Audience Manager] 고객이 매월 전체 파일을 보냅니다. 그러나 이러한 파일 간격과 증분은 유연합니다. 데이터를 증분으로 전송해야 합니다.

<br> 

**Audience Manager는 서버에 파일을 얼마나 오래 보관합니까?**

FTP 파일은 처리된 후에 제거됩니다. [!DNL S3] 파일은 30일 후 제거됩니다. 형식, 구문 또는 기타 오류로 인해 처리할 수 없는 파일은 제거됩니다. 개인 정보 및 [데이터 유지 FAQ도 참조하십시오](../faq/faq-privacy.md).

<br> 

**전체 파일과 증분 파일의 차이점은 무엇입니까?**

* **** 전체:전체 파일은 모든 기존 방문자 프로필을 덮어쓰고 파일의 데이터로 대체합니다. 전체 파일은 파일 이름에 추가된 `.overwrite` 태그로 식별됩니다. 파일을 사용하여 방문자 트레이트를 재설정하거나 오래된 트레이트를 제거할 수 있습니다. `.overwrite`

   >[!NOTE]
   >
   >이 [!DNL .overwrite] 파일은 이 데이터 공급자에 연결된 [!DNL Audience Manager] 프로필 데이터만 덮어씁니다. 즉, [!DNL Adobe Analytics] [!DNL .overwrite] 파일이 처리된 후에도 방문자와 연관된 모든 데이터는 그대로 유지됩니다.

* **** 증분:증분 파일은 기존 방문자 프로필에 새 데이터를 추가합니다. 증분 파일은 파일 이름에 추가된 `.sync` 태그로 식별됩니다. 증분 파일에서 전송해도 기존 프로필을 지우거나 덮어쓰지 않습니다.

다음 사용 사례는 이러한 파일 유형이 저장된 방문자 프로필에 어떤 영향을 미치는지 보여줍니다.

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>증분 및 전체</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">1일 <code> .sync</code> 파일 내용: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">2일 <code> .overwrite</code> 파일 내용: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> 3일 방문자 프로필 ID 123이 다음을 포함 <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>증분 전용</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">1일 <code> .sync</code> 파일 내용: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">2일 <code> .sync</code> 파일 내용: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">3일 방문자 프로필 ID 123이 다음을 포함 <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

전체 및 증분 파일 유형에 대한 자세한 내용은 다음을 참조하십시오.

* [인바운드 데이터의 Amazon S3 이름 및 파일 크기 요구 사항...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**페이지 내 ID 동기화를 수행한 적이 없는 방문자를 위해 ID가 있는 파일을 보내면 어떻게 됩니까?**

처리하는 동안 해당 레코드를 건너뛰고 다음 레코드로 이동합니다 [!DNL Audience Manager] . DPID(데이터 공급자 ID)가 크로스 장치 DPID로 설정된 경우 ID 동기화 전에 인제스트된 데이터가 저장되고 ID 동기화가 발생한 직후 사용할 수 있습니다.

<br> 

**타임스탬프는 무엇이며 어떤 용도로 사용할 수 있으며 예를 제공할 수 있습니까?**

타임스탬프는 기록 및 기록 유지에 사용됩니다. 올바른 형식의 인바운드 파일 이름에 사용되는 구문에 필요합니다. 다음을 참조하십시오.

* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**DPID(데이터 공급자 ID)란 무엇이며 어떻게 얻습니까?**

Adobe 컨설턴트는 특정 데이터 소스에 3자리 또는 4자리 DPID를 할당합니다. 이 ID는 고유하며 변경되지 않습니다.

<br> 

**일별 데이터 파일의 크기는 얼마나 됩니까?**

인바운드 [데이터 전송 파일에 대한 파일 압축을 참조하십시오](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Audience Manager는 파일 압축을 지원합니까?**

예. 다음을 참조하십시오.

* [인바운드 데이터 전송 파일에 대한 파일 압축](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**데이터 소스 데이터베이스의 기본 키는 이메일 주소입니다. 개인 식별 정보로 간주됩니까?**

예. [!DNL Audience Manager] 은 데이터베이스에 이메일 주소를 저장하지 않습니다. 방문자는 ID 동기화를 시작하기 전에 임의 ID 또는 단방향 해시된 이메일 주소 버전을 지정해야 합니다.

<br> 

**데이터 파일 내용은 대/소문자를 구분합니까? ID 동기화는 어떻습니까?**

데이터 파일에는 두 가지 기본 구성 요소가 있습니다.사용자 ID(정의된 [파일 변수의 사용자](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)ID 참조) 및 프로필 데이터(일반적으로 키-값 쌍 또는 코드 형식) 사용자 ID는 대/소문자를 구분합니다. 일반적으로 프로필 또는 키 값 데이터는 대/소문자를 구분하지 않습니다.

<br> 

**FTP를 사용해야 합니까, 아니면 파일을[!DNL Amazon S3]전송해야 합니까?**

가장 좋은 방법은 프로세스가 단순하기 [!DNL Amazon S3] 때문에 권장합니다. [!DNL Audience Manager] FTP 파일을 [!DNL S3] 에 전송하지 않아도 되므로 파일을 직접 드롭하면 프로세스가 더욱 간소화됩니다 [!DNL Amazon S3] . 또한 FTP에 동시에 업로드하는 고객은 FTP의 대역폭을 공유하므로 업로드 속도가 느려질 것으로 예상됩니다. [!DNL Amazon S3] 는 복제되고 배포되므로 FTP 서버보다 일반적으로 더 안전하고 안정적입니다. 자세한 내용은 Amazon [S3를](../reference/amazon-s3.md)참조하십시오.

<br> 

**Audience Manager는 인바운드 파일을 어떻게 처리합니까?**

[!DNL Audience Manager] 은 인바운드 데이터 처리에 [!DNL Amazon Simple Queue Service (SQS)] 사용됩니다. 이 방법은 다음과 같습니다.

1. [!DNL Audience Manager] 고객은 인바운드 데이터를 [!DNL Amazon S3] 버킷에 업로드합니다.

2. 데이터가 대기열로 진입하여 처리 대기 [!DNL Amazon SQS] [!DNL Audience Manager]중입니다.

3. [!DNL Audience Manager] 큐에서 최대 11,9000개의 항목을 읽고 최대 3개의 배치로 분할합니다. [!DNL Amazon SQS] 각 일괄 처리에 있는 파일은 동시에 처리됩니다.

<br> 

**여러 파일을 동시에 업로드해야 합니다. 파일이 동시에 처리됩니까?**

상황에 따라 다릅니다. [!DNL Audience Manager] 큐에서 최대 11,9000개의 항목을 읽고 최대 3개의 배치로 분할합니다. [!DNL Amazon SQS] 파일이 동일한 배치로 끝나는 경우에만 동시에 처리됩니다. 그러나 [!DNL Audience Manager] 매일 수집되는 데이터의 양이 많기 때문에 파일 처리 순서를 보장할 수 없습니다.

>[!MORELIKETHIS]
>
>* [배치 데이터 전송 프로세스 설명](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

