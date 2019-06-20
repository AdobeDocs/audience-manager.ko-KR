---
description: Aamgpt는 Audience Manager 쿠키 데이터를 읽고 해당 정보를 Google Publisher 태그로 전송하는 JavaScript 기능입니다.
seo-description: Aamgpt는 Audience Manager 쿠키 데이터를 읽고 해당 정보를 Google Publisher 태그로 전송하는 JavaScript 기능입니다.
seo-title: Google Publisher 태그를 위한 Audience Manager 코드
solution: Audience Manager
title: Audience Manager Google Publisher 태그용 코드
uuid: 24 ff 5 d 16-b 360-46 cc-a 4 c 6-6 db 34 d 7 fda 75
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Audience Manager Code for Google Publisher Tags {#audience-manager-code-for-google-publisher-tags}

`AamGpt` Audience Manager 쿠키 데이터를 읽고 해당 정보를 전송하는 [!DNL JavaScript][!DNL Google Publisher Tags]함수입니다.

>[!NOTE]
>
>This function is not required if you have your own code to read Audience Manager cookie data from the [!UICONTROL UUID] and destination cookies.

## 샘플 코드

Place the `AamGpt` code at the top of the page, ideally within the `<head>` code block. `AamGpt` 코드는 아래에서 사용할 수 있습니다.

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
