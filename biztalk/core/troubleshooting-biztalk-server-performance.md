---
title: BizTalk Server パフォーマンスのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dbf21fb9-1ae1-48b5-a65a-e96839b23945
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec29254a43a86f29a16ddb5babe5d3c607689f68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401870"
---
# <a name="troubleshooting-biztalk-server-performance"></a>BizTalk Server のパフォーマンスに関するトラブルシューティング
ここでは、BizTalk メッセージング エンジンに関連するパフォーマンスの問題を診断および解決するための一般的なガイドラインを示します。  
  
## <a name="estimating-document-processing-requirements"></a>ドキュメント処理要件の見積もり  
 ソリューションを実稼動環境に展開する前に、メッセージング エンジンのパフォーマンスを測定するための計画とテストを行います。 これは、BizTalk Server 環境および SQL Server 環境の適切な構築に役立ちます。  
  
1.  フォールト トレランスまたはバックアップと復旧に伴うオーバーヘッドについて考慮します。  
  
    -   SQL Server のディスクを RAID アレイで構成するか。  
  
    -   Windows クラスターを BizTalk ホスト、SQL Server、またはエンタープライズ シングル サインオンに使用するか。 詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)します。  
  
    -   ネットワーク負荷分散を使用するか。  
  
    -   環境のバックアップと復旧の要件は何か。 詳細については、次を参照してください。 [Backing Up and BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)します。  
  
2.  ガイドラインに従う[パフォーマンス維持の計画](../core/planning-for-sustained-performance.md)計画、テスト、および BizTalk Server と SQL Server 環境をスケーリングします。  
  
3.  ガイドラインに従う[パフォーマンス特性の追跡](../core/tracking-performance-characteristics.md)ドキュメント追跡の要件に関連付けられたオーバーヘッドについて考慮します。  
  
## <a name="optimizing-an-existing-biztalk-server-environment"></a>既存の BizTalk Server 環境の最適化  
 既存の BizTalk Server 環境を最適化するには、次の手順を実行します。  
  
1.  ガイドラインに従う[パフォーマンスのボトルネックを識別する](../core/identifying-performance-bottlenecks.md)に BizTalk Server 環境内のボトルネックの可能性を特定します。  
  
2.  ガイドラインに従う[を最適化するリソースをホストの調整](../core/optimizing-resource-usage-through-host-throttling.md)を BizTalk Server 環境のドキュメント スループットを最大化します。  
  
3.  記載されているパラメーターの変更を検討[構成パラメーターを アダプターのパフォーマンスの影響を与える](../core/configuration-parameters-that-affect-adapter-performance.md)を特定のシナリオでアダプターのパフォーマンスを最大化します。  
  
4.  ガイドラインに従う[どのように BizTalk Server プロセス サイズの大きいメッセージ](../core/how-biztalk-server-processes-large-messages.md)(100 MB を超える) のサイズの大きいメッセージを処理するときに、メッセージング エンジンのパフォーマンスを最適化するためにします。  
  
5.  送信アダプター、受信アダプター、およびオーケストレーションごとに別々のホストとホスト インスタンスを作成します。 これにより、各アダプターが個別のホスト インスタンスで実行され、あるアダプターが別のアダプターに悪影響を与えることがなくなります。 ホストの制限設定はホスト レベルで構成できるので、処理ロジックを異なるホストへ分離することによって、各ホストの処理要件に基づいて制限設定を構成できるようにもなります。  
  
## <a name="diagnosing-performance-problems-in-an-existing-biztalk-server-environment"></a>既存の BizTalk Server 環境におけるパフォーマンスの問題の診断  
 通常、パフォーマンスの問題は、BizTalk Server 環境の次のコンポーネントの 1 つに絞り込むことができます。  
  
- 受信アダプターまたはそのアダプターにドキュメントを送信しているシステム。 たとえば、最適ではないレートでドキュメントが HTTP アダプターで受信されている場合、問題は HTTP 受信アダプター、または HTTP アダプターに送信しているクライアントにあります。  
  
- オーケストレーション サービス インスタンス。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースをホストしている Microsoft SQL Server のパフォーマンス。  
  
- 送信アダプターまたはそのアダプターからドキュメントを受信しているシステム。 たとえば、最適ではないレートでドキュメントが SQL アダプターで送信されている場合、問題は SQL 送信アダプター、または SQL アダプターが更新している [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているコンピューターにあります。  
  
  次のガイドラインは、パフォーマンスが低下している [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のコンポーネントの特定に役立ちます。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] イベント ビューアーで生成された警告やエラーをすべてキャプチャします。  
  
- 次の手順では、[パフォーマンスのボトルネックを識別する](../core/identifying-performance-bottlenecks.md)パフォーマンスのボトルネックを識別できるようにします。  
  
  パフォーマンスの低いコンポーネントを特定したら、以下の該当するガイドラインに従って、問題を解決します。  
  
  **送信および受信アダプターに関連するパフォーマンスの問題を解決するためのガイドライン**  
  
- 参照してください[BizTalk Server アダプターのトラブルシューティング](../core/troubleshooting-biztalk-server-adapters.md)に関する問題のトラブルシューティングに一般的な情報は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。 このセクションには、特定のアダプターのログ記録の設定方法についての情報や、ネットワークの問題、MSDTC に関する問題、レジストリに関する問題、ファイル システムに関する問題、および IIS に関する問題の診断に使用できる情報など、一般的なトラブルシューティング情報が含まれています。  
  
- 該当セクションを参照してください[BizTalk Server の依存関係のトラブルシューティング](../core/troubleshooting-biztalk-server-dependencies.md)MSDTC、証明書、エンタープライズ シングル サインオン、問題をトラブルシューティングする一般的な情報は、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。  
  
  **オーケストレーションに関連するパフォーマンスの問題を解決するためのガイドライン**  
  
- 記載されている、BTSNTSvc.exe.config ファイルの適切なセクションを変更[オーケストレーション エンジンの構成](../core/orchestration-engine-configuration.md)します。  
  
  **SQL Server に関連するパフォーマンスの問題を解決するためのガイドライン**  
  
- SQL Server Profiler を使用すると、SQL Server に送信される Transact-SQL ステートメントや、これらのステートメントで返される SQL Server の結果セットを取得できます。 BizTalk Server は SQL Server と密接に連携しているので、SQL Server Profile のトレースを分析することで、SQL Server データベースに対する読み取りまたは書き込み時に BizTalk Server で発生する問題を分析するのに役立てることができます。 SQL Server Profiler を使用する方法の詳細については、SQL Server のマニュアルを参照してください。  
  
- SQL Server データベースに対して直接 SQL ステートメントを実行する SQL Server のクエリ エディターを使用できます。 この機能は、BizTalk Server データベースに対してクエリを実行するときや、特定のシナリオにおいて BizTalk Server データベースを更新するときに役立つ場合があります。 クエリ エディターの詳細については、SQL Server のマニュアルを参照してください。  
  
- レビュー [SQL Server のトラブルシューティング](../core/troubleshooting-sql-server.md)の追加情報。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング](../core/troubleshooting.md)