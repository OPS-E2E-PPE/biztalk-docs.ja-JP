---
title: "BAM プライマリ インポート データベース名および接続文字列への参照を更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- restoring [BAM], connection strings
- Primary Import database [BAM], updating references
- connection strings, restoring
- connection strings, BAM
- restoring, BAM
- restoring [BAM], Primary Import database
- restoring [BAM], updating references
- Primary Import database [BAM], restoring
- BAM, restoring
- restoring, connection strings
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b56264155ed9f739669da1cb6f646adac0f9db55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-references-to-the-bam-primary-import-database-name-and-connection-string"></a>BAM プライマリ インポート データベース名および接続文字列への参照を更新する方法
BAMPrimaryImport データベースをバックアップしておくと、システムまたはデータに障害が発生したときに、別のコンピューターにバックアップを復元し、その名前を変更することができます。  
  
 BAM イベント バス サービスでは、イベント データをメッセージ ボックス データベースから BAMPrimaryImport データベースに移動します。 BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。 BAM イベント バス サービスの詳細については、次を参照してください。 [BAM イベント バス サービスを管理する](../core/managing-the-bam-event-bus-service.md)です。  
  
 BAMPrimaryImport データベースを復元する」の手順を実行[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。 これらの手順を実行したうえで、次の手順を実行します (詳細な手順については後述)。  
  
-   すべての BAM DTS パッケージで、SQL 接続 1 の参照先が新しいデータベース名になるように更新します。  
  
-   新しいデータベース名で web.config ファイルを更新します。  
  
-   すべての BAM ライブ データの Microsoft Excel ファイルで BAMPrimaryImport データベースへの参照を更新します。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-update-references-to-the-bamprimaryimport-database-name-and-connection-string"></a>BAMPrimaryImport データベース名および接続文字列への参照を更新するには  
  
1.  すべての BAM キューブ更新およびデータ変換サービス (DTS) パッケージを停止するか、BAMPrimaryImport データベースの復元が完了するまで実行されないように措置を講じます。  
  
2.  (を BAM イベント バス サービスを含む)、BizTalk アプリケーション サービスを停止するため、データベースに多くのデータをインポートするのには試行されません。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。  
  
    2.  右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスを提供し、クリックして**停止**です。  
  
3.  」の手順を実行する、BAMPrimaryImport データベースを復元[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。  
  
4.  次の Web.Config ファイルを更新します。  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BamManagementService\Web.Config.  
  
         置換、  *\<ServerName >* 、新しいサーバー名の文字列と *\<DatabaseName >*で新しいデータベースの名前。 次の接続文字列を更新します。  
  
         \<appSettings >  
  
         < キーを追加"BamServer"の値を = ="*\<ServerName >*"/\>  
  
         < キーを追加"BamDatabase"の値を = ="*\<DatabaseName >*"/\>  
  
         \<キーを追加"MaxResultRows"の値を = =「2000」/>  
  
         \</appSettings >  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BamQueryService\Web.Config.  
  
         置換、  *\<ServerName >* 、新しいサーバー名の文字列と *\<DatabaseName >*で新しいデータベースの名前。 次の接続文字列を更新します。  
  
         \<appSettings >  
  
         < キーを追加"BamServer"の値を = ="*\<ServerName >*"/\>  
  
         <add key="BamDatabase" value="*<DatabaseName>*" />  
  
         <add key="MaxResultRows" value="2000" />  
  
         </appSettings>  
  
5.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
6.  次のディレクトリに移動: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]schema \restore です。  
  
7.  右クリック**SampleUpdateInfo.xml**、クリックして**編集**です。  
  
    1.  BizTalkMgmtDb、OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および Alert を除いて、すべてのデータベース セクションをコメント アウトします。  
  
    2.  BizTalkMgmtDb、OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および警告のセクションでは、設定、 **"SourceServer"**と**"Destination Server"**それらのデータベースが存在する既存のサーバーの名前にします。  
  
    3.  Primaryimportdatabase について、次のように設定します。、 **"SourceServer"** 、BAM プライマリ インポート データベースを移動したサーバーの名前にします。  
  
        > [!IMPORTANT]
        >  送信元システムおよび送信先システムの名前は、引用符で囲んでください。  
  
        > [!NOTE]
        >  いずれかの BizTalk Server データベースの名前を変更した場合、それに応じてデータベース名も更新する必要があります。  
  
    4.  ファイルの編集を終了したら、このファイルを保存して閉じます。  
  
8.  コマンド プロンプトで、次のように入力します。  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
    > [!NOTE]
    >  UpdateDatabase.vbs の実行は、1 度のみしか必要ありません。  
  
    > [!NOTE]
    >  64 ビット コンピューターの場合は、UpdateDatabase.vbs を 64 ビット コマンド プロンプトから実行する必要があります。  
  
9. コマンド プロンプトで、次のディレクトリに移動します  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡  
  
10. コマンド プロンプトで、bm.exe.config を編集して、key="DefaultServer" の値を新しいサーバー名に変更し、ファイルを保存します。  
  
11. すべての BAM ライブ データの Microsoft Excel ファイルで BAMPrimaryImport データベースへの参照を更新します。 各ファイルで次の操作を実行します。  
  
    1.  Excel ライブ データ ファイルを開きます。 ファイル名の末尾は _LiveData.xls となっています。  
  
    2.  **BAM**  メニューをクリックして**BAM データベースの接続**です。  
  
    3.  **[BAM データベース**] ダイアログ ボックスでは、SQL Server および BAMPrimaryImport データベースを入力し、をクリックして**OK**です。  
  
    4.  **ファイル** メニューのをクリックして**閉じて Microsoft Excel へ戻る**です。  
  
    5.  **[ファイル]** メニューの **[保存]**をクリックします。  
  
12. BizTalk Server アプリケーション サービスを再起動します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。  
  
    2.  右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスを提供し、クリックして**開始**です。  
  
13. すべての BAM キューブ更新およびデータ保守 DTS パッケージを有効にします。  
  
14. 不完全なアクティビティ インスタンスを解決するには、次を参照してください。[不完全なアクティビティ インスタンスの解決方法](../core/how-to-resolve-incomplete-activity-instances.md)です。  
  
## <a name="see-also"></a>参照  
 [バックアップおよび BAM を復元します。](../core/backing-up-and-restoring-bam.md)