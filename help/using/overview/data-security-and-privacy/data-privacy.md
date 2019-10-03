---
description: Audience Manager 통합 및 소비자 개인 정보 보호 및 옵트아웃 절차와 관련하여 일반적으로 수용되는 우수 사례 준수 등에 대해 설명합니다.
seo-description: Audience Manager 통합 및 소비자 개인 정보 보호 및 옵트아웃 절차와 관련하여 일반적으로 수용되는 우수 사례 준수 등에 대해 설명합니다.
seo-title: 데이터 개인 정보
solution: Audience Manager
title: 데이터 개인 정보
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# 데이터 개인 정보{#data-privacy}

Audience Manager 통합 및 소비자 개인 정보 보호 및 옵트아웃 절차와 관련하여 일반적으로 수용되는 우수 사례 준수 등에 대해 설명합니다.

## 데이터 개인 정보{#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## 개인 정보 보호 {#consumer-privacy-protection}

Adobe Audience Manager는 고객과 인터랙션하는 온라인 브랜드 간의 암묵적인 계약을 인식합니다. 두 업체 모두 익명의 데이터 요소를 투명하게 교환함으로써 혜택을 누릴 수 있습니다.

* 소비자는 개인화된 컨텐츠, 할인 제품 및 간소화된 사용자 경험을 제공합니다.
* 브랜드 기업은 다양한 온라인 비즈니스 모델을 지원하는 중요한 수익원을 창출할 수 있습니다.

이 모델을 지속적으로 지원하는 Adobe의 경우 Audience Manager는 소비자에게 투명성과 제어를 제공하고 OBA(Online Behavioral Advertising) 자율 규제 원칙을 준수하기 위해 최선의 노력을 다하고 있습니다.

## 옵트아웃 관리 {#opt-out-management}

옵트아웃 설명서가 연장되어 설명서의 별도 부분으로 이동되었습니다. 옵트아웃 [관리를 참조하십시오](../../overview/data-security-and-privacy/opt-out-management.md).

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

## IP 주소 및 IP 주소 난독화 수집 {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** IP 난독화 방법론:"Privacy By Design"의 원칙에 따라 Adobe Audience Manager를 사용하면 모든 지리적 지역 또는 특정 국가에서 UI [!DNL IP] 의 난독화를 활성화할 수 있습니다. 이 설정을 활성화하면 Audience Manager로 주소를 인제스트할 때 [!DNL IP] 주소의 마지막 8진수(마지막 부분) [!DNL IP] 가 즉시 삭제됩니다. Audience Manager는 처리 전(선택 사항인 지리적 조회 또는 주소의 로깅 전에 포함) 주소의 이 부분을 [!DNL IP] [!DNL IP] 삭제합니다. 예:

* : `255.255.255.255`
* 후: `255.255.255.0`

>[!NOTE]
>
>Audience [Manager UI에서 주소 난독화를](/help/using/features/administration/ip-obfuscation.md) 활성화하는 방법은 IP 주소 난독화를 [!DNL IP] 참조하십시오.

Audience Manager에서 주소 난독화가 작동하는 방식을 이해하려면 아래 비디오를 [!DNL IP] 시청하십시오.

[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=kor)

**** 지리 특성:주소 난독화를 활성화하면 주소의 나머지 [!DNL IP] [!DNL IP] 주소를 여전히 Audience Manager의 지리 특성 및 보고에 사용할 수 있습니다. 주소 난독화를 활성화하지 않으면 Audience Manager에서 전체 [!DNL IP] [!DNL IP] 주소를 사용합니다. 두 경우 모두 지리적 영역별로 [!DNL IP] 위치를 식별할 수 있지만, 난독화를 사용하는 경우 약간의 정밀도가 손실되는 지리적 세그멘테이션 기능을 사용할 [!DNL IP] 수 있습니다. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. 지역 및 국가 수준 정보를 획득하는 것은 약간 영향을 받아야 합니다. 지리적 세그멘테이션 데이터는 도시 수준이나 우편 번호 수준에만 세분화되며 개별 수준에는 해당되지 않습니다. 지리적 [타깃팅](/help/using/features/traits/trait-geotarget-keys.md) 및 지리적 변수를 사용하여 트레이트를 설정하는 방법에 대한 자세한 내용을 살펴보십시오.

## 관련 개념 {#related-concepts}

* [옵트아웃 관리](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [개인 정보 및 데이터 유지 FAQ](/help/using/faq/faq-privacy.md)