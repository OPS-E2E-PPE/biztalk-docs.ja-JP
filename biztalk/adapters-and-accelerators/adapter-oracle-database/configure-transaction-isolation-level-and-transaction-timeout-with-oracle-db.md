---
title: Oracle データベースとトランザクション分離レベルとトランザクションのタイムアウトの構成 |Microsoft Docs
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
ms.openlocfilehash: 3fa97e17f29775059c6f8d80818a177cd640abd4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970131"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-oracle-database"></a>Oracle データベースとトランザクション分離レベルとトランザクションのタイムアウトを構成します。
使用して受信操作 (ポーリング) を実行中に、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、トランザクション分離レベルとトランザクションのタイムアウト値を適切に構成する必要があります。 これを行うには :  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開、 **BizTalk グループ**、順に展開**アプリケーション**します。  

3. 使用してメタデータを生成した後で展開されている BizTalk アプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  

4. 右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  

5. **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  

6. 左側のウィンドウで、**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**受信場所**、順にクリックします**新規**右側のウィンドウで、新しい定義には、受信場所。  

7. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**Wcf-custom**で、**型**一覧。  

8. クリックして**構成**の横にある、**型**一覧。  

9. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブ。  

10. **動作**一覧で、右クリックして**ServiceBehavior**、 をクリック**拡張機能の追加**します。  

11. **動作拡張機能の選択**ダイアログ ボックスで、 **oracleDBAdapterInboundTransactionBehavior**、 をクリック**OK**します。  

12. 左側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**を選択、 **oracleDBAdapterInboundTransactionBehavior**サービス**ServiceBehavior**します。  

13. 右側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**、適切な値を指定、 **transactionIsolationLevel**と**transactionTimeout**パラメーター。 次のトランザクション分離レベルのいずれかを選択することができます: **Serializable**、 **RepeatableRead**、 **ReadCommitted**、 **ReadUncommitted**、**スナップショット**、**混乱**、および**未指定**します。 これらのトランザクション分離レベルについては、次を参照してください。、**メンバー**セクションで[ http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983)します。  

    > [!IMPORTANT]
    >  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の 2 つのトランザクション分離レベルのみをサポートしています。 ReadCommitted および Serializable。  

     ![トランザクション分離レベルの設定](../../adapters-and-accelerators/adapter-oracle-database/media/96a66f86-0321-4aa6-9e72-ada30d7de064.gif "96a66f86-0321-4aa6-9e72-ada30d7de064")  

14. クリックして**OK**で、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。  

15. をクリックして**OK**変更を保存する [開く] ダイアログ ボックス。
