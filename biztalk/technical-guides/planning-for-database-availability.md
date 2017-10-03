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
ms.openlocfilehash: ea5aa21ad9db78236d7b1e5335053b7c9ce28770
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-database-availability"></a>データベースの可用性の計画
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ことにより、ビジネス プロセスが信頼できるとなり、持続性の保存することでプロセスの状態およびビジネス データをメッセージング エンジンは[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース、BizTalk メッセージ ボックス データベースと呼ばれます。 信頼性および持続データの持続性では、基になるデータ ストアと同程度のみであるための高可用性の計画、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは非常に重要です。  
  
## <a name="hardware-considerations"></a>ハードウェアについての注意事項  
 高可用性を確保する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは、ハードウェアを計画する場合、次を検討してください。  
  
1.  家に記憶域エリア ネットワーク (SAN) の実装の検討、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 SAN ディスクは、RAID を使用して構成する必要がありますトポロジを最高のパフォーマンスと高可用性を実現可能な場合に 1 + 0 (ストライプはミラー セット)。 家に SAN の使用の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください、 [BizTalk Server データベースの最適化](http://go.microsoft.com/fwlink/?LinkID=101578)ホワイト ペーパー ([http://go.microsoft.com/fwlink/?LinkID=101578](http://go.microsoft.com/fwlink/?LinkID=101578))。  
  
2.  実行している複数のコンピューターのインストールに関する計画[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ハウスへ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 実行している複数のコンピューター[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]必要になる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)](推奨) クラスタ リングや特定のハウジング[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]別個の物理データベース[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)](推奨も) のインスタンス。  
  
3.  実行する 1 つまたは複数のコンピューターのインストールに関する計画[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を実装する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログ配布の障害復旧の目的でします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実装してデータベースのスタンバイの機能の使用により[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログ配布します。 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログ配布は、スタンバイ サーバーで、実稼働サーバーが失敗した場合に、データベース処理を再開できるように、データベースとトランザクション ログ ファイルの復元とバックアップを自動化します。 実装の詳細については[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログ配布の障害復旧の目的を参照してください[新機能は、BizTalk Server ログ配布しますか?](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="software-considerations"></a>ソフトウェアの考慮事項  
 高可用性を確保する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは、ソフトウェアを計画する場合、次を検討してください: バージョンおよびエディションをインストールする予定[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]フェールオーバー クラスタ リングのサポートや BizTalk ログ配布のサポートをサポートします。 各エディションでサポートされる機能の完全な一覧については[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]を参照してください[SQL Server 2008 の各エディションでサポートされる機能](http://go.microsoft.com/fwlink/?LinkId=151940)([http://go.microsoft.com/fwlink/?LinkId = 151940](http://go.microsoft.com/fwlink/?LinkId=151940)) で、[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]ドキュメント。  
  
## <a name="high-availability-vs-disaster-recovery"></a>高可用性とします。災害復旧  
 可用性を高めるための 2 つの異なるメソッドがある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境: フォールト トレランスおよび負荷分散、または災害復旧を使用して可用性を実現するを使用して高可用性を提供します。 各メソッドでは、可用性が向上、中にそれらの主な違いは、フォールト トレランスや、負荷分散を通常は、災害復旧よりもはるかに高速の復旧時間を提供します。 そのため、フォールト トレランスにソリューションをビルドまたは負荷分散がより一般的なと考えるの可用性を実現するだけではなく高可用性を提供します。 どちらの方法は、実稼働環境で使用しないでください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
 高い可用性を実現、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows クラスタ リングとフォールト トレランスを使用するデータベース。 高可用性を提供することの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[データベースの高可用性](../technical-guides/high-availability-for-databases.md)です。  
  
 災害復旧を使用して可用性を向上させる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布します。 可用性を高めるため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と災害復旧、データベースには、トピックの手順[チェックリスト: 可用性と災害復旧を増やす](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)です。