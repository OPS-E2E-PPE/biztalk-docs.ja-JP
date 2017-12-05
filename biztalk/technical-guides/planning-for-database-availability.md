---
title: "データベースの可用性の計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aa74257-4159-46f6-b538-f7e9083d74ad
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d77ce6572ace3617308a046a422a3422b2dd8df5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="planning-for-database-availability"></a>データベースの可用性の計画
BizTalk Server メッセージング エンジンは、ビジネス プロセスは、信頼できると、保存することで持続性の状態およびビジネス データを BizTalk メッセージ ボックス データベースと呼ばれる SQL Server データベースを処理することにより、します。 信頼性および持続データの持続性に有効なは、基になるデータ ストアとして、BizTalk Server データベースの高可用性の計画が非常に重要です。  
  
## <a name="hardware-considerations"></a>ハードウェアについての注意事項  
 ハードウェアを計画する場合は、BizTalk Server データベースの高可用性を確保するには、次について考えてみます。  
  
1.  記憶域エリア ネットワーク (SAN)、BizTalk Server データベースを格納するための実装を検討します。 SAN ディスクは、RAID を使用して構成する必要がありますトポロジを最高のパフォーマンスと高可用性を実現可能な場合に 1 + 0 (ストライプはミラー セット)。 
  
2.  BizTalk Server データベースを格納する SQL Server を実行している複数のコンピューターをインストールする方法を計画します。 SQL Server を実行している複数のコンピューターは、SQL server クラスタ リング (推奨) や (推奨も)、独立した物理 SQL Server インスタンス上の特定の BizTalk Server データベースを格納している必要があります。  
  
3.  SQL Server のログ配布の障害復旧の目的で実装する SQL Server を実行している 1 つまたは複数のコンピューターをインストールする方法を計画します。 BizTalk Server が SQL Server を使用してデータベースのスタンバイ機能を実装してログ配布します。 スタンバイ サーバーで、実稼働サーバーが失敗した場合に、データベース処理を再開できるように SQL のサーバーはログ配布のバックアップと、データベースとトランザクション ログ ファイルの復元を自動化します。 SQL Server のログ配布の障害復旧の目的での実装の詳細については、次を参照してください[新機能は、BizTalk Server ログ配布しますか?。](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="software-considerations"></a>ソフトウェアの考慮事項  
 ソフトウェアを計画する場合、BizTalk Server データベースの高可用性を確保するには、次を検討してください: バージョンおよびフェールオーバー クラスタ リングのサポートや BizTalk ログ配布のサポートをサポートする SQL Server のエディションをインストールする予定です。 SQL Server のエディションでサポートされる機能の完全な一覧を参照してください。[エディションとサポートされる機能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)します。
  
## <a name="high-availability-vs-disaster-recovery"></a>高可用性とします。災害復旧  
 BizTalk Server 環境の可用性を高めるための 2 つの異なるメソッド: フォールト トレランスおよび負荷分散、または災害復旧を使用して可用性を実現するを使用して高可用性を提供します。 各メソッドでは、可用性が向上、中にそれらの主な違いは、フォールト トレランスや、負荷分散を通常は、災害復旧よりもはるかに高速の復旧時間を提供します。 そのため、フォールト トレランスにソリューションをビルドまたは負荷分散がより一般的なと考えるの可用性を実現するだけではなく高可用性を提供します。 どちらの方法は、実稼働の BizTalk Server 環境で使用しないでください。  
  
 Windows クラスタ リングとフォールト トレランスを使用して、BizTalk Server データベースの高可用性を実現します。 詳細については、BizTalk Server データベースの高可用性を実現する、次を参照してください。[データベースの高可用性](../technical-guides/high-availability-for-databases.md)です。  
  
 災害と可用性を向上させる BizTalk Server を使用して回復をログ配布します。 障害復旧に BizTalk Server データベースの可用性を向上させるには、トピックの手順に従います[チェックリスト: 可用性と災害復旧を増やす](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)です。