---
description: 프로필 병합 규칙을 만들려면 이 섹션에 설명된 각 절차의 단계를 검토하고 완료하십시오.
seo-description: 프로필 병합 규칙을 만들려면 이 섹션에 설명된 각 절차의 단계를 검토하고 완료하십시오.
seo-title: 프로필 병합 규칙 시작하기
solution: Audience Manager
title: 프로필 병합 규칙 시작하기
uuid: 7 d 32 c 60 f -467 c -42 dd-afa 9-437 fd 7 c 473 c 5
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Getting Started with Profile Merge Rules {#getting-started-with-profile-merge-rules}

To create [!UICONTROL Profile Merge Rules], review and complete the steps in each of the procedures described in this section.

<!-- merge-rules-start.xml -->

## Create a Cross-Device Data Source {#create-data-source}

To create a cross-device data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. 관리자 권한은 장치 간 데이터 소스를 만들거나 편집하는 데 필요합니다.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. 데이터 소스의 이름을 지정합니다.
1. *(선택 사항)* 데이터 소스를 설명합니다. 간결한 설명은 데이터 소스의 역할이나 목적을 정의하는 데 도움이 됩니다.
1. 통합 코드를 제공합니다. 통합 코드는 이 데이터 소스에 대한 고유한 고유 ID 입니다.
1. **[!UICONTROL ID Type]** 목록에서 **[!UICONTROL Cross Device]** 를 선택합니다.
1. **[!UICONTROL ID Definition]** 목록에서 데이터 소스 유형을 정의하는 옵션을 선택합니다. 옵션은 다음과 같습니다.
   * **[!UICONTROL Person]**: 단일 사람을 정의하는 ID. This ID can be mapped to multiple [!DNL Audience Manager] IDs.
   * **[!UICONTROL Household]**: 사용자 그룹을 정의하는 ID. This ID can be mapped to multiple [!DNL Audience Manager] IDs.

## 데이터 내보내기 제어 {#export-controls}

[데이터 내보내기 컨트롤은](../../features/data-export-controls.md) 데이터 소스 및 대상에 적용할 수 있는 선택적 분류 규칙입니다. 이러한 행위는 해당 행동이 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우에 사용자가 대상에 데이터를 전송하지 못하도록 합니다. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] section는 여러 옵션을 제공하지만, 다음 2는 장치 간 데이터 소스를 만드는 데 중요합니다.

* **[!UICONTROL Use as Authenticated Profile]**: 기본적으로 선택되어 있는 이 설정을 사용하면 인증된 자체 데이터로 A [!UICONTROL Profile Merge Rule] 를 빌드할 수 있습니다.

* **[!UICONTROL Use as a Device Graph]**: 이 컨트롤은 데이터 공급자로 나열된 계정에만 사용할 수 있습니다. Selecting this check box creates your data source as a device graph and lets you share it with other [!DNL Audience Manager] customers. [!DNL Audience Manager] 컨설턴트와 협력하여 데이터 공급자로 설정하고 이를 [!UICONTROL Data Source] 공유할 고객을 지정합니다. 컨설턴트는 내부 프로비저닝 프로세스를 통해 계정 및 디바이스 그래프 공유를 프로비저닝합니다.

* **[!UICONTROL Data retention for inactive Customer IDs]**: 이 컨트롤을 사용하면 비활성 고객 ID의 데이터 유지 기간을 설정할 수 있습니다. Audience Manager 플랫폼에서 마지막으로 본 후 Audience Manager가 고객 ID를 데이터베이스에 유지하는 기간을 결정합니다. 기본값은 24 개월 (720 일) 입니다. 설정할 수 있는 최소 값은 1 개월이며 최대 값은 5 년입니다. Adobe는 모든 달을 30 일로 계산합니다. Audience Manager는 비활성 고객 ID에 대해 설정한 데이터 보존에 따라 일주일에 한 번 비활성 고객 ID를 삭제하는 프로세스를 실행합니다.

The text fields associated with these settings let you rename the [!UICONTROL Data Source] with an alias that appears in the [Profile Merge Rule options](../../features/profile-merge-rules/merge-rule-definitions.md). For example, if you add an alias to **[!UICONTROL Use as Authenticated Profile]**, that name appears in the [!UICONTROL Authenticated Profile Options] list. If you add an alias to **[!UICONTROL Use as a Device Graph]**, that name appears in the [!UICONTROL Device Options] list.

