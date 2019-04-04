---
title: SQL を使用したトランザクション分離レベルとトランザクションのタイムアウトの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55355272-60c0-49e4-b37e-9198458ab305
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2783b8741a7f8a703ad8aae22db5b114ea20f0b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013139"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-sql"></a>SQL を使用したトランザクション分離レベルとトランザクションのタイムアウトを構成します。
(ポーリングと通知) の受信操作の実行中を使用して、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、トランザクション分離レベルとトランザクションのタイムアウト値を適切に構成する必要があります。 これを行うには :  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開、 **BizTalk グループ**、順に展開**アプリケーション**します。  

3. 展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

4. 右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  

5. **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  

6. 左側のウィンドウで、**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**受信場所**、順にクリックします**新規**右側のウィンドウで、新しい定義には、受信場所。  

7. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**Wcf-custom**で、**型**一覧。  

8. クリックして**構成**の横にある、**型**一覧。  

9. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブ。  

10. **動作**一覧で、右クリックして**ServiceBehavior**、 をクリック**拡張機能の追加**します。  

11. **動作拡張機能の選択**ダイアログ ボックスで、 **sqlAdapterInboundTransactionBehavior**、 をクリック**OK**します。  

12. 左側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**を選択、 **sqlAdapterInboundTransactionBehavior**サービス**ServiceBehavior**します。 1 つの受信 (受信操作のメッセージ) は、分離レベルを制御する、sqlAdapterInboundTransactionBehavior を使用して、既定値は**ReadCommitted**します。  

13. 右側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**、適切な値を指定、 **transactionIsolationLevel**と**transactionTimeout**パラメーター。 次のトランザクション分離レベルのいずれかを選択することができます: **Serializable**、 **RepeatableRead**、 **ReadCommitted**、 **ReadUncommitted**、**スナップショット**、**混乱**、および**未指定**します。  

    > [!NOTE]
    >  トランザクション分離レベルの既定値は**Serializable** WCF-SQL アダプターの受信と送信の両方の操作をします。 これらのトランザクション分離レベルについては、、**メンバー**セクションで[分離レベルの列挙体](http://go.microsoft.com/fwlink/?LinkId=126983)(http://go.microsoft.com/fwlink/?LinkId=126983)を参照してください。  

     ![トランザクション分離レベルの設定](../../adapters-and-accelerators/adapter-sql/media/b39c180e-ca9f-48ca-9550-f4837826d00e.gif "b39c180e-ca9f-48ca-9550-f4837826d00e")  

14. クリックして**OK**で、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。  

15. をクリックして**OK**変更を保存する [開く] ダイアログ ボックス。
