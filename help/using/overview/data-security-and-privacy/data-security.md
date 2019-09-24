---
description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: 데이터 보안
solution: Audience Manager
title: 데이터 보안
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 9e1abb305c66a4adf6a42a7873144222491692f9

---


# 데이터 보안 {#data-security}

Audience Manager는 데이터 보안 및 개인 정보를 매우 중요시합니다. Adobe는 시스템의 보안을 유지하고 중요한 데이터를 보호하기 위해 노력하고 있습니다.

Adobe Audience Manager의 보안 관행은 외부 및 내부 감사, 활동 로깅, 트레이닝 및 Adobe 시스템과 중요한 데이터를 보호하기 위해 고안된 기타 절차를 포함합니다. Adobe는 안전한 제품을 통해 고객이 신뢰할 수 있는 제품을 구축하고 유지 관리할 수 있다고 믿습니다.

Adobe Audience Manager에서는 세 가지 주요 범주의 보안에 대해 살펴봅니다.

| 보안 유형 | 다음을 지원합니다. |
|---|---|
| **정보 보안** | 엔터프라이즈급 인증, 암호화 및 데이터 스토리지 방식 |
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

**** Security Assets:  Audience Manager has a dedicated network operations team that monitors firewalls and intrusion-detection devices. Only key personnel have access to our security technology and data.

**** Security Training:  Internally, our commitment to security extends to developers who work on our product. Adobe provides formal training to developers on how to build secure applications and services.

**** Secure Access:  Audience Manager requires strong passwords to log on to the system. See password requirements.[](../../reference/password-requirements.md)

## Privacy and Personally Identifiable Information (PII) {#pii}

Processes that help keep personal information safe. For additional privacy information, see the Adobe Privacy Center.[](https://www.adobe.com/privacy/advertising-services.html)

**** PII 데이터: Adobe Audience Manager는 고객 및 데이터 파트너가 PII 정보를 Adobe 시스템으로 보내는 것을 금지합니다. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP Addresses:  Audience Manager does collect IP addresses. IP addresses are used in data-processing and log-aggregation processes. They are also required for geographic/location look-ups and targeting. Additionally, all IP addresses within retained log files are obfuscated within 90 days.

## Data Partitioning {#data-partitioning}

개별 클라이언트가 소유한 데이터를 보호하는 프로세스입니다.

**** 트레이트 데이터 분할: 데이터(트레이트, ID 등) 는 클라이언트에 의해 분할됩니다. 이렇게 하면 다른 클라이언트 간에 우발적인 정보 노출을 방지할 수 있습니다. 예를 들어 쿠키의 특성 데이터는 고객이 분할하고 클라이언트별 하위 도메인에 저장됩니다. 다른 Audience Manager 클라이언트에서 이를 읽거나 실수로 사용할 수 없습니다. 또한, 에 저장된 트레이트 데이터도 [!UICONTROL Profile Cache Servers (PCS)] 고객이 분할합니다. 이렇게 하면 다른 클라이언트가 이벤트 호출 또는 기타 요청에서 데이터를 실수로 사용하지 못하도록 합니다.

**** 보고서의 데이터 분할: 클라이언트 ID는 모든 보고 테이블에서 식별 키의 일부이며 보고서 쿼리는 ID로 필터링됩니다. 이렇게 하면 다른 Audience Manager 고객의 보고서에 데이터가 표시되지 않도록 할 수 있습니다.

## S2S(Inbound Server-to-Server) 전송 {#inbound-s2s}

Adobe Audience Manager는 S2S 온보드 데이터 파일을 Adobe 시스템으로 전송하는 두 가지 주요 방법을 지원합니다.

두 방법 모두 Adobe 고객과 파트너 데이터의 보안을 고려하여 설계되었으며, 데이터는 시스템과 Adobe 시스템 간에 이동됩니다.

**** SFTP:SFTP 옵션의 경우 대부분의 고객은 SSH(Secure Shell) 프로토콜을 사용하는 SFTP(Secure FTP) 프로토콜을 통해 파일을 배달하도록 선택합니다. 이 방법을 사용하면 고객의 시스템과 Adobe 시스템 간에 파일을 암호화할 수 있습니다. 각 고객에 대해 SFTP 서버에 해당 시스템의 사용자 계정에 연결된 비공개 드롭 박스 위치를 만듭니다. 고객의 자격 증명과 권한이 있는 내부 시스템 사용자만 비공개 드롭 박스 위치에 액세스할 수 있습니다. 이 감옥은 다른 고객에게는 결코 접근할 수 없다.

**** HTTPS를 통한 Amazon Web Services S3:S3 배달 옵션의 경우 모든 고객이 파일 전송에 HTTPS 암호화 방법을 사용하도록 S3 클라이언트를 구성하는 것이 좋습니다(기본값이 아니므로 명시적으로 구성해야 함). HTTPS 옵션은 s3cmd 명령줄 도구와 모든 주요 프로그래밍 언어에서 사용할 수 있는 S3 라이브러리 모두에서 지원됩니다. 이 HTTPS 옵션을 활성화하면 Adobe 시스템으로 이동하는 동안 고객의 데이터가 암호화됩니다. 각 고객에 대해, Adobe는 고객의 자격 증명과 내부 시스템 사용자의 자격 증명으로만 액세스할 수 있는 별도의 S3 버킷 하위 디렉토리를 만듭니다.

데이터 파일에 PGP 암호화를 추가하려면 인바운드 데이터 [유형에 대한 파일 PGP 암호화를 참조하십시오](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## 이스케이프하여 데이터 보호 {#escaping-data}

XSS(Cross-Site Scripting) 등에 대해 보안을 유지하기 위해 나가는 데이터를 escape하지 [!DNL Audience Manager] 않습니다. 들어오는 데이터를 escape하는 것은 클라이언트의 책임입니다.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] 는 [!DNL HTTP] 트래픽을 허용하지 않고 모든 [!DNL HTTP] 트래픽을 로 투명하게 업그레이드하여 쿠키 하이재킹 및 프로토콜 다운그레이드 공격으로부터 보호하는 웹 보안 정책 메커니즘입니다 [!DNL HTTPS].

이 정책은 클라이언트와 Adobe Edge Server 간의 데이터 보안을 향상시킵니다.

### 예 {#hsts-example}

When trying to access ,  will automatically upgrade the request to  , in case the browser doesn’t automatically request the  domain.`http://bank.demdex.com`[!DNL HSTS]`https://bank.demdex.com`[!DNL HTTPS]

See HTTP Strict Transport Security - Wikipedia for more information about HSTS.[](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
