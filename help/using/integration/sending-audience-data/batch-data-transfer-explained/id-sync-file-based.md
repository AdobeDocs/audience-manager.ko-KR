---
description: 파일 기반 ID 동기화에 사용되는 필수 필드, 구문 및 이름 지정 규칙에 대해 설명합니다. 이러한 사양에 따라 파일 컨텐츠에 이름을 지정하고 구성합니다.
seo-description: 파일 기반 ID 동기화에 사용되는 필수 필드, 구문 및 이름 지정 규칙에 대해 설명합니다. 이러한 사양에 따라 파일 컨텐츠에 이름을 지정하고 구성합니다.
seo-title: ID 동기화 파일 이름 및 컨텐츠 요구 사항
solution: Audience Manager
title: ID 동기화 파일 이름 및 컨텐츠 요구 사항
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: 인바운드 데이터 전송
exl-id: e6b3a438-f843-4a24-89fd-03ef77d7cf04
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 6%

---

# ID 동기화 파일 이름 및 컨텐츠 요구 사항 {#name-and-content-requirements-for-id-synchronization-files}

파일 기반 ID 동기화에 사용되는 필수 필드, 구문 및 이름 지정 규칙에 대해 설명합니다. 이러한 사양에 따라 파일 컨텐츠에 이름을 지정하고 구성합니다.

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 이 문서에서는 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../../reference/code-style-elements.md)을 참조하십시오.

## 파일 이름 구문 및 예 {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID 파일 이름에는 다음 필수 및 선택적 요소가 포함됩니다.

