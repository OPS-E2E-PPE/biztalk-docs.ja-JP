---
title: サポートされていないセキュリティ アルゴリズム スイート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11696fed-c3a8-4b11-8249-9f99f7abc8f2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f8b66c1047dde836f965f6ab6345973d3525db4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398637"
---
# <a name="unsupported-security-algorithm-suite"></a>サポートされていないセキュリティ アルゴリズム スイート
## <a name="details"></a>詳細  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                     サポートされていないセキュリティ アルゴリズム スイート。 {0}                      |

## <a name="explanation"></a>説明  
 このエラーは、受信場所または送信ポートのセキュリティ アルゴリズム スイート プロパティが、間違った値に設定されている場合に発生します。  

## <a name="user-action"></a>ユーザーの操作  
 トランザクション プロトコルのプロパティが有効な値に設定されていることを確認します。  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを見つけて、トランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. **[プロパティ]** をクリックします。  

6. ポート**型**一覧で、 **Wcf-nettcp**します。  

7. をクリックして**構成**です。  

8. **Wcf-nettcp トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。  

9. **メッセージ セキュリティ**セクションでは、値を必ず**アルゴリズム スイート**が正しい。
