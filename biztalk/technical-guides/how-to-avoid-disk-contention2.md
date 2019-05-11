---
title: ディスク Contention2 を回避する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37bdf6bd-cb34-4540-819e-908d83a22d40
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf152826fa5e2e0873d0544236fa73c110c4536d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393510"
---
# <a name="how-to-avoid-disk-contention"></a>ディスクの競合を防止する方法
BizTalk Server は、永続的なシステムとして設計されています。 高スループットのシナリオで、メッセージ ボックス データベースおよび BizTalk 追跡データベース深刻な競合が発生することができます。 ディスクが遅い場合には事態がさらに悪化します。 ディスクの場合は (平均の平均値を使うよりも大きい低速します。Disk Sec/read や avgDisk Sec/write)、長い時間ロック (ロック待機時間と高のロック タイムアウト数) を保持する SQL Server をしまう可能性があります。 これは、さらに、可能性があります、メッセージ ボックス テーブル (スプールとアプリケーション キュー) に増加し、データベースの肥大と調整します。 このような状況は、最終的に、全体的な持続可能なスループットの低下に生じます。  
  
> [!NOTE]  
>  サーバーがディスクのボトルネックを特定する方法の詳細については、次を参照してください。 [Windows パフォーマンス モニター](http://go.microsoft.com/fwlink/?LinkID=204007) (http://go.microsoft.com/fwlink/?LinkID=204007)します。 Windows パフォーマンス モニターは、システムのパフォーマンスを分析するためのツールを提供する Microsoft 管理コンソール (MMC) スナップインです。  
  
 ディスクの競合を回避するには、次の操作を行います。  
  
|手順|リファレンス|  
|-----------|---------------|  
|Raid10 を使用して/0 と 1 つのディスク構成します。|[ボトルネックを回避するためのベスト プラクティス](../technical-guides/best-practices-for-avoiding-bottlenecks.md)|  
|可能であれば、高速な SAN 上のデータベースをデプロイします。 別の構成をお勧めの複数のデータベースは、同じディスクで共有されている場合**専用**ディスク。 さらに、個別のディスク上にメッセージ ボックス データベースの MDF および LDF ファイルを分離することをお勧めします。|[Databases2 のファイルグループの最適化](../technical-guides/optimizing-filegroups-for-the-databases2.md)|  
|これは大幅にディスクの競合を減らす、複数のデータ ファイル間で負荷を分散させるので、TEMPDB データベース用の複数のファイルの割り当てを検討してください。|[データベースの事前構成 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|BizTalk 追跡データベースから分離された専用のサーバーにメッセージ ボックス データベースを分離することを検討してください。|[構成後のデータベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|MSDTC ログ ファイルのディレクトリを別の専用のドライブに割り当てます。|[オペレーティング システムのパフォーマンスの最適化](../technical-guides/optimizing-operating-system-performance.md)|  
|ページファイルや MSDTC のログによってローカル ドライブで競合が発生する場合は、ページファイルや MSDTC のログを別のドライブに移してみてください。|[ボトルネックを回避するためのベスト プラクティス](../technical-guides/best-practices-for-avoiding-bottlenecks.md)|  
|書き込み操作の追跡データベースを最適化します。|[追跡データベースのボトルネックを特定する方法](../technical-guides/how-to-identify-bottlenecks-in-the-tracking-database.md)|  
|読み取り、メッセージ ボックス データベースを最適化し、書き込み操作です。|[メッセージ ボックス データベース 1 のボトルネックを特定する方法](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)|  
|BizTalk ホスト インスタンスの CPU が飽和、送信、受信、処理、および複数のホストに追跡機能を分離することを検討してください。 これにより、オーケストレーション機能は、システム全体のスループットを向上させるために別の専用サーバーで実行されるよう、システムを構成します。|[BizTalk Server パフォーマンスの最適化](../technical-guides/optimizing-biztalk-server-performance.md)|  
|複数のオーケストレーションが展開されている場合は、異なる専用オーケストレーション ホストに参加することを検討してください。 これにより、別のオーケストレーションを分離され、同じ物理アドレス空間または同じサーバー上の共有リソースの競合を防ぎます。|[BizTalk Server パフォーマンスの最適化](../technical-guides/optimizing-biztalk-server-performance.md)|  
|Windows パフォーマンス モニターを使用して、ディスクの競合の問題を診断することを検討してください.|[Windows パフォーマンス モニター](http://go.microsoft.com/fwlink/?LinkID=204007)|  
  
 ディスク パフォーマンス分析の詳細については、次のリソースを参照してください。  
  
- [ディスクの制限の問題は除きます](http://go.microsoft.com/fwlink/?LinkId=120947)(HYPERLINK"<http://go.microsoft.com/fwlink/?LinkId=120947>"\t"_blank"<http://go.microsoft.com/fwlink/?LinkId=120947>)。  
  
- [SQL Server の展開前 I/O のベスト プラクティス](http://go.microsoft.com/fwlink/?LinkId=120948)(http://go.microsoft.com/fwlink/?LinkId=120948)します。  
  
- 「I/O ボトルネック」セクション[SQL Server 2008 でのパフォーマンスに関する問題のトラブルシューティング](http://go.microsoft.com/fwlink/?LinkID=153586)(http://go.microsoft.com/fwlink/?LinkID=153586)します。  
  
## <a name="see-also"></a>参照  
 [データベース層のボトルネック](../technical-guides/bottlenecks-in-the-database-tier.md)