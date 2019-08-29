---
description: 파일 기반 ID 동기화에 사용되는 필수 필드, 구문 및 이름 지정 규칙을 설명합니다. 이러한 사양에 따라 파일 컨텐츠의 이름을 지정하고 구성할 수 있습니다.
seo-description: 파일 기반 ID 동기화에 사용되는 필수 필드, 구문 및 이름 지정 규칙을 설명합니다. 이러한 사양에 따라 파일 컨텐츠의 이름을 지정하고 구성할 수 있습니다.
seo-title: ID 동기화 파일 이름 및 컨텐츠 요구 사항
solution: Audience Manager
title: ID 동기화 파일 이름 및 컨텐츠 요구 사항
uuid: BFE 42 AF 9-9149-4 DA 3-830 E-F 227 C 4 E 610 C 2
translation-type: tm+mt
source-git-commit: 5624eac36a7f2b8892136688f89fc22af241fc3a

---


# ID 동기화 파일 이름 및 컨텐츠 요구 사항 {#name-and-content-requirements-for-id-synchronization-files}

파일 기반 ID 동기화에 사용되는 필수 필드, 구문 및 이름 지정 규칙을 설명합니다. 이러한 사양에 따라 파일 컨텐츠의 이름을 지정하고 구성할 수 있습니다.

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 이 문서에서는 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../../reference/code-style-elements.md)을 참조하십시오.

## 파일 이름 구문 및 예제 {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID 파일 이름에는 다음과 같은 필수 요소와 선택적 요소가 포함됩니다.

