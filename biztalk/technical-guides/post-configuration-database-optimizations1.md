---
title: 構成後のデータベース Optimizations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 763b5358-97ed-4ada-8318-0ad07388ba89
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16f789c57c57ce198a6adeaaad549f275b90fbc4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249623"
---
# <a name="post-configuration-database-optimizations"></a>構成後のデータベースの最適化
推奨事項に従うだけでなく[事前構成のデータベースの最適化](../technical-guides/post-configuration-database-optimizations1.md)、いくつかの手順は、SQL Server で BizTalk Server データベースのパフォーマンスを最適化するために従う必要があります*後*BizTalk Server がインストールされているし、BizTalk Server データベースが構成されています。 このトピックでは、これらの最適化の一覧を示します。  
  
## <a name="pre-allocate-space-for-biztalk-server-databases-and-define-auto-growth-settings-for-biztalk-server-databases-to-a-fixed-value-instead-of-a-percentage-value"></a>BizTalk Server データベース用の領域を事前割り当てし、割合の値ではなく固定値に BizTalk Server データベースの自動拡張設定の定義  
  
-   SQL Server データベースの自動拡張は、BizTalk Server データベースのパフォーマンスの低下をブロックしている操作です。 そのためデータベース自動拡張の発生を最小限に抑えるには、事前に、BizTalk Server データベースに対して十分な領域を割り当てることが重要です。  
  
-   データベース自動拡張は、固定数の割合の代わりにメガバイト単位に設定する必要があります (ファイルの拡張を指定**メガバイト単位で**)。 これは、過剰なデータベース サイズの増加が発生する可能性を軽減測定方式では自動拡張が発生した場合、実行する必要があります。 拡張増分値は、100 MB (サイズの大きいファイル) を (中規模ファイル用)、10 MB または 1 MB (小さなファイル) の以下通常場合があります。  
  
