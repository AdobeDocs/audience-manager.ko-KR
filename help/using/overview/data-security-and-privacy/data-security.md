---
description: Audience Manager에서는 데이터 보안 및 개인 정보 보호를 매우 중요하게 생각합니다. Adobe는 시스템의 보안을 유지하고 중요한 데이터를 보호하기 위해 노력하고 있습니다.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Data Security in Audience Manager
solution: Audience Manager
title: Audience Manager의 데이터 보안
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
feature: Data Governance & Privacy
exl-id: 94b70250-dca3-4c50-b4dd-bc37178a587e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 92%

---

# Audience Manager의 데이터 보안 {#data-security}

Audience Manager에서는 데이터 보안 및 개인 정보 보호를 매우 중요하게 생각합니다. Adobe는 시스템의 보안을 유지하고 중요한 데이터를 보호하기 위해 노력하고 있습니다.

Audience Manager 보안 방침에는 Adobe 시스템과 귀하의 중요한 데이터를 보호하기 위해 설계된 외부 및 내부 감사, 활동 로깅, 교육 및 기타 절차가 포함됩니다. Adobe는 안전한 제품을 통해 Adobe에 대한 고객의 신뢰가 만들어지고 유지된다고 믿습니다.

Audience Manager에서는 세 가지 주요 카테고리의 보안에 대해 생각합니다.

| 보안 유형 | 지원 대상 |
|---|---|
| **정보 보안** | 엔터프라이즈 수준 인증, 암호화 및 데이터 저장 방식 |
| **데이터 누출/투명성** | 데이터 누출을 구성하거나 이에 기여하는 온사이트 활동에 대한 깊고 실행 가능한 통찰력 |
| **프로세스/정책 개선 사항** | 클라이언트(개인 정보 보호 및 데이터 보안에 대한 업계 우수 사례를 사용하여 작업) |

## 시스템, 교육 및 액세스 {#systems-training-access}

시스템 및 데이터의 보안을 유지하는 프로세스입니다.

**외부 보안 유효성 확인:**  Audience Manager는 매년 및 분기별로 보안을 테스트합니다.

* 연간: 1년에 한 번, Audience Manager는 독립적인 타사에서 실시하는 전체 침투 테스트를 받습니다. 테스트는 애플리케이션의 보안 취약점을 식별하도록 설계됩니다. 테스트에는 사이트 간 스크립팅, SQL 주입, 양식 매개 변수 조작 및 기타 애플리케이션 수준 취약점에 대한 검사가 포함됩니다.
* 분기별: 각 분기에 한 번, 내부팀이 보안 취약점을 확인합니다. 이러한 테스트에는 열린 포트 및 서비스 취약점에 대한 네트워크 검사가 포함됩니다.

**시스템 보안:**  데이터를 안전하게 보호하고 보안을 유지하기 위해 Audience Manager에서는

* 권한 없는 IP 주소로부터의 요청을 차단합니다.
* 방화벽, VPN 및 가상 사설 클라우드 저장소 뒤의 데이터를 보호합니다.
* 트리거 기반의 감사 기록을 통해 고객 및 제어 정보 데이터베이스의 변경 사항을 추적합니다. 이러한 로그는 변경을 수행한 사용자 ID 및 IP 주소를 포함하여 데이터베이스 수준에서 모든 변경 사항을 추적합니다.

**보안 자산:**  Audience Manager에는 방화벽 및 침입 탐지 장치를 모니터링하는 전담 네트워크 운영팀이 있습니다. 핵심 직원만 Adobe 보안 기술과 데이터에 액세스할 수 있습니다.

**보안 교육:**  내부적으로, 보안에 대한 Adobe의 노력은 제품 개발자에게까지 확장됩니다. Adobe는 개발자에게 보안 애플리케이션 및 서비스를 구축하는 방법에 대한 공식 교육을 제공합니다.

**보안 액세스:**  Audience Manager에서는 시스템 로그온에 강력한 암호를 요구합니다. 자세한 내용은 [암호 요구 사항](../../reference/password-requirements.md)을 참조하십시오.

## 개인 정보 및 PII(개인 식별 정보) {#pii}

