---
description: 데이터 작업 구성 요소에는 고객 데이터 피드, 데이터 수집 서버, SFTP/S3/HTTP 게시자, IRIS 및 프로필 캐시 서버가 포함됩니다.
seo-description: 데이터 작업 구성 요소에는 고객 데이터 피드, 데이터 수집 서버, SFTP/S3/HTTP 게시자, IRIS 및 프로필 캐시 서버가 포함됩니다.
seo-title: 데이터 작업 구성 요소
solution: Audience Manager
title: 데이터 작업 구성 요소
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: system components
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 3%

---


# 데이터 작업 구성 요소{#data-action-components}

데이터 작업 구성 요소에는 고객 데이터 피드, 데이터 수집 서버, SFTP/S3/HTTP 게시자, IRIS 및 프로필 캐시 서버가 포함됩니다.

<!-- 

c_compact.xml

 -->

작업 구성 요소는 데이터를 [!DNL Audience Manager] 안팎으로 이동할 수 있는 시스템 및 프로세스로서, 더 나은 문구가 없는 경우에는 해당 작업을 수행할 수 있습니다. 이러한 [!DNL Audience Manager] 구성 요소는 다음과 같습니다.

## CDF(고객 데이터 피드) {#cdf}

[!UICONTROL CDF] 은 고객에게 시간별로 전송되는 파일입니다. 여기에는 연결된 세그먼트 ID, 특성 ID 및 기타 데이터와 함께 사용자 ID가 포함됩니다. 자세한 내용은 [고객 데이터 피드 개요](../../features/cdf-files.md)를 참조하십시오.

## 데이터 수집 서버(DCS) {#dcs}

[데이터 수집 구성 요소](../../reference/system-components/components-data-collection.md)를 참조하십시오.

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3] 게시자는 [!UICONTROL Outbound Feed Converter]에서 동기화된 ID 데이터를 받습니다. 이러한 파일이 준비되면 [!UICONTROL SFTP/S3 publishers] 클라이언트에서 지정한 대상으로 이 데이터를 보냅니다. 이러한 파일에는 [!DNL Audience Manager] 사용자 ID(UUID)를 다음으로 일대다 매핑하는 동기화된 ID 데이터가 포함되어 있습니다.

* 장치 ID/데이터 공급자 ID(DPUUID)
* 자격이 있는 세그먼트 ID
* 특성 ID

[!DNL Audience Manager] 고객은 직접 제어하는 기능에 액세스할 수 없습니다 [!UICONTROL SFPT/S3 publishers]. 고객은 데이터를 만들어 대상에 보낼 때 이 서비스를 간접적으로 사용합니다. [!UICONTROL SFTP/S3] 시스템은 기본적으로 예약된 간격으로 실행되는 자동화된 작업 프로세스입니다.

## IRIS {#iris}

그리스 신화에서 &#39;a0/&#39;는 메시지를 빠르게 전달하고 여행하면서 얻은 인물이기 때문이다. [!UICONTROL Iris] [!UICONTROL IRIS]은 고대로부터 온 이 형상의 특성을 반영하는 이름 표본인 셈이다. 최신 용어로, [!UICONTROL IRIS]은 낮은 지연, 고빈도 쿠키 동기화 및 데이터 전송 서비스입니다.

[!UICONTROL IRIS] 은  [!UICONTROL SFTP/S3] 시스템과 동일한 유형의 데이터를 사용하여 작동합니다. 하지만 [!UICONTROL IRIS]은 설정된 간격보다는 실시간으로 대상에 데이터를 보내기 때문에 다릅니다. [!UICONTROL SFTP/S3] 게시자가 HTTP 대상에 데이터를 보낼 수 없고 실시간 데이터 전송을 위해 설계되지 않았기 때문에 별도의 시스템입니다.

고객이 [!UICONTROL IRIS]에서 직접 작업할 수 있는 UI 컨트롤이 없습니다. 고객은 데이터를 만들어 대상에 보낼 때, 그리고 신속한 데이터 전송을 필요로 하는 기타 프로세스에 대해 간접적으로 [!UICONTROL IRIS]과 함께 작업합니다.

[!UICONTROL IRIS] 서비스 및 기능의 예는 다음과 같습니다.

* 쿠키와 세그먼트에 대한 빠른 동기화(30초 이내) 제공 [!DNL Audience Manager] 쿠키, 파트너 쿠키 또는 둘 다를 동기화할 수 있습니다.
* 실시간 데이터 전송 [!UICONTROL IRIS] 은 파트너 또는 다른 대상에 실시간 세그먼트 자격 이벤트를 보낼 책임이 있습니다. 이 데이터는 JSON 포맷으로 HTTP `POST` 요청을 통해 전송됩니다.

* 서버 간 일괄 데이터 전송:많은 양의 데이터를 [!DNL Audience Manager]과 교환하는 경우, [!UICONTROL IRIS]은 서버가 데이터를 전송하기 위해 사용하는 시스템입니다.

* 규모에 맞게 작동하고 내결함성이 있는 안정적인 인프라 [!UICONTROL IRIS] 전원을 사용하는 시스템에는 Amazon SQS, Amazon EC2 및 Cassandra가 포함됩니다.

**세그먼트 매핑 규칙**

[!UICONTROL IRIS] 및 세그먼트 대상 간의 트래픽을 최적화하기 위해 [!UICONTROL IRIS]은(는) 규칙 세트를 기반으로 세그먼트를 대상에 보냅니다.

1. **새 세그먼트 자격**:장치가 새 세그먼트를 받을 자격이 있으면, 해당 장치에 연결된 모든 세그먼트를 이러한 세그먼트에 매핑된 모든 대상에  [!UICONTROL IRIS] 보냅니다.

1. **새로운 세그먼트 결격**:장치가 더 이상 세그먼트에 적격하지 않으면, 해당 장치에 연결된 모든 세그먼트 자격 조건과 결격사유가 이러한 세그먼트에 매핑된 모든 대상에  [!UICONTROL IRIS] 전송됩니다.

1. **대상 매핑 업데이트**:대상 매핑이 업데이트되면 장치에 연결된 모든 세그먼트를 이러한 세그먼트에 매핑된 모든 대상에  [!UICONTROL IRIS] 보냅니다. 다음에 Audience Manager에서 장치를 볼 때

1. **장치 그래프 업데이트**:세그먼트를 평가하는 데 사용되는 장치 그래프에서 장치 ID가 추가 또는 제거되면, 해당 장치에 연결된 모든 세그먼트를 이러한 세그먼트에 매핑된 모든 대상에  [!UICONTROL IRIS] 보냅니다. 다음 번 Audience Manager에서 장치를 보게 됩니다.

>[!IMPORTANT]
>
>Audience Manager이 3일 연속으로 위의 업데이트를 감지하지 못하면, [!UICONTROL IRIS]은 장치에 연결된 모든 세그먼트를 이러한 세그먼트에 매핑된 모든 대상에 전송하고, 다음 번 Audience Manager에서 장치를 보게 됩니다.

**샘플 데이터 파일**

다음 예제는 [!UICONTROL IRIS]의 실시간 세그먼트 데이터를 포함합니다. 이 데이터는 샘플 데이터에만 해당됩니다. 각 고객은 서로 다른 형식 요구 사항을 가지므로 내용이 다를 수 있습니다.

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## 프로필 캐시 서버(PCS) {#pcs}

[데이터 수집 구성 요소](../../reference/system-components/components-data-collection.md)를 참조하십시오.
