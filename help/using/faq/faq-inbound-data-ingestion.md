---
description: 오프라인 데이터를 Audience Manager에 가져오는 것에 대한 FAQ입니다.
keywords: ftp 또는 s3;s3 또는 ftp
seo-description: Frequently asked questions about bringing offline data into Audience Manager.
seo-title: Inbound Customer Data Ingestion FAQ
solution: Audience Manager
title: 인바운드 고객 데이터 섭취 FAQ
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
feature: Onboarding Offline Data
exl-id: 48eef5f1-0655-4dac-9ab4-74b11c705c13
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1343'
ht-degree: 86%

---

# 인바운드 고객 데이터 섭취 FAQ{#inbound-customer-data-ingestion-faq}

오프라인 데이터를 Audience Manager에 가져오는 것에 대한 FAQ입니다.

 

**온보딩 프로세스를 요약해줄 수 있습니까?**

온보딩 프로세스는 [Audience Manager로 배치 데이터 보내기 개요](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)에 설명된 두 개의 단계로 구성됩니다.

* 1단계: 사용자 ID 동기화
* 2단계: 파일 형식 요구 사항을 준수하여 인바운드 데이터 파일을 만들고 전송

 

**배포 프로세스를 요약해줄 수 있습니까?**

다음 사항을 권장합니다.

