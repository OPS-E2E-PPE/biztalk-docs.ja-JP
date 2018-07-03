---
title: パフォーマンス Issues3 のトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 40f7ae950a7078152d2952fb72ebe39303d41813
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998811"
---
# <a name="troubleshooting-performance-issues"></a>パフォーマンスの問題のトラブルシューティング
このセクションには、診断するための一般的なガイドラインが含まれていますとに関連するパフォーマンスの問題を解決する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]とその依存関係。 これらのガイドラインを事前に、使用の重要な問題になる前に、潜在的な問題を識別するためにします。  
  
## <a name="diagnosing-performance-problems-in-the-biztalk-server-environment"></a>BizTalk Server 環境のパフォーマンスの問題を診断します。  
 通常、パフォーマンスの問題は絞り込むことがの次のコンポーネントの 1 つに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
- 受信アダプターまたはアダプターがドキュメントを受信は、システム。 たとえば、HTTP に問題がありますが、最適ではないレートで HTTP アダプターで受信されるドキュメントの場合は、受信アダプターまたは HTTP アダプターへの投稿は、クライアントとします。  
  
- オーケストレーション サービス インスタンス。  
  
- パフォーマンス、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をホストする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
- 送信アダプターまたはそのアダプターからドキュメントを受信しているシステム。 たとえば、最適ではないレートで SQL アダプターによってドキュメントが送信される場合、問題可能性がありますまたはを実行しているコンピューターと SQL 送信アダプタで[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]SQL アダプタを更新します。  
  
  次のガイドラインは、パフォーマンスが低下している [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のコンポーネントの特定に役立ちます。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] イベント ビューアーで生成された警告やエラーをすべてキャプチャします。  
  
- 「パフォーマンスのボトルネックを識別する」の手順に従って[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=154238 ](http://go.microsoft.com/fwlink/?LinkId=154238)パフォーマンスのボトルネックを識別できるようにします。  
  
  パフォーマンスの低いコンポーネントを特定したら、以下の該当するガイドラインに従って、問題を解決します。  
  
  **送信および受信アダプターに関連するパフォーマンスの問題を解決するためのガイドライン**  
  
- に関する問題のトラブルシューティングについては[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、アダプターの「BizTalk Server アダプターのトラブルシューティング」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=154240](http://go.microsoft.com/fwlink/?LinkId=154240)します。 このセクションには、アダプターの特定のログ記録を設定する方法に関する情報など、一般的なトラブルシューティング情報が含まれていて、ネットワークの問題、問題、レジストリとファイルの問題、MSDTC を使用した問題を診断するために使用できる情報システム、および IIS に関する問題。  
  
- MSDTC を使用した、証明書、エンタープライズ シングル サインオン、問題のトラブルシューティングについては、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、「BizTalk サーバー依存関係のトラブルシューティング」の該当セクションを参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=154242](http://go.microsoft.com/fwlink/?LinkId=154242).  
  
  **オーケストレーションに関連するパフォーマンスの問題を解決するためのガイドライン**  
  
- BTSNTSvc.exe.config ファイルの該当セクションを変更する方法については、「オーケストレーション エンジンの構成」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=154244](http://go.microsoft.com/fwlink/?LinkId=154244)します。  
  
  **SQL Server に関連するパフォーマンスの問題を解決するためのガイドライン**  
  
- SQL Server Profiler に送信される TRANSACT-SQL ステートメントをキャプチャするために使用できる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]これらのステートメントから結果セットします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]緊密に統合されて[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の分析、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]プロファイル トレースで発生する可能性のある問題を分析するための便利なツールをできる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]から読み取りと書き込み時に[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。 使用する方法については[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Profiler を参照してください"を使用して SQL Server Profiler"[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]でオンライン ブックの「 [ http://go.microsoft.com/fwlink/?linkid=104423](http://go.microsoft.com/fwlink/?linkid=104423)します。  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio は、に対して直接 SQL ステートメントを実行するために使用できる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。 この機能は、クエリを実行するのに便利な可能性があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースまたは更新するため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定のシナリオでのデータベース。 SQL Server Management Studio を使用して SQL ステートメントを実行する方法の詳細についてを参照してください「の書き込み、分析、および SQL Server Management Studio を使用してスクリプトを編集」[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]でオンライン ブックの「 [ http://go.microsoft.com/fwlink/?linkid=104425](http://go.microsoft.com/fwlink/?linkid=104425)します。  
  
- 関連するパフォーマンスの問題の解決の詳細については、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、データベースの「SQL Server のトラブルシューティング」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=154250](http://go.microsoft.com/fwlink/?LinkId=154250)します。  
  
## <a name="see-also"></a>参照  
 [http://go.microsoft.com/fwlink/?linkid=104430](http://go.microsoft.com/fwlink/?linkid=104430)