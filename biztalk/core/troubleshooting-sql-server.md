---
title: SQL Server のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f6707c5-7c6e-4375-bfa6-9b1a86ec5e81
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 632ca1c46a3df313e3aac4e144cad1647eb2360f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975784"
---
# <a name="troubleshooting-sql-server"></a>SQL Server のトラブルシューティング
Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に影響を与える Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の問題の大部分は、次のカテゴリのいずれかに分類されます。  
  
-   接続に関連した問題  
  
-   アクセス許可関連の問題  
  
-   データベース サイズの問題  
  
 このトピックでは、これらのカテゴリそれぞれについて、および関連する問題を解決するための手順について説明します。  
  
## <a name="connectivity-related-problems"></a>接続関連の問題  
 次の問題は、一般的に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターと、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースがある [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターの間の接続の問題に関連付けられます。  
  
#### <a name="errors-related-to-failed-transactions-or-communication-with-the-underlying-transaction-manager-errors-are-written-to-the-biztalk-server-application-log"></a>失敗したトランザクションに関連するエラー、または基になるトランザクション マネージャーとの通信の失敗を示すエラーが BizTalk Server アプリケーションのログに書き込まれる  
  
##### <a name="problem"></a>問題  
 MSDTC トランザクションの失敗または基になるトランザクション マネージャーとの通信の失敗を示すエラーが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションのログに書き込まれます。  
  
##### <a name="cause"></a>原因  
 間の MSDTC 接続[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]に失敗しました。  
  
##### <a name="resolution"></a>解決策  
 間の MSDTC 接続のトラブルシューティングについては、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターおよび[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納しているコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[MSDTC の問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)です。  
  
#### <a name="error-a-connection-was-successfully-established-with-the-server-but-then-an-error-occurred-during-the-pre-login-handshake-occurs-when-connecting-to-remote-sql-server-databases-on-sql-server-2008"></a>SQL Server 2008 上のリモート SQL Server データベースに接続するときに、サーバーとの接続は正常に確立されたが、ログイン前のハンドシェイク時にエラーが発生したことを示すエラーが発生する  
  
##### <a name="problem"></a>問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースのあるリモート [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターとの接続を失い、エラー メッセージが生成されます。  
  
##### <a name="cause"></a>原因  
 この問題は、次の条件の 1 つ以上が当てはまるときに発生します。  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] がリモート接続を受け入れるように構成されていません。  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に必要なプロトコルが、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューター、または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行している [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] クライアント コンピューターで有効になっていません。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、次の手順を実行します。  
  
-   **SQL Server セキュリティ構成**ツールは SQL Server 2008 では使用できません。 SQL Server 2008 コンピューターで [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のリモート接続を有効にするには、SQL Server 2008 オンライン ヘルプの説明に従ってください。  
  
-   使用して、 **SQL Server 構成マネージャー**を有効にするツール、 **TCP/IP**と**名前付きパイプ**のプロトコル、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
    1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリック**SQL Server 構成マネージャー**です。  
  
    2.  クリックして展開**SQL Server ネットワーク構成** をクリックし、 **MSSQLSERVER のプロトコル**です。  
  
    3.  右クリックし、 **TCP/IP**プロトコルをクリックして**を有効にする**です。  
  
    4.  右クリックし、**名前付きパイプ**プロトコルをクリックして**を有効にする**です。  
  
    5.  閉じる、 **SQL Server 構成マネージャー**ツールです。  
  
-   使用して、 **SQL Server 構成マネージャー**を有効にするツール、 **TCP/IP**と**名前付きパイプ**のプロトコル、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているクライアントコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
    1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリック**SQL Server 構成マネージャー**です。  
  
    2.  クリックして展開**SQL Server ネットワーク構成** をクリックし、 **ClientProtocols**です。  
  
    3.  右クリックし、 **TCP/IP**プロトコルをクリックして**を有効にする**です。  
  
    4.  右クリックし、**名前付きパイプ**プロトコルをクリックして**を有効にする**です。  
  
    5.  閉じる、 **SQL Server 構成マネージャー**ツールです。  
  
    > [!NOTE]
    >  [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行している [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] クライアント コンピューターにおけるプロトコルの少なくとも 1 つが、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューターで有効になっているプロトコルに一致することを確認してください。  
  
#### <a name="a-biztalk-host-instance-fails-and-a-general-network-error-is-written-to-the-application-log-when-the-biztalk-server-based-server-processes-a-high-volume-of-documents"></a>BizTalk Server ベースのサーバーで大量のドキュメントを処理するときに、BizTalk ホスト インスタンスが失敗して、"一般的なネットワーク" エラーがアプリケーション ログに書き込まれる  
  
##### <a name="problem"></a>問題  
 大量のドキュメントを処理するときに、BizTalk ホスト インスタンスが失敗し、"一般的なネットワーク" エラーがアプリケーション ログに書き込まれます。  
  
##### <a name="cause"></a>原因  
 この問題は、Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] に実装されているセキュリティ機能により、サーバーへの同時 TCP/IP 接続のためのキューのサイズが減らされるために発生します。 この機能は、サービス拒否攻撃の回避に役立ちます。  
  
##### <a name="resolution"></a>解決策  
 この問題の解決の詳細については、次を参照してください。 [DBNETLIB 例外の回避](../core/avoiding-dbnetlib-exceptions.md)です。  
  
## <a name="permissions-related-problems"></a>アクセス許可に関連した問題  
  
#### <a name="biztalk-server-run-time-or-design-time-operations-fail-and-a-cannot-open-database-requested-in-login-database-error-is-written-to-the-application-log-of-the-biztalk-server-or-sql-server-computer"></a>BizTalk Server が実行時またはデザイン時の操作が失敗して、"ログインで要求されたデータベースを開くことができません\<データベース\>"エラーが BizTalk Server または SQL Server コンピューターのアプリケーション ログに書き込まれます  
  
##### <a name="problem"></a>問題  
 実行時またはデザイン時の操作が失敗し、次のようなエラーが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューターのアプリケーション ログに書き込まれます。  
  
 ログインで要求されたデータベースを開くことができません\<*データベース*\>です。 ログインに失敗しました.   
ユーザーはログインできませんでした\< *username*\>です。  
  
##### <a name="cause"></a>原因  
 このエラーは、指定したアカウントが適切な Windows グループまたは [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ロールに属していない場合に発生する可能性があります。  
  
##### <a name="resolution"></a>解決策  
 指定したアカウントが適切な Windows グループまたは [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ロールのメンバーであることを確認します。 適切なメンバーシップの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。  
  
## <a name="database-sizing-problems"></a>データベース サイズに関連した問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースがチェックされない状態で肥大する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のパフォーマンスが悪影響を受けます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの肥大を制御するには、以下の手順を実行します。  
  
#### <a name="the-biztalk-server-messagebox-database-is-growing-unchecked-and-impacting-overall-performance"></a>BizTalk Server メッセージ ボックス データベースがチェックされない状態で肥大しており、パフォーマンス全体に影響を与えている  
  
##### <a name="problem"></a>問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースの肥大によって [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のパフォーマンスに悪影響が及んでいます。  
  
##### <a name="cause"></a>原因  
 この問題は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを管理している SQL エージェント ジョブが実行されていない場合に発生することがあります。  
  
##### <a name="resolution"></a>解決策  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを管理している SQL エージェント ジョブが実行されていることを確認します。 参照してください[データベース構造とジョブ](../core/database-structure-and-jobs.md)と一緒にインストールされている SQL エージェント ジョブの完全な一覧について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
#### <a name="the-biztalk-server-tracking-database-is-growing-unchecked-and-impacting-overall-performance"></a>BizTalk Server 追跡データベースがチェックされない状態で肥大しており、パフォーマンス全体に影響を与えている  
  
##### <a name="problem"></a>問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 追跡データベースがチェックされない状態で肥大しており、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のパフォーマンス全体に悪影響を及ぼしています。  
  
##### <a name="cause"></a>原因  
 この問題は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 追跡データベースを削除およびアーカイブするための手順が実行されていない場合に発生することがあります。  
  
##### <a name="resolution"></a>解決策  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 追跡データベースを削除およびアーカイブするための手順を実行する必要があります。 参照してください[アーカイブ化および BizTalk 追跡データベースを削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)詳細についてはします。  
  
## <a name="see-also"></a>参照  
 [SQL Server のアクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-sql-server-permissions-problems.md)