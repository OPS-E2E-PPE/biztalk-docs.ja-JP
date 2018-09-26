---
title: BAM プライマリ インポート データベース名と接続文字列の更新 |Microsoft Docs
ms.custom: ''
ms.date: 02/01/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3c58db0-f14f-429a-813c-bae29f6950d3
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 846aa3b08ce6cce9b2334da72440cf5ba918e5d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003139"
---
# <a name="update-references-to-the-bam-primary-import-database-name-and-connection-string"></a>BAM プライマリ インポート データベース名および接続文字列への参照を更新します。
BAMPrimaryImport データベースをバックアップしておくと、システムまたはデータに障害が発生したときに、別のコンピューターにバックアップを復元し、その名前を変更することができます。  
  
 BAM イベント バス サービスでは、イベント データをメッセージ ボックス データベースから BAMPrimaryImport データベースに移動します。 BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。 BAM イベント バス サービスの詳細については、次を参照してください。 [BAM イベント バス サービスの管理](../core/managing-the-bam-event-bus-service.md)します。  
  
 BAMPrimaryImport データベースを復元する手順を実行[、データベースを復元する方法](../core/how-to-restore-your-databases.md)します。 これらの手順を実行したうえで、次の手順を実行します (詳細な手順については後述)。  
  
-   すべての BAM DTS パッケージで、SQL 接続 1 の参照先が新しいデータベース名になるように更新します。  
  
-   新しいデータベース名で web.config ファイルを更新します。  
  
-   すべての BAM ライブ データの Microsoft Excel ファイルで BAMPrimaryImport データベースへの参照を更新します。  
  
## <a name="prerequisites"></a>前提条件  
BizTalk Server 管理者グループのメンバーとしてサインインします。  
  
## <a name="update-the-references"></a>参照を更新します  
  
1. すべての BAM キューブ更新およびデータ変換サービス (DTS) パッケージを停止するか、BAMPrimaryImport データベースの復元が完了するまで実行されないように措置を講じます。  
  
2. (これは、BAM イベント バス サービスが含まれています)、BizTalk アプリケーション サービスを停止するためより多くのデータをデータベースにインポートする試行は行われません。  
  
   1.  **開始**メニューで、「 **services.msc**、開き**サービス**します。  
  
   2.  右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスし**停止**します。  
  
3. BAMPrimaryImport データベースを復元する (手順[、データベースを復元する方法](../core/how-to-restore-your-databases.md))。  
  
4. 次の Web.Config ファイルを更新します。  
  
   - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\BAMPortal\BamManagementService\Web.Config します。  
  
      置換、 *\<ServerName\>* 、新しいサーバー名を含む文字列と*\<DatabaseName\>* で新しいデータベース名。 次の接続文字列を更新します。  
  
      \<appSettings\>  
  
      < キーを追加"BamServer"の値を = ="*\<ServerName\>*"/\>  
  
      <add key="BamDatabase" value="*\<DatabaseName\>*" /\>  
  
      \<add key="MaxResultRows" value="2000" /\>  
  
      \</appSettings\>  
  
   - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\BAMPortal\BamQueryService\Web.Config します。  
  
      置換、 *\<ServerName\>* 、新しいサーバー名を含む文字列と*\<DatabaseName\>* で新しいデータベース名。 次の接続文字列を更新します。  
  
      \<appSettings\>  
  
      \<キーの追加"BamServer"の値を = ="*\<ServerName\>*"/\>  
  
      \<add key="BamDatabase" value="*\<DatabaseName\>*" /\>  
  
      \<add key="MaxResultRows" value="2000" /\>  
  
      \</appSettings\>  
  
5. コマンド プロンプトを開き ([スタート] メニュー > コマンド プロンプト)、次のディレクトリに移動します: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Schema\Restore します。  
  
6. 右クリックして**SampleUpdateInfo.xml**、および**編集**します。  
  
   1.  データベース セクションでは、OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、およびアラートを除くのすべてのコメントします。 
   2.  OldPrimaryImportDatabase、PrimaryImportDatabase、ArchivingDatabase、AnalysisDatabase、StarSchemaDatabase、および警告のセクションでは、設定、 **SourceServer**と**移行先サーバー**に、これらのデータベースが存在する既存のサーバーの名前です。  
  
   3.  PrimaryImportDatabase、設定、 **"SourceServer"** BAM プライマリ インポート データベースを移動するサーバーの名前にします。  
  
       > [!IMPORTANT]
       >  送信元システムおよび送信先システムの名前は、引用符で囲んでください。  
  
       > [!NOTE]
       >  BizTalk Server データベースの名前を変更した場合は、データベース名も更新することを確認します。  
  
   4.  ファイルの編集を終了したら、ファイルを保存して閉じます。  
  
7. コマンド プロンプトで、次のように入力します。  
  
    **cscript UpdateDatabase.vbs SampleUpdateInfo.xml**  
  
   > [!NOTE]
   >  UpdateDatabase.vbs を 1 回のみ実行されます。  
   > 
   >  64 ビットのコンピューターでは、64 ビット コマンド プロンプトから UpdateDatabase.vbs を実行します。  
  
8. コマンド プロンプトで、次のディレクトリに移動します  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking  
  
9. コマンド プロンプトで、bm.exe.config を編集して、key="DefaultServer" の値を新しいサーバー名に変更し、ファイルを保存します。  
  
10. すべての BAM ライブ データの Microsoft Excel ファイルで BAMPrimaryImport データベースへの参照を更新します。 各ファイルで次の操作を実行します。  
  
    1.  Excel ライブ データ ファイルを開きます。 ファイル名の末尾は _LiveData.xls となっています。  
  
    2.  **BAM**  メニューのをクリックして**BAM データベースの接続**します。  
  
    3.  **BAM データベースの選択** ダイアログ ボックスが、SQL Server および BAMPrimaryImport データベースを入力し、クリックして**OK**。  
  
    4.  **ファイル** メニューのをクリックして**閉じて Microsoft Excel へ戻る**します。  
  
    5.  **[ファイル]** メニューの **[保存]** をクリックします。  
  
11. BizTalk Server アプリケーション サービスを再起動します。  
  
    1.  開いている**services.msc**します。  
  
    2.  右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスし**開始**します。  
  
12. すべての BAM キューブ更新およびデータ保守 DTS パッケージを有効にします。  
  
13. すべての不完全なトレース インスタンスを解決するには、次を参照してください。[不完全なアクティビティ インスタンスの解決](../core/how-to-resolve-incomplete-activity-instances.md)します。  
  
## <a name="see-also"></a>参照  
 [BAM のバックアップと復元](../core/backing-up-and-restoring-bam.md)