`adobe_id_`*`[c2c_id_]`*`MASTERDPID_DPID[_DPID_DPID`*`]_`*`TIMESTAMP`*`.sync[.`*`SPLIT_NUMBER`*`][.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_ id</code> </p> </td> 
   <td colname="col2"> <p>파일을 ID 동기화 파일로 식별하는 정적 접두사입니다. 장치 ID를 다른 장치 ID 또는 고객 ID (DPUUIDS) 와 일치시킬 때 이 접두사를 사용합니다.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c 2 c_ id</code> </p> </td> 
   <td colname="col2"> <p>사용자를 기반 대상에 대한 ID 동기화 파일로 식별하는 정적 접두사입니다. 고객 ID (DPUUIDS) 를 사용자 기반 대상의 해시된 이메일 주소에 연결할 때 이 접두사를 사용합니다.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>masterdpid</i></code> </td> 
   <td colname="col2"> 마스터 데이터 공급자 ID는 파일 이름에 있는 DPIDS의 상위 ID 입니다. 또한 데이터 파일의 첫 번째 사용자 ID는 마스터 ID에 해당합니다. 후속 DPIDS는 마스터에 속한 다른 식별자입니다. 동기화가 파일 이름에 있는 DPIDS를 파일의 UUID로 매핑합니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>dpid</i></code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 ID. 이러한 ID는 마스터 DPID와 연결된 엔티티 또는 데이터 소스를 나타냅니다. 동기화가 파일 이름에 있는 DPIDS를 파일의 UUID로 매핑합니다. </p> <p>파일 이름에 있는 DPIDS의 수는 데이터 파일의 UUID 수와 일치해야 합니다. 예를 들어 파일 이름에 마스터 DPID와 3 DPIDS가 포함되어 있다고 가정합니다. 데이터 파일에는 아래의 파일 컨텐츠 섹션에 설명된 대로 형식이 지정된 4 개의 해당 UUID 열이 포함되어야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>10 자리 UNIX 타임스탬프 (초 단위) 타임스탬프는 각 파일 이름을 고유하게 만드는 데 도움이 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> . sync</code> </p> </td> 
   <td colname="col2"> <p>일반적인 전체 동기화를 가리킵니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>. split_ number</i>]</code> </p> </td> 
   <td colname="col2"> <p>정수. 큰 파일을 여러 개의 작은 파일로 분할할 때 사용됩니다. 처리 시간을 단축할 수 있습니다. 숫자는 전송 중인 원본 파일의 부분을 나타냅니다. 아래 파일 이름 예를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>파일이 선택적 GZIP 압축을 통해 압축되도록 지정합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 파일 이름 예

다음 예는 형식이 올바르게 지정된 파일 이름을 보여줍니다. 파일 이름은 비슷합니다.

<ul class="simplelist"> 
 <li> <code> Adobe_ ID_ 111_ 222_ 333_ 444_ 1454442149. Sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> People-based 대상에 대한 ID 동기화 파일 이름 지정 (C 2 C 접두사) 의 [경우, Workflow A - 오프라인 데이터](../../../features/destinations/people-based-destinations-workflow-combined.md) 또는 [Workflow B와 결합된 모든 온라인 활동에 기반을 둔 개인화 B - 오프라인 전용 데이터를 기반으로 개인화를 참조하십시오](../../../features/destinations/people-based-destinations-workflow-offline.md).

## 파일 내용 구문 및 예제 {#file-content-syntax}

ID 파일의 컨텐츠에는 다음과 같은 요소가 포함됩니다.

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

파일에는 사용자 ID ([!DNL UUID]) 가 포함되어 있습니다. 각 행에서 ID를 탭과 구분합니다. 다음 예는 올바른 형식의 ID 파일을 보여 줍니다. 컨텐츠가 유사하게 보일 수 있습니다.

```
abc123 def456 ghi789 xyz987
```

## 동기화가 upuuids와 uuids 일치 {#sync-matches-dpuuids-uuids}

ID 동기화 파일의 목적은 자체 데이터 소스의 [DPUUIDS](../../../reference/ids-in-aam.md) 를 UUID와 [!DNL Audience Manager] 동기화하는 것입니다. 동기화가 마스터 [!DNL DPUUID][!DNL DPID] 및 관련 [!DNL DPID]s와 [!DNL Audience Manager][!DNL UUID]s를 매핑합니다. 파일 이름 및 본문에 ID를 넣으면 이러한 식별자가 서로 매핑되는 방식이 결정됩니다. 예를 들어 다음 두 개의 샘플 파일을 표시합니다.

* **파일 1:**`adobe_id_0_12345_1476312152.sync`

* **파일 2:**`adobe_id_12345_67890_1476312876.sync`

<br/>

샘플 이름과 컨텐츠가 제공되면 ID가 다음과 같이 매핑됩니다.

**파일 1** (샘플 파일 [다운로드](assets/adobe_id_0_12345_1476312152.sync))

| dpid 0 = Adobe Audience Manager UUIDS | dpid 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-TTRJ 6 E 4 NJAMR 38 |
| 67412682083411995725538770443620307584 | xyz 3017 bbr 4 dafjwfm 6 d 4 gb 4 ln_ t 5 jk_ f 7 rdecqns 9 wfna 7 h 70 |
| 89159024796760343733111707646026765593 | xyz 3017 prypid 8 tzfhkee-ge 034 li -53 jde 0 utcyciwd 0 a 2 olm |
| 66552757407517449462805881945288602094 | xyz 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bvqjmlwregju 2 m |
| 66184778222667870903738139438735041506 | xyz 3017 q 9 r 60 kuhpoca_ ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw |

1 단계: ID 동기화 프로세스는 12345 [!DNL DPUUID]와 [!DNL DPID] 왼쪽 열의 [!DNL Audience Manager][!DNL UUID]s를 동기화합니다. 파일 이름에 [!DNL DPID] 있는 "0" 는 s를 나타냅니다 [!DNL Audience Manager][!DNL UUID].<br/>


**파일 2** (샘플 파일 [다운로드](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-TTRJ 6 E 4 NJAMR 38 | 4598060374 |
| xyz 3017 bbr 4 dafjwfm 6 d 4 gb 4 ln_ t 5 jk_ f 7 rdecqns 9 wfna 7 h 70 | 4581274262 |
| xyz 3017 prypid 8 tzfhkee-ge 034 li -53 jde 0 utcyciwd 0 a 2 olm | 4392434426 |
| xyz 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bvqjmlwregju 2 m | 2351382994 |
| xyz 3017 q 9 r 60 kuhpoca_ ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw | 4601584763 |

2 단계: 12345의 [!DNL DPUUID][!DNL DPID] s는 1 단계에서 Audience Manager [!DNL UUID]S와 동기화되었습니다. 이 ID 동기화가 수행하는 작업은 단계 1 [!DNL DPUUID]에서 [!DNL DPID] Audience Manager [!DNL UUID]S와 67890를 동기화하는 것입니다.

<br/>

## 기타 형식 요구 사항 {#other-format-reqs}

사용자 ID는 다음을 수행할 수 없습니다.

* ID 자체에 탭이 있습니다. 탭은 데이터 파일에서 개별 ID를 구분하는 데만 사용됩니다.
* 개인 식별 정보 ([!UICONTROL PII]) 를 포함합니다.
* [!DNL URL] 인코딩 사용. 인코딩되지 않은 ID만 전달합니다.

탭 또는 공백으로 끝나는 모든 행은 처리 또는 실현되지 않습니다. 규칙으로, 행의 끝을 지워야 합니다.