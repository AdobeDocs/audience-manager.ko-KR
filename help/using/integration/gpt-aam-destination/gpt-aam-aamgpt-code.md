---
description: AamGpt는 Audience Manager 쿠키 데이터를 읽고 해당 정보를 Google 게시자 태그로 전송하는 JavaScript 함수입니다.
seo-description: AamGpt is a JavaScript function that reads Audience Manager cookie data and sends that information to Google Publisher Tags.
seo-title: Audience Manager Code for Google Publisher Tags
solution: Audience Manager
title: Google Publisher Tag용 Audience Manager 코드
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
feature: Third-party Integration
exl-id: 04e74399-7b6a-400e-a1e6-94fe296e7209
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 17%

---

# Google Publisher Tag용 Audience Manager 코드 {#audience-manager-code-for-google-publisher-tags}

`AamGpt` 다음 값: [!DNL JavaScript] Audience Manager 쿠키 데이터를 읽고 해당 정보를 로 보내는 함수 [!DNL Google Publisher Tags].

>[!NOTE]
>
>에서 Audience Manager 쿠키 데이터를 읽는 자체 코드가 있는 경우 이 함수는 필요하지 않습니다. [!UICONTROL UUID] 및 대상 쿠키입니다.

## 샘플 코드

배치 `AamGpt` 페이지 맨 위에 있는 코드, 이상적으로 `<head>` 코드 블록. 다음 `AamGpt` 코드는 아래에서 사용할 수 있습니다.

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
