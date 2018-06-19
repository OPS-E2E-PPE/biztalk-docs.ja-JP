---
title: インストール後の構成データベース Optimizations1 |Microsoft ドキュメント
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
ms.openlocfilehash: eeb1c5c8bbb93bce5eb69462585c2da69d587dad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302330"
---
# <a name="post-configuration-database-optimizations"></a>インストール後の構成データベースの最適化
推奨事項に従うだけでなく[事前構成データベースを最適化](../technical-guides/post-configuration-database-optimizations1.md)、いくつかの手順は、SQL Server 上の BizTalk Server データベースのパフォーマンスを最適化するために従う必要があります*後*BizTalk Server がインストールされているし、BizTalk Server データベースが構成されています。 このトピックでは、これらの最適化の一覧を示します。  
  
## <a name="pre-allocate-space-for-biztalk-server-databases-and-define-auto-growth-settings-for-biztalk-server-databases-to-a-fixed-value-instead-of-a-percentage-value"></a>BizTalk Server データベースの容量をあらかじめ割り当てし、パーセント値ではなく、固定値に BizTalk Server データベースの自動拡張設定を定義  
  
-   SQL Server データベースの自動拡張は、BizTalk Server データベースのパフォーマンスの低下をブロックしている操作です。 したがって、BizTalk Server データベースのデータベースの自動拡張の発生を最小限に抑えるには、事前に十分な空き領域を割り当てることが重要です。  
  
-   データベースの自動拡張は、固定の代わりにパーセンテージをメガバイト数に設定する必要があります (ファイルの拡張を指定**メガバイト単位で**)。 これは、ため、過剰なデータベース サイズの増加する可能性が低くなります測定に基づく方式では自動拡張が発生した場合に行う必要があります。 拡張増分値を超える 100 MB (サイズの大きいファイル)、10 MB (中規模ファイル用)、または 1 MB (小さなファイル用)、通常場合があります。  
  
