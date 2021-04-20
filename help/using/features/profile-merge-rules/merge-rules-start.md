---
description: 프로필 병합 규칙 검토를 만들고 이 섹션에 설명된 각 절차의 단계를 완료하려면
seo-description: 프로필 병합 규칙 검토를 만들고 이 섹션에 설명된 각 절차의 단계를 완료하려면
seo-title: 프로필 병합 규칙 시작
solution: Audience Manager
title: 프로필 병합 규칙 시작
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 4%

---

# 프로필 병합 규칙 시작 {#getting-started-with-profile-merge-rules}

[!UICONTROL Profile Merge Rules]을(를) 만들려면 이 섹션에 설명된 각 절차의 단계를 검토하고 완료합니다.

<!-- merge-rules-start.xml -->

## 장치 간 데이터 소스 만들기 {#create-data-source}

장치 간 데이터 소스를 만들려면 **[!UICONTROL Audience Data > Data Sources > Add New]**&#x200B;으로 이동하여 여기에 설명된 각 섹션에 대한 단계를 완료하십시오. 장치 간 데이터 소스를 만들거나 편집하려면 관리자 권한이 필요합니다.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>이러한 다른 컨트롤에 대한 설명은 [데이터 소스 설정 및 메뉴 옵션](../datasources-list-and-settings.md#settings-menu-options)을 참조하십시오.

## 데이터 소스 세부 정보 {#details}

[!UICONTROL Data Source Details] 섹션을 완료하려면 다음을 수행하십시오.

1. 데이터 소스의 이름을 지정합니다.
2. *(선택 사항)* 데이터 소스를 설명합니다. 간결한 설명은 데이터 소스의 역할이나 목적을 정의하는 데 도움이 됩니다.
3. 통합 코드를 제공합니다. 통합 코드는 이 데이터 소스의 고유 ID입니다.
4. **[!UICONTROL ID Type]** 목록에서 **[!UICONTROL Cross Device]**&#x200B;을 선택합니다.
5. **[!UICONTROL ID Definition]** 목록에서 데이터 소스 유형을 정의하는 옵션을 선택합니다. 옵션은 다음과 같습니다.
   * **[!UICONTROL Person]**:한 사람을 정의하는 ID. 이 ID는 여러 [!DNL Audience Manager] ID에 매핑할 수 있습니다.
   * **[!UICONTROL Household]**:인물 그룹을 정의하는 ID. 이 ID는 여러 [!DNL Audience Manager] ID에 매핑할 수 있습니다.

## 데이터 내보내기 제어 {#export-controls}

[데이터 내보내기 ](../data-export-controls.md) 컨트롤은 데이터 소스 및 대상에 적용할 수 있는 선택적 분류 규칙입니다. 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우 데이터가 대상으로 전송되지 않도록 합니다. [!UICONTROL Data Export Controls]을(를) 사용하지 않으면 이 섹션을 건너뜁니다.

## 데이터 소스 설정 {#settings}

[!UICONTROL Data Source Settings] 섹션은 여러 옵션을 제공하지만, 다음 2는 장치 간 데이터 소스를 만드는 데 중요합니다.

* **[!UICONTROL Use as Authenticated Profile]**:기본적으로 이 설정을 사용하면 자체 인증된 데이터 [!UICONTROL Profile Merge Rule] 로 A를 만들 수 있습니다.

* **[!UICONTROL Use as a Device Graph]**:이 컨트롤은 데이터 공급자로 나열된 계정에만 사용할 수 있습니다. 이 확인란을 선택하면 데이터 소스가 장치 그래프로 만들어지고 다른 [!DNL Audience Manager] 고객과 공유할 수 있습니다. [!DNL Audience Manager] 컨설턴트와 협력하여 데이터 공급자로 설정하고 이 [!UICONTROL Data Source]을(를) 공유할 고객을 지정합니다. 컨설턴트는 내부 프로비저닝 프로세스를 통해 계정 및 디바이스 그래프 공유를 프로비저닝합니다.

* **[!UICONTROL Data retention for inactive Customer IDs]**:이 컨트롤을 사용하여 비활성 고객 ID에 대한 데이터 보존 기간을 설정할 수 있습니다. Audience Manager 플랫폼에서 고객 ID를 마지막으로 본 후 Audience Manager이 데이터베이스에 있는 기간을 결정합니다. 기본값은 24개월(720일)입니다. 설정할 수 있는 최소 값은 1개월이고 최대 값은 5년입니다. 모든 달은 30일로 계산됩니다. Audience Manager은 비활성 고객 ID에 대해 설정한 데이터 보유에 따라 일주일에 한 번 비활성 고객 ID를 삭제하는 프로세스를 실행합니다.

