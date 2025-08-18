---
description: 베타 환경은 Audience Manager 구현을 테스트하기 위한 것입니다. Beta에서 변경한 사항은 프로덕션 데이터에 영향을 주지 않습니다. Beta 환경 사용에 관심이 있는 경우 Audience Manager 파트너 솔루션 담당자에게 문의하십시오.
keywords: 샌드박스
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Beta 환경
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: fce39268f1c8c4dd1b7ff21b61a9830a20fa0b4e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Beta 환경 {#beta-environment}

베타 환경은 Audience Manager 구현을 테스트하기 위한 것입니다. Beta에서 변경한 사항은 프로덕션 데이터에 영향을 주지 않습니다. Beta 환경 사용에 관심이 있는 경우 Audience Manager 파트너 솔루션 담당자에게 문의하십시오.

## 개요

베타 환경의 기능은 실험적이거나 릴리스되지 않은 기능 없이 프로덕션 환경의 정확한 복제본입니다. 프로덕션 환경의 로그인 자격 증명은 Beta 환경에서 유효합니다.

**일정 업데이트**

Beta 환경은 사용량이 적은 시간 동안 매월 말에 업데이트됩니다.

>[!IMPORTANT]
>
>고객 데이터([신호, 트레이트 및 세그먼트](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=ko))는 프로덕션 환경과 Beta 환경 간에 동기화되지 않습니다.

## 인바운드 트래픽

베타 환경은 파일 이름 및 콘텐츠 구문 유효성 검사 목적으로만 인바운드 트래픽을 지원합니다. Beta 환경에서 발생하는 ID 매핑이 없으므로 고객에게 세그먼트 인구가 표시되지 않습니다.

따라서 [!UICONTROL Onboarding Status] 페이지는 Beta 환경에서 파일 수집 시 항상 [!UICONTROL No matching AAM ID]을(를) 보고합니다.

모든 고객은 프로덕션 환경에서 인바운드 테스트를 수행하는 것이 좋습니다.

## 아웃바운드 트래픽

Beta 환경에 대해 아웃바운드 트래픽이 활성화되지 않았습니다.

## 엔드포인트

| 서비스 | URL/호스트 이름 | 액세스 권한을 얻는 방법 |
|--- |--- | --- |
| S3 | Audience Manager 파트너 솔루션 담당자 또는 고객 지원 센터에 문의하십시오 | Beta 인스턴스에 대한 Audience Manager S3 버킷을 설정하려면 Amazon 파트너 솔루션 담당자 또는 고객 지원 센터에 문의하십시오. Amazon S3 사용의 [장점](../reference/amazon-s3.md)을 읽어 보십시오. |
| DCS | `https://dcs-beta.demdex.net/...` | [Beta 환경에서 DCS에 액세스](../reference/beta-environment.md#access-dcs-beta-environment)를 참조하십시오. |
| UI | `https://bank-beta.demdex.com` | 프로덕션 환경 자격 증명은 Beta 환경에 유효합니다. |
| API | `https://api-beta.demdex.com/...` | 프로덕션 환경 자격 증명은 Beta 환경에 유효합니다. 일반 API 사용자를 만드는 것이 좋습니다. [세부 정보 보기](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Beta 환경에서 DCS에 액세스 {#access-dcs-beta-environment}

1. curl [command](https://curl.haxx.se/docs/manpage.html)을(를) 사용하여 DCS를 호출합니다. Curl은 지원되는 여러 프로토콜 중 하나를 사용하여 서버에서 또는 서버로 데이터를 전송하는 도구입니다.

   예:

   `curl -v https://dcs-beta.demdex.net/event`

1. DCS 응답 헤더에서 &quot;샌드박스&quot;를 찾아 Beta DCS에서 요청이 제공되었는지 확인합니다.

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