>[!MORE_ like_ this]
>
>* [데이터 소스 만들기](../../features/manage-datasources.md#create-data-source)


## Create a Profile Merge Rule {#create-profile-merge-rule}

To create a [!UICONTROL Profile Merge Rule], go to **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** and complete the steps for each section described here. 장치 간 데이터 소스를 설정한 후 최대 3 개의 병합 규칙을 만들 수 있습니다. 관리자 권한은 규칙을 만들거나 편집하거나 삭제하는 데 필요합니다. All users can view and use existing [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**전제 조건:** A를 만들려면 장치 간 데이터 소스가 [!UICONTROL Profile Merge Rule]필요합니다. See [Create a Data Source](../../features/manage-datasources.md#create-data-source).

>[!TIP]
>
>See [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md) for descriptions of these different controls.

## 기본 정보 {#basic-info}

To complete the [!UICONTROL Basic Information] section:

1. Name the [!UICONTROL Profile Merge Rule].
2. *(선택 사항) 에* 대해 설명합니다 [!UICONTROL Profile Merge Rule]. 간결한 설명은 규칙의 역할이나 목적을 정의하는 데 도움이 됩니다.
3. *(선택 사항)* 이 설정을 **[!UICONTROL Set as default]** 기본값으로 만들려면 [!UICONTROL Profile Merge Rule]선택합니다. 새 세그먼트는 기본 규칙과 자동으로 연결됩니다.

## 데이터 내보내기 제어 {#data-export-controls}

[데이터 내보내기 컨트롤은](../../features/data-export-controls.md) 선택 사항인 선택 분류 규칙입니다 [!UICONTROL Profile Merge Rule]. 이러한 행위는 해당 행동이 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우에 사용자가 대상에 데이터를 전송하지 못하도록 합니다. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Profile Merge Rule Setup {#profile-merge-rule-setup}

To complete the [!UICONTROL Proflie Merge Rule Setup] section:

1. **[!UICONTROL Authenticated Option]** 을 선택합니다. 옵션은 다음과 같습니다.
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Select an **[!UICONTROL Authenticated Profile Option]** (up to 3, maximum). These are the [cross-device data sources](../../features/profile-merge-rules/merge-rules-start.md) you have created previously.
3. Select a **[!UICONTROL Device Option]**. 옵션은 다음과 같습니다.
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. 클릭 **[!UICONTROL Save]**.

## Configure Merge Rule Code {#configure-merge-rule-code}

Follow these instructions to set up the [!UICONTROL Experience Cloud ID Service], [!UICONTROL DIL], and mobile [!DNL SDK] code to work with your merge rules.

<!-- merge-rules-configure-code.xml -->

### 전제 조건

You must set up a [cross-device data source](#create-data-source) and [profile merge rules](#create-profile-merge-rule) *before* completing these procedures.

## For Experience Cloud ID Service Customers {#id-service-customers}

The [!UICONTROL Experience Cloud ID Service] and the latest version of [DIL](../../dil/dil-overview.md) are recommended when working with [!UICONTROL Profile Merge Rules]. However, you don&#39;t have to use the [!UICONTROL Experience Cloud ID Service] to work with this feature. If you&#39;re just using [!UICONTROL DIL], see the [legacy DIL section](../../features/profile-merge-rules/merge-rules-start.md#legacy-dil) below.

### 고객 ID 설정 기능 구성

When working with the [!UICONTROL Experience Cloud ID Service], the `setCustomerIDs` function passes declared IDs to [!DNL Audience Manager]. To use a profile merge rule, you must modify `setCustomerIDs` to use the integration code specified when you created a cross-device data source. For example, say you&#39;ve created a cross-device data source with the integration code `my_datasource_ic`. 선언된 ID를 전달하려면 아래의 수정된 코드 샘플에 표시된 것처럼 방문자 ID 함수에 통합 코드를 추가합니다.

#### 범용 코드 샘플

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### 수정된 코드 샘플

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

For more information, see [Create a Cross-Device Data Source](#create-data-source) and [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html).

### Configure `DIL.create` function

[!UICONTROL DIL] 최신 버전의는의 [!UICONTROL declared ID]`visitorService``DIL.create` 함수에서를 자동으로 가져옵니다 [(선언된 ID 변수](../../features/declared-ids.md#declared-id-variables)참조). Check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>var vdil = dil. create ({partner: " 파트너 이름 ",
 Visitorservice: {namespace: "<i>insert-mcorg-id-here</i>"}});</code>
</pre>

In the namespace key-value pair, the `*`MCORG`*` variable is your [!DNL Experience Cloud] Organization ID. If you don&#39;t have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. 이 대시보드를 보려면 관리자 권한이 필요합니다. [관리 참조: 핵심 서비스](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### SDK 구성

See the [Configure SDKs](../../features/profile-merge-rules/merge-rules-start.md#configure-sdks) section below.

## Legacy DIL {#legacy-dil}

[!DNL Experience Cloud ID Service] 아직 사용하지 않을 경우 그러나 새로운 코드로 옮겨도 신중한 사고 및 테스트가 필요하다는 사실을 잘 알고 있습니다. In these cases, check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>DIL. CREATE ({PARTNER: " 파트너 이름 ",
 Declaredid: {dpuuid:<i>dpuuid</i>,
 dpid:<i>dpid</i>}});</code>
</pre>

For more information, see the legacy [!UICONTROL DIL] section in [Declared ID Variables](../../features/declared-ids.md#declared-id-variables).

### Configure SDKs {#configure-sdks-legacy-dil}

[!DNL SDK] 코드에서 전달할 [!UICONTROL declared IDs] 수 있는 코드 방법을 [!DNL Android][!DNL iOS] 확인하십시오. [!DNL Android] 및 [!DNL iOS] 코드 라이브러리의 변수 이름은 동일합니다.

* `dpid`: 장치 간 데이터 소스 ID 입니다.
* `dpuuid`: ( [!UICONTROL declared ID] 즉, 사용자 ID).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 장치 유형 </th> 
   <th colname="col2" class="entry"> 메서드 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>구문:</b> </p> <p> <pre> public static void setdpidanddpuuid (string dpid, String DPUUID); </pre> </p> <p> <b>예:</b> </p> <p> <pre> Audiencemanager. setdpidanddpuuid ("mydpid", "mydpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> Audiencesetdpid: Dpuuid </code> </p> <p> <b>구문:</b> </p><p>
    <code class="javascript">+ (void) audiencesetdpid: (Nsstring *) DPID 
 DPUUID: (Nsstring *) Dpuuid; </code>
 </p>
    <p> <b>예:</b> </p><p>
    <code class="javascript">[Adbmobile audiencesetdpid: @ "290" DPUUID: @ "99301393923940"]; </code>
 </p>
    </td>
  </tr>
 </tbody>
</table>

See also, [Audience Manager Methods for Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) and [Audience Manager Methods for iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html).
