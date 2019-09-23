---
description: Audience Manager는 데이터 보안 및 개인 정보를 매우 중요시합니다. Adobe는 시스템의 보안을 유지하고 중요한 데이터를 보호하기 위해 노력하고 있습니다.
seo-description: Audience Manager는 데이터 보안 및 개인 정보를 매우 중요시합니다. Adobe는 시스템의 보안을 유지하고 중요한 데이터를 보호하기 위해 노력하고 있습니다.
seo-title: 데이터 보안
solution: Audience Manager
title: 데이터 보안
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 91444ad943fcd020c83e522922d67ef400bf8824

---


# 데이터 보안 {#data-security}

Audience Manager는 데이터 보안 및 개인 정보를 매우 중요시합니다. Adobe는 시스템의 보안을 유지하고 중요한 데이터를 보호하기 위해 노력하고 있습니다.

Adobe Audience Manager의 보안 관행은 외부 및 내부 감사, 활동 로깅, 트레이닝 및 Adobe 시스템과 중요한 데이터를 보호하기 위해 고안된 기타 절차를 포함합니다. Adobe는 안전한 제품을 통해 고객이 신뢰할 수 있는 제품을 구축하고 유지 관리할 수 있다고 믿습니다.

Adobe Audience Manager에서는 세 가지 주요 범주의 보안에 대해 살펴봅니다.

| Security Type | 다음을 지원합니다. |
|---|---|
| **정보 보안** | Enterprise-level authentication, encryption, and data storage practices |
| **Data leakage/transparency** | Deep and actionable insight into on-site activities that constitute or contribute to data leakage |
| **Process/policy enhancements** | Clients, by working with industry best practices for privacy and data security |

## Systems, Training, and Access {#systems-training-access}

Adobe 시스템 및 데이터의 보안을 유지하는 프로세스

**** External Security Validation:  Audience Manager tests security on an annual and quarterly basis.

* Yearly: Once a year, Audience Manager undergoes a full penetration test conducted by an independent third-party company. The test is designed to identify security vulnerabilities in the application. The tests include scanning for cross-site scripting, SQL injections, form parameter manipulation, and other application-level vulnerabilities.
* Quarterly: Once each quarter, internal teams check for security vulnerabilities. These tests include network scans for open ports and service vulnerabilities.

**** 시스템 보안: 데이터를 안전하게 보호하고 보안을 유지하기 위해 Audience Manager:

* 권한 없는 IP 주소에서 요청을 차단합니다.
* Protects data behind firewalls, VPNs, and with Virtual Private Cloud storage.
* 트리거 기반의 감사 기록을 사용하여 고객 및 제어 정보 데이터베이스의 변경 사항을 추적합니다. These logs track all changes at the database level, including the user ID and IP address from which changes are made.

**** 보안 자산: Audience Manager에는 방화벽과 침입 감지 장치를 모니터링하는 전용 네트워크 운영 팀이 있습니다. 핵심 직원만이 Adobe 보안 기술 및 데이터에 액세스할 수 있습니다.

**** 보안 교육: Adobe의 보안 노력은 Adobe 제품을 사용하는 개발자에게 확대될 수 있습니다. Adobe는 개발자에게 보안 애플리케이션 및 서비스를 구축하는 방법에 대한 공식 교육을 제공합니다.

**** 보안 액세스: Audience Manager에서 시스템에 로그온하려면 강력한 암호가 필요합니다. 자세한 내용은 [암호 요구 사항을](../../reference/password-requirements.md)참조하십시오.

## 개인 정보 및 개인 식별 정보(PII) {#pii}

