---
title: I/O の競合を監視および削減できるデータベース |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd6d3343-3fa3-469a-9772-e94f22fdf558
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 446a4b512b4f38869637cb3968305fad1e869dae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298778"
---
# <a name="monitoring-and-reducing-database-io-contention"></a>監視と、データベース I/O の競合を減らす
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によってパフォーマンスが前提として多くの場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンスで、さらには、多くの場合を前提としてディスク I/O のパフォーマンスにします。 したがって、する必要がありますを監視し、実行するコンピューター上のディスク I/O のパフォーマンスを調整[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]そのハウス、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
## <a name="monitoring-disk-io"></a>ディスク I/O の監視  
 データベース集約型の性質[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、ディスク I/O が、メッセージ ボックス データベースのボトルネックになる簡単に、BizTalk 追跡データベースですこれは true。 ディスク I/O でのデータベース ファイルのボトルネックをしたことがない場合でも、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 。環境。 したがって、事前に、データ ファイルとトランザクション ログ ファイルを格納するディスクのディスク I/O のパフォーマンスを測定することをお勧めします。 システム モニターを使用してディスク I/O パフォーマンスの監視の詳細については、次を参照してください。、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]記事["デプロイメント前 I/O のベスト プラクティス"](http://go.microsoft.com/fwlink/?LinkId=104829) (http://go.microsoft.com/fwlink/?LinkId=104829)。 SAN を使用している場合は、ディスク I/O パフォーマンスを測定する SAN ハードウェアの製造元から特定のツールも必要があります。  
  
## <a name="separating-the-messagebox-and-biztalk-tracking-dta-databases-and-log-files"></a>メッセージ ボックス データベースと BizTalk 追跡 (DTA) データベースおよびログ ファイルの分離  
 メッセージ ボックス データベースと BizTalk 追跡データベースが最もアクティブなので、これらをディスク I/O の競合の問題の可能性を減らすために専用のドライブ上のそれぞれのデータ ファイルとトランザクション ログ ファイルを配置することをお勧めします。 たとえば、メッセージ ボックス データベースと BizTalk 追跡データベース ファイルを 4 台のドライブを必要次の各 1 つのドライブ:  
  
-   メッセージ ボックス データ ファイル  
  
-   メッセージ ボックス データベースのトランザクション ログ ファイル  
  
-   データ ファイルを BizTalk 追跡  
  
-   トランザクション ログ ファイルを BizTalk 追跡  
  
 メッセージ ボックス データベースと BizTalk 追跡データベースを分離し、データベース ファイルとトランザクション ログ ファイルの異なる物理ディスクを分離することは、ディスク I/O の競合を減らすためのベスト プラクティスと見なされます。 可能な限り多くの物理スピンドル ディスク I/O に分散しようとしてください。 ディスクの競合の回避の詳細については、次を参照してください。[ディスクの競合を回避する方法](http://go.microsoft.com/fwlink/?LinkId=158809)(http://go.microsoft.com/fwlink/?LinkId=158809) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスの最適化をガイドします。  
  
 構成した後、ファイルを手動で分離する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 詳細については、次を参照してください。、 [BizTalk Server データベースの最適化のホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkId=101578) (http://go.microsoft.com/fwlink/?LinkId=101578)。  
  
## <a name="see-also"></a>参照  
 [ログ (PAL) のツールのパフォーマンス分析の使用](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)