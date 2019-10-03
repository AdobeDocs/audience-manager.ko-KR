---
description: Audience Manager 통합 및 소비자 개인 정보 보호 및 옵트아웃 절차와 관련하여 일반적으로 수용되는 우수 사례 준수 등에 대해 설명합니다.
seo-description: Audience Manager 통합 및 소비자 개인 정보 보호 및 옵트아웃 절차와 관련하여 일반적으로 수용되는 우수 사례 준수 등에 대해 설명합니다.
seo-title: 데이터 개인 정보
solution: Audience Manager
title: 데이터 개인 정보
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# 데이터 개인 정보{#data-privacy}

Audience Manager 통합 및 소비자 개인 정보 보호 및 옵트아웃 절차와 관련하여 일반적으로 수용되는 우수 사례 준수 등에 대해 설명합니다.

## 데이터 개인 정보{#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Consumer Privacy Protection {#consumer-privacy-protection}

Audience Manager recognizes the implicit pact between consumers and the online brands with which they interact. Both parties benefit from the transparent exchange of anonymous data elements:

* 소비자는 개인화된 컨텐츠, 할인 제품 및 간소화된 사용자 경험을 제공합니다.
* Brands receive vital revenue streams supporting multiple online business models.

In our continuing support of this model, Audience Manager remains committed to providing transparency and control to consumers, and meeting or exceeding the Online Behavioral Advertising (OBA) Self-Regulatory Principles.

## Opt-Out Management {#opt-out-management}

The opt-out documentation has been extended and moved to a separate part of our documentation. See Opt-out Management.[](../../overview/data-security-and-privacy/opt-out-management.md)

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

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** IP Obfuscation Methodology: Following the principles of "Privacy By Design", Adobe Audience Manager allows customers to enable  obfuscation from the UI, either globally across all geographic regions or for specific countries. [!DNL IP] 이 설정을 활성화하면 Audience Manager로 주소를 인제스트할 때 [!DNL IP] 주소의 마지막 8진수(마지막 부분) [!DNL IP] 가 즉시 삭제됩니다. Audience Manager discards this part of the  address prior to processing (including before any optional geographic lookup or logging of the  address). [!DNL IP][!DNL IP] 예:

* : `255.255.255.255`
* 후: `255.255.255.0`

>[!NOTE]
>
>See IP Address Obfuscation to learn how to enable  address obfuscation in the Audience Manager UI.[](/help/using/features/administration/ip-obfuscation.md)[!DNL IP]

Watch the video below to understand how  address obfuscation works in Audience Manager.[!DNL IP]

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=kor)

**** Geographic Segmentation: If you enable  address obfuscation, the remaining octets of the  address can still be used for geo-segmentation and reporting in Audience Manager. [!DNL IP][!DNL IP] If you do not enable  address obfuscation, Audience Manager uses the full  address. [!DNL IP][!DNL IP] 두 경우 모두 지리적 영역별로 [!DNL IP] 위치를 식별할 수 있지만, 난독화를 사용하는 경우 약간의 정밀도가 손실되는 지리적 세그멘테이션 기능을 사용할 [!DNL IP] 수 있습니다. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. 지역 및 국가 수준 정보를 획득하는 것은 약간 영향을 받아야 합니다. 지리적 세그멘테이션 데이터는 도시 수준이나 우편 번호 수준에만 세분화되며 개별 수준에는 해당되지 않습니다. 지리적 [타깃팅](/help/using/features/traits/trait-geotarget-keys.md) 및 지리적 변수를 사용하여 트레이트를 설정하는 방법에 대한 자세한 내용을 살펴보십시오.

## 관련 개념 {#related-concepts}

* [옵트아웃 관리](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [개인 정보 및 데이터 유지 FAQ](/help/using/faq/faq-privacy.md)