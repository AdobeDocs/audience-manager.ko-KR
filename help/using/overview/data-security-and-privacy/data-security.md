---
description: Audience Manager는 데이터 보안 및 개인 정보를 매우 중요시합니다. Adobe는 시스템의 보안을 유지하고 중요한 데이터를 보호하기 위해 노력하고 있습니다.
seo-description: Audience Manager는 데이터 보안 및 개인 정보를 매우 중요시합니다. Adobe는 시스템의 보안을 유지하고 중요한 데이터를 보호하기 위해 노력하고 있습니다.
seo-title: 데이터 보안
solution: Audience Manager
title: 데이터 보안
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# 데이터 보안 {#data-security}

Audience Manager는 데이터 보안 및 개인 정보를 매우 중요시합니다. Adobe는 시스템의 보안을 유지하고 중요한 데이터를 보호하기 위해 노력하고 있습니다.

Adobe Audience Manager의 보안 관행은 외부 및 내부 감사, 활동 로깅, 트레이닝 및 Adobe 시스템과 중요한 데이터를 보호하기 위해 고안된 기타 절차를 포함합니다. Adobe는 안전한 제품을 통해 고객이 신뢰할 수 있는 제품을 구축하고 유지 관리할 수 있다고 믿습니다.

Adobe Audience Manager에서는 세 가지 주요 범주의 보안에 대해 살펴봅니다.

| 보안 유형 | 다음을 지원합니다. |
|---|---|
| **Information security** | Enterprise-level authentication, encryption, and data storage practices |
| **데이터 누출/투명도** | Deep and actionable insight into on-site activities that constitute or contribute to data leakage |
| **Process/policy enhancements** | 클라이언트 - 개인 정보 및 데이터 보안에 대한 업계 모범 사례를 사용하여 작업 |

## Systems, Training, and Access {#systems-training-access}

Processes that help keep our system and your data secure.

**** External Security Validation:  Audience Manager tests security on an annual and quarterly basis.

* 연간:Audience Manager는 1년에 한 번 독립 서드 파티 회사가 실시하는 보급률 테스트를 받습니다. 이 테스트는 응용 프로그램의 보안 취약점을 식별하기 위해 고안되었습니다. The tests include scanning for cross-site scripting, SQL injections, form parameter manipulation, and other application-level vulnerabilities.
* 분기별:분기마다 한 번씩 내부 팀이 보안 취약점을 확인합니다. 이러한 테스트에는 개방형 포트 및 서비스 취약점에 대한 네트워크 검색이 포함됩니다.

**** 시스템 보안: 데이터를 안전하게 보호하고 보안을 유지하기 위해 Audience Manager:

* 권한 없는 IP 주소에서 요청을 차단합니다.
* 방화벽, VPN 및 가상 사설 클라우드 스토리지를 통해 데이터를 보호합니다.
* 트리거 기반의 감사 기록을 사용하여 고객 및 제어 정보 데이터베이스의 변경 사항을 추적합니다. 이러한 로그는 변경 사항이 있는 사용자 ID 및 IP 주소를 포함하여 데이터베이스 수준에서 모든 변경 사항을 추적합니다.

**** 보안 자산: Audience Manager에는 방화벽과 침입 감지 장치를 모니터링하는 전용 네트워크 운영 팀이 있습니다. 핵심 직원만이 Adobe 보안 기술 및 데이터에 액세스할 수 있습니다.

**** 보안 교육: Adobe의 보안 노력은 Adobe 제품을 사용하는 개발자에게 확대될 수 있습니다. Adobe는 개발자에게 보안 애플리케이션 및 서비스를 구축하는 방법에 대한 공식 교육을 제공합니다.

**** Secure Access:  Audience Manager requires strong passwords to log on to the system. See password requirements.[](../../reference/password-requirements.md)

## 개인 정보 및 개인 식별 정보(PII) {#pii}

