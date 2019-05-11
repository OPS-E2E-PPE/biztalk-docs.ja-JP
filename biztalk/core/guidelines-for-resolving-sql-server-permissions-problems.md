---
title: SQL Server のアクセス許可の問題を解決するためのガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c24512-5f65-4363-b806-8dd52b22f179
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54d7a26d4c781ea27c2cefa19540025b0688e9b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344853"
---
# <a name="guidelines-for-resolving-sql-server-permissions-problems"></a>SQL Server 権限の問題を解決するためのガイドライン
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Microsoft の広範に使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]実行時の操作とそのデータベースが重要ですが、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]アクセス許可が正しく設定。 このトピックでは、最小限に抑えるための一般的なガイドラインを提供します[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]アクセス許可の問題とトラブルシューティングに利用できる手順[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]アクセス許可の問題に影響を与える[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
## <a name="general-guidelines"></a>一般的なガイドライン  
  
- **ドメイン ユーザーおよびグループを使用して、BizTalk Server の複数コンピューターのインストール**  
  
   構成するときに、ドメイン ユーザー グループとアカウントを使用する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]など、複数コンピューター環境シナリオで実行する場所[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]別のコンピューターにインストールされます。 構成または実行しないで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、*パススルー*ドメイン グループおよびアカウントの使用を回避するには、各コンピューターに一致するユーザー名とパスワードのペアを作成するための認証シナリオ。 これにより、このようなパススルー シナリオは、一部のシナリオで正常に機能に見える場合があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他のシナリオで失敗して、サポートされる構成ではありません。  
  
   インストールと構成の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複数コンピューター構成では、ダウンロード、インストール ガイド[関連する BizTalk Server 2013 インストール ガイド](http://go.microsoft.com/fwlink/p/?LinkID=269582)します。  
  
- **適切な Windows ユーザーとグループが適切な SQL Server ロールで定義されていることを確認します。**  
  
   正しいことを確認[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ロールのメンバーシップのトピックの表に示す[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。  
  
- **ユーザーの SQL Server Profiler のアクセス許可の問題を診断するには**  
  
   設定する、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler トレースを監視する、 **Audit Login Failed イベント**アクセス許可のエラーに関する詳細情報を収集します。 使用する方法については[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Profiler を参照してください、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ドキュメント。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="the-sql-server-jobs-that-are-installed-with-biztalk-server-fail-to-execute"></a>BizTalk Server と共にインストールされる SQL Server ジョブの実行失敗します。  
  
##### <a name="problem"></a>問題  
 と共にインストールされる SQL Server ジョブ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で失敗して、次のようなエラーが生成される、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]アプリケーション ログ。  
  
 イベントの種類:警告  
  
 イベント ソース:SQLSERVERAGENT  
  
 イベント カテゴリ:ジョブ エンジン  
  
 イベント ID:208  
  
 日付:6/29/2008  
  
 時間:午後 4時 45分: 01  
  
 ユーザー :なし  
  
 コンピューター:*Sql Server*  
  
 説明:  
  
 SQL Server のスケジュールされたジョブ 'BizTalk Server のバックアップ'  
  
 (0x4AC7C44A48541443927A56C5C6699ECF) - 状態。Failed-invoked on:2008-6-29 01: 13時 45分 - メッセージ。ジョブが失敗しました。  By Schedule 305 (MarkAndBackupLogSched) ジョブが呼び出されました。 最後の手順を実行するには、手順 1 (BackupFull) がでした。  
  
 **- と -**  
  
 イベントの種類:[情報]  
  
 イベント ソース:MSSQLSERVER  
  
 イベント カテゴリ:(4)  
  
 イベント ID:17055  
  
 日付:6/29/2008  
  
 時間:午後 4時 45分: 01  
  
 ユーザー :なし  
  
 コンピューター:*Sql Server*  
  
 説明:  
  
 18456:ユーザー 'NT authority \system' はログインできませんでした。  
  
##### <a name="cause"></a>原因  
 このエラーから builtin \administrators ログインが削除された場合に発生する可能性が[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 Sqlmaint.exe にログオンできませんなります builtin \administrators ログインが削除された場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]SQL ジョブの実行ができなきます。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、builtin \administrators ログインを再作成し、db_owner ロールに追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースとマスター データベース。  
  
## <a name="see-also"></a>参照  
 [SQL Server のトラブルシューティング](../core/troubleshooting-sql-server.md)   
 [BizTalk Server のアクセス許可のトラブルシューティング](../core/troubleshooting-biztalk-server-permissions.md)