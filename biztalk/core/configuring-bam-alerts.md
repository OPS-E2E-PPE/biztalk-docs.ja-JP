---
title: "BAM 警告の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, alerts
- alerts, timeout values
- Notification Services, configuration tips
- alerts, configuring
- managing [BAM definitions], configuring alerts
ms.assetid: 29327466-c8e9-41e8-bc12-f3ac6b5d3096
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8198b17d07288bff04b64b0a1ad05db0cde4fd91
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-bam-alerts"></a>BAM 警告の構成
管理者は、BAM 警告フレームワークの特定の要素を変更できます。 このトピックでは、管理者が使用できる構成オプションについて説明します。  
  
> [!NOTE]
>  警告を作成するときは、時刻データが OLAP データベース、スター スキーマ データベース、および Notification Services データベースにローカル時刻形式で格納されることに注意してください。 また、これら 3 つのデータベースは同じタイム ゾーンに属していることが前提となります。 プライマリ インポート データベースには、情報が UTC 時刻形式で格納されます。このデータベースは必ずしも同じタイム ゾーンに属している必要はありません。  
  
## <a name="changing-the-adf-configuration"></a>ADF 構成の変更  
 BAM 管理ユーティリティでは、bm.exe.config ファイルで指定された CommandTimeout の値を使用して、Notification Services アプリケーション定義ファイルを事前設定のビューを展開するときに\<EventRule\>\\< ActionTimeout\>要素。  
  
 bm.exe.config の CommandTimeout の値を変更しても、変更前に展開したビューの CommandTimeout の値は変更されません。  
  
 次の手順では、ProcessBamNSFiles.vbs を使用して、構成と Notification Services アプリケーションの定義ファイルを取得します。 スクリプトの詳細については、次を参照してください。 [Notification Services の構成ファイル用の BAM コマンド ライン スクリプト](../core/bam-command-line-script-for-notification-services-configuration-files.md)です。  
  
 既に展開されているビューの NS の ActionTimeout を変更する方法  
  
#### <a name="to-change-the-command-timeout-value"></a>コマンドのタイムアウト値を変更するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトで入力して、追跡フォルダーに移動**cd"C:\Program files \microsoft BizTalk Server\<バージョン\>\Tracking"**または**cd"C:\Program Files (x86) \Microsoft BizTalkサーバー\<バージョン\>\Tracking"** 64 ビット コンピューターにします。 **Enter**キーを押します。  
  
3.  ADF ファイルを取得します。 型**cscript ProcessBamNSFiles.vbs-取得\<ConfigFilePath\> \<構成ファイルのパス\> \< PID サーバー\> \< PID データベース\>** . 構成ファイルのパス、ADF ファイルのパス、PID サーバー、および PID データベースは、インストール環境に適した値に置き換えてください。  
  
4.  **Enter**キーを押します。  
  
5.  エディターで、ADF ファイルを開き、検索\<ActionTimeout\>、目的の値に更新およびこの値は XML 期間でことに注意してください。  
  
6.  ADF ファイルを保存します。 型**cscript ProcessBamNSFiles.vbs-更新\<ConfigFilePath\> \<構成ファイルのパス\> \< PID サーバー\> \< PID データベース\>**.  
  
7.  **Enter**キーを押します。  
  
### <a name="notification-service-configuration-tips"></a>Notification Service の構成に関するヒント  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているリモート コンピューターに警告データベースを配置するように BAM 警告を構成する場合、SQL Server インスタンスに Notification Services データベース コンポーネントをインストールする必要があります。 これらのコンポーネントが SQL インスタンス上に存在しない場合、BAM 警告の構成は失敗し、Notification Services 拡張ストアド プロシージャに権限を与えることができなかったことを示すエラーが発生します。 Notification Services コンポーネントをインストールする方法の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=61999](http://go.microsoft.com/fwlink/?LinkId=61999)です。  
  
 BAM では Notification Services へのアクセスに使用されるアカウントを変更できます。 NSControl を実行する方法以外でこのアカウントを変更すると、アカウントの変更に NSControl を使用することを通知するエラーが表示されます。  
  
> [!NOTE]
>  Notification Services のインストールおよび構成には、LocalSystem アカウントと SYSTEM アカウントは使用できません。 これらのアカウントは、ログオンしたり、BAM 警告ユーザーにファイルや SQL Server へのアクセス許可を与えるのに使用したりすることができない特殊なアカウントです。  
>   
>  Notification Services をインストールおよび構成する場合は、ローカル コンピューターに新しいユーザー アカウントを作成して必要なアクセス許可を与えてから、このアカウントを Notification Services の構成に使用します。  
  
##### <a name="to-change-ns-user-account-for-bam"></a>BAM の NS ユーザー アカウントを変更するには  
  
1.  NSControl を使用してユーザー アカウントを更新します。  
  
2.  NS ユーザーに、共有される BAM 警告ファイルの場所に対する読み取り、書き込み、および変更のアクセス許可を与えます。  
  
3.  BAMAlerts インスタンス データベースとアプリケーション データベースの両方で、NS ユーザーを NSRunService ロールのメンバーとして追加します。  
  
4.  ドキュメントを使用してローカル コンピューターで NS ユーザー権限を与える[http://go.microsoft.com/fwlink/?LinkId=62005](http://go.microsoft.com/fwlink/?LinkId=62005)です。  
  
5.  よるとデータベースの NS に対する権限を付与[http://go.microsoft.com/fwlink/?LinkId=62008](http://go.microsoft.com/fwlink/?LinkId=62008)です。  
  
6.  NS ユーザーに、SQL Server に対するログイン権限とプライマリ インポート データベースに対するデータベース アクセス権限を与えます。  
  
7.  NS ユーザーを BAM_ManagmentNSReader SQL ロールに追加します。  
  
8.  NS ユーザーを BamAnalysis データベースの "BAM 警告" ロールに追加します。  
  
 ファイルで配信された警告のファイルの格納場所を変更した場合、 SQL Notifications Services を再起動する必要があります。  
  
 NS サービスを再起動しなかった場合、警告は元のファイルの格納場所に配信され続けます。  
  
 ファイルの格納場所は、BAM 構成ファイルの次の行を変更し、BAM 管理ユーティリティの update-config コマンドを使用することによって変更します。  
  
 \<プロパティ名 ="FileDropUNC"\>\\\\< コンピューター名\>\alerts\</Property\>  
  
 BAM 管理ユーティリティの詳細については、次を参照してください。 [BAM 管理ユーティリティ](../core/bam-management-utility.md)です。