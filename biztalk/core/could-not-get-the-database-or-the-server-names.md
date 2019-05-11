---
title: データベース名またはサーバー名を取得できませんでした。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0590f43b-0aec-491f-bca5-c50ab12552a5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 720e84c9d2305b85ec79f76873778e476f670900
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354342"
---
# <a name="could-not-get-the-database-or-the-server-names"></a>データベース名またはサーバー名を取得できませんでした。
## <a name="details"></a>詳細  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |                     データベース名またはサーバー名を取得できませんでした。                     |

## <a name="explanation"></a>説明  
 このエラーは、BizTalk から読み取れませんでした BizTalkMgmtDb 名とサーバー名レジストリを示します。 このエラーの考えられる理由の 1 つは、BizTalk グループが構成されていません。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、BizTalk グループを構成します。  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. コンソール ルートで [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。  

3. 右クリックして**BizTalk グループ**します。  

4. **[プロパティ]** をクリックします。  

5. 左側のウィンドウで次のようにクリックします。**全般**します。  

6. 確認、 **Server**名と**データベース**名が正しい。