개인 정보를 안전하게 유지하는 프로세스 자세한 개인 정보 정보는 Adobe 개인 정보 [센터를 참조하십시오](https://www.adobe.com/privacy/advertising-services.html).

**** PII 데이터: Adobe Audience Manager는 고객 및 데이터 파트너가 PII 정보를 Adobe 시스템으로 보내는 것을 금지합니다. 또한 UUID(고유 사용자 ID)는 ID 생성 알고리즘의 일부로 PII 데이터를 포함하거나 사용하지 않습니다.

**** IP 주소: Audience Manager는 IP 주소를 수집합니다. IP 주소는 데이터 처리 및 로그 수집 프로세스에서 사용됩니다. 지리적/위치 조회 및 타깃팅에도 필요합니다. 또한 보존된 로그 파일 내의 모든 IP 주소는 90일 이내에 난독화됩니다.

## 데이터 분할 {#data-partitioning}

개별 클라이언트가 소유한 데이터를 보호하는 프로세스입니다.

**** 트레이트 데이터 분할: 데이터(트레이트, ID 등) 는 클라이언트에 의해 분할됩니다. 이렇게 하면 다른 클라이언트 간에 우발적인 정보 노출을 방지할 수 있습니다. 예를 들어 쿠키의 특성 데이터는 고객이 분할하고 클라이언트별 하위 도메인에 저장됩니다. 다른 Audience Manager 클라이언트에서 이를 읽거나 실수로 사용할 수 없습니다. 또한, 에 저장된 트레이트 데이터도 [!UICONTROL Profile Cache Servers (PCS)] 고객이 분할합니다. 이렇게 하면 다른 클라이언트가 이벤트 호출 또는 기타 요청에서 데이터를 실수로 사용하지 못하도록 합니다.

**** 보고서의 데이터 분할: 클라이언트 ID는 모든 보고 테이블에서 식별 키의 일부이며 보고서 쿼리는 ID로 필터링됩니다. 이렇게 하면 다른 Audience Manager 고객의 보고서에 데이터가 표시되지 않도록 할 수 있습니다.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager supports two main methods of transferring S2S on-boarded data files to our systems:

Both methods are designed with the security of our customer and partner data in mind while data is in flight between their systems and our system.

**** SFTP: For the SFTP option, most customers choose to deliver files via the Secure FTP (SFTP) protocol, which uses the Secure Shell (SSH) protocol. This method ensures that files are encrypted while in flight between the customer's systems and Adobe's system. For each customer, we create a jailed drop-box location on our SFTP servers, which is tied to a user account on that system. Only the customer's credentialed and privileged internal system users can access this jailed drop-box location. This jail is never accessible to other customers.

**** Amazon Web Services S3 via HTTPS: For the S3 delivery option, we recommend that all customers configure their S3 clients to use the HTTPS encryption method for file transfers (this is not the default, so it must be explicitly configured). The HTTPS option is supported both by the s3cmd command line tool as well as the S3 libraries available in every major programming language. With this HTTPS option enabled, customer's data is encrypted while in flight to our systems. For each customer, we create a separate S3 bucket sub-directory that can be accessed only by that customer's credentials and those of our internal system users.

To add PGP encryption to your data files, see File PGP Encryption for Inbound Data Types.[](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)

## Protecting Data by Escaping {#escaping-data}

Note that  does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. [!DNL Audience Manager] 들어오는 데이터를 escape하는 것은 클라이언트의 책임입니다.

## HTTP Strict-Transport-Security(#hsts)

[!DNL HTTP Strict-Transport-Security (HSTS)] 는 [!DNL HTTP] 트래픽을 허용하지 않고 모든 [!DNL HTTP] 트래픽을 로 투명하게 업그레이드하여 쿠키 하이재킹 및 프로토콜 다운그레이드 공격으로부터 보호하는 웹 보안 정책 메커니즘입니다 [!DNL HTTPS].

이 정책은 클라이언트와 Adobe Edge Server 간의 데이터 보안을 향상시킵니다.

### 예 {#hsts-example}

액세스를 시도할 `http://bank.demdex.com`때 브라우저가 [!DNL HSTS] 도메인을 자동으로 요청하지 않는 `https://bank.demdex.com`[!DNL HTTPS] 경우 자동으로 요청을 로 업그레이드합니다.

HSTS [에 대한 자세한 내용은 HTTP Strict Transport Security](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) - Wikipedia를 참조하십시오.
