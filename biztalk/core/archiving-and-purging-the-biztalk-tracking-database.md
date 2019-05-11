---
title: アーカイブし、追跡データベースの削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7014cf31-86e8-4829-8055-056442329009
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99d1d1e65ff943c2a677abc5e71fea4248955f73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358969"
---
# <a name="archive-and-purge-the-biztalkdtadb-database"></a>アーカイブおよび BizTalkDTADb データベースの消去

## <a name="overview"></a>概要
BizTalk Server では、システムの詳細と詳細データを処理すると、BizTalk 追跡 (BizTalkDTADb) データベースはサイズで増え続けています。 未チェックの増加は、システム パフォーマンスが低下し、エラーで、Tracking Data Decode Service (TDDS) を生成可能性があります。 一般的な追跡データ、他にもディスク パフォーマンスの低下の原因と、メッセージ ボックス データベースに追跡メッセージも蓄積します。  
  
BizTalk Server では、DTA Purge and Archive ジョブを使用して両方のプロセスを自動化します。 アーカイブし、BizTalk 追跡データベースからデータを削除、することができます、健全なシステムの管理だけでなく将来使用するためにアーカイブされた追跡データを維持します。 BizTalk 追跡データベースのアーカイブは時間の経過と共に蓄積されるディスク領域を消費するためは、BizTalk 追跡データベースのアーカイブを定期的にセカンダリ ストレージに移動することをお勧めします。  
  
 BizTalk 追跡データベースからデータを削除すると、DTA Purge and Archive ジョブは、さまざまな種類のメッセージなどの情報とサービス インスタンス情報、オーケストレーション イベントの情報、およびルール エンジン追跡データの追跡を削除します。  
  
 データ レコードは、時間に基づいて追跡の有効期間、追跡データは、BizTalk 追跡データベースに挿入されました。 DTA Purge and Archive ジョブでは、タイムスタンプを使用して、継続的に、レコードがデータの有効期間よりも古いかどうかを確認します。 すべて有効期間の後に、BizTalk 追跡データベースがアーカイブされ、新しいアーカイブ ファイルが作成されます。 ジョブのスケジュールで指定された各 SQL Server エージェント ジョブ間隔では、すべてが完了した古いデータを追跡よりも、有効期間は消去されます。  
  
 BizTalk Server では、論理的な削除と物理削除の概念を使用します。 論理削除を使用して、物理削除が不完全なインスタンスを削除する使用のみに完了したインスタンスを消去します。  
  
## <a name="soft-purge"></a>論理削除
  
 DTA Archive and Purge ジョブでは、加算と LiveDays パラメーターの合計は、BizTalk Server 環境で管理するデータの有効期間。 データのこの有効期間よりも古い完了したインスタンスに関連付けられているすべてのデータは消去されます。 既定では、DTA Archive and Purge ジョブは有効になっていません。 最初に構成して、ジョブを有効にする必要があります。  
  
 たとえば、20 分ごとに実行する DTA Purge and Archive ジョブを構成し、設定した = 1、LiveDays = 0。 初めてこの SQL Server エージェント ジョブの実行 (T0) では、アーカイブの作成によって追跡データベースのバックアップが行わし、エントリは、このタイムスタンプを持つデータベースに保存されます。 正常なアーカイブは、追跡データを削除するために必要があります。 アーカイブが成功した場合、1 時間前に完了したインスタンスに関連付けられているすべてのデータが消去されます。 ジョブが実行されるたびに、1 時間前に完了したデータが削除されます。 (1 時間) の後に 3 番目の実行時に、1 時間の最後のセグメントで追跡データベースに挿入されたすべてのインスタンスのデータを含む新しいアーカイブが作成されます。  
  
 アーカイブを構成する方法と、削除の例では、一致するように、DTA Purge and Archive ジョブのステップを次に示します。  
  