-   SQL Server では、ファイルのサイズが増えた、ときを使用する新しい領域が初期化されて最初する必要があります。 これは、空のページで、新しい領域の入力を含むブロッキング操作です。 Windows Server 2003 以降を実行する SQL Server 2005 は、「ファイルの瞬時初期化します。」をサポートしています。 これは、ファイルの拡張操作のパフォーマンスに与える影響を大幅に削減できます。 詳細については、SQL Server 2008 のドキュメント「データベース ファイルの初期化」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=132063](http://go.microsoft.com/fwlink/?LinkId=132063)します。 このトピックでは、ファイルの瞬時初期化を有効にするための手順を説明します。  
  
## <a name="move-the-backup-biztalk-server-output-directory-to-a-dedicated-lun"></a>BizTalk Server のバックアップの出力ディレクトリを専用の LUN に移動します。  
 専用の LUN に BizTalk Server のバックアップ (完全およびログ バックアップ) の出力ディレクトリを移動、手順 1. および 2. (新しい出力パスを挿入する) の [BizTalkMgmtDb] BizTalk Server のバックアップ ジョブを編集します。 読み取りは専用 LUN に BizTalk Server のバックアップの出力ディレクトリは、ジョブとは異なるディスクに書き込むことで、ジョブの実行時にディスク I/O の競合を減らすが移動します。  
  
## <a name="verify-the-biztalk-server-sql-agent-jobs-are-running"></a>BizTalk Server の SQL エージェント ジョブを実行していることを確認します。  
 BizTalk Server には、動作状況と状態、サーバーを保持する重要な機能を実行するいくつかの SQL Server エージェント ジョブが含まれています。 これらのジョブの正常性を監視し、エラーなしで実行されていることを確認する必要があります。 BizTalk Server のパフォーマンスの問題の最も一般的な原因の 1 つは、BizTalk Server の SQL エージェント ジョブではなく、実行中、メッセージ ボックスがさらに可能性があるあり、データベースをオフに拡張するトラッキングします。 BizTalk Server の SQL エージェント ジョブが問題なく実行されていることを確認する次の手順に従います。  
  
 BizTalk Server のパフォーマンスの問題の最も一般的な原因の 1 つは、BizTalk Server の SQL エージェント ジョブではなく、実行中、メッセージ ボックスがさらに可能性があるあり、データベースをオフに拡張するトラッキングします。 BizTalk Server の SQL エージェント ジョブが問題なく実行されていることを確認する次の手順に従います。  
  
-   **SQL Server エージェント サービスが実行されていることを確認**します。  
  
-   **BizTalk Server によってインストールされる SQL Server エージェント ジョブが有効になっていることを確認し、正常に実行されている**します。  
  
     BizTalk Server SQL Server エージェント ジョブが非常に重要ですが、時間の経過と共に実行されていない場合、システムのパフォーマンスが低下します。  
  
-   **BizTalk Server SQL Server エージェント ジョブが適切なタイミングで完了することを確認**します。  
  
     Microsoft Operations Manager (MOM) 2005 または Microsoft System Center Operations Manager 2007 を設定すると、ジョブを監視します。  
  
     特定のジョブを特定のスケジュールの注意する必要があります。  
  
    -   既定では、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブが継続的に実行されます。 ソフトウェアを監視、このスケジュールを考慮に入れてし、警告を生成しない必要があります。  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb ジョブは有効、またはスケジュール設定をされませんが、10 秒ごと、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブによって起動されました。 そのため、このジョブする必要がありますいない有効、スケジュールまたは手動で開始されました。  
  
-   **SQL Server エージェント サービスのスタートアップの種類が正しく構成されていることを確認**します。  
  
     SQL Server エージェント サービスが構成されていることを確認、**スタートアップの種類**の**自動**SQL Server エージェント サービスが Windows Server クラスターでクラスター リソースとして構成されていない場合。 SQL Server エージェント サービスがクラスター リソースとして構成されているかどうかは、構成する必要があります、**スタートアップの種類**として**手動**サービスは、クラスター サービスによって管理されるためです。  
  
## <a name="configure-purging-and-archiving-of-tracking-data"></a>構成の削除と追跡データのアーカイブ  
 削除と追跡データのアーカイブが正しく構成されていることを確認する次の手順に従います。  
  
-   SQL エージェント ジョブ「DTA の消去およびアーカイブ」が適切に構成された、有効化、および正常に完了することを確認します。 詳細についてで BizTalk Server のドキュメントで「方法を構成、DTA Purge とアーカイブ ジョブ」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=104908](http://go.microsoft.com/fwlink/?LinkId=104908)します。  
  
-   ジョブが速やかに受信した追跡データが生成されると、追跡データを消去することを確認します。 詳細については、BizTalk Server 2006 R2 のドキュメント「を測定する最大の追跡スループット」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=104909](http://go.microsoft.com/fwlink/?LinkId=104909)します。  
  
-   論理削除と時間の最適な長さのデータを保持することを確認する物理削除パラメーターを確認します。 詳細についてで BizTalk Server のドキュメントで「アーカイブと削除、BizTalk 追跡データベース」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=101585](http://go.microsoft.com/fwlink/?LinkId=101585)します。  
  
-   古いデータを消去しないだけの場合必要があります、最初の変更を保存する SQL エージェント ジョブ"dtasp_PurgeTrackingDatabase"ストアド プロシージャを呼び出す 詳細についてで BizTalk Server のドキュメントで「方法にデータから、BizTalk 追跡データベースの削除」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=101584](http://go.microsoft.com/fwlink/?LinkId=101584)します。  
  
## <a name="monitor-and-reduce-dtc-log-file-disk-io-contention"></a>監視し、DTC ログ ファイルのディスク I/O の競合の削減  
 Microsoft 分散トランザクション コーディネーター (MS DTC) ログ ファイルは、トランザクション処理を要する環境でディスク I/O のボトルネックになります。 これは、トランザクション、またはマルチ メッセージ ボックス環境で SQL Server、MSMQ、MQSeries などをサポートするアダプターを使用する場合に特に当てはまります。 トランザクション アダプターが DTC トランザクションを使用し、メッセージ ボックスの複数の環境によって、DTC トランザクションを広範に使用します。 DTC ログ ファイルがディスク I/O のボトルネックにならないことを確認するには、SQL Server データベース サーバーには、DTC ログ ファイルが存在する場所、ディスクの I/O の使用量、ディスクを監視する必要があります。 ディスク、DTC ログ ファイルがあるディスクの I/O の使用量が過剰になると、DTC ログ ファイルを高速ディスクに移動し、検討してください。 SQL Server がクラスター化された環境でない問題の多くが複数のスピンドルを備えた高速な SAN ドライブ、共有ドライブ ログ ファイルが既に存在するためです。 それでもまだ、または、DTC ログ ファイルが他のハード ディスク ファイルと共有ディスク上の非クラスター化環境でのボトルネックになるため、ディスク I/O の使用状況を監視する必要があります。  
  
 DTC ログ ファイルがディスク I/O のボトルネックにならないことを確認するには、SQL Server データベース サーバーには、DTC ログ ファイルが存在する場所、ディスクの I/O の使用量、ディスクを監視する必要があります。 ディスク I/O、DTC ログ ファイルがあるディスクの使用量が過剰になると、DTC ログ ファイルを高速ディスクに移動し、検討してください。  
  
 SQL Server がクラスター化された環境でない問題の多くが複数のスピンドルを備えた高速な SAN ドライブ、共有ドライブ ログ ファイルが既に存在するためです。 それでもまだ、または、DTC ログ ファイルが他のハード ディスク ファイルと共有ディスク上の非クラスター化環境でのボトルネックになるため、ディスク I/O の使用状況を監視する必要があります。  
  
## <a name="separate-the-messagebox-and-tracking-databases"></a>メッセージ ボックス データベースと追跡データベースを分離します。  
 BizTalk メッセージ ボックスおよび BizTalk 追跡データベースは、最もアクティブであるために、ディスク I/O の競合に関する問題の可能性を低減する専用のドライブにこれらの各データ ファイルとトランザクション ログ ファイルを配置するをお勧めします。 たとえば、次の各メッセージ ボックス データベースと BizTalk 追跡データベース ファイルの 4 つのドライブ、1 つのドライブを必要があります。  
  
- メッセージ ボックス データ ファイル  
  
- メッセージ ボックス データベースのトランザクション ログ ファイル  
  
- データ ファイルを BizTalk 追跡 (DTA)  
  
- トランザクション ログ ファイルの BizTalk 追跡 (DTA)  
  
  BizTalk メッセージ ボックスおよび BizTalk 追跡データベースを分離し、データベース ファイルとトランザクション ログ ファイルの異なる物理ディスクを分離することは、ディスク I/O の競合を減らすためのベスト プラクティスと見なされます。 できるだけ多くの物理スピンドルにディスク I/O を分散しようとしてください。 専用の SQL Server で、BizTalk 追跡データベースを配置することで、ディスク I/O の競合を削減することも、データ ファイルとトランザクション ログ ファイルを分離することに関しては、上記のプラクティスがまだに従ってする必要があります。  
  
## <a name="optimize-filegroups-for-the-biztalk-server-databases"></a>BizTalk Server データベースのファイル グループを最適化します。  
 次の手順では、 [、Databases1 のファイル グループを最適化する](../technical-guides/optimizing-filegroups-for-the-databases1.md)「BizTalk Server データベースの最適化」ホワイト ペーパーと[ http://go.microsoft.com/fwlink/?LinkId=101578 ](http://go.microsoft.com/fwlink/?LinkId=101578) BizTalk の追加のファイル グループとファイルを作成するにはサーバーのデータベース。 これにより、1 つのディスク構成から BizTalk Server データベースのパフォーマンスが大幅に増加します。