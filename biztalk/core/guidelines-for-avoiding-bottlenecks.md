---
title: ボトルネックを回避するためのガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 640ab399-b22d-4f71-b41d-ea8d778e064a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db480df2d47fdc03b1719ecfb17fdbb8f23eea41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387566"
---
# <a name="guidelines-for-avoiding-bottlenecks"></a>ボトルネックを回避するためのガイドライン
既定の設定中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最適なパフォーマンスを提供する多くのハードウェアおよびソフトウェア構成の一部のシナリオである可能性があります設定または展開の構成を変更すると役立ちます。 構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、次のパフォーマンス ガイドラインを検討してください。  

-   リソースの競合を防ぐためには、受信、オーケストレーション、および別のホストに送信を分離します。 競合を最小限に抑えるさらに、他のホストから追跡サービスを分離します。  

-   BizTalk Server で CPU の処理がボトルネックになっている場合は、cpu を追加または高速の Cpu にアップグレードしてスケール アップは、BizTalk Server。  

## <a name="sql-server-guidelines"></a>SQL Server のガイドライン  
 Microsoft SQL Server を構成するときに、次のパフォーマンス ガイドラインを検討してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースは、可能であれば、専用の SQL Server インスタンス上で実行するように構成する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベース中心のアプリケーション、その分離、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターおよび格納する SQL Server コンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのパフォーマンスが向上し、運用環境でのベスト プラクティスを考慮する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  

- 可能であれば、SQL Server で高速なディスク サブシステムを使用します。 バックアップの電源装置と (raid 5/10) するときに、独立したディスクの種類 5 の冗長な配列または記憶域エリア ネットワーク (SAN) を使用します。  

- SQL Server のディザスター リカバリー プロセスを使用して、データベースを定期的にバックアップします。 BizTalk Server サービスは、SQL Server の接続障害から自動的に復旧します。  

- BizTalk 追跡データベース (BizTalkDTADb) から別のサーバーには、各メッセージ ボックスを分離します。 小規模な展開の CPU リソースが使用可能なメッセージ ボックスの上に、BizTalkDTADb データベースから別の物理ディスクを分離する可能性があります十分です。  

- プライマリ メッセージ ボックスには、CPU プロセッサの飽和やディスク操作 (ディスクの平均キュー長さ) からの待機時間が原因でボトルネック可能性があります。 CPU の処理がボトルネックになっている場合は、プライマリ メッセージ ボックスに CPU プロセッサを追加します。 指定しない場合、この方法がマスター メッセージ ボックスが、他のメッセージ ボックス データベースにメッセージのルーティングを処理できるより効率的にマスター メッセージ ボックスでのパブリッシングを無効にしてください。  

- ディスク操作がボトルネックとなっている場合は、BizTalkDTADb データベースを専用の SQL Server コンピューターまたは専用のディスクに移動します。 プライマリ メッセージ ボックスで、CPU の処理もディスク操作がボトルネックでない場合は、既存のハードウェアを活用する同じ SQL Server コンピューターに新しいメッセージ ボックス データベースを作成できます。  

- 別の物理ディスク上にメッセージ ボックス データベースと BizTalkDTADb データベースのトランザクションとデータのログ ファイルを分離する SQL Server のベスト プラクティスに従ってください。  

- データとログ ファイルのための十分な記憶域スペースを割り当てるそれ以外の場合 SQL Server では、すべてのログ ファイルが保持されているディスクの空き領域の消費が自動的にします。 ログ ファイルの初期サイズは、特定のシナリオでは、特定の要件によって異なります。 テスト結果に基づいて展開の平均ファイル サイズを推定し、ソリューションを実装する前に、記憶域スペースを展開します。  

- メッセージ ボックス データベース、追跡、およびビジネス アクティビティ監視 (BAM) データベースなどの高いディスクの使用状況データベースには、十分な記憶域を割り当てます。 ソリューションは、BizTalk Framework メッセージング プロトコルを使用している場合は、BizTalk 構成データベース (BizTalkMgmtDb) のための十分な記憶域を割り当てます。  

- ビジネス ニーズ [データの保有期間] を特定のシナリオで処理されたデータの量に応じて、BizTalkDTADb データベースが大きくなりすぎないように、追跡データベースの Archive/purge ジョブを構成します。 このデータベースの拡大とパフォーマンスが低下 (特に 1 つの BizTalkDTADb データベースには、複数のメッセージ ボックスがサポートされている) 場合データ挿入率に制限していますが、データベースの完全な容量に達しているためです。  

- スケール アップがボトルネックになっている場合は、messagebox データベースと BizTalkDTADb データベースをホストするサーバー。 Cpu の追加、メモリを追加する、高速の Cpu にアップグレードする、高速の専用ディスクを使用して、ハードウェアをスケール アップすることができます。
