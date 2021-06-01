---
description: 데이터를 전송할 도메인(쿠키 대상의 경우에만)을 만들고 관리할 수 있는 도메인 관리 메서드입니다.
seo-description: 데이터를 전송할 도메인(쿠키 대상의 경우에만)을 만들고 관리할 수 있는 도메인 관리 메서드입니다.
seo-title: 도메인 관리 API 메서드
solution: Audience Manager
title: 도메인 관리 API 메서드
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 6%

---

# 도메인 관리 API 메서드 {#domain-management-api-methods}

데이터를 전송할 도메인(쿠키 대상의 경우에만)을 만들고 관리할 수 있는 도메인 관리 메서드입니다.

<!-- c_partner_site.xml -->

## 새 도메인 만들기 {#create-new-domain}

에 대한 새 도메인을 만들 수 있는 `POST` 메서드(쿠키 대상만).

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

성공적인 응답은 해당 고유 ID를 포함하여 `201 created` 및 파트너 사이트를 반환합니다.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 도메인 {#delete-domain} 삭제

도메인을 제거할 수 있는 `DELETE` 메서드입니다(쿠키 대상의 경우에만).

<!-- r_delete_partner_site.xml -->

### 요청

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 응답

성공한 응답이 `204 no content`을 반환합니다. 파트너 사이트를 찾을 수 없으면 `404 not found`을 반환합니다.

## 도메인 {#return-props-domain}에 대한 속성 반환

지정된 도메인에 대한 세부 정보를 반환하는 `GET` 메서드입니다(쿠키 대상에 대해서만).

<!-- r_get_partner_site.xml -->

### 요청

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 응답

성공적인 응답은 아래 샘플에 표시된 것처럼 `200 OK` 및 데이터를 반환합니다. 사이트 ID 또는 파트너를 찾을 수 없으면 `404 Not found` 을 반환합니다.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 모든 도메인 {#return-props-all-domains}에 대한 속성 반환

모든 도메인에 대한 정보를 반환하는 `GET` 메서드입니다(쿠키 대상에 대해서만).

<!-- r_get_partner_sites.xml -->

### 요청

`GET https://api.demdex.com/v1/partner-sites/`

### 선택적 쿼리 매개 변수

객체에 대해 *모든* 속성을 반환하는 [!DNL API] 메서드와 함께 이러한 선택적 매개 변수를 사용할 수 있습니다. 해당 쿼리를 [!DNL API]에 전달할 때 요청 문자열에서 이러한 옵션을 설정합니다. [선택적 매개 변수](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)를 참조하십시오.

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
   <td colname="col2"> 페이지 번호별로 결과를 반환합니다. 번호 매기는 0부터 시작됩니다. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> 요청에서 반환된 응답 결과 수를 설정합니다(10은 기본값). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> 지정된 JSON 속성에 따라 결과를 정렬 및 반환합니다. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 결과를 내림차순으로 정렬하고 반환합니다. 오름차순 은 기본값입니다. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">검색 매개 변수로 사용할 지정된 문자열을 기반으로 결과를 반환합니다. 예를 들어 해당 항목의 값 필드에 "Test"라는 단어가 있는 모든 모델에 대한 결과를 찾겠다고 가정합니다. 샘플 요청은 다음과 같을 수 있습니다. <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>에서 보냅니다. </p> <p>모두 가져오기 메서드에서 반환된 값을 검색할 수 있습니다. </p> </td>
  </tr> 
 </tbody> 
</table>

### 응답

성공적인 응답은 아래 샘플에서와 같이 배열에 있는 `200 OK` 및 데이터를 반환합니다. 사이트 ID 또는 파트너를 찾을 수 없으면 `404 Not found` 을 반환합니다.

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
