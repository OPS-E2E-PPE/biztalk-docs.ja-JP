---
title: EDIFACT 受信確認は、システムによって生成されました。 ただし、区切り記号セットのコンテキスト プロパティがありませんが。 シリアル化できません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d7b1e62-3230-4cdc-830f-3267de1efd1c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 959be3b06db82d4bd0ca741076adaa9df7148d70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389334"
---
# <a name="the-edifact-acknowledgement-was-generated-by-the-system-however-it-is-missing-a-context-property-for-delimiter-set-it-cannot-be-serialized"></a>EDIFACT 受信確認は、システムによって生成されました。 ただし、区切り記号セットのコンテキスト プロパティがありませんが。 シリアル化できません。
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                               |
| 製品バージョン |                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                           |
|    イベント ID     |                                                                       -                                                                       |
|  イベント ソース   |                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                             |
|    コンポーネント    |                                                                  EDI エンジン                                                                   |
|  シンボル名  |                                                                       -                                                                       |
|  メッセージ テキスト   | EDIFACT 受信確認は、システムによって生成されました。 ただし、区切り記号セットのコンテキスト プロパティがありませんが。 シリアル化できません。 |
  
## <a name="explanation"></a>説明  
 このエラーは、BizTalk Server が EDIFACT 受信確認をシリアル化できません、区切り記号セット コンテキスト プロパティが BizTalk メッセージから見つからないを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、EDIFACT 受信確認を BizTalk メッセージ コンテキストに区切り記号セット コンテキスト プロパティを記述することを確認します。