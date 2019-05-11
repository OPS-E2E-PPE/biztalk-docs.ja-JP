---
title: バックアップおよび SQL エージェント ジョブを復元する方法 |Microsoft Docs
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
ms.openlocfilehash: ea39b09736904a6ba9ef7d19dc20e833b1d1f351
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342487"
---
# <a name="how-to-back-up-and-restore-sql-agent-jobs"></a>バックアップおよび SQL エージェント ジョブを復元する方法
このトピックでは、バックアップおよび SQL Server エージェント ジョブを復元する方法について説明します。 それらを構成した後は、SQL ジョブをバックアップする必要があります。  
  
## <a name="biztalk-server-jobs"></a>BizTalk Server ジョブ  
 次の SQL Server エージェント ジョブは、BizTalk Server に関連付けられます。 各サーバーにインストールされているジョブは、どの機能がインストールされ、構成によって異なります。 これらのジョブのほとんどは、BizTalk Server のセットアップ中に作成されます。 ログ配布を構成するときにいくつか作成されます。  
  
-   BizTalk Server (BizTalkMgmtDb) のバックアップします。  
  
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
  
-   BTS ログの配布のバックアップ履歴の取得  
  
-   BTS ログの配布の復元データベース  
  
-   BTS ログのマークまで復元の配布  
  
## <a name="back-up-a-job-using-a-script"></a>スクリプトを使用してジョブをバックアップします。  
  
1.  **SQL Server Management Studio** を開きます。  
  
2.  展開**SQL Server エージェント**、展開と**ジョブ**します。  
  
3.  バックアップ スクリプトを作成し、選択するジョブを右クリックして**ジョブをスクリプト化**します。  
  
4.  選択**Create**または**Drop**を選択し、**新しいクエリ エディター ウィンドウ**、**ファイル**、または**クリップボード**スクリプトの宛先を選択します。 コピー先のファイルは、通常、 **.sql**拡張機能。  
  
5.  各ジョブのスクリプトを作成するには、手順 3. からこの手順を繰り返します。 一覧を参照してください。 BizTalk Server に関連するどのジョブを確認するジョブをスクリプトする必要があります。  
  
     少なくともをバックアップする必要があります、 **BizTalk Server のバックアップ (BizTalkMgmtDb)** ジョブの構成が完了後します。  
  
## <a name="restore-a-job-from-a-script"></a>スクリプトからジョブを復元します。  
  
1.  **SQL Server Management Studio** を開きます。  
  
2.  **ファイル**] メニューの [**オープン**スクリプト化されたジョブを含むファイル。  
  
3.  ジョブを作成するスクリプトを実行します。  
  
## <a name="next-steps"></a>次の手順  
 [バックアップおよび SQL Server ログインを復元する方法](../core/how-to-back-up-and-restore-sql-server-logins.md)