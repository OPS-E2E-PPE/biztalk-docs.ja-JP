---
title: "アンインストールし、それを削除する BizTalk Server の構成を解除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9ea8757-ca49-421b-bf7b-89344201398a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce643460d7c5256829624de5ba4c32d664c26ac3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="uninstall-and-unconfigure-biztalk-server-to-remove-it"></a>BizTalk Server の削除 (アンインストールおよび構成の解除)
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のアンインストールおよび構成解除を行います。 
  
##  <a name="BKMK_BeforeYouBegin"></a> はじめに  
  
-   アンインストールする前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成を解除する必要があります。  
  
-   このトピックでは、削除されるジョブ、パッケージ、データベースの名前が記載されています。 ここに記載されている名前は、既定の名前です。 お使いの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境では、既定の名前を使用していない場合があります。  
  
-   手順は、ここに示している順序どおりに実行してください。 順序が変わるとアンインストールを完了できません。  
  
##  <a name="BKMK_Unconfigure"></a> BizTalk Server の構成解除  
  
1.  **[[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成]** を右クリックし、**[管理者として実行]** を選択します。  
  
2.  [構成] で **[機能の構成解除]** を選択します。  
  
3.  構成を解除する機能を選択し、**[OK]** を選択します。 続行を確認するメッセージが表示されたら、**[はい]** を選択します。 コンピューターからすべて削除する場合は、すべての機能を選択できます。  
  
4.  **[次へ]** を選択し、ウィザードを進みます。  
  
 C:\Users\ユーザー名\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log のようなログ ファイルが一時フォルダーに生成されます。  
  
##  <a name="BKMK_Uninstall"></a> BizTalk Server ランタイム コンポーネントのアンインストール  
  
1.  **[プログラムと機能]** を開きます。  
  
2.  リストから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バージョンを選択し、**アンインストール**します。  
  
3.  **削除**して、ウィザードを進みます。  
  
 C:\Users\\*ユーザー名*\AppData\Local\Setup(083016 xxxxxx).htm のようなログ ファイルが一時フォルダーに生成されます。  
  
##  <a name="BKMK_UninstallSSO"></a> Enterprise Single Sign-On のアンインストール  
  
1.  **[プログラムと機能]** を開きます。  
  
2.  リストから **[Microsoft Enterprise Single Sign-On]** を選択し、**アンインストール**します。  
  
3.  **削除**して、ウィザードを進みます。  
  
 C:\Users\\*ユーザー名*\AppData\Local\Setup(083016 xxxxxx).htm のようなログ ファイルが一時フォルダーに生成されます。  
  
##  <a name="BKMK_RemoveRemaining"></a> SQL ジョブ、データベース、およびパッケージを削除する  
  
#### <a name="delete-sql-server-agent-jobs"></a>SQL Server エージェント ジョブの削除  
  
1.  **SQL Server Management Studio** を管理者として開きます。  
  
2.  **SQL Server Management Studio** で、**データベース エンジン**に接続し、**[SQL Server エージェント]**、**[ジョブ]** の順に展開します。  
  
3.  次のジョブを削除します (ジョブを右クリックし、**[削除]** を選択します)。  
  
    -   BizTalk Server のバックアップ (BizTalkMgmtDb)  
  
    -   CleanupBTFExpiredEntriesJob_BizTalkMgmtDb  
  
    -   DTA Purge and Archive (BizTalkDTADb)  
  
    -   MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb  
  
    -   MessageBox_Parts_Cleanup_BizTalkMsgBoxDb  
  
    -   MessageBox_UpdateStats_BizTalkMsgBoxDb  
  
    -   BizTalk Server の監視 (BizTalkMgmtDb)  
  
    -   Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb  
  
    -   PurgeSubscriptionsJob_BizTalkMsgBoxDb  
  
    -   Rules_Database_Cleanup_BizTalkRuleEngineDb  
  
    -   TrackedMessages_Copy_BizTalkMsgBoxDb  
  
        > [!NOTE]
        >  BAM を展開した場合、bam _ を削除する必要がありますも\<*キューブ名*> _\<*ビュー名*> ジョブです。  
  
#### <a name="delete-biztalk-server-databases"></a>BizTalk Server データベースの削除  
  
1.  **オブジェクト エクスプローラー**で、**[データベース]** を展開します。  
  
2.  次のデータベースを削除します (データベースを右クリックし、**[削除]** を選択します)。  
  
    -   BAMArchive  
  
    -   BAMPrimaryImport  
  
    -   BAMStarSchema  
  
    -   BizTalkDTADb  
  
    -   BizTalkMgmtDb  
  
    -   BizTalkMsgBoxDb  
  
    -   BizTalkRuleEngineDb  
  
    -   SSODB  
  
#### <a name="remove-sql-server-integration-services-packages"></a>SQL Server Integration Services パッケージの削除  
  
1.  **オブジェクト エクスプローラー**で、**Integration Services** に**接続**します。  
  
2.  **[格納されたパッケージ]** を展開し、**[MSDB]** を展開します。  
  
3.  次のプレフィックスを持つパッケージを削除します (パッケージを右クリックし、**[削除]** を選択します)。  
  
    -   Bam_an _\<*キューブ名*>  
  
    -   Bam_dm _\<*ビュー名*>  
  
