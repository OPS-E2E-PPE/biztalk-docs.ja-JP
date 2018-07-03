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
ms.openlocfilehash: 32561c19bf099b226dc5425edb35ebbaf0a8b3b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992387"
---
# <a name="guidelines-for-resolving-sql-server-permissions-problems"></a>SQL Server 権限の問題を解決するためのガイドライン
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースをランタイム操作のため広範に使用するので、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 権限が正しく設定されていることが重要です。 このトピックでは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 権限の問題を最小限に抑えるための一般的なガイドラインと、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に影響を与える [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 権限の問題をトラブルシューティングするための手順を提供します。  
  
## <a name="general-guidelines"></a>一般的なガイドライン  
  
- **ドメイン ユーザーおよびグループを使用して、BizTalk Server の複数コンピューターのインストール**  
  
   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が別々のコンピューターにインストールされている場合など、複数コンピューターのシナリオで実行する [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を構成する場合は、ドメイン ユーザー グループとアカウントを使用する必要があります。 構成または実行しないで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、*パススルー*ドメイン グループおよびアカウントの使用を回避するには、各コンピューターに一致するユーザー名とパスワードのペアを作成するための認証シナリオ。 一部のシナリオでは、このようなパススルー シナリオが正常に機能しているように見える場合もありますが、これは他のシナリオで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が失敗する原因になりますし、サポートされる構成ではありません。  
  
   インストールと構成の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複数コンピューター構成では、ダウンロード、インストール ガイド[関連する BizTalk Server 2013 インストール ガイド](http://go.microsoft.com/fwlink/p/?LinkID=269582)します。  
  
- **適切な Windows ユーザーとグループが適切な SQL Server ロールで定義されていることを確認します。**  
  
   正しいことを確認[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ロールのメンバーシップのトピックの表に示す[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。  
  
- **ユーザーの SQL Server Profiler のアクセス許可の問題を診断するには**  
  
   設定する、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler トレースを監視する、 **Audit Login Failed イベント**アクセス許可のエラーに関する詳細情報を収集します。 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler の使用方法については、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のマニュアルを参照してください。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="the-sql-server-jobs-that-are-installed-with-biztalk-server-fail-to-execute"></a>BizTalk Server と共にインストールされる SQL Server ジョブの実行の失敗  
  
##### <a name="problem"></a>問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と共にインストールされる SQL Server ジョブが失敗して、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] アプリケーション ログに次のようなエラーが生成されます。  
  
 イベントの種類: 警告  
  
 イベント ソース: SQLSERVERAGENT  
  
 イベント カテゴリ: ジョブ エンジン  
  
 イベント ID: 208  
  
 日付: 6/29/2008  
  
 時刻: 4:45:01 PM  
  
 ユーザー: N/A  
  
 コンピューター: *SQLServer*  
  
 説明:  
  
 SQL Server Scheduled Job 'Backup BizTalk Server'  
  
 (0x4AC7C44A48541443927A56C5C6699ECF) - Status: Failed - Invoked on: 2008-6-29 13:45:01 - Message: The job failed.  The Job was invoked by Schedule 305 (MarkAndBackupLogSched).  The last step to run was step 1 (BackupFull).  
  
 **- と -**  
  
 イベントの種類: 情報  
  
 イベント ソース: MSSQLSERVER  
  
 イベント カテゴリ: (4)  
  
 イベント ID: 17055  
  
 日付: 6/29/2008  
  
 時刻: 4:45:01 PM  
  
 ユーザー: N/A  
  
 コンピューター: *SQLServer*  
  
 説明:  
  
 18456: ユーザー 'NT AUTHORITY\SYSTEM' はログインできませんでした。  
  
##### <a name="cause"></a>原因  
 このエラーは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] から BUILTIN\Administrators ログインが削除された場合に発生します。 BUILTIN\Administrators ログインが削除されると、sqlmaint.exe が [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] にログオンできなくなり、SQL ジョブの実行ができなくなります。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、BUILTIN\Administrators ログインを再作成して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースとマスター データベースの db_owner ロールに追加します。  
  
## <a name="see-also"></a>参照  
 [SQL Server のトラブルシューティング](../core/troubleshooting-sql-server.md)   
 [BizTalk Server のアクセス許可のトラブルシューティング](../core/troubleshooting-biztalk-server-permissions.md)