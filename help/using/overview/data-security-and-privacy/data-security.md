---
description: Audience Manager는 데이터 보안 및 개인 정보를 매우 중요시합니다. Adobe는 시스템의 보안을 유지하고 중요한 데이터를 보호하기 위해 노력하고 있습니다.
seo-description: Audience Manager는 데이터 보안 및 개인 정보를 매우 중요시합니다. Adobe는 시스템의 보안을 유지하고 중요한 데이터를 보호하기 위해 노력하고 있습니다.
seo-title: 데이터 보안
solution: Audience Manager
title: Data Security
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 34884e3212d50237c73fdc6aa163d90c29a642f5

---


# Data Security {#data-security}

Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.

Audience Manager security practices include external and internal audits, activity logging, training, and other procedures designed to help protect our systems and your valuable data. We believe a secure product helps build and maintain the trust customers place in us.

In Audience Manager, we think about security in three main categories:

| 보안 유형 | Provides Support For |
|---|---|
| **Information security** | 엔터프라이즈급 인증, 암호화 및 데이터 스토리지 방식 |
| **데이터 누출/투명도** | 데이터 누출을 구성하거나 기여하는 사이트 내 활동에 대한 심층적이고 실행 가능한 통찰력 |
| **프로세스/정책 개선 사항** | 클라이언트 - 개인 정보 및 데이터 보안에 대한 업계 모범 사례를 사용하여 작업 |

## 시스템, 트레이닝 및 액세스 {#systems-training-access}

Adobe 시스템 및 데이터의 보안을 유지하는 프로세스

**** 외부 보안 유효성 검사: Audience Manager는 보안을 연간 및 분기별로 테스트합니다.

* 연간:Audience Manager는 1년에 한 번 독립 서드 파티 회사가 실시하는 보급률 테스트를 받습니다. 이 테스트는 응용 프로그램의 보안 취약점을 식별하기 위해 고안되었습니다. 이 테스트에는 사이트 간 스크립팅, SQL 주입, 양식 매개 변수 조작 및 기타 애플리케이션 수준 취약점에 대한 검사가 포함됩니다.
* 분기별:분기마다 한 번씩 내부 팀이 보안 취약점을 확인합니다. 이러한 테스트에는 개방형 포트 및 서비스 취약점에 대한 네트워크 검색이 포함됩니다.

**** 시스템 보안: 데이터를 안전하게 보호하고 보안을 유지하기 위해 Audience Manager:

* 권한 없는 IP 주소에서 요청을 차단합니다.
* 방화벽, VPN 및 가상 사설 클라우드 스토리지를 통해 데이터를 보호합니다.
* 트리거 기반의 감사 기록을 사용하여 고객 및 제어 정보 데이터베이스의 변경 사항을 추적합니다. 이러한 로그는 변경 사항이 있는 사용자 ID 및 IP 주소를 포함하여 데이터베이스 수준에서 모든 변경 사항을 추적합니다.

**** 보안 자산: Audience Manager에는 방화벽과 침입 감지 장치를 모니터링하는 전용 네트워크 운영 팀이 있습니다. 핵심 직원만이 Adobe 보안 기술 및 데이터에 액세스할 수 있습니다.

**** 보안 교육: Adobe의 보안 노력은 Adobe 제품을 사용하는 개발자에게 확대될 수 있습니다. Adobe는 개발자에게 보안 애플리케이션 및 서비스를 구축하는 방법에 대한 공식 교육을 제공합니다.

**** Secure Access:  Audience Manager requires strong passwords to log on to the system. See password requirements.[](../../reference/password-requirements.md)

## Privacy and Personally Identifiable Information (PII) {#pii}

