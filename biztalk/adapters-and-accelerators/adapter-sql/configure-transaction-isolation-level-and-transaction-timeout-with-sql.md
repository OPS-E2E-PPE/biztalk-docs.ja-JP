---
title: "SQL を使用したトランザクションの分離レベルとトランザクションのタイムアウトを構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55355272-60c0-49e4-b37e-9198458ab305
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e75d63118c24602439434c9c7ba281fa9cbc7805
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-sql"></a>SQL を使用したトランザクションの分離レベルとトランザクションのタイムアウトを構成します。
入力方向の操作 (ポーリングおよび通知) を実行中を使用して、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、トランザクション分離レベルとトランザクションのタイムアウト値を適切に構成する必要があります。 これを行うには :  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで、展開、 **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
4.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。  
  
5.  **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
6.  左側のウィンドウで、**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**受信場所**、順にクリック**新規**受信場所を新しい定義の右側のウィンドウでします。  
  
7.  **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**Wcf-custom**で、**型** ボックスの一覧です。  
  
8.  をクリックして**構成**の横にある、**型** ボックスの一覧です。  
  
9. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブです。  
  
10. **動作**ボックスの一覧を右クリックして**ServiceBehavior**、 をクリック**拡張機能を追加**です。  
  
11. **動作拡張機能の選択**ダイアログ ボックスで、 **sqlAdapterInboundTransactionBehavior**、 をクリック**OK**です。  
  
12. 左側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**、select、 **sqlAdapterInboundTransactionBehavior**下にあるサービス**ServiceBehavior**です。 受信 (受信操作のメッセージ)、1 つを使用して、sqlAdapterInboundTransactionBehavior 分離レベルを制御し、既定値は**ReadCommitted**です。  
  
13. 右側のペインで、 **Wcf-custom トランスポートのプロパティ**、適切な値を指定、 **transactionIsolationLevel**と**transactionTimeout**パラメーター。 次のトランザクション分離レベルのいずれかを選択することができます: **Serializable**、 **RepeatableRead**、 **ReadCommitted**、 **ReadUncommitted**、**スナップショット**、 **Chaos**、および**未指定**です。  
  
    > [!NOTE]
    >  トランザクション分離レベルの既定値は**Serializable** WCF-SQL アダプターの受信と送信の両方の操作をします。 これらのトランザクション分離レベルについては、次を参照してください。、**メンバー**セクションで[分離レベルの列挙体](http://go.microsoft.com/fwlink/?LinkId=126983)(http://go.microsoft.com/fwlink/?LinkId=126983)。  
  
     ![トランザクション分離レベルに設定する](../../adapters-and-accelerators/adapter-sql/media/b39c180e-ca9f-48ca-9550-f4837826d00e.gif "b39c180e-ca9f-48ca-9550-f4837826d00e")  
  
14. をクリックして**OK**で、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。  
  
15. をクリックして**OK**変更を保存する開いているダイアログ ボックスでします。