Processes that help keep personal information safe. For additional privacy information, see the Adobe Privacy Center.[](https://www.adobe.com/privacy/advertising-services.html)

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP Addresses:  Audience Manager does collect IP addresses. IP addresses are used in data-processing and log-aggregation processes. They are also required for geographic/location look-ups and targeting. 또한 보존된 로그 파일 내의 모든 IP 주소는 90일 이내에 난독화됩니다.

## 데이터 분할 {#data-partitioning}

개별 클라이언트가 소유한 데이터를 보호하는 프로세스입니다.

**** 트레이트 데이터 분할: 데이터(트레이트, ID 등) 는 클라이언트에 의해 분할됩니다. 이렇게 하면 다른 클라이언트 간에 우발적인 정보 노출을 방지할 수 있습니다. 예를 들어 쿠키의 특성 데이터는 고객이 분할하고 클라이언트별 하위 도메인에 저장됩니다. 다른 Audience Manager 클라이언트에서 이를 읽거나 실수로 사용할 수 없습니다. 또한, 에 저장된 트레이트 데이터도 [!UICONTROL Profile Cache Servers (PCS)] 고객이 분할합니다. This prevents other clients from accidentally using your data in an event call or other request.

**** Data Partitioning in Reports:  Client IDs are part of the identifying key in all reporting tables and report queries are filtered by ID. This helps prevent your data from appearing in the reports of another Audience Manager customer.

## S2S(Inbound Server-to-Server) 전송 {#inbound-s2s}

Adobe Audience Manager는 S2S 온보드 데이터 파일을 Adobe 시스템으로 전송하는 두 가지 주요 방법을 지원합니다.

두 방법 모두 Adobe 고객과 파트너 데이터의 보안을 고려하여 설계되었으며, 데이터는 시스템과 Adobe 시스템 간에 이동됩니다.

**** SFTP: For the SFTP option, most customers choose to deliver files via the Secure FTP (SFTP) protocol, which uses the Secure Shell (SSH) protocol. 이 방법을 사용하면 고객의 시스템과 Adobe 시스템 간에 파일을 암호화할 수 있습니다. For each customer, we create a jailed drop-box location on our SFTP servers, which is tied to a user account on that system. Only the customer's credentialed and privileged internal system users can access this jailed drop-box location. 이 감옥은 다른 고객에게는 결코 접근할 수 없다.

**** Amazon Web Services S3 via HTTPS: For the S3 delivery option, we recommend that all customers configure their S3 clients to use the HTTPS encryption method for file transfers (this is not the default, so it must be explicitly configured). HTTPS 옵션은 s3cmd 명령줄 도구와 모든 주요 프로그래밍 언어에서 사용할 수 있는 S3 라이브러리 모두에서 지원됩니다. 이 HTTPS 옵션을 활성화하면 Adobe 시스템으로 이동하는 동안 고객의 데이터가 암호화됩니다. For each customer, we create a separate S3 bucket sub-directory that can be accessed only by that customer's credentials and those of our internal system users.

데이터 파일에 PGP 암호화를 추가하려면 인바운드 데이터 [유형에 대한 파일 PGP 암호화를 참조하십시오](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protecting Data by Escaping {#escaping-data}

XSS(Cross-Site Scripting) 등에 대해 보안을 유지하기 위해 나가는 데이터를 escape하지 [!DNL Audience Manager] 않습니다. 들어오는 데이터를 escape하는 것은 클라이언트의 책임입니다.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] 는 쿠키 하이재킹 및 프로토콜 다운그레이드 공격으로부터 보호하는 데 도움이 되는 업계 전반의 웹 보안 메커니즘입니다.

이 정책은 특정 도메인에 대한 보안 [!DNL HTTPS] 호출이 수행되면 해당 도메인에 대한 후속 비보안 호출([!DNL HTTP])이 허용되지 않도록 웹 브라우저에 지시합니다. 이 기능은 공격자가 안전하지 않은 호출을 다운그레이드하려고 할 수 있는 중간 [!DNL HTTPS] 공격으로부터 [!DNL HTTP] 보호합니다."

이 정책은 클라이언트와 Adobe Edge Server 간의 데이터 보안을 [개선합니다](../../reference/system-components/components-edge.md) .

### 예 {#hsts-example}

액세스를 시도할 `http://bank.demdex.com`때 브라우저가 [!DNL HSTS] 도메인을 자동으로 요청하지 않는 `https://bank.demdex.com`[!DNL HTTPS] 경우 자동으로 요청을 로 업그레이드합니다.

HSTS [에 대한 자세한 내용은 HTTP Strict Transport Security](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) - Wikipedia를 참조하십시오.
