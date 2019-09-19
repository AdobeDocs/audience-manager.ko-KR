---
description: 데이터를 전송할 도메인을 만들고 관리할 수 있는 도메인 관리 메서드(쿠키 목적지에만 해당).
seo-description: 데이터를 전송할 도메인을 만들고 관리할 수 있는 도메인 관리 메서드(쿠키 목적지에만 해당).
seo-title: 도메인 관리 API 메서드
solution: Audience Manager
title: 도메인 관리 API 메서드
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 도메인 관리 API 메서드 {#domain-management-api-methods}

데이터를 전송할 도메인을 만들고 관리할 수 있는 도메인 관리 메서드(쿠키 목적지에만 해당).

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

새 도메인(쿠키 대상만)을 만들 수 있는 `POST` 방법입니다.

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

성공적인 응답 반환 `201 created` 및 고유 ID를 포함한 파트너 사이트

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 도메인 삭제 {#delete-domain}

도메인을 제거할 수 있는 `DELETE` 방법입니다(쿠키 대상에만 해당).

<!-- r_delete_partner_site.xml -->

### 요청

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 응답

성공적인 응답이 반환됩니다 `204 no content`. 파트너 사이트를 찾을 수 없는 `404 not found` 경우 반환합니다.

## 도메인에 대한 속성 반환 {#return-props-domain}

지정된 도메인에 대한 세부 정보를 반환하는 `GET` 메서드입니다(쿠키 대상에만 해당).

<!-- r_get_partner_site.xml -->

### 요청

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 응답

성공적인 응답은 아래 샘플에 표시된 대로 반환과 `200 OK` 데이터를 반환합니다. 사이트 ID 또는 파트너가 없으면 `404 Not found` 반환합니다.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 모든 도메인의 속성 반환 {#return-props-all-domains}

모든 도메인에 대한 정보를 반환하는 `GET` 메서드입니다(쿠키 대상에만 해당).

<!-- r_get_partner_sites.xml -->

### 요청

`GET https://api.demdex.com/v1/partner-sites/`

### 선택적 쿼리 매개 변수

객체에 대한 [!DNL API] 모든 ** 속성을 반환하는 메서드와 함께 이러한 선택적 매개 변수를 사용할 수 있습니다. 요청 문자열에서 해당 쿼리를 [!DNL API]에 전달할 때 이 옵션을 설정합니다. 선택적 [매개 변수를 참조하십시오](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> 페이지 번호별로 결과를 반환합니다. 번호는 0부터 시작됩니다. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> 요청에 의해 반환되는 응답 결과 수를 설정합니다(기본값 10). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> 지정된 JSON 속성에 따라 결과를 정렬하고 반환합니다. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> 내림차순</code> </td>
   <td colname="col2"> 결과를 내림차순으로 정렬하고 반환합니다. 기본값은 오름차순입니다. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">검색 매개 변수로 사용할 지정된 문자열을 기반으로 결과를 반환합니다. 예를 들어 해당 항목에 대한 값 필드에 "테스트"라는 단어가 있는 모든 모델의 결과를 찾으려 합니다. 샘플 요청은 다음과 같습니다. <p><code> 'GET' 'https://api.demdex.com/v1/models/?search=Test'</code>. </p> <p>"모두 가져오기" 메서드에서 반환되는 값을 검색할 수 있습니다. </p> </td>
  </tr> 
 </tbody> 
</table>

### 응답

성공적인 응답은 아래 샘플에서와 같이 배열에서 반환과 `200 OK` 데이터를 반환합니다. 사이트 ID 또는 파트너가 없으면 `404 Not found` 반환합니다.

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