-   SQL Server では、ファイルのサイズを大きく、ときを使用する前に、新しい領域が初期化されて最初必要があります。 これは、ブロッキング操作を含む空のページで、新しい領域の情報を入力します。 Windows Server 2003 以降を実行する SQL Server 2005 は、「ファイルの瞬時初期化」をサポートしています。 これは、ファイルの拡張操作のパフォーマンスに与える影響を大幅に減らすことができます。 詳細についてを参照してください「データベース ファイルの初期化」で SQL Server 2008 のドキュメント[http://go.microsoft.com/fwlink/?LinkId=132063](http://go.microsoft.com/fwlink/?LinkId=132063)です。 このトピックでは、ファイルの瞬時初期化を有効にするための手順を説明します。  
  
## <a name="move-the-backup-biztalk-server-output-directory-to-a-dedicated-lun"></a>専用の LUN に、BizTalk Server のバックアップの出力ディレクトリを移動します。  
 専用の LUN に、BizTalk Server のバックアップ (完全およびログ バックアップ) の出力ディレクトリを移動、1 または 2 (新しい出力パスを挿入する) [BizTalkMgmtDb]、BizTalk Server のバックアップ ジョブのステップを編集します。 読み取りは、移動専用の LUN を BizTalk Server のバックアップの出力ディレクトリは、ジョブとは異なるディスクに書き込むことによって、ジョブが実行されている場合、ディスク I/O の競合が減少します。  
  
## <a name="verify-the-biztalk-server-sql-agent-jobs-are-running"></a>BizTalk Server の SQL エージェント ジョブを実行していることを確認します。  
 BizTalk Server には、動作状況と状態、サーバーを保つために重要な機能を実行するいくつかの SQL Server エージェント ジョブが含まれています。 これらのジョブの状態を監視し、エラーなく実行されていることを確認する必要があります。 BizTalk Server のパフォーマンスの問題の最も一般的な原因の 1 つは、BizTalk Server の SQL エージェント ジョブは実行中は、さらになる場合、メッセージ ボックス データベースおよび追跡データベース拡張がオフにします。 BizTalk Server の SQL エージェント ジョブが問題なく実行されていることを確認する手順に従います。  
  
 BizTalk Server のパフォーマンスの問題の最も一般的な原因の 1 つは、BizTalk Server の SQL エージェント ジョブは実行中は、さらになる場合、メッセージ ボックス データベースおよび追跡データベース拡張がオフにします。 BizTalk Server の SQL エージェント ジョブが問題なく実行されていることを確認する手順に従います。  
  
-   **SQL Server エージェント サービスが実行されていることを確認**です。  
  
-   **BizTalk Server によってインストールされる SQL Server エージェント ジョブが有効になっていることを確認し、正常に実行されている**です。  
  
     BizTalk Server SQL Server エージェント ジョブは重要な時間の経過と共に実行されていない場合システムのパフォーマンスが低下します。  
  
-   **BizTalk Server SQL Server エージェント ジョブに適時に完了していることを確認**です。  
  
     Microsoft Operations Manager (MOM) 2005 または Microsoft System Center Operations Manager 2007 を設定すると、ジョブを監視します。  
  
     特定のジョブを特定のスケジュールの注意する必要があります。  
  
    -   MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブは、既定では継続的に実行されます。 監視ソフトウェアと、このスケジュールを考慮する必要があります、警告を生成されません。  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb ジョブは有効になっているスケジュールも 10 秒ごと、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブによって起動されました。 そのため、このジョブ有効になっている、スケジュール、したりしないでを手動で開始します。  
  
-   **SQL Server エージェント サービスのスタートアップの種類が正しく構成されていることを確認**です。  
  
     SQL Server エージェント サービスを構成することを確認、**スタートアップの種類**の**自動**SQL Server エージェント サービスが、Windows Server クラスターでクラスター リソースとして構成されている場合を除き、します。 SQL Server エージェント サービスがクラスター リソースとして構成されているかどうかは、構成する必要があります、**スタートアップの種類**として**手動**サービスは、クラスター サービスによって管理するためです。  
  
## <a name="configure-purging-and-archiving-of-tracking-data"></a>消去および追跡データのアーカイブを構成します。  
 次の手順を消去および追跡データのアーカイブが正しく構成されていることを確認します。  
  
-   SQL エージェント ジョブ「DTA の消去およびアーカイブ」が適切に構成された、有効であり、正常に完了することを確認します。 詳細については、BizTalk Server のドキュメントに「方法を構成、DTA Purge とアーカイブ ジョブ」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=104908](http://go.microsoft.com/fwlink/?LinkId=104908)です。  
  
-   ジョブが速く受信追跡データが生成された追跡データを消去することを確認します。 詳細についてを参照してください「測定最大の追跡スループット」で BizTalk Server 2006 R2 マニュアル[http://go.microsoft.com/fwlink/?LinkId=104909](http://go.microsoft.com/fwlink/?LinkId=104909)です。  
  
-   論理削除と物理削除ようにパラメーターを最適な時間の長さのデータを保持している場合を確認します。 詳細については、BizTalk Server のドキュメントに「アーカイブと削除、BizTalk 追跡データベース」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=101585](http://go.microsoft.com/fwlink/?LinkId=101585)です。  
  
-   だけ古いデータを削除しないようにする必要がある場合必要があります、最初の変更をアーカイブする SQL エージェント ジョブ、ストアド プロシージャを呼び出す"dtasp_PurgeTrackingDatabase" 詳細については、BizTalk Server のドキュメントに「どのようにパージ データから BizTalk 追跡データベースへ」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=101584](http://go.microsoft.com/fwlink/?LinkId=101584)です。  
  
## <a name="monitor-and-reduce-dtc-log-file-disk-io-contention"></a>監視し、DTC ログ ファイル ディスク I/O の競合を削減  
 Microsoft 分散トランザクション コーディネーター (MS DTC) ログ ファイルは、トランザクションに依存する環境でディスク I/O のボトルネックになります。 これは、トランザクション、またはマルチ メッセージ ボックス環境で SQL Server、MSMQ、MQSeries などをサポートするアダプターを使用する場合に特に当てはまります。 トランザクション アダプターが DTC トランザクションを使用して、マルチ メッセージ ボックス環境 DTC トランザクションを広範に使用します。 DTC ログ ファイルがディスク I/O のボトルネックにならないようにには、ディスク DTC ログ ファイルが、SQL Server データベース サーバーに常駐するディスクの I/O の使用量を監視する必要があります。 ディスクが DTC ログ ファイルが存在するディスクの I/O の使用量が過剰な場合、DTC ログ ファイルの移動を高速なディスクを検討します。 SQL Server がクラスター化された環境では、これがありませんできるだけ多くの問題にならなければなので、ログ ファイルは既に共有ドライブが含まれ、複数のスピンドルを高速な SAN ドライブが場合があります。 非クラスター化環境でボトルネックになる、または DTC ログ ファイルが他の大量のディスク ファイルで共有ディスク上のためは、それでもまだディスク I/O の使用状況を監視してください。  
  
 DTC ログ ファイルがディスク I/O のボトルネックにならないようにには、ディスク DTC ログ ファイルが、SQL Server データベース サーバーに常駐するディスクの I/O の使用量を監視する必要があります。 ディスクの DTC ログ ファイルが存在するディスクの I/O 使用率が過剰になると、DTC ログ ファイルの移動を高速なディスクを検討します。  
  
 SQL Server がクラスター化された環境では、これがありませんできるだけ多くの問題にならなければなので、ログ ファイルは既に共有ドライブが含まれ、複数のスピンドルを高速な SAN ドライブが場合があります。 非クラスター化環境でボトルネックになる、または DTC ログ ファイルが他の大量のディスク ファイルで共有ディスク上のためは、それでもまだディスク I/O の使用状況を監視してください。  
  
## <a name="separate-the-messagebox-and-tracking-databases"></a>メッセージ ボックス データベースおよび追跡データベースを分割します。  
 BizTalk メッセージ ボックス データベースと BizTalk 追跡データベースは、最もアクティブであるために、これらをディスク I/O の競合の問題の可能性を減らすために専用のドライブ上のそれぞれのデータ ファイルとトランザクション ログ ファイルを配置するをお勧めします。 たとえば、する必要があります、メッセージ ボックス データベースおよび BizTalk 追跡データベース ファイルの 4 つのドライブ、1 つのドライブ、次のそれぞれに。  
  
-   メッセージ ボックス データ ファイル  
  
-   メッセージ ボックス データベースのトランザクション ログ ファイル  
  
-   データ ファイルを BizTalk 追跡 (DTA)  
  
-   トランザクション ログ ファイルの BizTalk 追跡 (DTA)  
  
 BizTalk メッセージ ボックス データベースと BizTalk 追跡データベースを分離して、データベース ファイルとトランザクション ログ ファイルの異なる物理ディスクを分離することは、ディスク I/O の競合を減らすためのベスト プラクティスと見なされます。 可能な限り多くの物理スピンドル ディスク I/O に分散しようとしてください。 専用の SQL Server で、BizTalk 追跡データベースを配置することでディスク I/O の競合を削減することもできます。 ただし、必要がありますもに従う必要がデータ ファイルとトランザクション ログ ファイルの分離に関する上記のプラクティスです。  
  
## <a name="optimize-filegroups-for-the-biztalk-server-databases"></a>BizTalk Server データベースのファイル グループを最適化します。  
 手順に従います[、Databases1 のファイル グループを最適化する](../technical-guides/optimizing-filegroups-for-the-databases1.md)と「BizTalk Server データベースの最適化」のホワイト ペーパー [http://go.microsoft.com/fwlink/?LinkId = 101578](http://go.microsoft.com/fwlink/?LinkId=101578)追加のファイル グループと BizTalk Server データベースのファイルを作成します。 これにより、1 つのディスク構成から BizTalk Server データベースのパフォーマンスが大幅に増加します。