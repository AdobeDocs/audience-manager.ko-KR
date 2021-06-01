---
description: 베타 환경은 Audience Manager 구현을 테스트하는 것입니다. 베타에서 변경한 사항은 프로덕션 데이터에 영향을 주지 않습니다. 베타 환경을 사용하려면 Audience Manager 파트너 솔루션 담당자에게 문의하십시오.
keywords: 샌드박스
seo-description: 베타 환경은 Audience Manager 구현을 테스트하는 것입니다. 베타에서 변경한 사항은 프로덕션 데이터에 영향을 주지 않습니다. 베타 환경을 사용하려면 Audience Manager 파트너 솔루션 담당자에게 문의하십시오.
seo-title: 베타 환경
solution: Audience Manager
title: 베타 환경
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: 참조
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 4%

---

# 베타 환경 {#beta-environment}

베타 환경은 Audience Manager 구현을 테스트하는 것입니다. 베타에서 변경한 사항은 프로덕션 데이터에 영향을 주지 않습니다. 베타 환경을 사용하려면 Audience Manager 파트너 솔루션 담당자에게 문의하십시오.

## 개요

베타 환경은 실험적이거나 릴리스되지 않은 기능 없이 프로덕션 환경의 정확한 복제본입니다. 프로덕션 환경의 로그인 자격 증명은 베타 환경에서 유효합니다.

**예약 업데이트**

베타 환경은 비성수기 동안 매월 말에 업데이트됩니다.

**아웃바운드 트래픽**

베타 환경에 대해 아웃바운드 트래픽을 사용할 수 없습니다.

<!-- 

Added re: AAM-30826.

 -->

## 끝점



| 서비스 | URL/호스트 이름 | 액세스 권한을 얻는 방법 |
|--- |--- | --- |
| S3 | Audience Manager 파트너 솔루션 담당자 또는 고객 지원 센터에 문의하십시오 | 베타 인스턴스에 대한 Amazon S3 버킷을 설정하려면 Audience Manager 파트너 솔루션 담당자 또는 고객 지원 센터에 문의하십시오. Amazon S3](../reference/amazon-s3.md)을 사용할 때의 [장점에 대해 읽어보십시오. |
| DCS | `https://dcs-beta.demdex.net/...` | 베타 환경에서 [DCS 액세스](../reference/beta-environment.md#access-dcs-beta-environment)를 참조하십시오. |
| UI | `https://bank-beta.demdex.com` | 프로덕션 환경 자격 증명은 베타 환경에 유효합니다. |
| API | `https://api-beta.demdex.com/...` | 프로덕션 환경 자격 증명은 베타 환경에 유효합니다. 일반 API 사용자를 만드는 것이 좋습니다. [세부 사항](../api/rest-api-main/aam-api-getting-started.md#requirements) 을 참조하십시오. |

## 베타 환경에서 DCS에 액세스 {#access-dcs-beta-environment}

1. curl [command](https://curl.haxx.se/docs/manpage.html)를 사용하여 DCS를 호출합니다. Curl은 지원되는 여러 프로토콜 중 하나를 사용하여 또는 서버에서 데이터를 전송하는 도구입니다.

   예:

   `curl -v https://dcs-beta.demdex.net/event`

1. DCS 응답 헤더에서 &quot;sandbox&quot;를 찾아 Beta DCS에서 요청이 제공되었는지 확인합니다.

   예:

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->
