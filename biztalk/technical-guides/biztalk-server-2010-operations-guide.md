---
title: BizTalk Server 2010 操作ガイド |Microsoft Docs
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
ms.openlocfilehash: 1b2dcbc8dcd8602828e8a2a04986de2a88d545cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399341"
---
# <a name="biztalk-server-2010-operations-guide"></a>BizTalk Server 2010 操作ガイド
Microsoft® BizTalk® Server 2010 操作ガイドへようこそ。 このガイドの実装と、BizTalk ソリューション、特に IT プロフェッショナルの管理に関連するすべてのユーザーにとって価値のあるリソースを作成しました。  
  
 Chm、pdf、docx フォームには、このガイドのコピーをダウンロードするには[Microsoft BizTalk Server 2010 操作ガイド](http://go.microsoft.com/fwlink/?LinkId=212652)(http://go.microsoft.com/fwlink/?LinkId=212652)します。  
  
## <a name="which-versions-of-biztalk-server-does-the-guide-cover"></a>このガイドは BizTalk Server のバージョンをでしょうか。  
 このガイドは、BizTalk Server に対応し、運用の準備に役立つ情報を立ち上げることができますを提供します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップします。  
  
> [!NOTE]
>  操作ガイドを参照する[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]または[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]を参照してください[ http://go.microsoft.com/fwlink/?LinkID=130458](http://go.microsoft.com/fwlink/?LinkID=130458)します。  
  
## <a name="where-do-i-start"></a>どこから始めるか。  
 計画、展開、および管理の機能面に従ってガイドで構成しました、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。 これらの機能面に従ってため読み取ることができます。 ただし、チェックリストがある最も収集後、BizTalk Server 操作ガイドの情報を実現するには、私たちは分類のアクセシビリティの容易にするための次の表に、ドキュメント内のすべてのチェックリスト。  
  
|||  
|-|-|  
|**BizTalk 環境の設定**|**高可用性とディザスター リカバリー環境を設定します。**|  
|-   [チェックリスト:BizTalk Server の概要](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)<br />-   [チェックリスト:Windows Server を構成します。](~/technical-guides/checklist-configuring-windows-server.md)<br />-   [チェックリスト:インターネット インフォメーション サービスを構成します。](~/technical-guides/checklist-configuring-internet-information-services.md)<br />-   [チェックリスト:SQL Server の構成](../technical-guides/checklist-configuring-sql-server.md)<br />-   [チェックリスト:BizTalk Server の構成](~/technical-guides/checklist-configuring-biztalk-server.md)|-   [チェックリスト:フォールト トレランスまたは負荷分散と高可用性を実現します。](~/technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)<br />-   [チェックリスト:ディザスター リカバリーによる可用性の向上](~/technical-guides/checklist-increasing-availability-with-disaster-recovery.md)|  
|**監視、テスト、およびトラブルシューティング**|**パフォーマンスとメンテナンス**|  
|-   [チェックリスト:運用準備状況の監視](~/technical-guides/checklist-monitoring-operational-readiness.md)<br />-   [チェックリスト:メンテナンスと BizTalk Server データベースのトラブルシューティング](../technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)<br />-   [チェックリスト:運用準備のテスト](~/technical-guides/checklist-testing-operational-readiness.md)<br />-   [チェックリスト:Operations Manager 2007 による BizTalk Server の監視](~/technical-guides/checklist-monitoring-biztalk-server-with-operations-manager-2007.md)<br />-   [チェックリスト:SQL Server の監視](~/technical-guides/checklist-monitoring-sql-servers.md)|保守関連のチェックリスト。<br /><br /> -   [チェックリスト:毎日のメンテナンス チェックの実行](~/technical-guides/checklist-performing-daily-maintenance-checks.md)<br />-   [チェックリスト:毎週のメンテナンス チェックの実行](~/technical-guides/checklist-performing-weekly-maintenance-checks.md)<br />-   [チェックリスト:毎月のメンテナンス チェックの実行](~/technical-guides/checklist-performing-monthly-maintenance-checks.md)<br /><br /> パフォーマンス関連のチェックリスト。<br /><br /> -   [チェックリスト:毎週のパフォーマンス チェックの実行](~/technical-guides/checklist-performing-weekly-performance-checks.md)<br />-   [チェックリスト:毎月のパフォーマンス チェックの実行](~/technical-guides/checklist-performing-monthly-performance-checks.md)|  
|**その他の重要なタスクのチェックリスト**||  
|-   [チェックリスト:アプリケーションを展開します。](~/technical-guides/checklist-deploying-an-application.md)<br />-   [チェックリスト:別のアプリケーションへのバインドのエクスポート](~/technical-guides/checklist-exporting-bindings-from-one-application-to-another.md)<br />-   [チェックリスト:アセンブリの更新](~/technical-guides/checklist-updating-an-assembly.md)<br />-   [チェックリスト:BizTalk アプリケーション内のアイテムを更新しています](~/technical-guides/checklist-updating-artifacts-in-a-biztalk-application.md)|-   [チェックリスト:サイド バイ サイド バージョン管理を使用してアプリケーションの更新](~/technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)<br />-   [チェックリスト:サイド バイ サイド バージョン管理を使用してオーケストレーションを更新しています](~/technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md)<br />-   [チェックリスト:インストールして、証明書の構成](../technical-guides/checklist-installing-and-configuring-certificates.md)<br />-   [チェックリスト:セキュリティで保護された環境での運用計画](../technical-guides/checklist-planning-for-operations-in-a-secure-environment.md)|  
  
 次のタスクを実行している場合は、関連するセクションで開始できます。  
  
- **運用準備状況を評価する**:評価との運用準備状況の評価に注目しているかどうか、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、展開し、読み取ることで開始、[運用チェックリスト](~/technical-guides/operations-checklists.md)と[のBizTalkServerの可用性を増やすと](~/technical-guides/increasing-availability-for-biztalk-server.md)セクション。  
  
- **運用できる状態になる**:いることを確認する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インフラストラクチャおよび運用できる状態になるアプリケーションを参照してください。、 [BizTalk server 環境のプランニング](~/technical-guides/planning-the-environment-for-biztalk-server.md)セクション。  
  
- **運用環境を維持**:操作ガイドのトピックのほとんどで、運用を維持を支援します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 次のセクションで、運用環境を維持するためのベスト プラクティス、主要な概念、およびプロシージャが表示されます。[BizTalk Server の可用性を高める](~/technical-guides/increasing-availability-for-biztalk-server.md)、 [BizTalk Server の監視](~/technical-guides/monitoring-biztalk-server2.md)、および[BizTalk Server2 のメンテナンス](~/technical-guides/maintaining-biztalk-server2.md)します。  
  
## <a name="whats-in-it"></a>これには  
 実際の経験に基づくガイダンスです。 Microsoft フィールド担当者、取引先組織、および、予定のお客様で発生したこのガイドの概念では、展開、および BizTalk Server のインストールを管理します。 IT プロフェッショナル向けのこのグループには、さまざまな BizTalk ソリューションの広範な実践的な経験が蓄積されています。 エクスペリエンスを獲得すると、作成のチェックリスト、ベスト プラクティス、およびプレゼンテーション ガイドを将来[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作。 収集し、ガイドを作成するには、この情報を整理します。  
  
 このガイドの主要な部分を初めて使用します。ただし、かなりの部分が指す[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ、ホワイト ペーパー、技術記事、およびその他のソース。 これが慎重にレビューおよびコミュニティの専門家によって検査[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]IT プロフェッショナルと、このトピックの最後にいただいたことを承認、製品開発チームのメンバー。 ここで説明する情報が役立つと思われます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を解決したり、何よりも、多くの展開および保守時に発生する一般的な問題を回避、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。  
  
## <a name="acknowledgments"></a>受信確認  
 ここで、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] User Education チームがのコンテンツの適切な対処だけでなく、技術的なフィードバックを提供するため次の個人の優れた貢献をいただいた確認、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作ガイド。  
  
-   Paolo Salvatori、Tim Wieman