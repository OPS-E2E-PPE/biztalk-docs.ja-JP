---
title: トランザクション プロトコルがサポートされていない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11fb2497-9971-4e85-b21a-161734f071e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05023ca937ab8ff74323f4dbcbe52643e5efa01d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399462"
---
# <a name="unsupported-transaction-protocol"></a>サポートされていないトランザクション プロトコル
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                       サポートされていないトランザクション プロトコル: {0}                        |
  
## <a name="explanation"></a>説明  
 このエラーは、受信場所または送信ポートのトランザクション プロトコル プロパティが無効な値に設定されている場合に発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  
  
9. **トランザクション**セクションで、選択、**トランザクションを有効にする**オプション。  
  
10. **トランザクション プロトコル**ドロップダウン リストで、いずれかを選択**OleTransactions**または **[wsatomictransactions]** します。  
  
    次の手順は、次のトランスポートの種類にのみ適用されます。  
  
-   カスタム  
  
-   CustomIsolated  
  
-   NetNamedPipe  
  
-   NetTcp  
  
-   WShttp