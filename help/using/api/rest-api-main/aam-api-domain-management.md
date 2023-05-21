---
description: 데이터를 전송할 도메인을 만들고 관리할 수 있는 도메인 관리 방법(쿠키 대상에만 해당).
seo-description: Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).
seo-title: Domain Management API Methods
solution: Audience Manager
title: 도메인 관리 API 메서드
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 5%

---

# 도메인 관리 API 메서드 {#domain-management-api-methods}

데이터를 전송할 도메인을 만들고 관리할 수 있는 도메인 관리 방법(쿠키 대상에만 해당).

<!-- c_partner_site.xml -->

## 새 도메인 만들기 {#create-new-domain}

A `POST` 에 대한 새 도메인을 만들 수 있는 메서드 (쿠키 대상에만 해당).

<!-- r_post_new_partner_site.xml -->

### 요청

`POST` `https://api.demdex.com/v1/partner-sites/`

### 샘플 요청

```
{
   "url":"example1.com"
}
```

### 응답

성공한 응답이 을 반환합니다. `201 created` 및 파트너 사이트(고유 ID 포함)로 식별됩니다.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 도메인 삭제 {#delete-domain}

A `DELETE` 도메인을 제거할 수 있는 메서드 (쿠키 대상의 경우에만).

<!-- r_delete_partner_site.xml -->

### 요청

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 응답

성공한 응답이 을 반환합니다. `204 no content`. 반환 `404 not found` 파트너 사이트를 찾을 수 없는 경우

## 도메인에 대한 속성 반환 {#return-props-domain}

A `GET` 지정된 도메인에 대한 세부 정보를 반환하는 메서드입니다( 쿠키 대상의 경우에만).

<!-- r_get_partner_site.xml -->

### 요청

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 응답

성공한 응답이 을 반환합니다. `200 OK` 및 아래 샘플과 같은 데이터가 포함되어 있습니다. 반환 `404 Not found` 사이트 ID 또는 파트너를 찾을 수 없는 경우

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 모든 도메인에 대한 속성 반환 {#return-props-all-domains}

A `GET` 모든 도메인에 대한 정보를 반환하는 메서드입니다( 쿠키 대상의 경우에만).

<!-- r_get_partner_sites.xml -->

### 요청

`GET https://api.demdex.com/v1/partner-sites/`

### 선택적 쿼리 매개 변수

다음 옵션 매개 변수를 사용할 수 있습니다. [!DNL API] 를 반환하는 메서드 *모두* 개체의 속성입니다. 해당 쿼리를 로 전달할 때 요청 문자열에서 이러한 옵션을 설정합니다. [!DNL API]. 다음을 참조하십시오 [선택적 매개 변수](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td> 
   <td colname="col2"> 페이지 번호별로 결과를 반환합니다. 번호 매기기는 0부터 시작합니다. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> 요청에서 반환되는 응답 결과 수를 설정합니다(기본값: 10). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> 지정된 JSON 속성에 따라 결과를 정렬하고 반환합니다. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 결과를 내림차순으로 정렬하고 반환합니다. 오름차순은 기본값입니다. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">검색 매개 변수로 사용할 지정된 문자열을 기반으로 결과를 반환합니다. 예를 들어 해당 항목의 값 필드 중 하나에서 "Test"라는 단어가 있는 모든 모델의 결과를 찾는다고 가정합니다. 샘플 요청은 다음과 같이 표시될 수 있습니다. <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>"모두 가져오기" 메서드에서 반환된 값을 검색할 수 있습니다. </p> </td>
  </tr> 
 </tbody> 
</table>

### 응답

성공한 응답이 을 반환합니다. `200 OK` 아래 샘플과 같이 배열에 있는 데이터를 내보낼 수 있습니다. 반환 `404 Not found` 사이트 ID 또는 파트너를 찾을 수 없는 경우

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```
