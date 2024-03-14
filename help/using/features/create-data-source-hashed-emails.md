---
title: 해시된 이메일 워크플로우에 대한 데이터 소스 구성
description: 해시된 이메일 워크플로우에 대한 해시된 이메일을 저장하는 데이터 소스를 만드는 방법을 알아봅니다.
solution: Audience Manager
feature: Data Sources
source-git-commit: b88f180808ec9723a2a5324441733f6383f6302d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---


# 해시된 이메일 워크플로우에 대한 데이터 소스 구성

사용자 기반 대상과 같은 해시된 이메일 워크플로를 사용하려면 해시된 이메일 주소를 저장할 데이터 소스를 만들어야 합니다.

해시된 이메일에 대한 데이터 소스를 만들고 구성하려면 아래 단계를 따르십시오.

1. Audience Manager 계정에 로그인하고 다음으로 이동 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**, 및 클릭 **[!UICONTROL Add New]**.
1. 입력 **[!UICONTROL Name]** 및 **[!UICONTROL Description]** 새 데이터 소스.
1. 다음에서 **[!UICONTROL ID Type]** 드롭다운 메뉴에서 다음을 선택합니다. **[!UICONTROL Cross Device]**.
   ![데이터 소스 세부 정보 섹션을 보여주는 Audience Manager UI 이미지입니다.](../features/assets/create-hashed-email-data-source.png)
1. 다음에서 **[!UICONTROL Data Source Settings]** 섹션에서 다음을 모두 선택합니다. **[!UICONTROL Inbound]** 및 **[!UICONTROL Outbound]** 옵션 및 활성화 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 옵션을 선택합니다.
1. 드롭다운 메뉴를 사용하여 **[!UICONTROL Emails(SHA256, lowercased)]** 이 데이터 소스의 레이블입니다.

   >[!IMPORTANT]
   >
   >이 옵션은 특정 알고리즘으로 해시된 데이터를 포함하는 것으로 데이터 소스에만 레이블을 지정합니다. Audience Manager은 이 단계에서 데이터를 해시하지 않습니다. 이 데이터 소스에 저장할 이메일 주소를 이미 해시했는지 확인합니다. [!DNL SHA256] 알고리즘. 그렇지 않으면 해시된 이메일 워크플로에 사용할 수 없습니다.

   ![데이터 소스 설정 섹션을 보여 주는 Audience Manager UI 이미지입니다.](../features/assets/data-source-settings.png)


