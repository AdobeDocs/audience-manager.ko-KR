---
description: DART Enterprise(및 기타 대상 유형)가 UUID(Audience Manager 고유 사용자 ID) 값을 캡처하는 데 필요한 코드입니다.
seo-description: DART Enterprise(및 기타 대상 유형)가 UUID(Audience Manager 고유 사용자 ID) 값을 캡처하는 데 필요한 코드입니다.
seo-title: get_aamCookie 코드
solution: Audience Manager
title: get_aamCookie 코드
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 9%

---


# `get_aamCookie` 코드 {#get-aamcookie-code}

Audience Manager 고유 사용자 ID([!DNL UUID]) 값을 캡처하기 위해 [!DNL DART Enterprise](및 기타 대상 유형)에 필요한 코드입니다.

페이지 맨 위에 `<head>` 코드 블록 내에서 이 함수를 정의합니다.

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