개인 정보를 안전하게 유지하는 데 도움이 되는 프로세스입니다. 개인 정보 보호에 대해 자세히 알려면 [Adobe 개인 정보 보호 센터](https://www.adobe.com/kr/privacy/advertising-services.html)를 참조하십시오.

**PII 데이터:**  Audience Manager는 고객 및 데이터 파트너가 PII 정보를 Adobe 시스템에 보내는 것을 계약상 금지하고 있습니다. 또한 UUID(고유 사용자 ID)는 PII 데이터를 ID 생성 알고리즘의 일부로 포함하거나 사용하지 않습니다.

**IP 주소:**  Audience Manager는 IP 주소를 수집합니다. IP 주소는 데이터 처리 및 로그 수집 프로세스에서 사용되며 지리적/위치 조회 및 타겟팅에도 필요합니다. 또한 보존된 로그 파일 내의 모든 IP 주소는 90일 이내에 난독화됩니다.

## 데이터 분할 {#data-partitioning}

개별 클라이언트가 소유한 데이터를 보호하는 데 도움이 되는 프로세스입니다.

**트레이트 데이터 분할:** 데이터([!UICONTROL traits], ID 등) 클라이언트별로 분할되는데 이것은 서로 다른 클라이언트 간의 우발적 정보 노출을 방지할 수 있습니다. 예를 들어 쿠키의 트레이트 데이터는 고객별로 분할되고 클라이언트별 하위 도메인에 저장됩니다. 이러한 데이터는 다른 Audience Manager 클라이언트가 실수로 읽거나 사용할 수 없습니다. 또한, [!UICONTROL Profile Cache Servers (PCS)]에 저장된 트레이트 데이터는 고객별로 분할됩니다. 따라서 다른 클라이언트가 이벤트 호출이나 기타 요청에서 데이터를 실수로 사용하지 않게 됩니다.

**보고서의 데이터 분할:**  클라이언트 ID는 모든 보고 테이블에 있는 식별 키의 일부이며 보고서 쿼리는 ID로 필터링됩니다. 이렇게 하면 다른 Audience Manager 고객의 보고서에 데이터가 표시되지 않도록 할 수 있습니다.

## 인바운드 서버 간(S2S) 전송 {#inbound-s2s}

Adobe Audience Manager는 S2S 온보딩된 데이터 파일을 Adobe 시스템에 전송하는 두 가지 주요 방법을 지원합니다.

두 방법 모두 고객 및 파트너 시스템과 Adobe 시스템 간 데이터 이동 중 고객 및 파트너 데이터의 보안을 염두에 두고 설계되었습니다.

**SFTP:** SFTP 옵션의 경우 대부분의 고객은 SSH(Secure Shell) 프로토콜을 사용하는 SFTP(Secure FTP) 프로토콜을 통해 파일을 전달하도록 선택합니다. 이 방법은 파일이 고객 시스템과 Adobe 시스템 간을 이동하는 동안 암호화되어 있도록 해줍니다. Adobe는 SFTP 서버에 감옥 드롭박스 위치를 만드는데, 이 위치는 각 고객에 대해 해당 시스템의 사용자 계정에 연결되어 있습니다. 고객의 자격 증명과 권한이 있는 내부 시스템 사용자만 이 감옥 드롭박스 위치에 액세스할 수 있습니다. 다른 고객은 이 감옥에 절대 액세스할 수 없습니다.

**[!UICONTROL Amazon Web Services S3]via HTTPS:** S3 배달 옵션의 경우 모든 고객이 파일 전송에 HTTPS 암호화 방법을 사용하도록 S3 클라이언트를 구성하는 것이 좋습니다(기본값이 아니므로 명시적으로 구성해야 함). HTTPS 옵션은 s3cmd 명령줄 도구와 모든 주요 프로그래밍 언어로 사용할 수 있는 S3 라이브러리 모두에서 지원됩니다. 이 HTTPS 옵션을 활성화하면 고객의 데이터가 Adobe 시스템으로 이동하는 동안 암호화되어 있습니다. Adobe에서는 각 고객에 대해 해당 고객의 자격 증명과 내부 시스템 사용자의 자격 증명으로만 액세스할 수 있는 별도의 S3 버킷 하위 디렉토리를 만듭니다.

데이터 파일에 PGP 암호화를 추가하려면 [인바운드 데이터 유형에 대한 파일 PGP 암호화](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)를 참조하십시오.

## 이스케이프 처리로 데이터 보호 {#escaping-data}

[!DNL Audience Manager]는 XSS(사이트 간 스크립팅) 등으로부터 발신 데이터를 보호하기 위해 이 데이터를 이스케이프 처리하지 않습니다. 들어오는 데이터를 이스케이프 처리하는 것은 클라이언트의 책임입니다.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)]는 쿠키 하이재킹 및 프로토콜 다운그레이드 공격으로부터 보호하는 업계 범위의 웹 보안 메커니즘입니다.

이 정책은 주어진 도메인에 대해 보안 [!DNL HTTPS] 호출이 수행되면 해당 도메인에 대한 후속 비보안 호출([!DNL HTTP])이 허용되지 않도록 웹 브라우저에 지시합니다. 따라서 공격자가 [!DNL HTTPS] 호출을 보안 처리가 안 된 [!DNL HTTP] 호출로 다운그레이드하려 시도할 수 있는 상황에서 중간자 공격으로부터 보호됩니다.

이 정책은 클라이언트와 Adobe [Edge](../../reference/system-components/components-edge.md) 서버 간의 데이터 보안을 개선합니다.

### 예 {#hsts-example}

`yourcompany.demdex.com` 도메인이 [!DNL HTTP]을(를) 통해 [!DNL DCS]에 트래픽을 보낸다고 가정해 보겠습니다. [!DNL HSTS]에서는 대신 [!DNL HTTPS]를 사용하도록 호출을 업그레이드하고 `yourcompany.demdex.com`에서 오는 모든 후속 [!DNL DCS] 호출은 [!DNL HTTP] 대신 [!DNL HTTPS]를 사용하게 됩니다.

HSTS에 대한 자세한 내용은 [HTTP Strict Transport Security - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)를 참조하십시오.