* 데이터 공급자와 협력하여 Adobe 사양에 따라 일별 인바운드 데이터 파일의 형식을 지정합니다. 파일 이름 지정 및 구문 요구 사항에 대해서는 다음 설명서를 참조하십시오.
   * [ID 동기화 파일 이름 및 컨텐츠 요구 사항](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [인바운드 데이터 파일 내용: 구문, 잘못된 문자, 변수 및 예](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [인바운드 데이터 파일에 대한 Amazon S3 이름 및 파일 크기 요구 사항](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* 형식 확인을 위해 [!DNL Adobe] 컨설턴트와 함께 테스트 데이터 파일을 [!DNL Adobe]에 전송합니다.
* [!DNL Adobe] 컨설턴트와 협력하여 데이터 파일의 내용을 해석하는 데 적합한 분류법을 생성합니다.
* 스테이징/개발 환경에서 ID 동기화가 데이터 공급자의 방문자 ID를 올바로 선택하고 이를 실시간으로 [!DNL Audience Manager] 서버에 전송하도록 구성되어 있는지 확인합니다.
* DIL/ID 동기화를 프로덕션에 배포합니다. ID 동기화는 Adobe 컨설턴트에 의해 DIL 코드 내에 모듈로 이미 구성되어 있습니다.
* 프로덕션 데이터 파일을 [!DNL Audience Manager]에 전송합니다. ID 동기화 매핑에 대한 종속성이 있는 경우, 코드가 프로덕션에 들어가는 즉시 데이터 파일 전송을 시작할 수 있지만 프로덕션 코드를 배포하고 최대 1주일 후까지는 데이터 전송을 시작하는 것이 적절할 수 있습니다.

 

**압축되었거나 암호화된 파일을 전송하는 데 어떤 FTP 모드를 사용해야 합니까?**

[인바운드 데이터 전송 파일에 대한 파일 압축](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)을 참조하십시오.

>[!WARNING]
>
>FTP 구성에 대한 지원을 점차 단계적으로 중단하고 있습니다. 기존 FTP 통합에서는 인바운드 데이터 파일 섭취가 여전히 지원되지만 새로운 통합을 위해 Amazon S3을 사용하여 오프라인 데이터를 온보딩하는 것이 좋습니다. 자세한 내용은 [인바운드 데이터 파일에 대한 Amazon S3 이름 및 파일 크기 요구 사항](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)을 참조하십시오.

 

**[!DNL Audience Manager] 코드를 프로덕션에 배포하기 전에 인바운드 데이터 파일([!DNL .sync] 또는 [!DNL .overwrite] 파일)을 업로드할 수 있습니까?**

예. [!UICONTROL cross-device data source]을(를) 사용하여 업로드한 CRM 데이터를 저장하는 한 Audience Manager은 항상 데이터를 저장합니다. 실제로 오프라인 전용 사용 사례를 허용하는 2019년 10월에 Audience Manager이 실행한 [!UICONTROL Profile Merge Rules] 개선 사항에 따라 Audience Manager 코드를 프로덕션에 배포하지 않고도 데이터를 업로드하고 작업을 수행할 수 있습니다. 다음을 참조하십시오.

* [프로필 병합 규칙 개선 사항 개요](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] - [오프라인 전용 데이터를 기반으로 하는 Personalization](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

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

**파일은 하루 중 언제 전송해야 합니까?**

[!DNL Audience Manager]에서는 하루 종일 여러 번 파일을 확인하고 처리합니다. 준비되면 언제든지 데이터 업로드하십시오.

 

**업로드된 파일의 데이터를 타겟팅할 수 있게 되는 데 시간이 얼마나 걸립니까?**

데이터는 48시간 후에 타겟팅할 수 있습니다. 또한 &quot;업로드 성공&quot; 이메일을 데이터를 사용할 수 있다는 의미로 해석하지 마십시오. 이 이메일은 [!DNL Audience Manager]가 파일을 선택했고 첫 번째 처리 단계를 완료했다는 의미일 뿐입니다.

 

**파일을 얼마나 자주 보내야 하며 이때 파일들은 전체여야 합니까 아니면 증분 파일이어야 합니까?**

새 방문자와 데이터가 변경된 방문자에 대해 하루에 한 번씩 증분 파일을 보내는 것이 좋습니다. 많은 [!DNL Audience Manager] 고객이 월 1회 전체 파일을 보냅니다. 그러나 이러한 파일 간격과 증분은 유연합니다. 데이터를 증분으로 전송해야 하며 가끔씩 적절할 때 전송해야 합니다.

 

**Audience Manager는 내 파일을 서버에 얼마나 오래 보관합니까?**

FTP 파일은 처리된 후에 제거됩니다. [!DNL S3] 파일은 30일 후 제거됩니다. 형식, 구문 또는 기타 오류로 인해 처리할 수 없는 파일은 제거됩니다. [개인 정보 보호 및 데이터 유지 관련 FAQ](../faq/faq-privacy.md)를 참조하십시오.

 

**전체 파일과 증분 파일 간의 차이점은 무엇입니까?**

* **전체:** 전체 파일은 기존 방문자 프로필을 모두 덮어쓰고 파일의 데이터로 대체합니다. 전체 파일은 파일 이름에 첨부된 `.overwrite` 태그로 식별됩니다. `.overwrite` 파일을 사용하여 방문자 트레이트를 재설정하거나 오래되어 더 이상 쓸모가 없는 트레이트를 제거할 수 있습니다.

  >[!NOTE]
  >
  >[!DNL .overwrite] 파일은 이 데이터 공급자에 연결된 [!DNL Audience Manager] 프로필 데이터만 덮어씁니다. 즉, [!DNL .overwrite] 파일이 처리된 후에도 방문자와 연관된 모든 [!DNL Audience Manager] 데이터가 그대로 유지됩니다.

* **증분:** 증분 파일은 기존 방문자 프로필에 새 데이터를 추가합니다. 증분 파일은 파일 이름에 첨부된 `.sync` 태그로 식별됩니다. 증분 파일로 보내도 기존 프로필을 지우거나 덮어쓰지 않습니다.

다음 사용 사례에서는 이러한 파일 유형이 저장된 방문자 프로필에 어떻게 영향을 주는지 보여줍니다.

| 사용 사례 | 설명 |
|---|---|
| 증분 및 전체 | <ul><li>1일 `.sync` 파일 내용: `visitor123 = a,b,c`</li><li>2일 `.overwrite` 파일 내용: `visitor123 = c,d,e`</li><li>3일 방문자 프로필 ID 123 내용: `c,d,e`</li></ul> |
| 증분만 해당 | <ul><li>1일 `.sync` 파일 내용: `visitor123 = a,b,c`</li><li>2일 `.sync` 파일 내용: `visitor123 = c,d,e`</li><li>3일 방문자 프로필 ID 123 내용: `a,b,c,d,e`</li></ul> |

전체 파일 및 증분 파일 유형에 대한 자세한 내용은 다음 문서를 참조하십시오.

* [인바운드 데이터에 대한 Amazon S3 이름 및 파일 크기 요구 사항...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**페이지 내 ID 동기화를 수행하지 않은 방문자를 위해 ID가 있는 파일을 보내면 어떻게 됩니까?**

처리하는 동안 [!DNL Audience Manager]는 해당 레코드를 건너뛰고 다음으로 이동합니다. [DPID(데이터 공급자 ID)](../reference/ids-in-aam.md)가 교차 장치 DPID로 설정된 경우 ID 동기화 전에 섭취되는 데이터는 저장되고 ID 동기화 발생 직후 사용할 수 있습니다.

 

**타임스탬프는 무엇이며, 어떤 용도이며, 예를 들어줄 수 있습니까?**

타임스탬프는 기록 및 레코드 유지에 사용됩니다. 올바른 형식의 인바운드 파일 이름에 사용되는 구문에서 필요로 합니다. 다음을 참조하십시오.

* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**[!DNL Data Provider ID (DPID)]은(는) 무엇이며 어떻게 얻습니까?**

Adobe 컨설턴트는 특정 데이터 소스에 3자리 또는 4자리 [DPID(데이터 공급자 ID)](../reference/ids-in-aam.md)를 지정합니다. 이 ID는 고유하며 변경되지 않습니다.

 

**일별 데이터 파일의 크기는 얼마나 됩니까?**

[인바운드 데이터 전송 파일에 대한 파일 압축](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)을 참조하십시오.

 

**Audience Manager에서 파일 압축을 지원합니까?**

예. 다음 문서를 참조하십시오.

* [인바운드 데이터 전송 파일에 대한 파일 압축](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**데이터 소스 데이터베이스의 기본 키는 이메일 주소입니다. 이것은 개인 식별 정보로 간주됩니까?**

예. [!DNL Audience Manager]는 자체 데이터베이스에 이메일 주소를 저장하지 않습니다. 방문자는 ID 동기화를 시작하기 전에 임의로 생성된 ID 또는 이메일 주소의 단방향 해시 버전을 지정해야 합니다.

 

**데이터 파일 내용은 대/소문자를 구분합니까? ID 동기화는 어떻습니까?**

데이터 파일에는 [!UICONTROL User ID] ([정의된 파일 변수](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)의 [!UICONTROL User ID] 참조)와 프로필 데이터(일반적으로 키-값 쌍 또는 코드 형식), 이렇게 두 가지 기본 구성 요소가 있습니다. [!UICONTROL User ID]는 대/소문자를 구분합니다. 일반적으로 프로필 또는 키 값 데이터는 대/소문자를 구분하지 않습니다.

 

**FTP와 [!DNL Amazon S3] 중 어느 것을 사용하여 파일을 전송해야 합니까?**

가장 좋은 방법은 프로세스가 단순하기 때문에 [!DNL Amazon S3]을 사용하는 것입니다. [!DNL Audience Manager]는 FTP 파일을 어떻든지 [!DNL S3]에 전송하며, 따라서 직접 [!DNL Amazon S3]에 파일을 놓는 경우 프로세스가 보다 간소화됩니다. 또한 FTP에 동시에 업로드하는 고객들은 FTP의 대역폭을 공유하므로 업로드 속도가 느려질 것으로 예상됩니다. 또한 [!DNL Amazon S3]은 복제되고 배포되므로 FTP 서버보다 일반적으로 더 안전하고 안정적입니다. 자세한 내용은 [Amazon S3 정보](../reference/amazon-s3.md)를 참조하십시오.

>[!WARNING]
>
>FTP 구성에 대한 지원을 점차 단계적으로 중단하고 있습니다. 기존 FTP 통합에서는 인바운드 데이터 파일 섭취가 여전히 지원되지만 새 통합을 위해 [!DNL Amazon S3]을(를) 사용하여 오프라인 데이터를 온보딩하는 것이 좋습니다. 자세한 내용은 [인바운드 데이터 파일에 대한 Amazon S3 이름 및 파일 크기 요구 사항](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)을 참조하십시오.

 

**Audience Manager는 인바운드 파일을 어떻게 처리합니까?**

[!DNL Audience Manager]는 인바운드 데이터 처리에 [!DNL Amazon Simple Queue Service (SQS)]를 사용합니다. 작동하는 방식은 다음과 같습니다.

1. [!DNL Audience Manager] 고객이 인바운드 데이터를 [!DNL Amazon S3] 버킷에 업로드합니다.
1. 데이터가 [!DNL Amazon SQS] 큐에 들어가 [!DNL Audience Manager]의 처리를 기다립니다.
1. [!DNL Audience Manager]가 [!DNL Amazon SQS] 큐에서 최대 119,000개의 항목을 읽고 최대 3개의 배치로 분할합니다. 각 배치에 있는 파일들은 동시에 처리됩니다.

 

**여러 파일을 동시에 업로드해야 합니다. 파일이 동시에 처리됩니까?**

경우에 따라 다릅니다. [!DNL Audience Manager]가 [!DNL Amazon SQS] 큐에서 최대 119,000개의 항목을 읽고 최대 3개의 배치로 분할합니다. 파일은 동일한 배치로 끝나는 경우에만 동시에 처리됩니다. 그러나 매일 [!DNL Audience Manager]가 수집하는 데이터 양이 많아서 파일 처리 순서를 보장할 수 없습니다.

>[!MORELIKETHIS]
>
>* [배치 데이터 전송 프로세스 설명](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)
