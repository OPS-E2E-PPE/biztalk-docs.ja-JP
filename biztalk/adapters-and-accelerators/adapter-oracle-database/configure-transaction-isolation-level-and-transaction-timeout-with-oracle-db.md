---
title: Oracle データベースとトランザクション分離レベルとトランザクションのタイムアウトを構成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b66e764-2330-441b-89ef-29118f27b366
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13d1beea3be34dbd818a94986fb8cae876bcdd81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214514"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-oracle-database"></a>Oracle データベースとトランザクション分離レベルとトランザクションのタイムアウトを構成します。
使用して受信操作 (ポーリング) を実行中に、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、トランザクション分離レベルとトランザクションのタイムアウト値を適切に構成する必要があります。 これを行うには :  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで、展開、 **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  使用してメタデータの生成後に展開した BizTalk アプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
4.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。  
  
5.  **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
6.  左側のウィンドウで、**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**受信場所**、順にクリック**新規**受信場所を新しい定義の右側のウィンドウでします。  
  
7.  **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**Wcf-custom**で、**型** ボックスの一覧です。  
  
8.  をクリックして**構成**の横にある、**型** ボックスの一覧です。  
  
9. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブです。  
  
10. **動作**ボックスの一覧を右クリックして**ServiceBehavior**、 をクリック**拡張機能を追加**です。  
  
11. **動作拡張機能の選択**ダイアログ ボックスで、 **oracleDBAdapterInboundTransactionBehavior**、 をクリック**OK**です。  
  
12. 左側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**、select、 **oracleDBAdapterInboundTransactionBehavior**下にあるサービス**ServiceBehavior**です。  
  
13. 右側のペインで、 **Wcf-custom トランスポートのプロパティ**、適切な値を指定、 **transactionIsolationLevel**と**transactionTimeout**パラメーター。 次のトランザクション分離レベルのいずれかを選択することができます: **Serializable**、 **RepeatableRead**、 **ReadCommitted**、 **ReadUncommitted**、**スナップショット**、 **Chaos**、および**未指定**です。 これらのトランザクション分離レベルについては、次を参照してください。、**メンバー**セクションで[http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983)です。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の 2 つのトランザクション分離レベルのみをサポートしています: ReadCommitted および Serializable です。  
  
     ![トランザクション分離レベルに設定する](../../adapters-and-accelerators/adapter-oracle-database/media/96a66f86-0321-4aa6-9e72-ada30d7de064.gif "96a66f86-0321-4aa6-9e72-ada30d7de064")  
  
14. をクリックして**OK**で、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。  
  
15. をクリックして**OK**変更を保存する開いているダイアログ ボックスでします。