---
title: 受信本文のパス式のコンテンツが見つかりません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed294662-a94e-4fbb-b125-878a27107eab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9de18c9d3fa7ccf89a33eb6b09e6c11381a73a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972027"
---
# <a name="unable-to-find-content-for-inbound-body-path-expression"></a>受信本文のパス式のコンテンツが見つかりません
## <a name="details"></a>詳細  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |      受信本文のパス式のコンテンツが見つかりません"{0}"メッセージ      |

## <a name="explanation"></a>説明  
 本文のパス式を実行して受信メッセージから抽出されるコンテンツに、データが含まれません。  

## <a name="user-action"></a>ユーザーの操作  
 本文のパス式が正しいこと、および受信メッセージのデータが正しいことを確認します。  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを特定し、次にトランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. **[プロパティ]** をクリックします。  

6. ポート**型**一覧で、適切なポートを選択します。  

7. クリックして**構成**します。  

8. Wcf **[**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブ。  

9. **受信 BizTalk メッセージ本文**セクションでの情報を確認、**本文のパス式**します。