```  
exec dtasp_BackupAndPurgeTrackingDatabase  
1, --@nLiveHours 1,   
0, --@nLiveDays   
1, --@nHardDeleteDays   
‘\\server\backup’, --@nvcFolder   
null, --@nvcValidatingServer   
0 --@fForceBackup Soft purge process  
```  
  
 最後のバックアップのタイムスタンプは、BizTalk 追跡データベースに格納され、により、前のアーカイブに存在する場合に、データが消去のみです。 その他の信頼性のアーカイブは、約 10 分が重なっています。 上記の例に基づいて、次の図は、論理削除プロセスを示します。 アーカイブと削除タスクとは限りません実行されないと同時に注意してください。  
  
 **論理削除プロセス**  
  
 ![論理削除プロセス](../core/media/archivingandpurging.gif "archivingandpurging")  
  
## <a name="hard-purge"></a>物理削除
  
 ソフト削除のためのみ、追跡データベースのサイズが増大してこれらのインスタンスは一切削除されません、無限に実行される多数のループ インスタンスがある場合は、完了したインスタンスに関連付けられているデータを削除します。 物理削除の日付では、消去、サービスの存在を示す情報を除き、指定された間隔よりも古いすべての情報を許可します。 使用して、物理削除を設定する、 <strong>@nHardDeleteDays</strong> Archive and Purge でパラメーターは、DTA Archive and Purge ジョブでステップ インします。 物理削除の設定は、論理削除の設定よりも大きいは常にします。 つまり、 <strong>@nHardDeleteDays</strong>の合計より大きくなければなりません<strong>@nLiveHours</strong>と <strong>@nLiveDays</strong>します。  
  
 アーカイブと削除には、次の表で説明する機能が含まれています。  
  
|機能|説明|  
|-------------|-----------------|  
|物理削除|指定した日付よりも古い不完全なインスタンスの情報を削除する時間間隔を構成できます。|  
|追跡データベースに追跡されたメッセージのコピー|CopyTrackedMessageToDTA オプションを使用して直接コピーできます追跡メッセージ、メッセージ ボックス サーバーから BizTalk 追跡データベースにします。 これは、DTA Purge and Archive ジョブを使用してデータを削除するために必要です。|  
|アーカイブの検証|必要に応じてサーバーを設定するセカンダリ データベースが作成されるときに、アーカイブを検証することができます。|  
|複数の BizTalk 追跡データベースのバージョンに対する追跡サポート|BizTalk Server で追跡を使用することをサポートできるようにデータベース アーカイブです。|  
|追跡データの削減|生成された追跡情報を減らさずに格納された追跡データの量を大幅に削減します。 これにより、追跡データベースの増加が遅くなります。|  
|高速な操作、データベース スキーマの大幅な最適化を追跡|大規模なデータベースは; でメッセージとサービス インスタンスを検索するための追跡のタスクを使用することができます。この機能が大幅に最適化されています。|  
  
> [!NOTE]
>  一時的に、BizTalk 追跡データベースを削除することで対処はパフォーマンスの問題が発生した、不要になった追跡情報を収集する BizTalk を構成する場合は、グローバル追跡を無効にすることを検討する可能性があります。 参照してください[グローバル追跡をオフに](../core/how-to-turn-off-global-tracking.md)します。  
  
## <a name="next-steps"></a>次のステップ
  
-   [チェックリスト:アーカイブおよび BizTalk 追跡データベースの削除](../core/checklist-archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [BizTalk 追跡データベースのデータをアーカイブおよび削除するために BTS_BACKUP_USERS ロールを構成する](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)  
  
-   [DTA Purge and Archive ジョブの構成](../core/how-to-configure-the-dta-purge-and-archive-job.md)  
  
-   [BizTalk 追跡データベースからデータを削除する](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [BizTalk 追跡データベースからデータを手動で削除する](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [アーカイブの自動検証の有効化](../core/how-to-enable-automatic-archive-validation.md)  
  
-   [追跡メッセージを BizTalk 追跡データベースにコピーする](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)  
  
-   [アーカイブおよび削除のプロセスのパフォーマンスの向上](../core/improving-the-performance-of-the-archiving-and-purging-process.md)  
  
-   [グローバル追跡の無効化](../core/how-to-turn-off-global-tracking.md)