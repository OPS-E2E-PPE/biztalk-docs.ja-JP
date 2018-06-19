---
title: パフォーマンス Issues3 のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a348c4b-7df2-43e9-810c-1f538a97d7e1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93f5aad28eb31b51122be4c17de6ab92e8244a5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302394"
---
# <a name="troubleshooting-performance-issues"></a>パフォーマンスの問題のトラブルシューティング
このセクションには、診断するための一般的なガイドラインが含まれています。 およびに関連するパフォーマンスの問題を解決する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]とその依存関係。 これらのガイドラインをプリエンプティブ、使用を重大な問題になる前に、潜在的な問題を識別します。  
  
## <a name="diagnosing-performance-problems-in-the-biztalk-server-environment"></a>BizTalk Server 環境のパフォーマンスの問題を診断します。  
 通常、パフォーマンスの問題に絞り込むの次のコンポーネントの 1 つ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
-   受信アダプターまたはアダプターがドキュメントを受信は、システムです。 たとえば、HTTP に問題がありますが、最適ではないレートで HTTP アダプターで受信されるドキュメントの場合は、受信アダプターまたは HTTP アダプターに送信するクライアントを使用します。  
  
-   オーケストレーション サービス インスタンス。  
  
-   パフォーマンス、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をホストする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
-   送信アダプターまたはそのアダプターからドキュメントを受信しているシステム。 たとえば、最適ではないレートで SQL アダプターがドキュメントを送信している場合、問題可能性があります SQL 送信アダプタでまたはを実行しているコンピューターと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]SQL アダプタを更新します。  
  
 次のガイドラインは、パフォーマンスが低下している [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のコンポーネントの特定に役立ちます。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] イベント ビューアーで生成された警告やエラーをすべてキャプチャします。  
  
-   「パフォーマンスのボトルネックを識別する」」の手順に従ってください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkId=154238](http://go.microsoft.com/fwlink/?LinkId=154238)パフォーマンスのボトルネックの特定に役立ちます。  
  
 パフォーマンスの低いコンポーネントを特定したら、以下の該当するガイドラインに従って、問題を解決します。  
  
 **送信および受信アダプターに関連するパフォーマンスの問題を解決するためのガイドライン**  
  
-   問題のトラブルシューティングについて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、アダプターの「BizTalk Server アダプターのトラブルシューティング」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でヘルプを[http://go.microsoft.com/fwlink/?LinkId=154240](http://go.microsoft.com/fwlink/?LinkId=154240)です。 このセクションには、アダプターの特定のログ記録を設定する方法に関する情報など、一般的なトラブルシューティング情報が含まれ、ネットワークの問題、MSDTC の問題であり、ファイルの問題、レジストリの問題を診断するために使用できる情報システム、および IIS の問題です。  
  
-   MSDTC、証明書、エンタープライズ シングル サインオン、に関する問題のトラブルシューティングについては、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、「BizTalk サーバー依存関係のトラブルシューティング」の該当セクションを参照して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でヘルプを[http://go.microsoft.com/fwlink/ しますか。LinkId = 154242](http://go.microsoft.com/fwlink/?LinkId=154242)です。  
  
 **オーケストレーションに関連するパフォーマンスの問題を解決するためのガイドライン**  
  
-   BTSNTSvc.exe.config ファイルの該当するセクションを変更する方法については、「オーケストレーション エンジンの構成」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkId=154244](http://go.microsoft.com/fwlink/?LinkId=154244)です。  
  
 **SQL Server に関連するパフォーマンスの問題を解決するためのガイドライン**  
  
-   SQL Server Profiler に送信される TRANSACT-SQL ステートメントをキャプチャするために使用できる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]これらのステートメントからの結果セットです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と密接に連携[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の分析、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]プロファイル トレースで発生する可能性のある問題を分析するための便利なツールを指定できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]から読み取りと書き込み時に[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。 使用する方法については[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]プロファイラーを参照してください"を使用して SQL Server Profiler"[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]でオンライン ブック[http://go.microsoft.com/fwlink/?linkid=104423](http://go.microsoft.com/fwlink/?linkid=104423)です。  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio は、に対して直接 SQL ステートメントを実行するために使用できる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。 この機能は、クエリを実行するのに役立ちます可能性があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースまたは更新するため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定のシナリオでのデータベースです。 SQL Server Management Studio を使用して SQL ステートメントを実行する方法の詳細についてを参照してください「の書き込み、分析、および SQL Server Management Studio での編集スクリプト」[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]でオンライン ブック[http://go.microsoft.com/fwlink/?linkid = 104425](http://go.microsoft.com/fwlink/?linkid=104425)です。  
  
-   関連するパフォーマンス問題の解決の詳細については、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、データベースの「SQL Server のトラブルシューティング」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkId=154250](http://go.microsoft.com/fwlink/?LinkId=154250)です。  
  
## <a name="see-also"></a>参照  
 [http://go.microsoft.com/fwlink/?linkid=104430](http://go.microsoft.com/fwlink/?linkid=104430)