이러한 설정과 연결된 텍스트 필드를 사용하여 [!UICONTROL Data Source]프로필 병합 규칙 옵션](merge-rule-definitions.md)에 나타나는 별칭으로 [의 이름을 변경할 수 있습니다. 예를 들어 **[!UICONTROL Use as Authenticated Profile]**&#x200B;에 별칭을 추가하면 해당 이름이 [!UICONTROL Authenticated Profile Options] 목록에 나타납니다. **[!UICONTROL Use as a Device Graph]**&#x200B;에 별칭을 추가하면 해당 이름이 [!UICONTROL Device Options] 목록에 나타납니다.

## 프로필 병합 규칙 만들기 {#create-profile-merge-rule}

[!UICONTROL Profile Merge Rule]을(를) 만들려면 **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]**&#x200B;로 이동하여 여기에 설명된 각 섹션에 대한 단계를 완료하십시오.

장치 간 데이터 소스를 설정한 후 최대 3개의 병합 규칙을 만들 수 있습니다. [사용자 기반 대상](../destinations/people-based-destinations-overview.md)에 등록하는 경우 제4회 프로필 병합 규칙([!UICONTROL All Cross-Device Profiles])에 액세스할 수 있습니다.

규칙을 만들거나, 편집하거나, 삭제하려면 관리자 권한이 필요합니다. 모든 사용자는 기존 [!UICONTROL Profile Merge Rules]을(를) 보고 사용할 수 있습니다.

<!-- create-profile-merge-rule.xml -->

