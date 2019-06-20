---
description: Audience Manager 고유 사용자 ID (UUID) 값을 캡처하기 위해 DART Enterprise (및 기타 대상 유형) 에 필요한 코드입니다.
seo-description: Audience Manager 고유 사용자 ID (UUID) 값을 캡처하기 위해 DART Enterprise (및 기타 대상 유형) 에 필요한 코드입니다.
seo-title: GET_ AAMCOOKIE 코드
solution: Audience Manager
title: GET_ AAMCOOKIE 코드
uuid: 89 C 30 FE 3-DBE 6-4 D 18-B 161-104167 D 75 BCD
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` 코드 {#get-aamcookie-code}

Code required by [!DNL DART Enterprise] (and other destination types) to capture the Audience Manager unique user ID ([!DNL UUID]) value.

Define this function at the top of the page, ideally within the `<head>` code block.

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
