---
description: 데이터 작업 구성 요소에는 고객 데이터 피드, 데이터 수집 서버, SFTP/S 3/HTTP 게시자, 조리개 및 프로필 캐시 서버가 포함됩니다.
seo-description: 데이터 작업 구성 요소에는 고객 데이터 피드, 데이터 수집 서버, SFTP/S 3/HTTP 게시자, 조리개 및 프로필 캐시 서버가 포함됩니다.
seo-title: 데이터 작업 구성 요소
solution: Audience Manager
title: 데이터 작업 구성 요소
uuid: C 4 C 4 CC 46-8 C 96-4 EF 5-8269-571 CC 5 AC 9276
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Action Components{#data-action-components}

데이터 작업 구성 요소에는 고객 데이터 피드, 데이터 수집 서버, SFTP/S 3/HTTP 게시자, 조리개 및 프로필 캐시 서버가 포함됩니다.

<!-- 

c_compact.xml

 -->

Action components are systems and processes that let you move data in and out of [!DNL Audience Manager] and (for the lack of a better phrase) do things with it. These [!DNL Audience Manager] components include:

## Customer Data Feeds (CDF) {#cdf}

[!UICONTROL CDF] 파일은 고객에게 시간별 전송됩니다. 여기에는 연관된 세그먼트 ID, 특성 ID 및 기타 데이터와 함께 사용자 ID가 포함됩니다. For more information, see [Customer Data Feed Overview](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

[데이터 수집 구성 요소를 참조하십시오](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3] 게시자는 로부터 동기화된 ID 데이터를 받습니다 [!UICONTROL Outbound Feed Converter]. When these files are ready, the [!UICONTROL SFTP/S3 publishers] send this data to a destination specified by the client. These files contain synchronized ID data with a one-to-many mapping of [!DNL Audience Manager] user IDs (UUID) to:

* 장치 ID/데이터 공급자 ID (DPUUID)
* 적격한 세그먼트 ID
* 특성 ID

[!DNL Audience Manager] 고객은을 직접 제어하는 기능에 액세스할 수 [!UICONTROL SFPT/S3 publishers]없습니다. 고객은 데이터를 만들어 대상으로 보낼 때 간접적으로 이 서비스를 사용합니다. [!UICONTROL SFTP/S3] 시스템은 본질적으로 예약된 간격으로 실행되는 자동화된 작업 프로세스입니다.

## IRIS {#iris}

In Greek mythology, [!UICONTROL Iris] is a figure who travels and delivers messages rapidly. The [!UICONTROL IRIS] system is a namesake that reflects the characteristics of this figure from the ancient world. In modern terms, [!UICONTROL IRIS] is a low-latency, high-frequency cookie synchronization and data transfer service.

[!UICONTROL IRIS] 시스템과 동일한 유형의 데이터를 [!UICONTROL SFTP/S3] 사용합니다. However, [!UICONTROL IRIS] is different because it sends data to destinations in real time rather than at set intervals. [!UICONTROL SFTP/S3] 이는 발행자가 HTTP 대상으로 데이터를 전송할 수 없고 실시간 데이터 전송을 위해 설계되지 않기 때문에 별도의 시스템입니다.

There are no UI controls that let customers work directly with [!UICONTROL IRIS]. Customers work with [!UICONTROL IRIS] indirectly when they create and send data to destinations, and for other processes that require rapid data transfers.

[!UICONTROL IRIS] 서비스 및 기능의 예는 다음과 같습니다.

* 쿠키 및 세그먼트에 대한 동기화 시간 (30 초 이내) 를 제공합니다. [!DNL Audience Manager] 쿠키, 파트너 쿠키 또는 둘 다를 동기화할 수 있습니다.
* 실시간 데이터 전송. [!UICONTROL IRIS] 는 실시간 세그먼트 자격 이벤트를 파트너 또는 다른 대상에 전송하는 책임을 집니다. This data is JSON-formatted and sent via an HTTP `POST` request.

* Bulk server-to-server data transfers: If you exchange large amounts of data with [!DNL Audience Manager], [!UICONTROL IRIS] is the system that your servers engage with to transfer data.

* 규모에 맞게 작동하고 내결함성이 있는 안정적인 인프라 Systems that power [!UICONTROL IRIS] include Amazon SQS, Amazon EC2, and Cassandra.

**세그먼트 매핑 규칙**

To optimize traffic between [!UICONTROL IRIS] and segment destinations, [!UICONTROL IRIS] sends segments to destinations based on a set of rules.

1. **새 세그먼트 자격 조건**: 장치가 새 세그먼트에 대한 자격을 갖춘 경우, 해당 장치에 연결된 모든 세그먼트를 이러한 세그먼트에 매핑된 모든 대상에 [!UICONTROL IRIS] 전송합니다.

1. **새로운 세그먼트 자격 조건**: 장치가 더 이상 세그먼트에 대해 자격이 없으면, 해당 장치에 연결된 모든 세그먼트 자격 조건과 부적격 항목을 이러한 세그먼트에 매핑된 모든 대상에 [!UICONTROL IRIS] 전송합니다.

1. **대상 매핑 업데이트**: 대상 매핑이 업데이트되면, 다음에 Audience Manager에서 장치를 볼 때 해당 세그먼트에 매핑된 모든 세그먼트를 해당 세그먼트에 매핑된 모든 대상에 [!UICONTROL IRIS] 전송합니다.

1. **장치 그래프 업데이트**: 세그먼트를 평가하는 데 사용된 장치 그래프에 장치 ID가 추가되거나 제거되면, 다음에 Audience Manager에서 장치를 볼 때 해당 장치에 연결된 모든 세그먼트를 이러한 세그먼트에 매핑된 모든 대상에 [!UICONTROL IRIS] 전송합니다.

>[!IMPORTANT]
>
>If Audience Manager doesn&#39;t detect any of the updates above for 3 consecutive days, [!UICONTROL IRIS] sends all segments associated to a device to all of the destinations mapped to these segments, the next time Audience Manager sees the device.

**샘플 데이터 파일**

The following example contains real-time segment data from [!UICONTROL IRIS]. 유의해야 할 사항은 샘플 데이터입니다. 각 고객은 서로 다른 서식 요구 사항을 가질 수 있으므로 컨텐츠가 달라질 수 있습니다.

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

## Profile Cache Server (PCS) {#pcs}

[데이터 수집 구성 요소를 참조하십시오](../../reference/system-components/components-data-collection.md).
