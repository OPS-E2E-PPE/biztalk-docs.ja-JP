---
title: トランザクションの要求-応答の受信場所はサポートされていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c89b619-280c-4ab5-b6aa-06b14a075f8e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37cea795e097596862e14f64b825696511ffbe6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399199"
---
# <a name="transactional-request-response-receive-location-is-not-supported"></a>トランザクションの要求 - 応答の受信場所がサポートされていません
## <a name="details"></a>詳細  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |         トランザクションの要求-応答の受信場所はサポートされていません。          |

## <a name="explanation"></a>説明  
 このエラーは、WCF 要求-応答の受信場所用に有効にするトランザクションが設定されたことを示します。 トランザクションは、要求-応答の受信、メッセージ ボックス データベースのための場所の BizTalk ではサポートされていません。  

## <a name="user-action"></a>ユーザーの操作  
 標準の WCF アダプターの要求-応答を構成するコードに移動して受信場所を使用します。 いることを確認、 **EnableTransaction**用の XML データ内の要素、 **TransportTypeData**のプロパティ、 **ITransportInfo**に設定されているインターフェイス**False**.  

 Wcf-custom アダプター。  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを見つけて、トランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. **[プロパティ]** をクリックします。  

6. ポート**型**一覧で、適切なポートを選択します。  

7. をクリックして**構成**です。  

8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  

9. TransactionFlow プロパティに設定されるように**False**します。
