---
description: Adobe Audience Manager는 데이터 보안과 개인 정보를 매우 중요하게 생각합니다. Adobe는 시스템을 안전하게 보호하고 귀중한 데이터를 보호합니다.
seo-description: Adobe Audience Manager는 데이터 보안과 개인 정보를 매우 중요하게 생각합니다. Adobe는 시스템을 안전하게 보호하고 귀중한 데이터를 보호합니다.
seo-title: 데이터 보안
solution: Audience Manager
title: 데이터 보안
uuid: 33 AD 19 CA -4690-4 D 97-853 B -1882 D 7 D 4 AC 01
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Security {#data-security}

Adobe Audience Manager는 데이터 보안과 개인 정보를 매우 중요하게 생각합니다. Adobe는 시스템을 안전하게 보호하고 귀중한 데이터를 보호합니다.

Audience Manager 보안 관행에 외부 및 내부 감사, 활동 로깅, 트레이닝, 그리고 시스템 및 귀중한 데이터를 보호하기 위해 고안된 기타 절차가 포함됩니다. 보안 제품은 신뢰할 수 있는 고객을 구축하고 유지 관리하는 데 도움이 됩니다.

Audience Manager 에서는 세 가지 주요 카테고리의 보안에 대해 생각합니다.

| 보안 유형 | Provides support for |
|---|---|
| **정보 보안** | 엔터프라이즈급 인증, 암호화 및 데이터 스토리지 작업 |
| **데이터 누수/투명도** | 데이터 누출을 구성하는 사이트 내 활동에 대한 심도 있고 실행 가능한 통찰력 |
| **프로세스/정책 개선 사항** | 클라이언트, 개인 정보 보호 및 데이터 보안에 대한 업계 모범 사례 |

## Systems, Training, and Access {#systems-training-access}

시스템 및 데이터의 보안을 유지하는 프로세스

**외부 보안 유효성 검사:** Audience Manager는 연간 및 분기별 기준으로 보안을 테스트합니다.

* 연간: Audience Manager는 1 년 동안 독립적인 타사 회사에서 실시한 전체 침투 테스트를 받습니다. 테스트는 애플리케이션의 보안 취약점을 확인하도록 설계되었습니다. 이 테스트에는 교차 사이트 스크립팅, SQL 주입, 양식 매개 변수 조작 및 기타 애플리케이션 수준의 취약성 검사가 포함됩니다.
* 분기별: 각 분기마다 내부 팀은 보안 취약점을 확인합니다. 이러한 테스트에는 개방형 포트 및 서비스 취약점에 대한 네트워크가 포함됩니다.

**시스템 보안:** 데이터를 안전하고 안전하게 유지하려면 Audience Manager:

* 인증되지 않은 IP 주소의 요청을 차단합니다.
* 방화벽, VPNS 및 가상 비공개 클라우드 스토리지를 통해 데이터를 보호합니다.
* 트리거 기반의 감사 로깅으로 고객 및 제어 정보 데이터베이스의 변경 사항을 추적할 수 있습니다. 이러한 로그는 변경이 이루어진 사용자 ID 및 IP 주소를 포함하여 데이터베이스 수준에서 모든 변경을 추적합니다.

**보안 에셋:** Audience Manager 에는 방화벽 및 침입 감지 디바이스를 모니터링하는 전용 네트워크 운영 팀이 있습니다. 주요 직원만이 Adobe의 보안 기술과 데이터에 액세스할 수 있습니다.

**보안 트레이닝:** 내부적으로 Adobe의 보안 노력은 Adobe 제품을 사용하는 개발자에게 확대됩니다. Adobe는 개발자가 보안 애플리케이션 및 서비스를 구축하는 방법에 대한 공식 교육을 제공합니다.

**보안 액세스:** Audience Manager에서 시스템에 로그온하려면 강력한 암호가 필요합니다. [암호 요구 사항을 참조하십시오](../../reference/password-requirements.md).

## Privacy and Personally Identifiable Information (PII) {#pii}

개인화된 정보를 안전하게 관리하는 프로세스 For additional privacy information, see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**PII 데이터:** Audience Manager는 고객과 데이터 파트너가 PII 정보를 시스템에 보내지 못하도록 계약상으로 금지합니다. 또한 고유 사용자 ID (UUID) 는 ID 생성 알고리즘의 일부로 PII 데이터를 포함하거나 사용하지 않습니다.

**IP 주소:** Audience Manager에서 IP 주소를 수집합니다. IP 주소는 데이터 처리 및 로그 집계 프로세스에서 사용됩니다. 지리적/위치 조회 및 타깃팅을 위해서도 필요합니다. 또한 보존된 로그 파일 내의 모든 IP 주소는 90 일 이내에 난독화됩니다.

## Data Partitioning {#data-partitioning}

개별 클라이언트가 소유한 데이터를 보호하는 프로세스.

**특성 데이터 분할:** 귀하의 데이터 (트레이트, ID 등) 는 클라이언트에 의해 구획됩니다. 따라서 다른 클라이언트 간의 우발적인 정보 노출을 방지할 수 있습니다. 예를 들어 쿠키에 있는 트레이트 데이터는 고객별로 구분되어 클라이언트별 하위 도메인에 저장됩니다. 다른 Audience Manager 클라이언트에서 실수로 읽거나 사용할 수 없습니다. Furthermore, trait data stored in the [!UICONTROL Profile Cache Servers (PCS)] is also partitioned by customer. 이렇게 하면 다른 클라이언트가 이벤트 호출 또는 기타 요청에서 실수로 데이터를 사용하는 것을 방지할 수 있습니다.

**보고서에서 데이터 분할:** 클라이언트 ID는 모든 보고 테이블의 식별 키에 속하며 보고서 쿼리는 ID로 필터링됩니다. 이렇게 하면 다른 Audience Manager 고객의 보고서에 데이터가 표시되지 않도록 할 수 있습니다.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager는 S 2 S 온보딩 데이터 파일을 시스템으로 전송하는 두 가지 주요 방법을 지원합니다.

두 방법 모두 시스템 및 시스템 시스템 간에 데이터를 비행하는 동안 고객 데이터와 파트너 데이터의 보안을 염두에 두고 설계되었습니다.

**Sftp:** SFTP 옵션의 경우 대부분의 고객은 보안 셸 (ssh) 프로토콜을 사용하는 SFTP (Secure FTP) 프로토콜을 통해 파일을 전달하도록 선택합니다. 이 방법을 사용하면 고객의 시스템과 Adobe 시스템 간의 기내 이동 중에도 파일이 암호화됩니다. 각 고객에게 해당 시스템의 사용자 계정과 연결되어 있는 Sftp 서버에서 징역형 드롭 박스 위치를 만듭니다. 고객의 자격 증명과 권한이 부여된 내부 시스템 사용자만 이 수감된 드롭 박스 위치에 액세스할 수 있습니다. 이 감옥은 다른 고객에게 접근할 수 없습니다.

**HTTPS를 통한 Amazon 웹 서비스 S 3:** S 3 전달 옵션의 경우 모든 고객이 파일 전송에 HTTPS 암호화 방법을 사용하도록 구성하는 것이 좋습니다 (기본값이 아니므로 명시적으로 구성해야 함). HTTPS 옵션은 S 3 Cmd 명령줄 도구와 모든 주요 프로그래밍 언어에서 사용할 수 있는 S 3 라이브러리를 통해 지원됩니다. 이 HTTPS 옵션을 사용할 수 있게 되면, 고객 데이터가 시스템에 있는 동안 암호화됩니다. 각 고객에 대해, 우리는 해당 고객의 자격 증명과 내부 시스템 사용자의 인증서만 액세스할 수 있는 별도의 S 3 버킷 하위 디렉토리를 만듭니다.

To add PGP encryption to your data files, see [File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protecting Data by Escaping {#escaping-data}

Note that [!DNL Audience Manager] does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. 들어오는 데이터를 이스케이프 처리하는 것은 클라이언트의 책임입니다.
