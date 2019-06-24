---
description: 오프라인 데이터를 Audience Manager로 가져오는 FAQ
keywords: FTP 또는 S 3; S 3 또는 FTP
seo-description: 오프라인 데이터를 Audience Manager로 가져오는 FAQ
seo-title: 인바운드 고객 데이터 통합 FAQ
solution: Audience Manager
title: 인바운드 고객 데이터 통합 FAQ
uuid: 491 E 9 EC 1-4731-46 A 8-86 E 7-D 8 C 613 E 6 CEDC
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Inbound Customer Data Ingestion FAQ{#inbound-customer-data-ingestion-faq}

오프라인 데이터를 Audience Manager로 가져오는 FAQ

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**온보딩 프로세스를 요약할 수 있습니까?**

The onboarding process consists of 2 core components described in [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process). 이러한 작업에는 다음이 포함됩니다.

* ID 동기화
* Inbound Data File ( [!DNL .sync] file or [!DNL .overwrite] file)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

다음은 설명서를 검토한 후 도움이 되는 질문과 대답 목록입니다.

>[!NOTE]
>
>이 섹션의 예는 간결하고 시의적절한 목적으로 단순화 또는 단축됩니다. 파일 형식 및 구문에 대한 자세한 사양은 인바운드 데이터 통합 설명서를 참조하십시오.

<br> 

**배포 프로세스를 요약할 수 있습니까?**

다음 사항을 권장합니다.

* Work with your data provider to format the daily inbound data file according to [!DNL Adobe] specifications.
* Transfer a test data file to [!DNL Adobe] for format verification.
* [!DNL Adobe] 컨설턴트와 협력하여 데이터 파일의 컨텐츠를 해석하는 데 적합한 분류법을 생성합니다.
* In the staging/development environment, confirm that the ID sync is configured to properly pick up the data provider&#39;s visitor ID and transfer it to the [!DNL Audience Manager] servers in realtime.
* DIL/ID 동기화를 프로덕션에 배포합니다. ID 동기화는 Adobe 컨설턴트가 DIL 코드 내에서 모듈로 이미 구성됩니다.
* Transfer production data files to [!DNL Audience Manager]. ID 동기화 매핑에 대한 종속성을 감안할 때, 코드가 프로덕션으로 들어가는 즉시 데이터 파일을 전송할 수 있지만 프로덕션 코드 배포 후 최대 1 주일 전에 데이터 전송을 시작하는 것이 적절할 수 있습니다.

<br> 

**압축되거나 암호화된 파일을 전송하는 데 어떤 FTP 모드를 사용해야 합니까?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**[!DNL Audience Manager]코드를 프로덕션에 배포하기 전에 인바운드 데이터 파일([!DNL .sync]또는[!DNL .overwrite]파일)을 업로드할 수 있습니까?**

* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

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
   <td colname="col2"> <p>월요일에, 방문자 ABC가 로그인하는 동안 CRM 데이터베이스에 식별된 방문자가 클라이언트측 ID 동기화를 시작합니다. <span class="keyword"> Audience Manager</span> 는 방문자 ABC의 매핑을 <span class="keyword"> Audience Manager</span> 방문자 123에 저장합니다. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender" = "male", "luxury_ shopper" = "yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">저장된 ID 동기화 매핑에서 방문자 ABC를 인식합니다. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>사례 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> def "gender" = "female", "wine_ celeast" = "yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager 에는</span> 이 방문자 (또는 관련 방문자 ID) 기록이 없으므로 이 레코드는 처리되지 않습니다. </p> <p>화요일에 방문자 DEF가 로그인됩니다. 이 작업은 해당 방문자에 대해 첫 번째 클라이언트측 ID 동기화를 시작합니다. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. 그러나 이 방문자의 프로필에는 CRM 데이터가 연결되어 있지 않습니다. <span class="keyword"> 따라서 Audience Manager</span> 는 이전 파일을 다시 처리하지 않습니다. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> def "gender" = "female", "wine_ enthusiast" = "yes", "dma" = "paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">저장된 ID 동기화 매핑에서 방문자 DEF를 인식합니다. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>사례 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .</code> 포함된 파일 동기화: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> . 다음을 포함한</code> 파일을 덮어씁니다. </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> ghi "gender" = "male" "wine_ celeast" = "no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender" = "female" "wine_ applet enthusiast" = "yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> 는 이전 ID 동기화에서 ID 789에 방문자 JKL의 매핑된 레코드를 보유합니다. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">저장된 ID 동기화 매핑에서 방문자 JKL를 인식합니다. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">방문자 GHI가 현재 묶음에 동기화되었기 때문에 방문자 GHI에 대한 특성 연결을 무시합니다. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**파일을 언제까지 전송해야 합니까?**

[!DNL Audience Manager] 하루 종일 여러 번 파일을 확인하고 처리합니다. 언제든지 데이터를 업로드할 수 있습니다.

<br> 

**업로드한 파일의 데이터를 타깃팅에 사용할 수 있으려면 얼마나 걸립니까?**

데이터는 48 시간 후 타깃팅에 사용할 수 있습니다. 또한, &quot;성공적인 업로드&quot; 이메일을 데이터를 사용할 수 있다는 메시지로 해석하지 마십시오. This only means that [!DNL Audience Manager] has picked up the file and completed the first step of processing.

<br> 

**파일을 얼마나 자주 보내야 합니까? 아니면 전체 파일이나 증분 파일이어야 합니까?**

우수 사례로서 새 방문자와 데이터가 변경된 방문자에 대해 하루에 한 번 증분 파일을 보낼 수 있습니다. Many [!DNL Audience Manager] customers send a full file once per month. 그러나 이러한 파일 간격과 증분은 유연합니다. 데이터를 증분적으로 전송해야 합니다.

<br> 

**Audience Manager는 얼마 동안 서버에 파일을 보관합니까?**

FTP 파일은 처리된 후 제거됩니다. [!DNL S3] 파일은 30 일 후에 제거됩니다. 형식, 구문 또는 다른 오류로 인해 처리할 수 없는 파일은 제거됩니다. [개인 정보 및 데이터 유지 FAQ](../faq/faq-privacy.md)를 참조하십시오.

<br> 

**전체 파일과 증분 파일의 차이점은 무엇입니까?**

* **전체:** 전체 파일은 기존의 모든 방문자 프로필을 덮어쓰고 파일의 데이터로 대체합니다. Full files are identified by the `.overwrite` tag appended to the file name. `.overwrite` 파일을 사용하여 방문자 특성을 재설정하거나 오래된, 오래된 트레이트를 제거할 수 있습니다.

   >[!NOTE]
   >
   >The [!DNL .overwrite] files only overwrite [!DNL Audience Manager] profile data associated to this data provider. In other words, all [!DNL Adobe Analytics] data associated to the visitor remains intact after a [!DNL .overwrite] file has been processed.

* **증분:** 증분 파일은 기존 방문자 프로필에 새 데이터를 추가합니다. Incremental files are identified by the `.sync` tag appended to the file name. 증분 파일로 전송해도 기존 프로필을 지우거나 덮어쓰지 않습니다.

다음 사용 사례는 이러한 파일 유형이 저장된 방문자 프로필에 어떤 영향을 주는지 보여줍니다.

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
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4"><code> 1 일.</code> 파일 내용 동기화: <code> 방문자 123 = A, B, C</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Day 2 <code> .overwrite</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Day 3 visitor profile ID 123 contains <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Incremental만 해당</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891"><code> 1 일.</code> 파일 내용 동기화: <code> 방문자 123 = A, B, C </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415"><code> 2 일.</code> 파일 내용 동기화: <code> 방문자 123 = C, D, E</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Day 3 visitor profile ID 123 contains <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

전체 및 증분 파일 유형에 대한 자세한 내용은 다음을 참조하십시오.

* [인바운드 데이터에 대한 Amazon S 3 이름 및 파일 크기 요구 사항...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**페이지에서 ID 동기화를 수행하지 않은 방문자에 대해 ID로 파일을 보내면 어떻게 됩니까?**

During processing, [!DNL Audience Manager] simply skips that record and moves on to the next. DPID (데이터 공급자 ID) 가 장치 간 DPID로 설정된 경우 ID 동기화가 동기화되기 전에 인제스트되는 데이터는 ID 동기화가 발생한 직후 사용할 수 있습니다.

<br> 

**타임스탬프는 무엇이며, 어떤 제품이며, 예를 제공할 수 있습니까?**

타임스탬프는 기록 및 기록 보관에 사용됩니다. 올바른 형식의 인바운드 파일 이름에 사용된 구문에서 필요합니다. 다음을 참조하십시오.

* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**데이터 공급자 ID (DPID) 는 무엇이며 어떻게 다운로드합니까?**

Adobe 컨설턴트가 특정 데이터 소스에 3 자리 또는 4 자리 DPID를 할당합니다. 이 ID는 고유하며 변경되지 않습니다.

<br> 

**일별 데이터 파일은 얼마나 클 수 있습니까?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Audience Manager는 파일 압축을 지원합니까?**

예, 다음을 참조하십시오.

* [인바운드 데이터 전송 파일을 위한 파일 압축](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**데이터 소스 데이터베이스의 기본 키는 이메일 주소입니다. Is that considered personally identifiable information?**

예. [!DNL Audience Manager] 는 이메일 주소를 데이터베이스에 저장하지 않습니다. 방문자에게 ID 동기화를 시작하기 전에 무작위 ID 또는 단방향 이메일 주소를 할당해야 합니다.

<br> 

**데이터 파일 컨텐츠가 대소문자를 구분합니까? How about the ID sync?**

데이터 파일에는 두 가지 기본 구성 요소가 있습니다. 고유 사용자 ID (UUID) 및 프로필 데이터 (일반적으로 키-값 쌍 또는 코드 형식) UUID는 대소문자를 구분합니다. 일반적으로 프로필 또는 키-값 데이터는 대/소문자를 구분하지 않습니다.

<br> 

**FTP를 사용하거나 파일을[!DNL Amazon S3]전송해야 합니까?**

As best practice, we recommend [!DNL Amazon S3] because the process is simpler. [!DNL Audience Manager] FTP 파일을 [!DNL S3] 전송할 수 있으므로 파일을 [!DNL Amazon S3] 직접 놓는 경우 프로세스가 더욱 간소화됩니다. 또한 FTP에 동시에 업로드하는 고객은 FTP 대역폭을 공유하므로 업로드 속도가 느려져야 합니다. [!DNL Amazon S3] 또한 복제 및 배포되므로 일반적으로 FTP 서버보다 안전하고 안정성이 높습니다. For more information, see [About Amazon S3](../reference/amazon-s3.md).

<br> 

**고객 관리자가 인바운드 파일을 처리하는 방법은?**

[!DNL Audience Manager] 인바운드 [!DNL Amazon Simple Queue Service (SQS)] 데이터 처리에 사용됩니다. 작동 방식은 다음과 같습니다.

1. [!DNL Audience Manager] 고객은 자신의 인바운드 데이터를 [!DNL Amazon S3] 버킷에 업로드합니다.

2. The data enters the [!DNL Amazon SQS] queue, waiting to be processed by [!DNL Audience Manager].

3. [!DNL Audience Manager][!DNL Amazon SQS] 큐에서 최대 119,000 개의 항목을 읽고 최대 3 개의 일괄적으로 분할합니다. 각 일괄 처리의 파일은 동시에 처리됩니다.

<br> 

**여러 파일을 동시에 업로드해야 합니다. Will the files be processed simultaneously?**

다릅니다. [!DNL Audience Manager][!DNL Amazon SQS] 큐에서 최대 119,000 개의 항목을 읽고 최대 3 개의 일괄적으로 분할합니다. 파일은 동일한 일괄 처리 작업으로 끝나는 경우에만 동시에 처리됩니다. However, due to the high amount of data ingested by [!DNL Audience Manager] on a daily basis, we cannot guarantee any file processing order.

>[!MORE_ like_ this]
>
>* [일괄 데이터 전송 프로세스 설명](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process)

