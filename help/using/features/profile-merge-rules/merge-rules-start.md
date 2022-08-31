---
description: 프로필 병합 규칙 검토를 만들고 이 섹션에 설명된 각 절차의 단계를 완료합니다.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: 프로필 병합 규칙 시작
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 3%

---

# 프로필 병합 규칙 시작 {#getting-started-with-profile-merge-rules}

만들려면 [!UICONTROL Profile Merge Rules]을 눌러 이 섹션에 설명된 각 절차의 단계를 검토하고 완료합니다.

<!-- merge-rules-start.xml -->

## 교차 장치 데이터 소스 만들기 {#create-data-source}

교차 장치 데이터 소스를 만들려면 다음 위치로 이동하십시오. **[!UICONTROL Audience Data > Data Sources > Add New]** 여기에서 설명하는 각 섹션에 대한 단계를 완료합니다. 장치 간 데이터 소스를 만들거나 편집하려면 관리자 권한이 있어야 합니다.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>자세한 내용은 [데이터 소스 설정 및 메뉴 옵션](../datasources-list-and-settings.md#settings-menu-options) 자세한 내용은

## 데이터 소스 세부 정보 {#details}

를 완료하려면 [!UICONTROL Data Source Details] 섹션:

1. 데이터 소스에 이름을 지정합니다.
2. *(선택 사항)* 데이터 소스를 설명합니다. 간결한 설명은 데이터 소스의 역할이나 목적을 정의하는 데 도움이 됩니다.
3. 통합 코드를 제공합니다. 통합 코드는 이 데이터 소스에 대한 고유한 ID입니다.
4. 에서 **[!UICONTROL ID Type]** 목록, 선택 **[!UICONTROL Cross Device]**.
5. 에서 **[!UICONTROL ID Definition]** 목록에서 데이터 소스 유형을 정의하는 옵션을 선택합니다. 옵션은 다음과 같습니다.
   * **[!UICONTROL Person]**: 한 개인을 정의하는 ID입니다. 이 ID를 여러 ID에 매핑할 수 있습니다 [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**: 사람 그룹을 정의하는 ID입니다. 이 ID를 여러 ID에 매핑할 수 있습니다 [!DNL Audience Manager] ID.

## 데이터 내보내기 제어 {#export-controls}

[데이터 내보내기 제어](../data-export-controls.md) 는 데이터 소스 및 대상에 적용할 수 있는 선택적 분류 규칙입니다. 따라서 해당 작업이 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우 데이터를 대상에 보내지 못합니다. 사용하지 않는 경우 이 섹션을 건너뜁니다 [!UICONTROL Data Export Controls].

## 데이터 소스 설정 {#settings}

[!UICONTROL Data Source Settings] 섹션에서는 여러 옵션을 제공하지만 교차 장치 데이터 소스를 만드는 데 중요합니다.

* **[!UICONTROL Use as Authenticated Profile]**: 기본적으로 선택됩니다. 이 설정을 사용하면 [!UICONTROL Profile Merge Rule] 를 사용하여 데이터를 암호화할 수 있습니다.

* **[!UICONTROL Use as a Device Graph]**: 이 컨트롤은 데이터 공급자로 나열된 계정에만 사용할 수 있습니다. 이 확인란을 선택하면 데이터 소스가 장치 그래프로 만들어지고 다른 사용자와 공유할 수 있습니다 [!DNL Audience Manager] 고객. 작업 [!DNL Audience Manager] 컨설턴트를 통해 데이터 공급자로 설정하고 이 [!UICONTROL Data Source] 와 공유해야 합니다. 컨설턴트는 내부 프로비저닝 프로세스를 통해 계정 및 장치 그래프 공유를 프로비저닝합니다.

* **[!UICONTROL Data retention for inactive Customer IDs]**: 이 컨트롤을 사용하면 비활성 고객 ID에 대한 데이터 유지 기간을 설정할 수 있습니다. 이는 Audience Manager이 고객 ID를 Audience Manager 플랫폼에서 마지막으로 본 후 데이터베이스에 유지하는 시간을 결정합니다. 기본값은 24개월(720일)입니다. 설정할 수 있는 최소값은 1개월이고 최대값은 5년입니다. 모든 개월 수를 30일로 계산합니다. Audience Manager은 비활성 고객 ID에 대해 설정한 데이터 유지에 따라 일주일에 한 번 비활성 고객 ID를 삭제하는 프로세스를 실행합니다.

이러한 설정과 연결된 텍스트 필드를 사용하면 [!UICONTROL Data Source] 에 표시되는 별칭으로 [프로필 병합 규칙 옵션](merge-rule-definitions.md). 예를 들어 **[!UICONTROL Use as Authenticated Profile]**&#x200B;에 해당 이름이 [!UICONTROL Authenticated Profile Options] 목록. 별칭을 **[!UICONTROL Use as a Device Graph]**&#x200B;에 해당 이름이 [!UICONTROL Device Options] 목록.

## 프로필 병합 규칙 만들기 {#create-profile-merge-rule}

을(를) 만들려면 [!UICONTROL Profile Merge Rule], 이동 **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** 여기에서 설명하는 각 섹션에 대한 단계를 완료합니다.

교차 장치 데이터 소스를 설정한 후 최대 3개의 병합 규칙을 만들 수 있습니다. 네 번째 프로필 병합 규칙([!UICONTROL All Cross-Device Profiles]) [사용자 기반 대상](../destinations/people-based-destinations-overview.md).

규칙을 만들거나 편집하거나 삭제하려면 관리자 권한이 필요합니다. 모든 사용자는 기존 [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**전제 조건:** 를 빌드하려면 장치 간 데이터 소스가 필요합니다 [!UICONTROL Profile Merge Rule]. 자세한 내용은 [데이터 소스 만들기](../manage-datasources.md#create-data-source).

>[!TIP]
>
>자세한 내용은 [정의된 프로필 병합 규칙 옵션](merge-rule-definitions.md) 자세한 내용은

## 기본 정보 {#basic-info}

를 완료하려면 [!UICONTROL Basic Information] 섹션:

1. 이름을 로 지정합니다 [!UICONTROL Profile Merge Rule].
2. *(선택 사항)* 설명 [!UICONTROL Profile Merge Rule]. 간결한 설명은 규칙의 역할이나 목적을 정의하는 데 도움이 됩니다.
3. *(선택 사항)* 선택 **[!UICONTROL Set as default]** 기본값을 다음과 같이 만들려면 [!UICONTROL Profile Merge Rule]. 새 세그먼트는 자동으로 기본 규칙과 연결됩니다.

## 데이터 내보내기 제어 {#data-export-controls}

[데이터 내보내기 제어](../data-export-controls.md) 는 선택적인 분류 규칙으로, [!UICONTROL Profile Merge Rule]. 따라서 해당 작업이 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우 데이터를 대상에 보내지 못합니다. 사용하지 않는 경우 이 섹션을 건너뜁니다 [!UICONTROL Data Export Controls].

## 프로필 병합 규칙 설정 {#profile-merge-rule-setup}

를 완료하려면 [!UICONTROL Proflie Merge Rule Setup] 섹션:

1. 선택 **[!UICONTROL Authenticated Option]**. 옵션은 다음과 같습니다.
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. 선택 **[!UICONTROL Authenticated Profile Option]** (최대 3, 최대) 다음은 [교차 장치 데이터 소스](merge-rules-start.md) 이전에 만들었습니다.
3. 선택 **[!UICONTROL Device Option]**. 옵션은 다음과 같습니다.
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. 클릭 **[!UICONTROL Save]**.

### 교차 장치 ID를 사용자 ID 키로 사용하는 Adobe Campaign 대상에 대한 고려 사항 {#considerations}

2019년 말에는 교차 장치 ID를 사용하여 생성된 일괄 처리 파일의 정확도를 개선하기 위해 일련의 프로필 병합 규칙 개선 사항을 발표했습니다. 이러한 개선 사항은 2020년 3월 16일 월요일부터 Audience Manager 인스턴스에 엄격하게 적용됩니다. 따라서 교차 장치 ID를 사용하여 대상에 매핑된 세그먼트는 일부 프로필 병합 규칙 구성에서 내보내기 생성을 중지합니다.

Adobe Campaign과 같은 교차 장치 ID를 사용하여 Audience Manager 인스턴스와 대상 간에 올바르게 통합하려면 다음 요구 사항을 충족하는지 확인하십시오.

1. Adobe Campaign 선언 ID 대상에 매핑된 세그먼트에서 사용하는 프로필 병합 규칙 을 검토하십시오. 프로필 병합 규칙은 [!UICONTROL Last Authenticated Profile] 옵션을 선택하면 인증된 모든 프로필을 내보내기에 포함할 수 있습니다. 프로필 병합 규칙에 다른 옵션이 있는 경우 [!UICONTROL Last Authenticated Profile].
2. 프로필 병합 규칙 설정에서 Adobe Campaign 선언된 ID 데이터 소스를 선택합니다.

>[!NOTE]
>
> 최대 개수 [!UICONTROL Profile Merge Rules] 또한 위의 지침에 따라 구성하는 데 도움이 필요한 경우 고객 지원 센터에 문의하십시오.

## 병합 규칙 코드 구성 {#configure-merge-rule-code}

다음 지침에 따라 [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL], 및 모바일 [!DNL SDK] 병합 규칙을 사용할 코드입니다.

<!-- merge-rules-configure-code.xml -->

### 사전 요구 사항

을(를) 설정해야 합니다 [교차 장치 데이터 소스](#create-data-source) 및 [프로필 병합 규칙](#create-profile-merge-rule) *이전* 이러한 절차를 완료합니다.

## Adobe Experience Platform Identity 서비스 고객의 경우 {#id-service-customers}

다음 [!UICONTROL Adobe Experience Platform Identity Service] 최신 버전의 [DIL](../../dil/dil-overview.md) 작업 시 권장되는 [!UICONTROL Profile Merge Rules]. 그러나 를 사용할 필요는 없습니다 [!UICONTROL Adobe Experience Platform Identity Service] 을 사용하여 이 기능을 사용할 수 있습니다. 그냥 [!UICONTROL DIL]를 참조하고 [레거시 DIL 섹션](#legacy-dil) 아래의 제품에서 사용할 수 있습니다.

### 고객 ID 설정 기능 구성

을 사용하여 작업할 때 [!UICONTROL Adobe Experience Platform Identity Service], `setCustomerIDs` 함수는 선언된 ID를에 전달합니다 [!DNL Audience Manager]. 프로필 병합 규칙을 사용하려면 수정해야 합니다 `setCustomerIDs` 교차 장치 데이터 소스를 만들 때 지정된 통합 코드를 사용하기 위해. 예를 들어 통합 코드를 사용하여 교차 장치 데이터 소스를 만들었다고 가정합니다 `my_datasource_ic`. 선언된 ID를 전달하려면 아래 수정된 코드 샘플에 표시된 대로 통합 코드를 방문자 ID 함수에 추가합니다.

#### 일반 코드 샘플

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

자세한 내용은 [교차 장치 데이터 소스 만들기](#create-data-source) 및 [고객 ID 및 인증 상태](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### 구성 `DIL.create` 함수

최신 버전의 [!UICONTROL DIL] 이제 자동으로 [!UICONTROL declared ID] 에서 `visitorService` 함수 `DIL.create` 자세한 내용은 [선언된 ID 변수](../declared-ids.md#declared-id-variables)). 다음 문서를 확인하십시오. `DIL.create` 가 아래 코드 샘플에 표시된 대로 제대로 설정되었는지 확인하는 함수입니다.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

네임스페이스 키-값 쌍에서 `*`MCORG`*` 변수는 [!DNL Experience Cloud] 조직 ID. 이 ID가 없는 경우에는 [!UICONTROL Administration] 섹션 [!DNL Experience Cloud] 대시보드 . 이 대시보드를 보려면 관리자 권한이 필요합니다. 자세한 내용은 [관리: 핵심 서비스](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

### SDK 구성

자세한 내용은 [SDK 구성](#configure-sdks-legacy-dil) 섹션을 참조하십시오.

## 기존 DIL {#legacy-dil}

사용하지 않는 경우 [!DNL Adobe Experience Platform Identity Service] 하지만, 당신은 정말로 해야만 합니다. 하지만 새로운 코드로 이동하려면 신중한 생각과 테스트가 필요하다는 것을 알고 있습니다. 이러한 경우 `DIL.create` 가 아래 코드 샘플에 표시된 대로 제대로 설정되었는지 확인하는 함수입니다.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

자세한 내용은 기존 [!UICONTROL DIL] 섹션 [선언된 ID 변수](../declared-ids.md#declared-id-variables).

### SDK 구성 {#configure-sdks-legacy-dil}

에서 메서드를 확인합니다. [!DNL SDK] 다음을 전달할 수 있는 코드 [!UICONTROL declared IDs] 변환 전: [!DNL Android] 및 [!DNL iOS] 모바일 장치입니다. 의 변수 이름 [!DNL Android] 및 [!DNL iOS] 코드 라이브러리는 동일합니다.

* `dpid`: 교차 장치 데이터 소스 ID입니다.
* `dpuuid`: 다음 [!UICONTROL declared ID] (즉, 사용자 ID).

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

또한, [Android용 Audience Manager 메서드](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) 및 [iOS에 대한 Audience Manager 방법](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [데이터 소스 만들기](../manage-datasources.md#create-data-source)

