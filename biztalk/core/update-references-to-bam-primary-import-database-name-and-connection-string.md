---
title: "BAM プライマリ インポート データベースの名前と接続文字列を更新 |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/01/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91792b66fa82be633123501f651d9a34784915ce
ms.sourcegitcommit: c670558deccec266f90ae7ed042dba1105b15596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2018
---
# <a name="update-references-to-the-bam-primary-import-database-name-and-connection-string"></a>BAM プライマリ インポート データベース名および接続文字列への参照を更新します。
BAMPrimaryImport データベースをバックアップしておくと、システムまたはデータに障害が発生したときに、別のコンピューターにバックアップを復元し、その名前を変更することができます。  
  
 BAM イベント バス サービスでは、イベント データをメッセージ ボックス データベースから BAMPrimaryImport データベースに移動します。 BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。 BAM イベント バス サービスの詳細については、次を参照してください。 [BAM イベント バス サービスを管理する](../core/managing-the-bam-event-bus-service.md)です。  
  
 BAMPrimaryImport データベースを復元する」の手順を実行[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。 これらの手順を実行したうえで、次の手順を実行します (詳細な手順については後述)。  
  
-   すべての BAM DTS パッケージで、SQL 接続 1 の参照先が新しいデータベース名になるように更新します。  
  
-   新しいデータベース名で web.config ファイルを更新します。  
  
-   すべての BAM ライブ データの Microsoft Excel ファイルで BAMPrimaryImport データベースへの参照を更新します。  
  
## <a name="prerequisites"></a>前提条件  
BizTalk Server 管理者グループのメンバーとしてサインインします。  
  
## <a name="update-the-references"></a>参照を更新します。  
  
1.  すべての BAM キューブ更新およびデータ変換サービス (DTS) パッケージを停止するか、BAMPrimaryImport データベースの復元が完了するまで実行されないように措置を講じます。  
  
2.  BizTalk アプリケーション サービス (を BAM イベント バス サービスを含む) を停止するためより多くのデータをデータベースにインポートするのには試行されません。  
  
    1.  **開始**メニューで、「 **services.msc**、開き**Services**です。  
  
    2.  右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービス、し**停止**です。  
  
3.  BAMPrimaryImport データベースの復元 (ステップの[、データベースを復元する方法](../core/how-to-restore-your-databases.md))。  
  
4.  次の Web.Config ファイルを更新します。  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\BAMPortal\BamManagementService\Web.Config です。  
  
         置換、  *\<ServerName\>*  、新しいサーバーの名前を持つ文字列と *\<DatabaseName\>* で新しいデータベースの名前。 次の接続文字列を更新します。  
  
         \<appSettings\>  
  
         <add key="BamServer" value="*\<ServerName\>*" /\>  
  
         <add key="BamDatabase" value="*\<DatabaseName\>*" /\>  
  
         \<add key="MaxResultRows" value="2000" /\>  
  
         \</appSettings\>  
  
    -   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\BAMPortal\BamQueryService\Web.Config.  
  
         置換、  *\<ServerName\>*  、新しいサーバー名の文字列と *\<DatabaseName\>* で新しいデータベースの名前。 次の接続文字列を更新します。  
  
         \<appSettings\>  
  
         \<キーを追加"BamServer"の値を = ="*\<ServerName\>*"/\>  
  
         \<add key="BamDatabase" value="*\<DatabaseName\>*" /\>  
  
         \<add key="MaxResultRows" value="2000" /\>  
  
         \</appSettings\>  
  
5.  コマンド プロンプトを開きます ([スタート] メニュー > コマンド プロンプト) を次のディレクトリに移動: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Schema\Restore です。  
  
6.  右クリック**SampleUpdateInfo.xml**、および**編集**です。  
  
    1.  すべてのデータベース セクションでは、OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、およびアラートを除くコメントします。 
    2.  OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および警告のセクションでは、設定、 **SourceServer**と**移行先サーバー**に、これらのデータベースが存在する既存のサーバーの名前です。  
  
    3.  PrimaryImportDatabase、設定、 **"SourceServer"** BAM プライマリ インポート データベースを移動したサーバーの名前にします。  
  
        > [!IMPORTANT]
        >  送信元システムおよび送信先システムの名前は、引用符で囲んでください。  
  
        > [!NOTE]
        >  BizTalk Server データベースの名前を変更した場合は、データベース名も更新することを確認します。  
  
    4.  ファイルの編集を終了したら、ファイルを保存して閉じます。  
  
7.  コマンド プロンプトで、次のように入力します。  
  
     **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
    > [!NOTE]
    >  UpdateDatabase.vbs を一度だけ実行します。  
    > 
    >  64 ビット コンピューターでは、64 ビット コマンド プロンプトから UpdateDatabase.vbs を実行します。  
  
8. コマンド プロンプトで、次のディレクトリに移動します  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking  
  
9. コマンド プロンプトで、bm.exe.config を編集して、key="DefaultServer" の値を新しいサーバー名に変更し、ファイルを保存します。  
  
10. すべての BAM ライブ データの Microsoft Excel ファイルで BAMPrimaryImport データベースへの参照を更新します。 各ファイルで次の操作を実行します。  
  
    1.  Excel ライブ データ ファイルを開きます。 ファイル名の末尾は _LiveData.xls となっています。  
  
    2.  **BAM**  メニューのをクリックして **BAM データベースの接続**します。  
  
    3.  **[BAM データベースの** ] ダイアログ ボックスでは、SQL Server および BAMPrimaryImport データベースを入力し、をクリックして **OK**します。  
  
    4.  **ファイル**  メニューのをクリックして **を閉じるし、Microsoft Excel へ戻る**します。  
  
    5.  **[ファイル]** メニューの **[保存]**をクリックします。  
  
11. BizTalk Server アプリケーション サービスを再起動します。  
  
    1.  開いている **services.msc**します。  
  
    2.  右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービス、し**開始**です。  
  
12. すべての BAM キューブ更新およびデータ保守 DTS パッケージを有効にします。  
  
13. 不完全なアクティビティ インスタンスを解決するには、次を参照してください。[不完全なアクティビティのインスタンスを解決するには](../core/how-to-resolve-incomplete-activity-instances.md)します。  
  
## <a name="see-also"></a>参照  
 [BAM のバックアップと復元](../core/backing-up-and-restoring-bam.md)
