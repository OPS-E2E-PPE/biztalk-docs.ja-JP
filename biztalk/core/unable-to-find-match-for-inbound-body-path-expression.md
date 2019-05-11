---
title: 受信本文のパス式に一致することができません。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0382348-96c4-414c-9dda-a390d491dee8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9199b959c4a120f294ef5cf30739bafccf901690
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266481"
---
# <a name="unable-to-find-match-for-inbound-body-path-expression"></a>受信本文のパス式に一致することができません。
## <a name="details"></a>詳細  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |       受信本文のパス式の一致が見つかりません"{0}"メッセージ       |

## <a name="explanation"></a>説明  
 受信メッセージで実行されるボディ パス式では、すべての一致が返されませんでした。  

## <a name="user-action"></a>ユーザーの操作  
 ボディ パス式が正しいことと、受信メッセージが適切なデータを確認してください。  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを見つけて、トランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. **[プロパティ]** をクリックします。  

6. ポート**型**一覧で、適切なポートを選択します。  

7. をクリックして**構成**です。  

8. Wcf **[**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブ。  

9. **受信 BizTalk メッセージ本文**セクションでの情報を確認、**本文のパス式**します。
