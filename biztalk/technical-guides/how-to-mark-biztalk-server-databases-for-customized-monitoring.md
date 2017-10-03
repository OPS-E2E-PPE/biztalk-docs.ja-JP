---
title: "マーク BizTalk Server データベースのカスタマイズを監視する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfbdc73d-a108-42ee-a5d8-401d5bfe5e7d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08807b1a365b84765221e3a71cb131d8c037fcf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-mark-biztalk-server-databases-for-customized-monitoring"></a>カスタマイズした監視の BizTalk Server データベースをマークする方法
Microsoft がインストールされている場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックは、方法をカスタマイズすることができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のデータベースを監視します。 これにより、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックは、次の監視[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
-   BAM アーカイブ (BAMArchive) データベース  
  
-   BAM プライマリ インポート (BAMPrimaryImport) データベース  
  
-   BAM スター スキーマ (BAMStarSchema) データベース  
  
-   BizTalk 追跡 (BizTalkDTADb) データベース  
  
-   BizTalk 管理 (BizTalkMgmtDb) データベース  
  
-   BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース  
  
-   ルール エンジン (BizTalkRuleEngineDb) データベース  
  
-   エンタープライズ シングル サインオン (SSODB) データベース  
  
> [!NOTE]  
>  Operations Manager の高度なオペレータ ロールのメンバーとしてログオンする必要がありますまたは[!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)]管理グループです。  
  
### <a name="to-mark-biztalk-server-databases-for-customized-monitoring"></a>監視をカスタマイズする場合は、BizTalk Server データベースをマークするには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**System Center Operations Manager 2007**、順にクリック**オペレーション コンソール**です。  
  
2.  オペレーション コンソールで、 **Authoring**ボタンをクリックします。  
  
3.  **Authoring**  ウィンドウで、展開**管理パック オブジェクト**、クリックして**オブジェクト検出**です。  
  
4.  SQL Server の検出を検索するオペレーション コンソール ツールバーのをクリックして**検索**、し、、**探します**テキスト ボックスに「 **SQL 2008** SQL Server 2008 を検索しますします。  
  
5.  下にある、**検出された種類: SQL 2008 DB**カテゴリで、**データベース エンジンのデータベースの検出**です。  
  
6.  オペレーション コンソール ツールバーで、をクリックして**オーバーライド**順にポイントして**オブジェクト検出の上書き**です。 に対して、特定の種類のオブジェクトまたはグループ内のすべてのオブジェクトの検出の上書きを選択できます。 無効にするオブジェクトの種類のグループを選択した後、**上書きのプロパティ** ダイアログ ボックスが表示されます。  
  
    > [!NOTE]  
    >  場合、**オーバーライド**ボタンは使用できません、[モニタ] ウィンドウで、モニター、コンテナー オブジェクトではなくを選択したかどうかを確認します。  
  
7.  チェック ボックスをオン、**オーバーライド**隣の列、**除外リスト**パラメーター、し、[、**上書き値**] 列を除外するデータベースの名前を入力監視します。 確認、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を監視するデータベースが記載されていない、**上書き値**列です。  
  
    > [!TIP]  
    >  変更されたオブジェクト検出を使用すると、新しい管理パックを作成します。 ウィンドウの下部にある、**目的の管理パックを選択して**ドロップダウンの既定値が表示**既定の管理パック**です。 をクリックして**新規**変更済みオブジェクト検出を使用して新しい管理パックを作成します。  
  
## <a name="see-also"></a>参照  
 [SQL サーバーの監視](../technical-guides/monitoring-sql-servers.md)