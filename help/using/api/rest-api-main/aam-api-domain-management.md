---
description: 데이터를 보낼 도메인을 만들고 관리할 수 있도록 해주는 도메인 관리 메서드입니다 (쿠키 대상에만 해당).
seo-description: 데이터를 보낼 도메인을 만들고 관리할 수 있도록 해주는 도메인 관리 메서드입니다 (쿠키 대상에만 해당).
seo-title: 도메인 관리 API 메서드
solution: Audience Manager
title: 도메인 관리 API 메서드
uuid: F 2 F 08 BC 5-EA 42-4171-9 A 43-0 B 20976 F 0 CB 0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domain Management API Methods {#domain-management-api-methods}

데이터를 보낼 도메인을 만들고 관리할 수 있도록 해주는 도메인 관리 메서드입니다 (쿠키 대상에만 해당).

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

A `POST` method that lets you create a new domain for (cookie destinations only).

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

A successful response returns `201 created` and the partner site, including its unique ID.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Delete a Domain {#delete-domain}

A `DELETE` method that lets you remove a domain (for cookie destinations only).

<!-- r_delete_partner_site.xml -->

### 요청

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 응답

A successful response returns `204 no content`. Returns `404 not found` if the partner site cannot be found.

## Return Properties for a Domain {#return-props-domain}

A `GET` method that returns details about the specified domain (for cookie destinations only).

<!-- r_get_partner_site.xml -->

### 요청

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 응답

A successful response returns `200 OK` and data as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Return Properties for all Domains {#return-props-all-domains}

A `GET` method that returns information about all your domains (for cookie destinations only).

<!-- r_get_partner_sites.xml -->

### 요청

`GET https://api.demdex.com/v1/partner-sites/`

### 선택적 쿼리 매개 변수

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. [선택적 매개 변수를 참조하십시오](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> 결과를 페이지 번호별로 반환합니다. 번호 매기기는 0 부터 시작합니다. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> Pagesize</code> </td> 
   <td colname="col2"> 요청에 의해 반환된 응답 결과 수를 설정합니다 (10는 기본값). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> Sortby</code> </td> 
   <td colname="col2"> 지정된 JSON 속성에 따라 결과를 정렬하고 반환합니다. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> 내림차순</code> </td>
   <td colname="col2"> 결과를 내림차순으로 정렬하고 반환합니다. 기본값은 기본값입니다. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">검색 매개 변수로 사용하려는 지정된 문자열을 기반으로 결과를 반환합니다. 예를 들어 해당 항목에 대한 값 필드에 "test" 단어가 있는 모든 모델에 대한 결과를 찾는다고 가정합니다. 샘플 요청은 다음과 같습니다. <p><code> ' get '' https://api.demdex.com/v1/models/?search=Test '</code>를 참조하십시오. </p> <p>" 모두 가져오기 "방법으로 반환되는 값을 검색할 수 있습니다. </p> </td>
  </tr> 
 </tbody> 
</table>

### 응답

A successful response returns `200 OK` and data in an array as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

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
