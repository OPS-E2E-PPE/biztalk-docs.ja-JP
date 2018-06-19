---
title: バックアップおよび SQL エージェント ジョブを復元する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f82fc5a5-5ea5-476c-bed1-c5d41a50e673
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 253055f9a45dfdb9864d4d5202661e750d28b1b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247202"
---
# <a name="how-to-back-up-and-restore-sql-agent-jobs"></a>SQL エージェント ジョブのバックアップ方法と復元方法
このトピックでは、SQL Server エージェント ジョブをバックアップおよび復元する方法について説明します。 SQL ジョブを構成してからバックアップすることをお勧めします。  
  
## <a name="biztalk-server-jobs"></a>BizTalk Server のジョブ  
 以下の SQL Server エージェント ジョブが BizTalk Server と関連付けられています。 各サーバーにインストールされるジョブは、インストールされて構成されている機能によって異なります。 これらのジョブのほとんどは、BizTalk Server のセットアップ中に作成されます。 ログ配布の構成を行う際に作成されるものもあります。  
  
-   BizTalk Server のバックアップ (BizTalkMgmtDb)  
  
-   CleanupBTFExpiredEntriesJob_BizTalkMgmtDb  
  
-   DTA Purge and Archive (BizTalkDTADb)  
  
-   MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb  
  
-   MessageBox_Message_Cleanup_BizTalkMsgBoxDb  
  
-   MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb  
  
-   MessageBox_Parts_Cleanup_BizTalkMsgBoxDb  
  
-   MessageBox_UpdateStats_BizTalkMsgBoxDb  
  
-   Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb  
  
-   PurgeSubscriptionsJob_BizTalkMsgBoxDb  
  
-   Rules_Database_Cleanup_BizTalkRuleEngineDb  
  
-   TrackedMessages_Copy_BizTalkMsgBoxDb  
  
-   BTS ログの配布 - バックアップ履歴の取得  
  
-   BTS ログの配布 - データベースの復元  
  
-   BTS ログの配布 - マークまで復元  
  
## <a name="back-up-a-job-using-a-script"></a>スクリプトを使用してジョブをバックアップします。  
  
1.  開いている**SQL Server Management Studio**です。  
  
2.  **[SQL Server エージェント]** を展開し、**[ジョブ]** を展開します。  
  
3.  では、バックアップ スクリプトを作成し、選択するジョブを右クリックして**ジョブをスクリプト**です。  
  
4.  選択**Create**または**Drop**選択してから、**新しいクエリ エディター ウィンドウ**、**ファイル**、または**クリップボード**スクリプトの保存先を選択します。 通常、変換先は、ファイルが、 **.sql**拡張機能です。  
  
5.  スクリプトを作成する各ジョブについて、手順 3. から繰り返します。 BizTalk Server 関連ジョブの一覧を参照して、どのジョブのスクリプトを作成するかを判断してください。  
  
     バックアップするには、少なくとも、 **Backup BizTalk Server (BizTalkMgmtDb)** ジョブを構成後します。  
  
## <a name="restore-a-job-from-a-script"></a>スクリプトからジョブを復元します。  
  
1.  開いている**SQL Server Management Studio**です。  
  
2.  **ファイル**] メニューの [**開く**スクリプト化されたジョブを含むファイルです。  
  
3.  スクリプトを実行してジョブを作成します。  
  
## <a name="next-steps"></a>次の手順  
 [バックアップおよび SQL Server ログインを復元する方法](../core/how-to-back-up-and-restore-sql-server-logins.md)