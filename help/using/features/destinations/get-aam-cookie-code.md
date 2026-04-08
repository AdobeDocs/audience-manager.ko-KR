---
description: DART Enterprise(및 기타 대상 유형)에서 Audience Manager UUID(고유 사용자 ID) 값을 캡처하는 데 필요한 코드.
seo-description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie 코드
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
exl-id: 66e61a4b-908e-4950-8953-37a9920b67b5
TQID: https://experienceleague.adobe.com/x8w8GMRG9gnMWQAXyaWdguFk1SaD7P-199ccfyIQf-s
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: c138d302-73f0-4186-93ea-10c4ba52f943
  - id: e7029888-c8b0-46a7-849a-cf132a1559bf
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 52
ht-degree: 0%

---

# `get_aamCookie` 코드 {#get-aamcookie-code}

Audience Manager 고유 사용자 ID([!DNL DART Enterprise]) 값을 캡처하기 위해 [!DNL UUID]&#x200B;(및 기타 대상 유형)에 필요한 코드입니다.

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
