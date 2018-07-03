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
ms.openlocfilehash: 45071b7990d8fd4a926efa56b9e98cbd633553ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017810"
---
# <a name="guidelines-for-avoiding-bottlenecks"></a>ボトルネックを回避するためのガイドライン
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の既定の設定は、多くのハードウェアやソフトウェアの構成に最適なパフォーマンスを提供しますが、シナリオによっては、設定や展開構成を変更すると効果的な場合があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成するときは、次のパフォーマンス ガイドラインを考慮してください。  

-   リソース競合を回避するには、受信、オーケストレーション、および送信を、個別のホストに分離します。 競合をさらに最小限に抑えるには、追跡サービスを他のホストから分離します。  

-   BizTalk Server 上の CPU 処理がボトルネックである場合は、CPU を追加するか、より高速の CPU にアップグレードして、BizTalk Server をスケール アップします。  

## <a name="sql-server-guidelines"></a>SQL Server のガイドライン  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で Microsoft SQL Server を構成するときは、次のパフォーマンス ガイドラインを考慮してください。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースは、できるだけ専用の SQL Server インスタンスで実行するよう構成してください。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、データベース中心のアプリケーションです。そのため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターと、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを格納する SQL Server コンピューターとを分離することでパフォーマンスが向上します。これは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 運用環境のベスト プラクティスといえます。  

- 可能であれば、高速なディスク サブシステムを SQL Server で使用するようにします。 RAID5/10 (Redundant Array of Independent Disks type 5) またはストレージ エリア ネットワーク (SAN) を、バックアップの電源装置と共に使用します。  

- SQL Server のディザスター リカバリー プロセスを使用して、データベースを定期的にバックアップします。 BizTalk Server サービスは、SQL Server の接続障害から自動的に復旧します。  

- BizTalk 追跡データベース (BizTalkDTADb) から各メッセージ ボックスを個別のサーバーに分離します。 小規模な展開で CPU リソースが使用可能であれば、BizTalkDTADb データベースからメッセージ ボックスを個別の物理ディスクに分離するだけで十分な場合もあります。  

- プライマリ メッセージ ボックスは、CPU プロセッサの飽和やディスク操作からの待機時間 (Average Disk Queue Length) が原因でボトルネックとなる可能性があります。 CPU 処理がボトルネックである場合は、プライマリ メッセージ ボックスに CPU プロセッサを追加します。 指定しない場合、この方法がマスター メッセージ ボックスが、他のメッセージ ボックス データベースにメッセージのルーティングを処理できるより効率的にマスター メッセージ ボックスでのパブリッシングを無効にしてください。  

- ディスク操作がボトルネックである場合は、BizTalkDTADb データベースを専用の SQL Server コンピューターまたは専用のディスクに移動します。 プライマリ メッセージ ボックスの CPU 処理もディスク操作もボトルネックでない場合は、既存のハードウェアを利用して、同じ SQL Server コンピューター上に新しいメッセージ ボックス データベースを作成できます。  

- SQL Server のベスト プラクティスに従って、MessageBox データベースと BizTalkDTADb データベースのトランザクションおよびデータ ログ ファイルを、個別の物理ディスクに分離します。  

- データ ファイルとログ ファイルには十分な記憶域を割り当てるようにします。そうしないと、ログ ファイルが格納されているディスク上の使用可能な全容量が、SQL Server によって自動的に消費されます。 ログ ファイルの初期サイズは、特定のシナリオにおける個別の要件によって異なります。 テスト結果に基づいて展開の平均ファイル サイズを見積もり、ソリューションの実装前に記憶域を拡張します。  

- メッセージ ボックス データベース、追跡データベース、ビジネス アクティビティ監視 (BAM) データベースなど、ディスク使用率の高いデータベースに十分な記憶域を割り当てます。 ソリューションで BizTalk Framework メッセージング プロトコルを使用する場合は、BizTalk 構成データベース (BizTalkMgmtDb) に十分な記憶域を割り当てます。  

- 特定のシナリオにおけるビジネス ニーズ [データの保有期間] および処理対象データの量に応じて、追跡データベースの Archive/Purge ジョブを構成して、BizTalkDTADb データベースが大きくなりすぎないようにします。 このデータベースが大きくなると、パフォーマンスが悪影響を受ける可能性があります (特に 1 つの BizTalkDTADb データベースで複数のメッセージ ボックスをサポートする場合)。データベース容量の上限に達すると、データ挿入率が制限されるためです。  

- メッセージ ボックス データベースおよび BizTalkDTADb データベースをホストするサーバーがボトルネックである場合は、これらのサーバーをスケール アップします。 CPU の追加、メモリの追加、高速な CPU へのアップグレード、および高速な専用ディスクの使用によって、ハードウェアをスケール アップできます。
