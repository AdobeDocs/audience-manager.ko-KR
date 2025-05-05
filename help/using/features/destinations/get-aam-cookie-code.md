---
description: DART Enterprise(및 기타 대상 유형)에서 Audience Manager UUID(고유 사용자 ID) 값을 캡처하는 데 필요한 코드.
seo-description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie 코드
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
exl-id: 66e61a4b-908e-4950-8953-37a9920b67b5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 0%

---

# `get_aamCookie` 코드 {#get-aamcookie-code}

Audience Manager 고유 사용자 ID([!DNL UUID]) 값을 캡처하는 데 [!DNL DART Enterprise] (및 기타 대상 형식)에 필요한 코드입니다.

페이지 맨 위에서 `<head>` 코드 블록 내에서 이 함수를 정의하십시오.

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```
