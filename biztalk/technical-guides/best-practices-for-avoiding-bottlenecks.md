---
title: ボトルネックを回避するためのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81da2e31-dce0-43fb-841f-e65ff99e80a7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07145b9b46f1527f970ec27511827d385468fcaa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401262"
---
# <a name="best-practices-for-avoiding-bottlenecks"></a>ボトルネックを回避するためのベスト プラクティス
既定の設定中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最適なパフォーマンスを提供する多くのハードウェアおよびソフトウェア構成の一部のシナリオである可能性があります設定または展開の構成を変更すると役立ちます。 構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、次のパフォーマンス ガイドラインを検討してください。  
  
-   リソースの競合を防ぐためには、受信、オーケストレーション、および個別のホスト上の送信を分離します。 競合を最小限に抑えるさらに、他のホストから追跡サービスを分離します。  
  
-   BizTalk Server を実行しているコンピューターで CPU の処理がボトルネックになっている場合は、cpu を追加または高速の Cpu にアップグレードして BizTalk Server を実行するコンピューターをスケールします。  
  
## <a name="sql-server-guidelines"></a>SQL Server のガイドライン  
 Microsoft SQL Server を構成するときに、次のパフォーマンス ガイドラインを検討してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   可能であれば、SQL Server で高速なディスク サブシステムを使用します。 Redundant array of 10 独立したディスクの種類を使用して (RAID10/0 + 1) またはバックアップ電源装置の記憶域エリア ネットワーク (SAN)。  
  
-   BizTalk 追跡データベース (BizTalkDTADb) から別のサーバー上の各メッセージ ボックス データベースを分離します。 小規模な展開の CPU リソースがある場合があります、BizTalk 追跡データベースから別の物理ディスク上のメッセージ ボックス データベースを分離するための十分です。  
  
-   プライマリ メッセージ ボックス データベースには、CPU プロセッサの飽和やディスク操作 (ディスクの平均キュー長さ) からの待機時間が原因でボトルネック可能性があります。 CPU の処理がボトルネックになっている場合は、プライマリ メッセージ ボックスに CPU プロセッサを追加します。 有効でない場合は、マスター メッセージ ボックス データベースでパブリッシングを無効にしてください。 こうすると、マスター メッセージ ボックス データベースの詳細は効率的に処理他のメッセージ ボックス データベースにメッセージをルーティングできます。 パブリッシングを無効にするオプションは、複数のメッセージ ボックス データベースを使用している場合に有効です。  
  
-   ディスク操作がボトルネックとなっている場合は、BizTalk 追跡データベースを専用の SQL Server コンピューターまたは専用のディスクに移動します。 プライマリ メッセージ ボックス データベースでの CPU 処理もディスク操作がボトルネックでない場合は、既存のハードウェアを活用する同じ SQL Server コンピューターに新しいメッセージ ボックス データベースを作成できます。  
  
-   推奨事項に従って[、Databases2 のファイル グループを最適化する](../technical-guides/optimizing-filegroups-for-the-databases2.md)トランザクションとデータ ログを分離する別々 の物理ディスクと、メッセージ ボックスおよび BizTalk 追跡データベースのファイルします。  
  
-   データとログ ファイルには、十分な記憶域を割り当てます。 それ以外の場合 SQL Server では、すべてのログ ファイルが保存されているディスクの空き領域の消費が自動的にします。 ログ ファイルの初期サイズは、実際のシナリオでは、特定の要件によって異なります。 テスト結果に基づいて展開の平均ファイル サイズを推定し、ソリューションを実装する前に、記憶域スペースを展開します。  
  
-   メッセージ ボックス、正常性と動作状況の追跡 (HAT)、およびビジネス アクティビティ監視 (BAM) などのディスク使用の頻度の高いデータベースに十分な記憶域を割り当てます。 ソリューションは、BizTalk Framework メッセージング プロトコルを使用している場合は、BizTalk 構成データベース (BizTalkMgmtDb) のための十分な記憶域を割り当てます。  
  
-   に応じてビジネス、データの保有期間、およびシナリオでは、処理されたデータの量などを構成して「DTA のアーカイブと削除」の SQL Server エージェント ジョブ、HAT 追跡データベース、BizTalk 追跡データベースが大きくなりすぎません。 データ挿入率に制限していますが、データベースの完全な容量に達しているために、このデータベースの増加でパフォーマンスが低下することができます。 これは、1 つの BizTalk 追跡データベースには、複数のメッセージ ボックス データベースがサポートされている場合に特に当てはまります。  
  
-   スケール アップがボトルネックになっている場合、メッセージ ボックス データベースおよび BizTalk 追跡データベースをホストするサーバー。 Cpu の追加、メモリを追加する、高速の Cpu にアップグレードする、高速の専用ディスクを使用して、ハードウェアをスケール アップすることができます。  
  
-   複数のファイル、TempDB ファイルを分割すると、I/O 操作に関連するパフォーマンスの問題は解決します。 一般的なガイドラインとして 1 プロセッサあたり 1 つのファイルのデータ ファイルを作成し、同じサイズを使用して作成されたすべてのファイル。  
  
-   データベースの変更は、100 ~ 150 台 MB などの固定値に設定を自動-拡張します。 データベース サイズの増加が 10% に構成が既定では、その遅延をより大きなデータベースの拡張中に潜在顧客ことができます。  
  
-   SQL Server のメモリは、Min Server Memory と Max Server Memory の両方を同じ値に設定して、固定値に設定する必要があります。 一般に、SQL Server に物理メモリの 75% を割り当てるし、オペレーティング システムとアプリケーションの残りの 25% のままにします。 専用の SQL Server の場合は、1 GB の最小オペレーティング システム用に予約量を減らすことができます。  
  
## <a name="see-also"></a>参照  
 [ボトルネックの検索と解消](../technical-guides/finding-and-eliminating-bottlenecks.md)