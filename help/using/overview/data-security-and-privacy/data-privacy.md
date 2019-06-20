---
description: Audience Manager 통합과 소비자 개인 정보 보호 및 옵트아웃 절차와 관련하여 일반적으로 수용되는 우수 사례를 준수하고 있습니다.
seo-description: Audience Manager 통합과 소비자 개인 정보 보호 및 옵트아웃 절차와 관련하여 일반적으로 수용되는 우수 사례를 준수하고 있습니다.
seo-title: 데이터 개인 정보
solution: Audience Manager
title: 데이터 개인 정보
uuid: 865 E 7 B 4 E-FEE 1-4 FA 4-8035-1595 FC 77 CD 96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

---


# 데이터 개인 정보{#data-privacy}

Audience Manager 통합과 소비자 개인 정보 보호 및 옵트아웃 절차와 관련하여 일반적으로 수용되는 우수 사례를 준수하고 있습니다.

## 데이터 개인 정보{#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Consumer Privacy Protection {#consumer-privacy-protection}

Audience Manager는 고객과 온라인 브랜드 간의 암묵적 합의를 인식합니다. 양 당사자는 익명의 데이터 요소를 교환함으로써 이점을 얻을 수 있습니다.

* 소비자는 개인화된 컨텐츠, 할인된 제품 제안 및 간소화된 사용자 경험을 받습니다.
* 기업은 다양한 온라인 비즈니스 모델을 지원하는 중요한 수익원을 받게 됩니다.

이 모델에 대한 지속적인 지원을 통해 Audience Manager는 소비자에게 투명성과 제어를 제공하고 OBA (온라인 행동 광고) 자율 규제 원칙을 준수하기 위해 끊임없이 노력할 것입니다.

## Opt-Out Management {#opt-out-management}

옵트아웃 문서는 확장되었으며 문서의 일부로 이동되었습니다. [옵트아웃 관리를 참조하십시오](../../overview/data-security-and-privacy/opt-out-management.md).

<!-- 

<p>  </p>
<table id="table_A1FF33B328BD451FAFF6C6B8422F928B"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="2.74*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Opt-Out For </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
    <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page</a> provides 1-click features that let you control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section</a> of the Privacy Choices page. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Browsers that do not support third-party cookies </p> </td> 
    <td colname="col2"> <p>See <a href="../../features/declared-ids.md#declared-id-targeting"> Declared ID Targeting</a>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Mobile devices </p> </td> 
    <td colname="col2"> <p>See the opt-out and privacy settings for: </p> <p> 
      <ul id="ul_86EFAB879215403D937B5148C26A41D9"> 
       <li id="li_C0B544E8F4FE473B94A5436D3A60BDB1"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android devices</a> </li> 
       <li id="li_26C787BAB729499A9FEDF055E9AB0637"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS devices</a> </li> 
      </ul> </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

고객의 웹 사이트에 대한 방문자의 IP 주소는 이 IP 주소가 저장되어 있을 수 있는 Adobe DPC(Data Processing Center)로 전송됩니다. 방문자에 대한 네트워크 구성에 따라, IP 주소가 반드시 방문자의 컴퓨터의 IP 주소를 나타내지는 않을 수 있습니다. 예를 들어 IP 주소가 NAT(Network Address Translation) 방화벽, HTTP 프록시 또는 인터넷 게이트웨이의 외부 IP 주소일 수 있습니다.

**유사 IP 탐지 방법론:** &quot; 개인 정보 보호 중심의 설계 &quot;의 원칙을 따르는 Adobe Audience Manager를 사용하면 모든 지리적 지역 또는 특정 국가에서 전 세계적으로 IP 난독화를 활성화할 수 있습니다. 이 설정을 활성화하면 IP 주소가 Audience Manager로 인제스트되면 IP 주소의 마지막 옥텟 (마지막 부분) 이 즉시 무시됩니다. Audience Manager는 처리하기 전에 IP 주소의 이 부분을 삭제합니다 (선택 사항인 지리적 조회 또는 IP 주소의 기록 전). 예:

* : `255.255.255.255`
* 후: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) to learn how to enable IP address obfuscation in the Audience Manager UI.

**지리 특성:** IP 주소 난독화를 활성화하는 경우, 나머지 IP 주소는 여전히 Audience Manager의 지리 특성 및 보고 기능에 사용할 수 있습니다. IP 주소 난독화를 활성화하지 않으면 Audience Manager에서 전체 IP 주소를 사용합니다. 지리적 세그먼테이션 기능을 사용하면 두 경우 모두 지리적 위치별로 IP 위치를 식별할 수 있지만 IP 난독화가 사용될 때 약간의 정밀도를 잃게 됩니다. 도시 수준의 정보를 획득하는 것은 IP 주소 난독화의 영향을 크게 받을 수 있습니다. 지역 및 국가 수준 정보를 얻는 것은 약간 영향을 받습니다. 지리 특성 데이터는 개별 수준이 아니라 도시 수준이나 우편 번호 수준으로만 세분화됩니다. Read more about [geo-targeting](/help/using/features/traits/trait-geotarget-keys.md) and how to set up traits with geographic variables.

## 관련 개념 {#related-concepts}

* [옵트아웃 관리](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [개인 정보 및 데이터 유지 FAQ](/help/using/faq/faq-privacy.md)