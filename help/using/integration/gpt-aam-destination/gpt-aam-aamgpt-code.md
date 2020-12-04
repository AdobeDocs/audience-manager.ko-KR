---
description: AamGpt는 Audience Manager 쿠키 데이터를 읽고 해당 정보를 Google 게시자 태그로 보내는 JavaScript 함수입니다.
seo-description: AamGpt는 Audience Manager 쿠키 데이터를 읽고 해당 정보를 Google 게시자 태그로 보내는 JavaScript 함수입니다.
seo-title: Google Publisher Tag용 Audience Manager 코드
solution: Audience Manager
title: Google Publisher Tag용 Audience Manager 코드
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: c63467dec62ff08c3cd32f19ac2e4675c9ce18e3
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 19%

---


# Google Publisher Tag용 Audience Manager 코드 {#audience-manager-code-for-google-publisher-tags}

`AamGpt` 는 Audience Manager 쿠키 데이터를 읽고 해당 정보를 전송하는  [!DNL JavaScript] 함수입니다 [!DNL Google Publisher Tags].

>[!NOTE]
>
>이 함수는 [!UICONTROL UUID] 및 대상 쿠키의 Audience Manager 쿠키 데이터를 읽는 자체 코드가 있는 경우에는 필요하지 않습니다.

## 샘플 코드

`AamGpt` 코드를 페이지 맨 위에 배치하고, 가장 좋은 방법은 `<head>` 코드 블록 내에 넣습니다. `AamGpt` 코드는 아래에서 사용할 수 있습니다.

```js
var AamGpt = {  
 strictEncode: function(str){ 
  return encodeURIComponent(str).replace(/[!'()]/g, escape).replace(/\*/g, "%2A"); 
 }, 
 getCookie: function(c_name) 
 { 
  var i,x,y,c=document.cookie.split(";"); 
  for (i=0;i<c.length;i++) 
  { 
   x=c[i].substr(0,c[i].indexOf("=")); 
   y=c[i].substr(c[i].indexOf("=")+1); 
   x=x.replace(/^\s+|\s+$/g,""); 
   if (x==c_name) 
   { 
    return unescape(y); 
   } 
  } 
 }, 
 getKey: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[0] != "undefined" && cList[0].match(/\w+/)) 
   { 
    return cList[0]; 
   } 
  }  
 }, 
 getValues: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D\w+/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[1] != "undefined" && cList[1].match(/\w+/)) 
   { 
    var vList=cList[1].split("%2C"); 
    if(typeof vList[0] != "undefined") 
    { 
     return vList; 
    } else { 
     return null; 
    }    
   } else { 
    return null; 
   } 
  } else { 
   return null; 
  } 
 } 
};
```