*`[adobe_id_]`* *`[c2c_id_]`*`MASTERDPID_DPID`*`[_DPID]`*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*`[.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>파일을 ID 동기화 파일로 식별하는 정적 접두사입니다. 다른 장치 ID 또는 DPUUID(고객 ID)에 장치 ID를 일치시킬 때 이 접두사를 사용합니다.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>파일을 사용자 기반 대상에 대한 ID 동기화 파일로 식별하는 정적 접두사입니다. 고객 ID(DPUUID)를 사용자 기반 대상에 대한 해시된 이메일 주소에 일치시킬 때 이 접두사를 사용합니다.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>마스터 데이터 공급자 ID는 파일 이름에 있는 DPID의 상위 ID입니다. 또한, 데이터 파일의 첫 번째 사용자 ID는 마스터 ID에 해당합니다. 후속 DPID는 마스터에 속하는 다른 식별자입니다. 동기화는 파일 이름의 DPID를 파일의 UUID에 매핑합니다.</p> <p>이 DPID에는 AAM UUID, GAID, IDFA 등과 같은 장치 ID만 포함되어야 합니다. 여기에는 DPUUID를 포함할 수 없습니다. 이렇게 하면 잘못된 동기화가 발생할 수 있습니다.</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 ID. 이러한 ID는 마스터 DPID와 연결된 엔티티 또는 데이터 소스를 나타냅니다. 동기화는 파일 이름의 DPID를 파일의 UUID에 매핑합니다. </p> <p>파일 이름의 DPID 수는 데이터 파일의 UUID 수와 일치해야 합니다. 예를 들어 파일 이름에 마스터 DPID와 3개의 DPID가 포함되어 있다고 가정합니다. 데이터 파일에는 아래 파일 컨텐츠 섹션에 설명된 대로 형식이 지정된 4개의 해당 UUID 열이 포함되어야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>10자리, UNIX 타임스탬프(초)입니다. 타임스탬프는 각 파일 이름을 고유하게 만드는 데 도움이 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>일반적인 전체 동기화를 나타냅니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>정수. 큰 파일을 여러 개의 작은 파일로 분할할 때 사용됩니다. 이렇게 하면 처리 시간이 향상됩니다. 숫자는 원본 파일을 보내는 부분을 가리킵니다. 아래의 파일 이름 예를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>파일이 선택적 gzip 압축으로 압축되도록 지정합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 파일 이름 예

다음 예제는 올바른 형식의 파일 이름을 보여 줍니다. 파일 이름은 유사할 수 있습니다.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> 사용자 기반 대상의 ID 동기화 파일 이름 지정(c2c 접두사)에 대해서는 [워크플로우 A - 오프라인 데이터와 결합된 모든 온라인 활동을 기반으로 한 개인화](../../../features/destinations/people-based-destinations-workflow-combined.md) 또는 [워크플로우 B - 오프라인 전용 데이터를 기반으로 한 개인화](../../../features/destinations/people-based-destinations-workflow-offline.md)를 참조하십시오.

## 파일 컨텐츠 구문 및 예 {#file-content-syntax}

ID 파일의 컨텐츠에는 다음 요소가 포함됩니다.

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

파일에 사용자 ID([!DNL UUID])가 포함되어 있습니다. 각 행에서 탭으로 ID를 구분합니다. 다음 예는 올바른 형식의 ID 파일을 보여줍니다. 내용이 비슷할 수 있습니다.

```
abc123 def456 ghi789 xyz987
```

### 파일 콘텐츠 고려 사항 {#considerations}

인바운드 파일을 만들 때 첫 번째 열이 [!DNL AAM UUID], [!DNL GAID], [!DNL IDFA] 등과 같은 장치 ID로만 채워졌는지 확인하십시오. Audience Manager에서 지원하는 ID에 대한 자세한 내용은 Audience Manager](../../../reference/ids-in-aam.md)의 [ID 색인 을 참조하십시오.

>[!IMPORTANT]
>
>첫 번째 열에서 [DPUUIDs](../../../reference/ids-in-aam.md)를 사용하지 마십시오. 이렇게 하면 잘못된 동기화가 발생할 수 있습니다.

## 동기화는 DPUUID와 UUIDs {#sync-matches-dpuuids-uuids}에 일치합니다.

ID 동기화 파일의 목적은 자신의 데이터 소스에서 [DPUUIDs](../../../reference/ids-in-aam.md)를 [!DNL Audience Manager] UUID와 동기화하는 것입니다. 동기화는 마스터 [!DNL DPID]의 [!DNL DPUUID]과 관련된 [!DNL DPID]를 [!DNL Audience Manager] [!DNL UUID]s에 매핑합니다.파일 이름 및 본문에 ID를 지정하는 위치에 따라 이러한 식별자가 서로 매핑됩니다. 예를 들어, 여기에 표시된 두 샘플 파일을 예로 들어 보겠습니다.

* **파일 1:** `adobe_id_0_12345_1476312152.sync`

* **파일 2:**  `adobe_id_12345_67890_1476312876.sync`

<br/>

샘플 이름 및 컨텐츠가 주어지면 ID가 다음과 같이 함께 매핑됩니다.

**파일 1** (  [샘플 파일 다운로드](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = Adobe Audience Manager UUID | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TtRJ6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

1단계:id 동기화 프로세스는 [!DNL DPID] 12345의 [!DNL DPUUID]을 왼쪽 열의 [!DNL Audience Manager] [!DNL UUID]과 동기화합니다. 파일 이름의 [!DNL DPID] &quot;0&quot;은 [!DNL Audience Manager] [!DNL UUID]를 나타냅니다.
<br/>

**파일 2** (  [샘플 파일 다운로드](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TtRJ6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

2단계:[!DNL DPID] 12345의 [!DNL DPUUID]이(가) Audience Manager [!DNL UUID]과(와) 1단계에서 동기화되었습니다.이 ID 동기화를 수행하면 [!DNL DPID] 67890의 [!DNL DPUUID]을 1단계의 Audience Manager [!DNL UUID]과 동기화됩니다.

<br/>

## 기타 형식 요구 사항 {#other-format-reqs}

사용자 ID는 다음을 수행할 수 없습니다.

* ID 자체에 탭이 있습니다. 탭은 데이터 파일에서 개별 ID를 구분하는 데에만 사용됩니다.
* 개인 식별 정보([!UICONTROL PII])를 포함합니다.
* [!DNL URL] 인코딩을 사용하십시오. 인코딩되지 않은 ID만 전달합니다.

탭이나 공백으로 끝나는 모든 행은 처리되거나 실현되지 않습니다. 규칙으로서, 행 끝을 명확하게 유지합니다.
