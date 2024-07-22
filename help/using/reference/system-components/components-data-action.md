---
description: 데이터 작업 구성 요소에는 고객 데이터 피드, 데이터 수집 서버, SFTP/S3/HTTP 게시자, IRIS 및 프로필 캐시 서버가 포함됩니다.
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: 데이터 작업 구성 요소
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---

# 데이터 작업 구성 요소{#data-action-components}

데이터 작업 구성 요소에는 고객 데이터 피드, 데이터 수집 서버, SFTP/S3/HTTP 게시자, IRIS 및 프로필 캐시 서버가 포함됩니다.

<!-- 

c_compact.xml

 -->

작업 구성 요소는 [!DNL Audience Manager] 안팎으로 데이터를 이동할 수 있도록 해 주는 시스템 및 프로세스입니다. 더 나은 문구가 없으므로 작업을 수행합니다. 이러한 [!DNL Audience Manager] 구성 요소는 다음과 같습니다.

## CDF(고객 데이터 피드) {#cdf}

[!UICONTROL CDF]은(는) 매시간 고객에게 전송되는 파일입니다. 여기에는 관련 세그먼트 ID, 트레이트 ID 및 기타 데이터와 함께 사용자 ID가 포함됩니다. 자세한 내용은 [고객 데이터 피드 개요](../../features/cdf-files.md)를 참조하십시오.

## DCS(데이터 수집 서버) {#dcs}

[데이터 수집 구성 요소](../../reference/system-components/components-data-collection.md)를 참조하십시오.

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3] 게시자가 [!UICONTROL Outbound Feed Converter]에서 동기화된 ID 데이터를 받습니다. 이러한 파일이 준비되면 [!UICONTROL SFTP/S3 publishers]에서 이 데이터를 클라이언트가 지정한 대상으로 보냅니다. 이러한 파일에는 [!DNL Audience Manager] UUID(사용자 ID)의 일대다 매핑이 있는 동기화된 ID 데이터가 포함되어 있습니다.

* 장치 ID/데이터 공급자 ID(DPUUID)
* 적격 세그먼트 ID
* 트레이트 ID

[!DNL Audience Manager] 고객은 [!UICONTROL SFPT/S3 publishers]을(를) 직접 제어하는 기능에 액세스할 수 없습니다. 고객은 데이터를 만들고 대상으로 전송할 때 이 서비스를 간접적으로 사용합니다. [!UICONTROL SFTP/S3] 시스템은 기본적으로 예약된 간격으로 실행되는 자동화된 작업 프로세스입니다.

## 홍채 {#iris}

그리스 신화에서 [!UICONTROL Iris]은(는) 메시지를 빠르게 여행하고 전달하는 인물이다. [!UICONTROL IRIS] 시스템은 고대 세계의 이 인물의 특성을 반영하는 이름입니다. 기본적으로 [!UICONTROL IRIS]은(는) 지연 시간이 짧고 빈도가 높은 쿠키 동기화 및 데이터 전송 서비스입니다.

[!UICONTROL IRIS]은(는) [!UICONTROL SFTP/S3] 시스템과 동일한 유형의 데이터를 사용합니다. 그러나 [!UICONTROL IRIS]은(는) 설정된 간격이 아니라 실시간으로 대상에 데이터를 보내기 때문에 다릅니다. [!UICONTROL SFTP/S3] 게시자는 HTTP 대상에 데이터를 보낼 수 없고 실시간 데이터 전송을 위해 디자인되지 않았으므로 이 시스템은 별도의 시스템입니다.

고객이 [!UICONTROL IRIS]을(를) 직접 사용할 수 있도록 하는 UI 컨트롤이 없습니다. 고객은 데이터를 만들고 대상으로 전송할 때 또는 신속한 데이터 전송이 필요한 다른 프로세스에 대해 [!UICONTROL IRIS]과(와) 간접적으로 작업합니다.

[!UICONTROL IRIS] 서비스 및 기능의 예는 다음과 같습니다.

* 쿠키 및 세그먼트에 대해 빠른(30초 이내) 동기화를 제공합니다. [!DNL Audience Manager] 쿠키, 파트너 쿠키 또는 둘 다를 동기화할 수 있습니다.
* 실시간 데이터 전송. [!UICONTROL IRIS]은(는) 실시간 세그먼트 자격 이벤트를 파트너 또는 다른 대상으로 보냅니다. 이 데이터는 JSON 형식이며 HTTP `POST` 요청을 통해 전송됩니다.

* 대량 서버 간 데이터 전송: 대량의 데이터를 [!DNL Audience Manager]과(와) 교환하는 경우 [!UICONTROL IRIS]은(는) 서버에서 데이터를 전송하기 위해 사용하는 시스템입니다.

* 규모에 맞게 작동하며 내결함성이 있는 안정적인 인프라 [!UICONTROL IRIS]을(를) 지원하는 시스템에는 Amazon SQS, Amazon EC2 및 Cassandra가 포함됩니다.

**세그먼트 매핑 규칙**

[!UICONTROL IRIS]과(와) 세그먼트 대상 간의 트래픽을 최적화하기 위해 [!UICONTROL IRIS]은(는) 규칙 집합을 기준으로 대상에 세그먼트를 보냅니다.

1. **새 세그먼트 자격**: 장치가 새 세그먼트를 사용할 수 있는 경우 [!UICONTROL IRIS]은(는) 해당 장치와 연결된 모든 세그먼트를 이 세그먼트에 매핑된 모든 대상으로 보냅니다.

1. **새 세그먼트 결격**: 장치가 더 이상 세그먼트에 적합하지 않을 경우 [!UICONTROL IRIS]은(는) 해당 장치와 관련된 모든 세그먼트 자격 및 결격 사유를 이러한 세그먼트에 매핑된 모든 대상으로 보냅니다.

1. **대상 매핑 업데이트**: 대상 매핑이 업데이트되면 [!UICONTROL IRIS]이(가) 장치에 연결된 모든 세그먼트를 이러한 세그먼트에 매핑된 모든 대상으로 보냅니다. Audience Manager은 다음에 장치를 봅니다.

1. **장치 그래프 업데이트**: 세그먼트를 평가하는 데 사용된 장치 그래프에서 장치 ID가 추가되거나 제거되면 [!UICONTROL IRIS]은(는) 해당 장치와 연결된 모든 세그먼트를 이러한 세그먼트에 매핑된 모든 대상으로 보내며, 다음에 Audience Manager이 장치를 볼 때 이 장치를 봅니다.

>[!IMPORTANT]
>
>Audience Manager이 연속 3일 동안 위의 업데이트를 검색하지 못하면 [!UICONTROL IRIS]은(는) 다음 번에 Audience Manager이 장치를 볼 때 장치와 연결된 모든 세그먼트를 해당 세그먼트에 매핑된 모든 대상으로 보냅니다.

**샘플 데이터 파일**

다음 예제에서는 [!UICONTROL IRIS]의 실시간 세그먼트 데이터를 포함합니다. 이 데이터는 샘플 데이터에만 해당됩니다. 각 고객은 콘텐츠가 다를 수 있도록 다양한 서식 요구 사항을 가질 수 있습니다.

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

## PCS(프로필 캐시 서버) {#pcs}

[데이터 수집 구성 요소](../../reference/system-components/components-data-collection.md)를 참조하십시오.
