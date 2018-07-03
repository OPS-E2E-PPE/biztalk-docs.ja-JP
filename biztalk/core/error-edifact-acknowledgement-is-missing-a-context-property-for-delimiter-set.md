---
title: EDIFACT 受信確認がシステムによって生成されました。 ただし、区切り記号セットのコンテキスト プロパティがありません。 シリアル化できません |Microsoft Docs
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
ms.openlocfilehash: e15887960035daa9847c133e361ce5bb60085215
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993107"
---
# <a name="the-edifact-acknowledgement-was-generated-by-the-system-however-it-is-missing-a-context-property-for-delimiter-set-it-cannot-be-serialized"></a>EDIFACT 受信確認がシステムによって生成されました。 ただし、区切り記号セットのコンテキスト プロパティがありません。 この受信確認はシリアル化できません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                               |
| 製品バージョン |                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                           |
|    イベント ID     |                                                                       -                                                                       |
|  イベント ソース   |                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                             |
|    コンポーネント    |                                                                  EDI エンジン                                                                   |
|  シンボル名  |                                                                       -                                                                       |
|  メッセージ テキスト   | EDIFACT 受信確認がシステムによって生成されました。 ただし、区切り記号セットのコンテキスト プロパティがありません。 この受信確認はシリアル化できません |
  
## <a name="explanation"></a>説明  
 このエラーは、BizTalk Server が EDIFACT 受信確認をシリアル化できず、区切り記号セット コンテキスト プロパティが BizTalk メッセージに見つからないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、EDIFACT 受信確認を BizTalk メッセージ コンテキストに区切り記号セット コンテキスト プロパティを記述することを確認します。