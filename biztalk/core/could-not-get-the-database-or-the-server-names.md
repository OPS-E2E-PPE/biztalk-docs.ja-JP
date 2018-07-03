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
ms.openlocfilehash: 6e2d346c2771328ac67df3e2aa7454288779cb9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990267"
---
# <a name="could-not-get-the-database-or-the-server-names"></a>データベース名またはサーバー名を取得できませんでした
## <a name="details"></a>詳細  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |                     データベース名またはサーバー名を取得できませんでした                     |

## <a name="explanation"></a>説明  
 このエラーは、BizTalk がレジストリから BizTalkMgmtDb 名とサーバー名を読み取れなかったことを示します。 このエラーの考えられる原因の 1 つとして、BizTalk グループが構成されていないことがあります。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のようにして BizTalk グループを構成します。  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. コンソール ルートで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]] を展開します。  

3. 右クリックして**BizTalk グループ**します。  

4. **[プロパティ]** をクリックします。  

5. 左側のウィンドウで次のようにクリックします。**全般**します。  

6. 確認、 **Server**名と**データベース**名が正しい。
