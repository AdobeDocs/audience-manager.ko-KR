---
description: 인증 요구 사항 및 클래스 수준 DIL 설명서에 사용되는 텍스트 서식을 설명합니다.
seo-description: 인증 요구 사항 및 클래스 수준 DIL 설명서에 사용되는 텍스트 서식을 설명합니다.
seo-title: 클래스 수준 DIL API 시작
solution: Audience Manager
title: 클래스 수준 DIL API 시작
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL 구현
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 15%

---

# 클래스 수준 DIL API 시작{#getting-started-with-class-level-dil-apis}

클래스 수준 DIL API를 사용하면 프로그래밍 방식으로 Audience Manager 개체를 만들고 사용할 수 있습니다. 클래스 수준 API는 다른 인스턴스 수준 함수와 함께 사용하여 값을 설정하거나 데이터를 반환합니다.

## 클래스 수준 DIL API 시작 {#get-started}

인증 요구 사항 및 클래스 수준 [!UICONTROL DIL] 설명서에 사용되는 텍스트 서식을 설명합니다.

<!-- 

c_class_start.xml

 -->

클래스 수준 [!UICONTROL DIL] API를 사용하여 작업하는 경우:

* 액세스하려면 파트너 이름 및 컨테이너 네임스페이스 ID(NSID)가 필요합니다. 이 정보를 얻으려면 Audience Manager 계정 관리자에게 문의하십시오.
* API 설명서의 모든 샘플 *기울임화된* 텍스트를 작업 중인 메서드에서 필요한 값, ID 또는 기타 변수로 바꿉니다.
* [!UICONTROL DIL] 인코딩된 데이터를 대상 쿠키에 씁니다. 예를 들어 공백은 `%20` 로 인코딩되고 세미콜론은 `%3B` 로 인코딩됩니다.
