---
title: "ディスク Contention2 を回避する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37bdf6bd-cb34-4540-819e-908d83a22d40
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7be7a38ac3f3f6cc1d7d266c664cbb85f731c22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-avoid-disk-contention"></a>ディスクの競合を防止する方法
BizTalk Server は、永続的なシステムとして設計されています。 高スループットのシナリオで、メッセージ ボックス データベースと BizTalk 追跡データベース深刻な競合が発生することができます。 ディスクが遅い場合には事態がさらに悪化します。 場合は、ディスク速度の遅い (平均の平均値で使うより大きいDisk Sec/read または avgDisk Sec/write)、ロックが長くなります (ロック待機時間と高のロック タイムアウト数) を保持する SQL Server をしまう可能性があります。 これには、さらに、可能性があります、メッセージ ボックス テーブル (スプールとアプリケーション キュー) に増加し、データベースの肥大化の原因と調整します。 このような状況は、最終的には、全体的な持続可能なスループットの低下になります。  
  
> [!NOTE]  
>  サーバーがディスクのボトルネックを識別する方法については、次を参照してください。 [Windows パフォーマンス モニター](http://go.microsoft.com/fwlink/?LinkID=204007) (http://go.microsoft.com/fwlink/?LinkID=204007)。 Windows パフォーマンス モニターでは、システムのパフォーマンスを分析するためのツールを提供する Microsoft 管理コンソール (MMC) スナップインです。  
  
 ディスクの競合を回避するのには、次の操作を行います。  
  
|手順|リファレンス|  
|-----------|---------------|  
|Raid10 を使用して/0 + 1 のディスク構成します。|[ボトルネックを回避するためのベスト プラクティス](../technical-guides/best-practices-for-avoiding-bottlenecks.md)|  
|可能であれば、高速な SAN 上のデータベースを展開します。 複数のデータベースは、同じディスクで共有されている場合ことをお勧めは別に構成する**専用**ディスクです。 さらに、別のディスク上にメッセージ ボックス データベースの MDF と LDF ファイルを分離することをお勧めします。|[ファイル グループを Databases2 の最適化](../technical-guides/optimizing-filegroups-for-the-databases2.md)|  
|これは大幅にディスクの競合を減らす、複数のデータ ファイル間で負荷を分散させるので、TEMPDB データベース用の複数のファイルの割り当てを検討してください。|[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|BizTalk 追跡データベースから別の専用のサーバーにメッセージ ボックス データベースを分離することを検討してください。|[インストール後の構成データベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|独立した専用のドライブに、MSDTC ログ ファイル ディレクトリを割り当てます。|[オペレーティング システムのパフォーマンスを最適化します。](../technical-guides/optimizing-operating-system-performance.md)|  
|ページファイルや MSDTC のログによってローカル ドライブで競合が発生する場合は、ページファイルや MSDTC のログを別のドライブに移してみてください。|[ボトルネックを回避するためのベスト プラクティス](../technical-guides/best-practices-for-avoiding-bottlenecks.md)|  
|書き込み操作の追跡データベースを最適化します。|[追跡データベースのボトルネックを特定する方法](../technical-guides/how-to-identify-bottlenecks-in-the-tracking-database.md)|  
|読み取り、メッセージ ボックス データベースを最適化し、書き込み操作です。|[メッセージ ボックス データベース Database1 のボトルネックを特定する方法](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)|  
|BizTalk ホスト インスタンスが、CPU を飽和する場合は、送信、受信、処理、および複数のホストに追跡機能を分離することを検討します。 これにより、オーケストレーションの機能は、システム全体のスループットを向上させるために別の専用サーバーで実行されるように、システムが構成されます。|[BizTalk Server のパフォーマンスを最適化します。](../technical-guides/optimizing-biztalk-server-performance.md)|  
|複数のオーケストレーションを展開している場合は、異なる専用オーケストレーション ホストに参加することを検討してください。 これにより、異なるオーケストレーションを分離され、同一の物理アドレス空間または同じサーバー上の共有リソースの競合を防ぎます。|[BizTalk Server のパフォーマンスを最適化します。](../technical-guides/optimizing-biztalk-server-performance.md)|  
|Windows パフォーマンス モニターを使用して、ディスクの競合の問題を診断することを検討してください.|[Windows パフォーマンス モニター](http://go.microsoft.com/fwlink/?LinkID=204007)|  
  
 ディスク パフォーマンス分析の詳細については、次のリソースを参照してください。  
  
-   [ディスクにバインドされて問題は除きます](http://go.microsoft.com/fwlink/?LinkId=120947)(ハイパーリンク"http://go.microsoft.com/fwlink/?LinkId=120947"\t"_blank"http://go.microsoft.com/fwlink/?LinkId=120947)。  
  
-   [SQL Server の展開前 I/O のベスト プラクティス](http://go.microsoft.com/fwlink/?LinkId=120948)(http://go.microsoft.com/fwlink/?LinkId=120948)。  
  
-   「I/O ボトルネック」セクション[SQL Server 2008 でのパフォーマンス問題のトラブルシューティング](http://go.microsoft.com/fwlink/?LinkID=153586)(http://go.microsoft.com/fwlink/?LinkID=153586)。  
  
## <a name="see-also"></a>参照  
 [データベース層のボトルネック](../technical-guides/bottlenecks-in-the-database-tier.md)