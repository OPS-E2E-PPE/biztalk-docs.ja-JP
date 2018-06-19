---
title: インストール後の構成データベース Optimizations2 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 609eda22-8399-4b7c-b860-21b495d2f68d
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 168323f1e7dfdbb796fe29e0025c5d2a6f40c957
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302666"
---
# <a name="post-configuration-database-optimizations"></a>インストール後の構成データベースの最適化
推奨事項に従うだけでなく[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)、いくつかの手順は、SQL Server 上の BizTalk Server データベースのパフォーマンスを最適化するために従う必要があります*後*BizTalk Server がインストールされているし、BizTalk Server データベースが構成されています。 このトピックでは、これらの最適化の一覧を示します。  
  
## <a name="consider-setting-the-text-in-row-table-option-on-specific-messagebox-database-tables"></a>特定のメッセージ ボックス データベース テーブルの 'text in row' テーブル オプションの設定を検討してください。  
 SQL Server と呼ばれるテーブル オプションを提供する**行内テキスト**ことを宣言する型のフィールドの内容**テキスト**、 **ntext**、または**イメージ**次元は、データ ページ (8 Kb) のものより小さいデータは、データ行に格納する必要があります。 BizTalkMsgBoxDb テーブル (Parts テーブル、スプール テーブルおよび DynamicStateInfo テーブル) に対してこのオプションを設定するで、小規模のコンテキストとサイズは小さい永続化するオーケストレーションを持つ小さいメッセージを使用する場合、メッセージのスループットを向上できます。  
  
-   **テーブルの部品**: メッセージのサイズが 8 kb のデータ ページの寸法より小さい場合は、適用、**行内テキスト**部品テーブルにテーブルのオプションは、BizTalk Server のパフォーマンスの向上につながる可能性がします。 Parts テーブルには、次のフィールドが含まれています。  
  
    -   **ImgPart**: メッセージの一部またはメッセージ部分フラグメントが含まれています。  
  
    -   **ImgPropBag**: メッセージの一部のプロパティ バッグが含まれています。  
  
     これにより、メッセージ ボックスに対してループ処理時に BizTalk ホストで実行されているメッセージ エージェント メッセージのバッチ テーブルから取得できます、部分少量のページを読み取ることによってです。 によっては、特定のシナリオおよびハードウェア構成では、この手法は、SQL Server と BizTalk Server の両方の CPU 使用率を削減し、待機時間とスループットの観点から大幅に向上できます。  
  
-   **スプール テーブル**: メッセージ コンテキストの平均サイズが 8 kb 未満の場合に有効にすると、**行内テキスト**スプール テーブルのテーブル オプションでは、に沿って、MessageBox からメッセージを読み取るときに、アクセスの数を削減できます。そのコンテキスト。 スプール テーブルには、このオプションを適用するには、不要なコンテキスト プロパティと識別フィールドを 8 Kb よりも低いメッセージ コンテキストのサイズを減らすためを除去する必要があります。  
  
-   **DynamicStateInfo テーブル**、各ホストのいずれかのようなテーブルには、実行中に永続化ポイントを検出したときに、オーケストレーションのバイナリ シリアル化の状態を含む imgData と呼ばれる型が image のフィールドが含まれています。 ホスト HostA 内のオーケストレーションの内部状態が非常に小さいため、1 回のシリアル化のサイズが 8 kb 未満である場合に、**行内テキスト**手法は DynamicStateInfo_HostA テーブルに正常に適用されることができます。 そのためのオーケストレーションの内部状態できるだけ小さくする保持することをお勧めします。 この手法では、シリアル化、永続化、逆シリアル化および永続化ポイントが発生した場合、オーケストレーションの内部状態を復元するには、XLANG エンジンによって費やされた時間を大幅に短縮できます。  
  
 ラボ テストの結果で、次の設定を使用しました。  
  
-   EXEC sp_tableoption N'Spool'、'text in row'、'6000'  
  
-   EXEC sp_tableoption N'Parts'、'text in row'、'6000'  
  
## <a name="define-auto-growth-settings-for-biztalk-server-databases-to-a-fixed-value-instead-of-a-percentage-value"></a>パーセント値ではなく、固定値に BizTalk Server データベースの自動拡張設定を定義します。  
  
-   SQL Server データベースの自動拡張は、BizTalk Server データベースのパフォーマンスの低下、ブロッキング操作です。 したがって、BizTalk Server データベースのデータベースの自動拡張の発生を最小限に抑えるには、事前に十分な空き領域を割り当てることが重要です。  
  
