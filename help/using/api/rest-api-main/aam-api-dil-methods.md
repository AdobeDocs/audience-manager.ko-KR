---
description: DIL(데이터 통합 라이브러리)을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.
seo-description: DIL(데이터 통합 라이브러리)을 사용하여 프로그래밍 방식으로 작업할 수 있는 메서드입니다.
seo-title: 데이터 통합 라이브러리 API 메서드
solution: Audience Manager
title: 데이터 통합 라이브러리 API 메서드
uuid: 507e7afd-3ae7-44de-98b0-589d699c453b
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 14%

---


# 데이터 통합 라이브러리 API 메서드 {#data-integration-library-api-methods}

프로그래밍 방식으로 ( [!UICONTROL Data Integration Library] )으로 작업할 수 있는[!UICONTROL DIL]메서드입니다.

>[!IMPORTANT]
>
>데이터 통합 라이브러리 API는 더 이상 사용되지 않습니다. 이 API는 DIL을 생성하는 데 사용되었으며 이제 여기에서 직접 다운로드할 수 있습니다. [DIL 다운로드](https://github.com/Adobe-Marketing-Cloud/dil/releases).

<!-- c_data_integr_library_api.xml -->

## DIL용 반환 버전 {#return-version-dil}

가장 오래된 버전에서 최신 버전으로 순서가 지정된 버전 목록을 반환하는 `GET` 메서드입니다.

<!-- r_api_return_versions_dil.xml -->

### 요청

`GET https://api.demdex.com/v1/dil/`

### 응답

요청이 성공하면 아래와 `["4.0", "4.1"]` 같이 응답 코드를 반환합니다.

```
["4.0", "4.1"]
```

## 버전에 대한 JSON 스키마 반환 {#return-json-schema-version}

버전에 대한 스키마 `GET` 를 반환하는 [!DNL JSON] [!UICONTROL DIL] 메서드입니다. 최신 버전 [!UICONTROL LATEST] 을 얻기 위해 버전에 대한 별칭 사용을 지원합니다 [!UICONTROL DIL].

<!-- r_api_return_json_schema_for_version.xml -->

### 요청

`GET https://api.demdex.com/v1/dil/`*`<version>`*

### 응답

요청이 성공하면 아래와 같이 응답 코드 `["4.0", "4.1"]` 및 데이터를 반환합니다.

```
{ 
    "type": "object", 
    "$schema": "https://json-schema.org/draft-03/schema", 
    "required": true, 
    "additionalProperties": false, 
    "properties": { 
        "core": { 
            "id": "core", 
            "required": true, 
            "type": "object", 
            "properties": { 
                "code": { 
                    "type": "boolean", 
                    "required": true, 
                    "id": "code" 
                }, 
                "instanceVariable": { 
                    "type": "string", 
                    "id": "instanceVariable", 
                    "required": false 
                }, 
                "create": { 
                    "type": "object", 
                    "id": "create", 
                    "required": false, 
                    "properties": { 
                        "initConfig": { 
                            "additionalProperties": false, 
                            "type": "object", 
                            "id": "initConfig", 
                            "required": true, 
                            "properties": { 
                                "declaredId": { 
                                    "id": "declaredId", 
                                    "required": false, 
                                    "type": "object", 
                                    "additionalProperties": false, 
                                    "properties": { 
                                        "dpid": { 
                                            "id": "dpid", 
                                            "required": true, 
                                            "type": "string" 
                                        }, 
                                        "dpuuid": { 
                                            "id": "dpuuid", 
                                            "required": true, 
                                            "type": "string" 
                                        } 
                                    } 
                                }, 
                                "containerNSID": { 
                                    "type": "number", 
                                    "id": "containerNSID", 
                                    "required": false 
                                }, 
                                "disableDestinationPublishingIframe": { 
                                    "type": "boolean", 
                                    "id": "disableDestinationPublishingIframe", 
                                    "required": false 
                                }, 
                                "enableErrorReporting": { 
                                    "type": "boolean", 
                                    "id": "enableErrorReporting", 
                                    "required": false 
                                }, 
                                "iframeAkamaiHTTPS": { 
                                    "type": "boolean", 
                                    "id": "iframeAkamaiHTTPS", 
                                    "required": false 
                                }, 
                                "iframeAttachmentDelay": { 
                                    "type": "number", 
                                    "id": "iframeAttachmentDelay", 
                                    "required": false 
                                }, 
                                "mappings": { 
                                    "type": "object", 
                                    "id": "mappings", 
                                    "required": false, 
                                    "additionalProperties": { 
                                        "type": "string" 
                                    } 
                                }, 
                                "removeFinishedScriptsAndCallbacks": { 
                                    "type": "boolean", 
                                    "id": "removeFinishedScriptsAndCallbacks", 
                                    "required": false 
                                }, 
                                "uuidCookie": { 
                                    "type": "object", 
                                    "id": "uuidCookie", 
                                    "additionalProperties": false, 
                                    "required": false, 
                                    "properties": { 
                                        "days": { 
                                            "type": "number", 
                                            "id": "days", 
                                            "required": false 
                                        }, 
                                        "domain": { 
                                            "type": "string", 
                                            "id": "domain", 
                                            "required": false 
                                        }, 
                                        "name": { 
                                            "type": "string", 
                                            "id": "name", 
                                            "required": true 
                                        }, 
                                        "path": { 
                                            "type": "string", 
                                            "id": "path", 
                                            "required": false 
                                        }, 
                                        "secure": { 
                                            "type": "boolean", 
                                            "id": "secure", 
                                            "required": false 
                                        } 
                                    } 
                                }, 
                                "visitorService": { 
                                    "type": "object", 
                                    "id": "visitorService", 
                                    "required": false, 
                                    "properties": { 
                                        "namespace": { 
                                            "type": "string", 
                                            "id": "namespace", 
                                            "required": true 
                                        } 
                                    } 
                                } 
                            } 
                        } 
                    } 
                } 
            } 
        }, 
        "options": { 
            "id": "options", 
            "type": "object", 
            "required": false, 
            "properties": { 
                "minify": { 
                    "id": "minify", 
                    "required": false, 
                    "type": "boolean" 
                } 
            } 
        }, 
        "include": { 
            "type": "object", 
            "id": "include", 
            "required": false, 
            "properties": { 
                "modules": { 
                    "type": "object", 
                    "id": "modules", 
                    "required": false, 
                    "additionalProperties": false, 
                    "properties": { 
                        "GoogleAnalytics": { 
                            "type": "object", 
                            "id": "GoogleAnalytics", 
                            "required": false, 
                            "properties": { 
                                "code": { 
                                    "id": "code", 
                                    "type": "boolean", 
                                    "required": true 
                                } 
                            } 
                        }, 
                        "Peer39": { 
                            "type": "object", 
                            "id": "Peer39", 
                            "required": false, 
                            "properties": { 
                                "code": { 
                                    "id": "code", 
                                    "type": "boolean", 
                                    "required": true 
                                } 
                            } 
                        }, 
                        "SiteCatalyst": { 
                            "type": "object", 
                            "id": "SiteCatalyst", 
                            "required": false, 
                            "additionalProperties": false, 
                            "properties": { 
                                "code": { 
                                    "type": "boolean", 
                                    "id": "code", 
                                    "required": true 
                                }, 
                                "init": { 
                                    "type": "object", 
                                    "id": "init", 
                                    "required": false, 
                                    "additionalProperties": false, 
                                    "properties": { 
                                        "siteCatalystInstance": { 
                                            "type": "string", 
                                            "id": "siteCatalystInstance", 
                                            "required": true 
                                        }, 
                                        "dilInstance": { 
                                            "type": "string", 
                                            "id": "dilInstance", 
                                            "required": true 
                                        }, 
                                        "trackedVariables": { 
                                            "id": "trackedVariables", 
                                            "required": false, 
                                            "type": "object", 
                                            "properties": { 
                                                "iteratedNames": { 
                                                    "type": "array", 
                                                    "id": "iteratedNames", 
                                                    "required": false, 
                                                    "items": { 
                                                        "type": "object", 
                                                        "id": "0", 
                                                        "required": true, 
                                                        "properties": { 
                                                            "maxIndex": { 
                                                                "type": "number", 
                                                                "id": "maxIndex", 
                                                                "required": true 
                                                            }, 
                                                            "name": { 
                                                                "type": "string", 
                                                                "id": "name", 
                                                                "required": true 
                                                            } 
                                                        } 
                                                    } 
                                                }, 
                                                "names": { 
                                                    "type": "array", 
                                                    "additionalItems": false, 
                                                    "id": "names", 
                                                    "required": false, 
                                                    "items": [ 
                                                        { 
                                                            "type": "string", 
                                                            "required": true 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        } 
                                                    ] 
                                                } 
                                            } 
                                        } 
                                    } 
                                } 
                            } 
                        } 
                    } 
                }, 
                "tools": { 
                    "type": "object", 
                    "id": "tools", 
                    "required": false, 
                    "additionalProperties": false, 
                    "properties": { 
                        "getMetaTags": { 
                            "type": "boolean", 
                            "id": "getMetaTags", 
                            "required": false 
                        }, 
                        "getSearchReferrer": { 
                            "type": "boolean", 
                            "id": "getSearchReferrer", 
                            "required": false 
                        }, 
                        "decomposeURI": { 
                            "type": "boolean", 
                            "id": "decomposeURI", 
                            "required": false 
                        } 
                    } 
                } 
            } 
        } 
    } 
} 
```

## DIL 생성 {#generate-dil}

지정된 버전 `GET` 을 사용하여 전달된 요청 본문에 [!UICONTROL DIL] 따라 생성되는 [!UICONTROL DIL]메서드입니다. URL의 버전 `LATEST` 에 별칭을 사용하는 경우 최신 버전의 별칭이 [!UICONTROL DIL] 생성됩니다.

<!-- r_api_generate_dil.xml -->

### 요청

`POST https://api.demdex.com/v1/dil/`*`<version>`*`/generate`

### 샘플 요청

```
{ 
    core: { 
        code: true, 
        instanceVariable: 'dil_instance', 
        create: { 
            initConfig: { 
                declaredId: { 
                    dpid: '159', 
                    dpuuid: '456' 
                }, 
                containerNSID: 81, 
                disableDestinationPublishingIframe: false, 
                enableErrorReporting: false, 
                iframeAkamaiHTTPS: false, 
                iframeAttachmentDelay: 575, 
                mappings: { 
                    c_k1: 'd_k1', 
                    c_k2: 'd_k2' 
                }, 
                removeFinishedScriptsAndCallbacks: false, 
                uuidCookie: { 
                    days: 12, 
                    domain: 'adobe.com', 
                    name: 'adobe_did', 
                    path: '/', 
                    secure: false 
                }, 
                visitorService: { 
                    namespace: 'demofirst' 
                } 
            } 
        } 
    }, 
    options: { 
        minify: true 
    }, 
    include: { 
        modules: { 
            GoogleAnalytics: { 
                code: true 
            }, 
            Peer39: { 
                code: true 
            }, 
            SiteCatalyst: { 
                code: true, 
                init: { 
                    siteCatalystInstance: 'sc_instance', 
                    dilInstance: 'dil_instance', 
                    trackedVariables: { 
                        iteratedNames: [{ 
                            name: 'prop', 
                            maxIndex: 5 
                        }, { 
                            name: 'pev', 
                            maxIndex: 3 
                        }], 
                        names: ['pageName', 'channel', 'campaign', 'products', 'events', 'spe', 'spev1', 'spev2', 'spev3'] 
                    } 
                } 
            } 
        }, 
        tools: { 
            getMetaTags: true, 
            getSearchReferrer: true, 
            decomposeURI: true 
        } 
    } 
} 
```

### 응답

업데이트가 성공하면 코드 `201 created` 와 함께 응답 코드를 [!UICONTROL DIL] 반환합니다 [!DNL JavaScript] .
