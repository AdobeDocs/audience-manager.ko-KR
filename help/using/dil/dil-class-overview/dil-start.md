---
description: 클래스 수준 DIL 설명서에 사용되는 인증 요구 사항 및 텍스트 서식에 대해 설명합니다.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: 클래스 수준 DIL API 시작
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# 클래스 수준 DIL API 시작{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>2023년 7월부터 Adobe은 [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장 개발을 중단했습니다.
>
>기존 고객은 [!DNL DIL] 구현을 계속 사용할 수 있습니다. 그러나 Adobe은 이 시점 이후에는 [!DNL DIL]을(를) 개발하지 않습니다. 고객은 장기 데이터 수집 전략에 대해 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)을(를) 평가하는 것이 좋습니다.
>
>2023년 7월 이후에 새로운 데이터 수집 통합을 구현하려는 고객은 대신 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)을 사용해야 합니다.

클래스 수준 DIL API를 사용하면 Audience Manager 개체를 프로그래밍 방식으로 만들고 작업할 수 있습니다. 클래스 수준 API는 다른 인스턴스 수준 함수와 함께 작동하여 값을 설정하거나 데이터를 반환합니다.

## 클래스 수준 DIL API 시작 {#get-started}

클래스 수준 [!UICONTROL DIL] 설명서에서 사용되는 인증 요구 사항 및 텍스트 형식을 설명합니다.

<!-- 

c_class_start.xml

 -->

클래스 수준 [!UICONTROL DIL] API로 작업하는 경우:

* 액세스하려면 파트너 이름과 컨테이너 네임스페이스 ID(NSID)가 필요합니다. 이 정보를 얻으려면 Audience Manager 계정 관리자에게 문의하십시오.
* 작업 중인 메서드의 필요에 따라 API 설명서의 샘플 *italicized* 텍스트를 값, ID 또는 다른 변수로 바꿉니다.
* [!UICONTROL DIL]이(가) 인코딩된 데이터를 대상 쿠키에 씁니다. 예를 들어 공백은 `%20`, 세미콜론은 `%3B` 형식으로 인코딩됩니다.
