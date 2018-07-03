---
title: カスタマイズした監視用データベースを BizTalk Server のマークする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfbdc73d-a108-42ee-a5d8-401d5bfe5e7d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea069140b9dd89fafa13fe57be9eefa17eceb790
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023712"
---
# <a name="how-to-mark-biztalk-server-databases-for-customized-monitoring"></a>カスタマイズした監視用の BizTalk Server データベースをマークする方法
Microsoft がインストールされている場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックは、方法をカスタマイズする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のデータベースを監視します。 これにより、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックは、次の監視[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
-   BAM アーカイブ (BAMArchive) データベース  
  
-   BAM プライマリ インポート (BAMPrimaryImport) データベース  
  
-   BAM スター スキーマ (BAMStarSchema) データベース  
  
-   BizTalk 追跡 (BizTalkDTADb) データベース  
  
-   BizTalk 管理 (BizTalkMgmtDb) データベース  
  
-   BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース  
  
-   ルール エンジン (BizTalkRuleEngineDb) データベース  
  
-   エンタープライズ シングル サインオン (SSODB) データベース  
  
> [!NOTE]
>  Operations Manager の高度なオペレータ ロールのメンバーとしてログオンする必要がありますまたは[!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)]管理グループ。  
  
### <a name="to-mark-biztalk-server-databases-for-customized-monitoring"></a>監視をカスタマイズするは、BizTalk Server データベースをマークするには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**System Center Operations Manager 2007**、順にクリックします**オペレーション コンソール**します。  
  
2. オペレーション コンソールでをクリックして、 **Authoring**ボタンをクリックします。  
  
3. **Authoring**ウィンドウで、展開**管理パック オブジェクト**、 をクリックし、**オブジェクト検出**します。  
  
4. SQL Server の検出を見つけ、オペレーション コンソール ツールバーをクリックして**検索**、し、**探して**テキスト ボックスに「 **SQL 2008** SQL Server 2008 を検索しますします。  
  
5. で、**検出された種類: SQL 2008 DB**カテゴリで、**データベース エンジンのデータベースの検出**します。  
  
6. オペレーション コンソール ツールバーで、次のようにクリックします。**オーバーライド**順にポイント**オブジェクト検出の上書き**します。 に対して、特定の種類のオブジェクトまたはグループ内のすべてのオブジェクトの検出の上書きを選択することができます。 オーバーライドするにはオブジェクトの種類のグループを選択した後、**上書きのプロパティ** ダイアログ ボックスが表示されます。  
  
   > [!NOTE]  
   >  場合、**オーバーライド**ボタンは使用できません [モニタ] ウィンドウで、モニター、コンテナー オブジェクトではなくを選択したかどうかを確認してください。  
  
7. チェック ボックスをオン、**オーバーライド**列隣に、**除外リスト**パラメーター、し、**上書き値** 列を除外するデータベースの名前を入力監視します。 必ず、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を監視するデータベースが記載されていない、**上書き値**列。  
  
   > [!TIP]  
   >  変更されたオブジェクトの検出を使用すると、新しい管理パックを作成します。 ウィンドウの下部にある、**目的の管理パックを選択します。** ドロップダウンの既定値を示しています**既定の管理パック**します。 クリックして**新規**変更オブジェクト検出を使用して新しい管理パックを作成します。  
  
## <a name="see-also"></a>参照  
 [SQL Server の監視](../technical-guides/monitoring-sql-servers.md)