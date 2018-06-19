---
title: BizTalk Server 2010 操作ガイド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dc0d8e9-9ad6-4ce1-8ca7-399b67cb360e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5078cdc0a4b2d28e81daf2247cb0f1f35b3d6288
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010387"
---
# <a name="biztalk-server-2010-operations-guide"></a>BizTalk Server 2010 操作ガイド
Microsoft® BizTalk® Server 2010 操作ガイドへようこそ。 実装と特に IT プロフェッショナル向けに、BizTalk ソリューションの管理に関連するすべてのユーザーにとって価値のあるリソースにするには、このガイドを作成しました。  
  
 Chm、pdf、または docx フォームでは、このガイドのコピーをダウンロードするには[Microsoft BizTalk Server 2010 操作ガイド](http://go.microsoft.com/fwlink/?LinkId=212652)(http://go.microsoft.com/fwlink/?LinkId=212652)。  
  
## <a name="which-versions-of-biztalk-server-does-the-guide-cover"></a>このガイドはどのバージョンの BizTalk Server をカバーしますか。  
 このガイドは BizTalk Server の要求を満たす、運用の準備について説明するとすぐに開始、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップします。  
  
> [!NOTE]
>  操作ガイド」を参照してくださいに[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]または[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]を参照してください[http://go.microsoft.com/fwlink/?LinkID=130458](http://go.microsoft.com/fwlink/?LinkID=130458)です。  
  
## <a name="where-do-i-start"></a>ここで行いますか。  
 計画、展開、および管理の機能面に従ってガイドを編成して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。 これらの機能面に従ってため読み取ることができます。 ただし、チェックリストことが最も収集後は、BizTalk Server オペレーション ガイドの情報を実現するには、私たちが分類ユーザー補助の簡単操作の次の表に、ドキュメント内のすべてのチェックリスト。  
  
|||  
|-|-|  
|**BizTalk 環境の設定**|**高可用性と障害回復環境を設定します。**|  
|-   [チェックリスト: BizTalk Server の概要](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)<br />-   [チェックリスト: Windows Server を構成します。](~/technical-guides/checklist-configuring-windows-server.md)<br />-   [チェックリスト: インターネット インフォメーション サービスを構成します。](~/technical-guides/checklist-configuring-internet-information-services.md)<br />-   [チェックリスト: SQL Server を構成します。](../technical-guides/checklist-configuring-sql-server.md)<br />-   [チェックリスト: BizTalk Server を構成します。](~/technical-guides/checklist-configuring-biztalk-server.md)|-   [チェックリスト: フォールト トレランスと負荷分散と高可用性を実現します。](~/technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)<br />-   [チェックリスト: 災害復旧と可用性の向上](~/technical-guides/checklist-increasing-availability-with-disaster-recovery.md)|  
|**監視、テスト、およびトラブルシューティング**|**パフォーマンスとメンテナンス**|  
|-   [チェックリスト: 監視の運用の準備](~/technical-guides/checklist-monitoring-operational-readiness.md)<br />-   [チェックリスト: を維持し、BizTalk Server データベースのトラブルシューティング](../technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)<br />-   [チェックリスト: テスト運用の準備](~/technical-guides/checklist-testing-operational-readiness.md)<br />-   [チェックリスト: Operations Manager 2007 の BizTalk Server の監視](~/technical-guides/checklist-monitoring-biztalk-server-with-operations-manager-2007.md)<br />-   [チェックリスト: SQL サーバーの監視](~/technical-guides/checklist-monitoring-sql-servers.md)|保守関連のチェックリスト。<br /><br /> -   [チェックリスト: メンテナンスを毎日チェックを実行します。](~/technical-guides/checklist-performing-daily-maintenance-checks.md)<br />-   [チェックリスト: 毎週の保守チェックの実行](~/technical-guides/checklist-performing-weekly-maintenance-checks.md)<br />-   [チェックリスト: 毎月の保守チェックの実行](~/technical-guides/checklist-performing-monthly-maintenance-checks.md)<br /><br /> パフォーマンス関連のチェックリスト。<br /><br /> -   [チェックリスト: 毎週のパフォーマンス チェックの実行](~/technical-guides/checklist-performing-weekly-performance-checks.md)<br />-   [チェックリスト: を実行する毎月パフォーマンス チェック](~/technical-guides/checklist-performing-monthly-performance-checks.md)|  
|**その他の重要なタスクのチェックリスト**||  
|-   [チェックリスト: アプリケーションを展開します。](~/technical-guides/checklist-deploying-an-application.md)<br />-   [チェックリスト: から別のアプリケーションへのバインドのエクスポート](~/technical-guides/checklist-exporting-bindings-from-one-application-to-another.md)<br />-   [チェックリスト: アセンブリを更新します。](~/technical-guides/checklist-updating-an-assembly.md)<br />-   [チェックリスト: BizTalk アプリケーション内のアイテムを更新します。](~/technical-guides/checklist-updating-artifacts-in-a-biztalk-application.md)|-   [チェックリスト: サイド バイ サイドのバージョン管理を使用してアプリケーションの更新](~/technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)<br />-   [チェックリスト: サイド バイ サイドのバージョン管理を使用してオーケストレーションを更新します。](~/technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md)<br />-   [チェックリスト: インストールと証明書の構成](../technical-guides/checklist-installing-and-configuring-certificates.md)<br />-   [チェックリスト: がセキュリティで保護された環境での操作の計画](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md)|  
  
 次のタスクを実行する場合は、関連するセクションで開始できます。  
  
-   **運用の準備を評価する**: 評価しての運用の準備の評価に注目しているかどうか、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、展開し、読み取ることで開始、 [Operations チェックリスト](~/technical-guides/operations-checklists.md)と[BizTalk Server の可用性を高める](~/technical-guides/increasing-availability-for-biztalk-server.md)セクションです。  
  
-   **運用できる状態になる**: ことを確認する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インフラストラクチャと運用できる状態になるアプリケーションを参照してください。、 [BizTalk server 環境のプランニング](~/technical-guides/planning-the-environment-for-biztalk-server.md)セクションです。  
  
-   **運用環境を維持する**: operations guide の「トピックほとんどに役立つ運用を維持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 次のセクションでは、運用環境を維持するためのベスト プラクティス、主要な概念、およびプロシージャが検索されます: [BizTalk Server の可用性の向上](~/technical-guides/increasing-availability-for-biztalk-server.md)、 [のBizTalkServerの監視](~/technical-guides/monitoring-biztalk-server2.md)、および[BizTalk Server2 を維持する](~/technical-guides/maintaining-biztalk-server2.md)です。  
  
## <a name="whats-in-it"></a>これには  
 実際の経験に基づいてガイダンスです。 Microsoft フィールド担当者、取引先組織を設定されている場合、顧客によって作成されたものは、ガイドの概念は、配置、および BizTalk Server 環境を維持します。 IT プロフェッショナル向けのこのグループには、多様な範囲の BizTalk ソリューションと豊富な実践的な経験を蓄積しました。 エクスペリエンスを獲得すると、作成のチェックリスト、ベスト プラクティス、およびプレゼンテーション ガイドを将来[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作します。 お収集され、番組ガイドを作成するには、この情報を構成します。  
  
 このガイドの主要な部分は新しいです。ただし、かなりの部分が指す[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ、ホワイト ペーパー、サポート技術情報の記事、およびその他のソース。 慎重にレビューおよびのコミュニティからの専門家によって調査[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]IT プロフェッショナルと、このトピックの最後に感謝ことを承認、製品開発チームのメンバーです。 ここで示す情報が役立つことが確信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ユーザーを解決、およびすべての上、展開および保守中に発生する一般的な問題の多くを回避、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。  
  
## <a name="acknowledgments"></a>受信確認  
 ここで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ユーザー教育チームは、相当のコンテンツのだけでなく、技術的なフィードバックを提供するため次の個人の未処理の投稿を確認する感謝、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operations guide の「します。  
  
-   Paolo Salvatori、Tim Wieman