Processes that help keep personal information safe. 자세한 개인 정보 정보는 Adobe 개인 정보 [센터를 참조하십시오](https://www.adobe.com/privacy/advertising-services.html).

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP 주소: Audience Manager는 IP 주소를 수집합니다. IP 주소는 데이터 처리 및 로그 수집 프로세스에서 사용됩니다. 지리적/위치 조회 및 타깃팅에도 필요합니다. 또한 보존된 로그 파일 내의 모든 IP 주소는 90일 이내에 난독화됩니다.

## 데이터 분할 {#data-partitioning}

Processes that help protect data owned by individual clients.

**** 트레이트 데이터 분할: 데이터(트레이트, ID 등) is partitioned by client. This helps prevent accidental information exposure between different clients. For example, trait data in cookies is partitioned by customer and stored in a client-specific sub-domain. It cannot be read or used accidentally by another Audience Manager client. Furthermore, trait data stored in the  is also partitioned by customer. [!UICONTROL Profile Cache Servers (PCS)] This prevents other clients from accidentally using your data in an event call or other request.

**** 보고서의 데이터 분할: 클라이언트 ID는 모든 보고 테이블에서 식별 키의 일부이며 보고서 쿼리는 ID로 필터링됩니다. 이렇게 하면 다른 Audience Manager 고객의 보고서에 데이터가 표시되지 않도록 할 수 있습니다.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager supports two main methods of transferring S2S on-boarded data files to our systems:

두 방법 모두 Adobe 고객과 파트너 데이터의 보안을 고려하여 설계되었으며, 데이터는 시스템과 Adobe 시스템 간에 이동됩니다.

**** SFTP:SFTP 옵션의 경우 대부분의 고객은 SSH(Secure Shell) 프로토콜을 사용하는 SFTP(Secure FTP) 프로토콜을 통해 파일을 배달하도록 선택합니다. 이 방법을 사용하면 고객의 시스템과 Adobe 시스템 간에 파일을 암호화할 수 있습니다. 각 고객에 대해 SFTP 서버에 해당 시스템의 사용자 계정에 연결된 비공개 드롭 박스 위치를 만듭니다. 고객의 자격 증명과 권한이 있는 내부 시스템 사용자만 비공개 드롭 박스 위치에 액세스할 수 있습니다. 이 감옥은 다른 고객에게는 결코 접근할 수 없다.

**** HTTPS를 통한 Amazon Web Services S3:S3 배달 옵션의 경우 모든 고객이 파일 전송에 HTTPS 암호화 방법을 사용하도록 S3 클라이언트를 구성하는 것이 좋습니다(기본값이 아니므로 명시적으로 구성해야 함). HTTPS 옵션은 s3cmd 명령줄 도구와 모든 주요 프로그래밍 언어에서 사용할 수 있는 S3 라이브러리 모두에서 지원됩니다. 이 HTTPS 옵션을 활성화하면 Adobe 시스템으로 이동하는 동안 고객의 데이터가 암호화됩니다. 각 고객에 대해, Adobe는 고객의 자격 증명과 내부 시스템 사용자의 자격 증명으로만 액세스할 수 있는 별도의 S3 버킷 하위 디렉토리를 만듭니다.

데이터 파일에 PGP 암호화를 추가하려면 인바운드 데이터 [유형에 대한 파일 PGP 암호화를 참조하십시오](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## 이스케이프하여 데이터 보호 {#escaping-data}

XSS(Cross-Site Scripting) 등에 대해 보안을 유지하기 위해 나가는 데이터를 escape하지 [!DNL Audience Manager] 않습니다. 들어오는 데이터를 escape하는 것은 클라이언트의 책임입니다.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] 는 쿠키 하이재킹 및 프로토콜 다운그레이드 공격으로부터 보호하는 데 도움이 되는 업계 전반의 웹 보안 메커니즘입니다.

이 정책은 특정 도메인에 대한 보안 [!DNL HTTPS] 호출이 수행되면 해당 도메인에 대한 후속 비보안 호출([!DNL HTTP])이 허용되지 않도록 웹 브라우저에 지시합니다. 이 기능은 공격자가 안전하지 않은 호출을 다운그레이드하려고 할 수 있는 중간 [!DNL HTTPS] 공격으로부터 [!DNL HTTP] 보호합니다."

이 정책은 클라이언트와 Adobe Edge Server 간의 데이터 보안을 [개선합니다](../../reference/system-components/components-edge.md) .

### 예 {#hsts-example}

도메인이 `yourcompany.demdex.com` 을 통해 [!DNL DCS] 트래픽을 전송한다고 가정해 봅시다 [!DNL HTTP]. [!DNL HSTS] upgrades the calls to use  instead, and all subsequent  calls coming from  will use  instead of .[!DNL HTTPS][!DNL DCS]`yourcompany.demdex.com`[!DNL HTTPS][!DNL HTTP]

HSTS [에 대한 자세한 내용은 HTTP Strict Transport Security](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) - Wikipedia를 참조하십시오.
