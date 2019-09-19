---
description: DART Enterprise(및 기타 대상 유형)가 Audience Manager 고유 사용자 ID(UUID) 값을 캡처하는 데 필요한 코드입니다.
seo-description: DART Enterprise(및 기타 대상 유형)가 Audience Manager 고유 사용자 ID(UUID) 값을 캡처하는 데 필요한 코드입니다.
seo-title: get_aamCookie 코드
solution: Audience Manager
title: get_aamCookie 코드
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` 코드 {#get-aamcookie-code}

Audience Manager 고유 사용자 ID( [!DNL DART Enterprise] ) 값을 캡처하는 데 필요한[!DNL UUID](및 기타 대상 유형)의 코드입니다.

페이지 맨 위에 이 함수를 정의하면, 코드 블록 내에서 편리하게 사용할 수 `<head>` 있습니다.

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
