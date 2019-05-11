---
title: データベースの I/O の競合の監視と軽減 |Microsoft Docs
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
ms.openlocfilehash: ab8c8ca63556281644100e026a278c4141e19077
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379475"
---
# <a name="monitoring-and-reducing-database-io-contention"></a>監視と、データベース I/O 競合の削減
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パフォーマンスは、多くの場合に実行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンスで、さらに、ディスク I/O パフォーマンスに基づいて多くの場合は。 したがって、する必要がありますを監視し、ディスク I/O を実行しているコンピューターのパフォーマンスを調整[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]その家、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
## <a name="monitoring-disk-io"></a>ディスク I/O の監視  
 データベース処理を要する性質[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ディスク I/O がメッセージ ボックス データベースのボトルネックになることができます簡単に、BizTalk 追跡データベースですこれはディスク I/O でデータベース ファイルのボトルネックをしたことがない場合でも、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 。環境。 そのため、事前にデータとトランザクション ログ ファイルを格納するディスクのディスク I/O パフォーマンスを測定することをお勧めします。 システム モニターを使用してディスク I/O パフォーマンスを監視する方法の詳細については、次を参照してください。、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]記事["展開前 I/O のベスト プラクティス"](http://go.microsoft.com/fwlink/?LinkId=104829) (<http://go.microsoft.com/fwlink/?LinkId=104829>)。 SAN を使用している場合は、ディスク I/O パフォーマンスを測定する SAN ハードウェアの製造元から特定のツールも必要があります。  
  
## <a name="separating-the-messagebox-and-biztalk-tracking-dta-databases-and-log-files"></a>メッセージ ボックス データベースと BizTalk 追跡 (DTA) データベースとログ ファイルの分離  
 メッセージ ボックス データベースと BizTalk 追跡データベースは、最もアクティブであるために、ディスク I/O の競合に関する問題の可能性を低減する専用のドライブにこれらの各データ ファイルとトランザクション ログ ファイルを配置することをお勧めします。 たとえば、メッセージ ボックス データベースと BizTalk 追跡データベース ファイルを 4 つのドライブを必要次の各の 1 つのドライブ:  
  
- メッセージ ボックス データ ファイル  
  
- メッセージ ボックス データベースのトランザクション ログ ファイル  
  
- データ ファイルを BizTalk 追跡  
  
- トランザクション ログ ファイルを BizTalk 追跡  
  
  メッセージ ボックス データベースと BizTalk 追跡データベースを分離し、データベース ファイルとトランザクション ログ ファイルの異なる物理ディスクを分離することは、ディスク I/O の競合を減らすためのベスト プラクティスと見なされます。 できるだけ多くの物理スピンドルにディスク I/O を分散しようとしてください。 ディスクの競合を避ける方法についての詳細については、次を参照してください。[ディスクの競合を回避する方法](http://go.microsoft.com/fwlink/?LinkId=158809)(<http://go.microsoft.com/fwlink/?LinkId=158809>) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスの最適化をガイドします。  
  
  構成した後、ファイルを手動で分離する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。、 [BizTalk Server データベースの最適化に関するホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkId=101578) (<http://go.microsoft.com/fwlink/?LinkId=101578>)。  
  
## <a name="see-also"></a>参照  
 [ログ (PAL) ツールのパフォーマンス分析の使用](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)