**사전 요구 사항:** 구성 요소를 만들려면 장치 간 데이터 소스가 필요합니다 [!UICONTROL Profile Merge Rule]. [데이터 소스 만들기](../manage-datasources.md#create-data-source)를 참조하십시오.

>[!TIP]
>
>이러한 다른 컨트롤에 대한 설명은 [프로필 병합 규칙 옵션 정의](merge-rule-definitions.md)을 참조하십시오.

## 기본 정보 {#basic-info}

[!UICONTROL Basic Information] 섹션을 완료하려면 다음을 수행하십시오.

1. [!UICONTROL Profile Merge Rule] 이름을 지정합니다.
2. *(선택 사항)* 을  [!UICONTROL Profile Merge Rule]설명합니다. 간결한 설명은 규칙의 역할이나 목적을 정의하는 데 도움이 됩니다.
3. *(선택 사항)* 이 기본값 **[!UICONTROL Set as default]** 으로 설정하려면 선택합니다 [!UICONTROL Profile Merge Rule]. 새 세그먼트는 기본 규칙과 자동으로 연결됩니다.

## 데이터 내보내기 제어 {#data-export-controls}

[데이터 내보내기 ](../data-export-controls.md) 컨트롤은 사용자 [!UICONTROL Profile Merge Rule]에게 적용할 수 있는 선택적 분류 규칙입니다. 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우 데이터가 대상으로 전송되지 않도록 합니다. [!UICONTROL Data Export Controls]을(를) 사용하지 않으면 이 섹션을 건너뜁니다.

## 프로필 병합 규칙 설정 {#profile-merge-rule-setup}

[!UICONTROL Proflie Merge Rule Setup] 섹션을 완료하려면 다음을 수행하십시오.

1. **[!UICONTROL Authenticated Option]**&#x200B;을 선택합니다. 옵션은 다음과 같습니다.
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. **[!UICONTROL Authenticated Profile Option]**(최대 3, 최대)을 선택합니다. 이전에 만든 [장치 간 데이터 소스](merge-rules-start.md)입니다.
3. **[!UICONTROL Device Option]**&#x200B;을 선택합니다. 옵션은 다음과 같습니다.
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. 클릭 **[!UICONTROL Save]**.

### 사용자 ID 키로 장치 간 ID를 사용하는 Adobe Campaign 대상에 대한 고려 사항 {#considerations}

2019년 말에는 장치 간 ID를 사용하여 생성된 일괄 처리 파일의 정확도를 개선하기 위해 일련의 향상된 프로필 병합 규칙을 발표했습니다. 이러한 개선 사항은 2020년 3월 16일 월요일부터 Audience Manager 인스턴스에 엄격하게 적용됩니다. 마지막으로, 장치 간 ID를 사용하여 대상에 매핑된 세그먼트는 일부 프로필 병합 규칙 구성에서 내보내기 생성을 중지합니다.

Audience Manager 인스턴스와 대상 간에 Adobe Campaign과 같은 장치 간 ID를 사용하여 올바르게 통합하려면 다음 요구 사항을 충족해야 합니다.

1. Adobe Campaign 선언된 ID 대상에 매핑된 세그먼트에서 사용하는 프로필 병합 규칙을 검토하십시오. 프로필 병합 규칙은 [!UICONTROL Last Authenticated Profile] 옵션을 사용해야 하므로 인증된 모든 프로필을 내보내기에 포함할 수 있습니다. 프로필 병합 규칙이 다른 옵션을 사용하는 경우 [!UICONTROL Last Authenticated Profile]으로 전환합니다.
2. 프로필 병합 규칙 설정에서 Adobe Campaign 선언된 ID 데이터 소스를 선택합니다.

>[!NOTE]
>
> 최대 [!UICONTROL Profile Merge Rules]에 도달했고 위의 지침에 따라 이를 구성하는 데 도움이 필요한 경우 고객 지원 센터에 문의하십시오.

## 병합 규칙 코드 {#configure-merge-rule-code} 구성

다음 지침에 따라 병합 규칙과 함께 작동하도록 [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL] 및 모바일 [!DNL SDK] 코드를 설정합니다.

<!-- merge-rules-configure-code.xml -->

### 사전 요구 사항

이러한 절차를 완료하기 전에 [장치 간 데이터 소스](#create-data-source) 및 [프로필 병합 규칙](#create-profile-merge-rule) *을(를) 설정해야 합니다.*

## Adobe Experience Platform ID 서비스 고객의 경우 {#id-service-customers}

[!UICONTROL Profile Merge Rules]으로 작업할 때 [!UICONTROL Adobe Experience Platform Identity Service] 및 최신 버전의 [DIL](../../dil/dil-overview.md)이(가) 권장됩니다. 그러나 이 기능을 사용하기 위해 [!UICONTROL Adobe Experience Platform Identity Service]을 사용할 필요는 없습니다. [!UICONTROL DIL]을(를) 사용하고 있는 경우 아래 [레거시 DIL 섹션](#legacy-dil)을 참조하십시오.

### 고객 ID 설정 기능 구성

[!UICONTROL Adobe Experience Platform Identity Service] 작업 시 `setCustomerIDs` 함수는 선언된 ID를 [!DNL Audience Manager]에 전달합니다. 프로필 병합 규칙을 사용하려면 장치 간 데이터 소스를 만들 때 지정한 통합 코드를 사용하도록 `setCustomerIDs`을(를) 수정해야 합니다. 예를 들어 통합 코드 `my_datasource_ic`을(를) 사용하여 장치 간 데이터 소스를 만들었다고 가정해 봅시다. 선언된 ID를 전달하려면 아래 수정된 코드 샘플에 표시된 대로 통합 코드를 방문자 ID 함수에 추가합니다.

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

자세한 내용은 [장치 간 데이터 소스 만들기](#create-data-source) 및 [고객 ID 및 인증 상태](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)를 참조하십시오.

### `DIL.create` 함수 구성

이제 최신 버전의 [!UICONTROL DIL]이(가) `DIL.create`의 `visitorService` 함수에서 [!UICONTROL declared ID]을(를) 자동으로 선택합니다([선언된 ID 변수](../declared-ids.md#declared-id-variables) 참조). `DIL.create` 함수를 확인하여 아래 코드 샘플에서와 같이 이 함수가 제대로 설정되어 있는지 확인합니다.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

네임스페이스 키-값 쌍에서 `*`MCORG`*` 변수는 [!DNL Experience Cloud] 조직 ID입니다. 이 ID가 없는 경우 [!DNL Experience Cloud] 대시보드의 [!UICONTROL Administration] 섹션에서 찾을 수 있습니다. 이 대시보드를 보려면 관리자 권한이 필요합니다. [관리:핵심 서비스](https://docs.adobe.com/content/help/ko-KR/core-services/interface/manage-users-and-products/admin-getting-started.html).

### SDK 구성

아래의 [SDK 구성](#configure-sdks-legacy-dil) 섹션을 참조하십시오.

## 레거시 DIL {#legacy-dil}

아직 [!DNL Adobe Experience Platform Identity Service]을(를) 사용하지 않는 경우 반드시 사용해야 합니다. 그러나 새로운 코드로 이동하는 것은 신중한 생각과 테스트가 필요하다는 것을 알고 있습니다. 이러한 경우 `DIL.create` 함수를 확인하여 아래 코드 샘플에서와 같이 이 함수가 제대로 설정되어 있는지 확인합니다.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

자세한 내용은 [선언된 ID 변수](../declared-ids.md#declared-id-variables)의 기존 [!UICONTROL DIL] 섹션을 참조하십시오.

### SDK 구성 {#configure-sdks-legacy-dil}

[!DNL Android] 및 [!DNL iOS] 모바일 장치에서 [!UICONTROL declared IDs]을 전달할 수 있는 [!DNL SDK] 코드의 메서드를 확인합니다. [!DNL Android] 및 [!DNL iOS] 코드 라이브러리의 변수 이름은 동일합니다.

* `dpid`:장치 간 데이터 소스 ID.
* `dpuuid`:( [!UICONTROL declared ID] 즉, 사용자 ID).

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>구문:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>예:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>구문:</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>예:</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

또한 Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html)용 [Audience Manager 메서드 및 iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html)용 [Audience Manager 메서드를 참조하십시오.

>[!MORELIKETHIS]
>
>* [데이터 소스 만들기](../manage-datasources.md#create-data-source)

