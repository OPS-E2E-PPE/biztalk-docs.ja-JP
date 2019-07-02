---
title: アンインストールし、それを削除する BizTalk Server の構成を解除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9ea8757-ca49-421b-bf7b-89344201398a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df844f6fce54b7be266a068561638b512a687924
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401462"
---
# <a name="uninstall-and-unconfigure-biztalk-server-to-remove-it"></a>アンインストールし、それを削除する BizTalk Server の構成を解除
アンインストールし、構成解除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 
  
##  <a name="BKMK_BeforeYouBegin"></a> はじめに  
  
- 解除する必要があります、アンインストールする前に、構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
- このトピックでは、さまざまなジョブ、パッケージ、および削除するデータベースを一覧表示します。 表示名は、既定の名前です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境に既定以外の名前を使用することがあります。  
  
- 表示されている順序で手順を実行します。 それ以外の場合、アンインストールは完了しません。  
  
##  <a name="BKMK_Unconfigure"></a> BizTalk Server の構成を解除  
  
1. 右クリック **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成**、選び**管理者として実行**します。  
  
2. 構成では、次のように選択します。**機能の構成解除**します。  
  
3. この構成を解除すると、選択する機能の選択**OK**します。 続行するように求められたら、選択**はい**します。 コンピューターからすべてのものを削除するには、すべての機能を選択できます。  
  
4. 選択**次**、し、ウィザードを続行します。  
  
   ような一時フォルダーには、ログ ファイルが生成されます。C:\Users\username\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log.  
  
##  <a name="BKMK_Uninstall"></a> BizTalk Server ランタイム コンポーネントをアンインストールします。  
  
1. 開いている**プログラムと機能**します。  
  
2. 選択、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]リストから、バージョンと**アンインストール**します。  
  
3. **削除**し、ウィザードを続行します。  
  
   ような一時フォルダーには、ログ ファイルが生成されます。C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm  
  
##  <a name="BKMK_UninstallSSO"></a> エンタープライズ シングル サインオンのアンインストールします。  
  
1. 開いている**プログラムと機能**します。  
  
2. 選択**Microsoft エンタープライズ シングル サインオン**リストから、および**アンインストール**します。  
  
3. **削除**し、ウィザードを続行します。  
  
   ような一時フォルダーには、ログ ファイルが生成されます。C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm  
  
##  <a name="BKMK_RemoveRemaining"></a> SQL ジョブ、データベース、およびパッケージを削除します。  
  
#### <a name="delete-sql-server-agent-jobs"></a>SQL Server エージェント ジョブを削除します。  
  
1.  開いている**SQL Server Management Studio**管理者として。  
  
2.  **SQL Server Management Studio**への接続**データベース エンジン**、展開**SQL Server エージェント**、展開と**ジョブ**します。  
  
3.  次のジョブを削除 (ジョブを右クリックし、選択**削除**)。  
  
    -   BizTalk Server (BizTalkMgmtDb) のバックアップします。  
  
    -   CleanupBTFExpiredEntriesJob_BizTalkMgmtDb  
  
    -   DTA Purge and Archive (BizTalkDTADb)  
  
    -   MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb  
  
    -   MessageBox_Parts_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_UpdateStats_BizTalkMsgBoxDb  
  
    -   BizTalk Server (BizTalkMgmtDb) の監視します。  
  
    -   Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb  
  
    -   PurgeSubscriptionsJob_BizTalkMsgBoxDb  
  
    -   Rules_Database_Cleanup_BizTalkRuleEngineDb  
  
    -   TrackedMessages_Copy_BizTalkMsgBoxDb  
  
        > [!NOTE]
        >  BAM を展開した場合、bam _ を削除する必要がありますも\<*キューブ名*\>_\<*ビュー名*\>ジョブ。  
  
#### <a name="delete-biztalk-server-databases"></a>BizTalk Server データベースを削除します。  
  
1.  **オブジェクト エクスプ ローラー**、展開**データベース**します。  
  
2.  次のデータベースの削除 (データベースを右クリックして**削除**)。  
  
    -   BAMArchive  
  
    -   BAMPrimaryImport  
  
    -   BAMStarSchema  
  
    -   BizTalkDTADb  
  
    -   BizTalkMgmtDb  
  
    -   BizTalkMsgBoxDb  
  
    -   BizTalkRuleEngineDb  
  
    -   SSODB  
  
#### <a name="remove-sql-server-integration-services-packages"></a>SQL Server Integration Services パッケージを削除します。  
  
1.  **オブジェクト エクスプ ローラー**、**接続**に**Integration Services**します。  
  
2.  展開**格納されたパッケージ**、展開と**MSDB**します。  
  
3.  次のプレフィックスを持つパッケージを削除する (パッケージを右クリックして**削除**)。  
  
    -   Bam_an _\<*キューブ名*\>  
  
    -   Bam_dm _\<*ビュー名*\>  
  
