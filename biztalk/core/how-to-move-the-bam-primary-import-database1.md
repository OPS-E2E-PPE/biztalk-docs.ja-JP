---
title: "BAM プライマリ インポート データベース 1 に移動する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migrating, Primary Import database [BAM]
- Primary Import database [BAM], migrating
ms.assetid: fab13fea-5c35-4a9f-977d-cc45545c54b2
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a63c556bfb95f4b22a3256540d3ecb336a17f7f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-move-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースを移動する方法
ここでは、BAM プライマリ インポート データベースを他のサーバーに移動する手順について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-move-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースを移動するには  
  
1.  BizTalk Server サービスをすべて停止します。 詳細については、次を参照してください。[開始、停止、一時停止、再開、または BizTalk Server サービスを再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)です。  
  
2.  IIS サービスを停止します。  
  
3.  BAM 警告の Notification Services を停止します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
        ```  
        Net stop NS$BamAlerts  
        ```  
  
4.  SQL Server Books Online に記載されている手順に従い、古いサーバーの BAM プライマリ インポート データベースをバックアップします。  
  
5.  BAM プライマリ インポート データベースを新しい SQL サーバーにコピーします。  
  
6.  SQL Server Books Online に記載されている手順に従い、新しいサーバーに BAM プライマリ インポート データベースを復元します。  
  
7.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が動作しているコンピューターで、次のフォルダーを参照します。  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore  
  
8.  右クリック**SampleUpdateInfo.xml**、クリックして**編集**です。  
  
9. ファイルのプライマリ インポート データベース セクションで置き換えます**"SourceServer"**ソース システムと、置換の名前を持つ**"DestinationServer"**送信先システムの名前に置き換えます。  
  
    > [!IMPORTANT]
    >  送信元システムおよび送信先システムの名前は、引用符で囲んでください。  
  
    > [!NOTE]
    >  いずれかの BizTalk Server データベースの名前を変更した場合、それに応じてデータベース名も更新する必要があります。  
  
10. xml ファイルの次の行のコメント化を解除します。  
  
    ```  
    - <UpdateConfiguration>  
      <MessageBoxDB oldDBName="BizTalkMsgboxDb" oldDBServer="Server01" newDBName="BizTalkMsgboxDb" newDBServer="Server01" IsMaster="1" />   
      <TrackingDB oldDBName="BizTalkDTADb" oldDBServer="Server01" newDBName="BizTalkDTADb" newDBServer="Server01" />   
      <ManagementDB oldDBName="BizTalkMgmtDb" oldDBServer="Server01" newDBName="BizTalkMgmtDb" newDBServer="Server01" />   
    - <BAM>  
    - <DeploymentUnit Name="OldPrimaryImportDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="PrimaryImportDatabase">  
      <Property Name="ServerName">Server02</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="ArchivingDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMArchive</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="AnalysisDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMAnalysis</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="StarSchemaDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMStarSchema</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="Alert">  
      <Property Name="DBServer">Server01</Property>   
      <Property Name="InstanceDatabaseName">BAMAlerts</Property>   
      </DeploymentUnit>  
      </BAM>  
    - <OtherDatabases>  
      <Database Name="SSO" oldDBName="SSODB" oldDBServer="Server01" newDBName="SSODB" newDBServer="Server01" />   
      </OtherDatabases>  
      </UpdateConfiguration>  
    ```  
  
11. ファイルの編集を終了したら、このファイルを保存して閉じます。  
  
12. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
13. コマンド プロンプトで、次のディレクトリに移動します  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema\Restore  
  
14. コマンド プロンプトで、次のように入力します。  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
15. すべての BAM ライブ データの Microsoft Excel ファイルで BAM プライマリ インポート データベースへの参照を更新します。 各ファイルで次の操作を実行します。  
  
    1.  Excel ライブ データ ファイルを開きます。 ファイル名の末尾は _LiveData.xls となっています。  
  
    2.  **BAM**  メニューをクリックして**BAM データベースの接続**です。  
  
    3.  **[BAM データベース**] ダイアログ ボックスでは、SQL Server および BAMPrimaryImport データベースを入力し、をクリックして**OK**です。  
  
    4.  **ファイル** メニューのをクリックして**閉じて Microsoft Excel へ戻る**です。  
  
    5.  **[ファイル]** メニューの **[保存]**をクリックします。  
  
16. 次の手順を実行して、すべての BAM 分析 DTS パッケージのサーバー名およびデータベース名を更新します。名前は "BAM_AN_" または "BAM_DM_" で始まります。  
  
    1.  BAM をホストするサーバーで、SQL Server Enterprise Manager を開きます。  
  
    2.  開く、**データ変換サービス**フォルダーです。  
  
    3.  開く、**ローカル パッケージ**フォルダー、DTS パッケージを開きます。  
  
    4.  **パッケージ** メニューのをクリックして**プロパティ**です。  
  
    5.  **グローバル変数** タブで、プライマリ インポート サーバーおよびデータベースの値を更新します。  
  
    6.  新しいサーバーおよびデータベースに対応するように、次の行を変更します。  
  
         PrimaryImportServer ="*\<ServerName\>*"  
  
         PrimaryImportDatabase ="*\<DatabaseName\>*"  
  
17. BizTalk Server サービスをすべて開始します。 詳細については、次を参照してください。[開始、停止、一時停止、再開、または BizTalk Server サービスを再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)です。  
  
18. IIS サービスを開始します。  
  
19. BAM 警告の Notification Services を開始します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
        ```  
        Net start NS$BamAlerts  
        ```  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースの移動](../core/moving-biztalk-server-databases.md)