-   データベースの自動拡張は、固定の代わりにパーセンテージをメガバイト数に設定する必要があります (ファイルの拡張を指定**メガバイト単位で**)。 これは、できるように、場合の自動拡張が発生すると、それは測定された方法で行う必要があります。 これにより、過剰なデータベース サイズの増加する可能性が減少します。 BizTalk Server データベースの拡張増分値は、一般に 100 MB 以上でする必要があります。  
  
## <a name="pre-size-biztalk-server-databases-to-appropriate-size-with-multiple-data-files"></a>複数のデータ ファイルと適切なサイズに事前にサイズの BizTalk Server データベース  
 SQL Server では、ファイルのサイズを大きく、ときに、新しい領域最初初期化を使用する前に、必要があります。 これは、ブロッキング操作を含む空のページで、新しい領域の情報を入力します。 SQL Server 2005 またはそれ以降を実行している Windows Server 2003 またはそれ以降は、「ファイルの瞬時初期化」をサポートしています これは、ファイルの拡張操作のパフォーマンスに与える影響を大幅に減らすことができます。 詳細については、次を参照してください。[データベース ファイルの初期化](http://go.microsoft.com/fwlink/?LinkId=132063)(http://go.microsoft.com/fwlink/?LinkId=132063)、SQL Server オンライン ブック。 このトピックでは、ファイルの瞬時初期化を有効にするための手順を説明します。  
  
 次の一覧には、このラボのテストで使用される BizTalk Server データベースの構成について説明します。  
  
-   **BizTalk DTADB (BizTalk 追跡データベース ファイル):** 100 MB の増加に 2048 MB のファイル サイズと最大 1024 MB のログ ファイルに 100 MB の拡張を持つデータ ファイル。  
  
-   **BizTalkMgmtdb (BizTalk 管理データベース ファイル):** データ ファイルに 100 MB の拡張の 512 MB のファイル サイズと 512 MB のログ ファイルに 100 MB 拡張します。  
  
-   **SSODB:** データ ファイルに 100 MB の拡張の 512 MB のファイル サイズと 512 MB のログ ファイルに 100 MB 拡張します。  
  
-   **BizTalkMsgBoxDb (BizTalk メッセージ ボックス データベース):** 8 つのデータ ファイルは、それぞれは 100 MB の増加に 2 GB のファイル サイズと 20 GB のログ ファイルに 100 MB 拡張します。 BizTalk メッセージ ボックス データベースは、最もアクティブであるため、データ ファイルとトランザクション ログ ファイルをディスク I/O の競合の問題の可能性を減らすために専用のドライブ上に配置するをお勧めします。 このラボ環境で、1 つのドライブを使用する、次のそれぞれに。  
  
    -   メッセージ ボックス データ ファイル  
  
    -   メッセージ ボックス データベースのトランザクション ログ ファイル  
  
 ドライブ J (J:\BizTalkMsgBoxDb.mdf) 上のデータ ファイルとログ ファイルにドライブ K (K:\BizTalkMsgBoxDb_log の最初にある BizTalkMsgBoxDb のサイズを事前に、次の SQL スクリプトを使用することができます。LDF):  
  
> [!IMPORTANT]  
>  このスクリプトは、提供「としては、」デモまたは演習目的でのみ、向けし、各自の責任で使用されます。 、Microsoft では、このスクリプトの使用はサポートされていないと、Microsoft がこのスクリプトの適合性に関して保証を行いません。  
  
```  
EXEC dbo.sp_helpdb BizTalkMsgBoxDb  
ALTER DATABASE BizTalkMsgBoxDb MODIFY FILE (NAME = BizTalkMsgBoxDb , FILENAME = 'J:\BizTalkMsgBoxDb.mdf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_2 , FILENAME = 'J:\BizTalkMsgBoxDb_2.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_3 , FILENAME = 'J:\BizTalkMsgBoxDb_3.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_4 , FILENAME = 'J:\BizTalkMsgBoxDb_4.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_5 , FILENAME = 'J:\BizTalkMsgBoxDb_5.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_6 , FILENAME = 'J:\BizTalkMsgBoxDb_6.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_7 , FILENAME = 'J:\BizTalkMsgBoxDb_7.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_8 , FILENAME = 'J:\BizTalkMsgBoxDb_8.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
GO  
ALTER DATABASE BizTalkMsgBoxDb MODIFY FILE (NAME = BizTalkMsgBoxDb_log , FILENAME = 'K:\BizTalkMsgBoxDb_log.LDF', SIZE =  20GB , FILEGROWTH = 100MB)  
GO  
```  
  
## <a name="move-the-backup-biztalk-server-output-directory-to-a-dedicated-lun"></a>専用の LUN に、BizTalk Server のバックアップの出力ディレクトリを移動します。  
 専用の LUN にバックアップ BizTalk (フル インストール オプションとログ バックアップ) の出力ディレクトリに移動し、専用の LUN をポイントする BizTalk Server のバックアップ ジョブを編集します。 読み取りは、移動専用の LUN を BizTalk Server のバックアップの出力ディレクトリは、ジョブとは異なるディスクに書き込むことによって、ジョブが実行されている場合、ディスク I/O の競合が減少します。 BizTalk Server のバックアップ ジョブの構成の詳細については、次を参照してください。[を BizTalk Server のバックアップ ジョブを構成する方法](http://go.microsoft.com/fwlink/?LinkID=153813)(http://go.microsoft.com/fwlink/?LinkID=153813) BizTalk Server 2010 ヘルプ。  
  
## <a name="verify-that-the-biztalk-server-sql-agent-jobs-are-running"></a>BizTalk Server の SQL エージェント ジョブが実行されていることを確認してください。  
 BizTalk Server には、動作状況と状態、サーバーを保つために重要な機能を実行するいくつかの SQL Server エージェント ジョブが含まれています。 これらのジョブの状態を監視し、エラーなく実行されていることを確認する必要があります。 BizTalk Server のパフォーマンスの問題の最も一般的な原因の 1 つは、BizTalk Server の SQL エージェント ジョブは実行中は、さらになる場合、メッセージ ボックス データベースおよび追跡データベース拡張がオフにします。 BizTalk Server の SQL エージェント ジョブが問題なく実行されていることを確認する手順に従います。  
  
1.  **SQL Server エージェント サービスが実行されていることを確認してください。** です。  
  
2.  **BizTalk Server によってインストールされる SQL Server エージェント ジョブが有効になっていることを確認し、正常に実行されている**です。  
    BizTalk Server SQL Server エージェント ジョブがきわめて重要です。 時間の経過と共に実行されていない場合システムのパフォーマンスが低下します。  
  
3.  **適切なタイミングで、BizTalk Server SQL Server エージェント ジョブが完了することを確認してください。** です。   
    Microsoft System Center Operations Manager の最新バージョンを設定すると、ジョブを監視します。  
    特定のジョブを特定のスケジュールの注意する必要があります。  
  
    -   MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブは、既定では継続的に実行されます。 監視ソフトウェアと、このスケジュールを考慮する必要があります、警告を生成されません。  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb ジョブは有効になっているスケジュールも 10 秒ごと、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブによって起動されました。 そのため、このジョブ有効になっている、スケジュール、したりしないでを手動で開始します。  
  
4.  **SQL Server エージェント サービスのスタートアップの種類が正しく構成されていることを確認してください。** です。  
    SQL Server エージェント サービスを構成することを確認、**スタートアップの種類**の**自動**SQL Server エージェント サービスが、Windows Server クラスターでクラスター リソースとして構成されている場合を除き、します。 SQL Server エージェント サービスがクラスター リソースとして構成されているかどうかは、構成する必要があります、**スタートアップの種類**として**手動**サービスは、クラスター サービスによって管理するためです。  
  
## <a name="configure-purging-and-archiving-of-tracking-data"></a>消去および追跡データのアーカイブを構成します。  
 次の手順を消去および追跡データのアーカイブが正しく構成されていることを確認します。  
  
1.  SQL エージェント ジョブ「DTA の消去およびアーカイブ」が適切に構成された、有効であり、正常に完了することを確認します。 詳細については、次を参照してください。 [DTA Purge and Archive ジョブを構成する方法](http://go.microsoft.com/fwlink/?LinkID=153814)(http://go.microsoft.com/fwlink/?LinkID=153814)、BizTalk Server のドキュメントにします。  
  
2.  ジョブが速く受信追跡データが生成された追跡データを消去することを確認します。 詳細については、次を参照してください。[維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)、BizTalk Server のドキュメントにします。  
  
3.  論理削除と物理削除ようにパラメーターを最適な時間の長さのデータを保持している場合を確認します。 詳細については、次を参照してください。[アーカイブ化および BizTalk 追跡データベースを削除](http://go.microsoft.com/fwlink/?LinkID=153816)(http://go.microsoft.com/fwlink/?LinkID=153816)、BizTalk Server のドキュメントにします。  
  
4.  だけ古いデータを削除しないようにする必要がある場合必要があります、最初の変更をアーカイブする SQL エージェント ジョブ、ストアド プロシージャを呼び出す"dtasp_PurgeTrackingDatabase" 詳細については、次を参照してください。 [BizTalk 追跡データベースからデータを消去する方法](http://go.microsoft.com/fwlink/?LinkID=153817)(http://go.microsoft.com/fwlink/?LinkID=153817)、BizTalk Server のドキュメントにします。  
  
## <a name="monitor-and-reduce-dtc-log-file-disk-io-contention"></a>監視し、DTC ログ ファイル ディスク I/O の競合を削減  
 分散トランザクション コーディネーター (DTC) ログ ファイルは、トランザクションに依存する環境でディスク I/O のボトルネックになります。 これは、トランザクション、またはマルチ メッセージ ボックス環境で SQL Server、MSMQ、MQSeries などをサポートするアダプターを使用する場合に特に当てはまります。 トランザクション アダプターが DTC トランザクションを使用して、マルチ メッセージ ボックス環境 DTC トランザクションを広範に使用します。 DTC ログ ファイルがディスク I/O のボトルネックにならないことを確認するには、するには、ディスクが SQL Server データベース サーバーで DTC ログ ファイルが存在するディスクの I/O の使用量を監視する必要があります。 ディスクの DTC ログ ファイルが存在するディスクの I/O 使用率が過剰になると、DTC ログ ファイルの移動を高速なディスクを検討してください。 SQL Server がクラスター化された環境では、これがありませんできるだけ多くの問題にならなければなので、ログ ファイルは既に共有ドライブが含まれ、複数のスピンドルを高速な SAN ドライブが場合があります。 それでもまだディスク I/O の使用状況を監視する必要があります。 非クラスター化環境またはときに、DTC ログ ファイルは他の大量のディスク ファイルで共有ディスク上でボトルネックになるためにです。  
  
## <a name="separate-the-messagebox-and-tracking-databases"></a>メッセージ ボックス データベースおよび追跡データベースを分割します。  
 BizTalk メッセージ ボックス データベースと BizTalk 追跡データベースは、最もアクティブであるために、これらをディスク I/O の競合の問題の可能性を減らすために専用のドライブ上のそれぞれのデータ ファイルとトランザクション ログ ファイルを配置するをお勧めします。 たとえば、する必要があります、メッセージ ボックス データベースおよび BizTalk 追跡データベース ファイルの 4 つのドライブ、1 つのドライブ、次のそれぞれに。  
  
-   メッセージ ボックス データ ファイル  
  
-   メッセージ ボックス データベースのトランザクション ログ ファイル  
  
-   データ ファイルを BizTalk 追跡 (DTA)  
  
-   トランザクション ログ ファイルの BizTalk 追跡 (DTA)  
  
 BizTalk メッセージ ボックス データベースと BizTalk 追跡データベースを分離して、データベース ファイルとトランザクション ログ ファイルの異なる物理ディスクを分離することは、ディスク I/O の競合を減らすためのベスト プラクティスと見なされます。 可能な限り多くの物理スピンドル ディスク I/O に分散しようとしてください。 専用の SQL Server で、BizTalk 追跡データベースを配置することによって、ディスク I/O の競合を削減することもできます。ただし、引き続きデータ ファイルとトランザクション ログ ファイルの分離に関する上記のプラクティスに従ってください。  
  
## <a name="optimize-filegroups-for-the-biztalk-server-databases"></a>BizTalk Server データベースのファイル グループを最適化します。  
 手順に従います[、Databases2 のファイル グループを最適化する](../technical-guides/optimizing-filegroups-for-the-databases2.md)と[BizTalk Server データベースの最適化](http://go.microsoft.com/fwlink/?LinkId=101578)ホワイト ペーパー ([http://go.microsoft.com/fwlink/?LinkId = 101578](http://go.microsoft.com/fwlink/?LinkId=101578)) 追加のファイル グループと BizTalk Server データベースのファイルを作成します。 これにより、1 つのディスク構成から BizTalk Server データベースのパフォーマンスが大幅に増加します。  
  
## <a name="see-also"></a>参照  
 [データベースのパフォーマンスを最適化します。](../technical-guides/optimizing-database-performance.md)