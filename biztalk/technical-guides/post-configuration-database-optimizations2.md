---
title: 構成後のデータベース Optimizations2 |Microsoft Docs
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
ms.openlocfilehash: 8489d69489a23d6c81efb8443cccbb40c7a357ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993795"
---
# <a name="post-configuration-database-optimizations"></a>構成後のデータベースの最適化
推奨事項に従うだけでなく[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)、いくつかの手順は、SQL Server で BizTalk Server データベースのパフォーマンスを最適化するために従う必要があります*後*BizTalk Server がインストールされているし、BizTalk Server データベースが構成されています。 このトピックでは、これらの最適化の一覧を示します。  
  
## <a name="consider-setting-the-text-in-row-table-option-on-specific-messagebox-database-tables"></a>特定のメッセージ ボックス データベース テーブルの 'text in row' テーブル オプションを設定してみてください。  
 SQL Server と呼ばれるテーブル オプションを提供する**行内テキスト**を宣言する型のフィールドの内容**テキスト**、 **ntext**、または**イメージ**次元は、データ ページ (8 Kb) のものより小さいデータは、データ行に格納する必要があります。 BizTalkMsgBoxDb テーブル (Parts テーブル、スプール テーブルおよび DynamicStateInfo テーブル) でこのオプションを設定して、小規模なコンテキストとサイズが小さい永続化するオーケストレーションが含まれる小さいメッセージを使用する場合、メッセージ スループットを向上できます。  
  
- **テーブルのパーツ**: メッセージのサイズが 8 kb のデータ ページのサイズより小さい場合は、適用、**行内テキスト**部品テーブルにテーブルのオプションが BizTalk Server パフォーマンスが向上する可能性があります。 Parts テーブルには、次のフィールドが含まれています。  
  
  - **ImgPart**: メッセージの一部またはメッセージ部分のフラグメントが含まれています。  
  
  - **ImgPropBag**: メッセージの一部のプロパティ バッグが含まれています。  
  
    これにより、ループして、メッセージ ボックスに対して BizTalk ホストで実行されているメッセージ エージェントから取得できますメッセージのバッチ Parts テーブル少量のページを読み取ることで。 特定のシナリオとハードウェア構成によっては、この方法は SQL Server と BizTalk Server の両方での CPU 使用率を低減され、待機時間とスループットの観点から重要な強化点を提供します。  
  
- **スプール テーブル**: メッセージ コンテキストの平均サイズが 8 kb 未満の場合に有効にすると、**行内テキスト**スプール テーブルのテーブル オプションには、に沿って MessageBox からメッセージを読み取るときに、アクセスの数を削減するのに役立ちますそのコンテキスト。 スプール テーブルには、このオプションを適用するには、不要なコンテキスト プロパティと 8 Kb 未満のメッセージ コンテキストのサイズを小さく識別フィールドを排除する必要があります。  
  
- **DynamicStateInfo テーブル**ホストごとに 1 つずつ、これらのテーブルには、実行中に永続化ポイントを検出したときに、バイナリでシリアル化されたオーケストレーションの状態を含む imgData と呼ばれるイメージのタイプのフィールドが含まれています。 ホスト HostA 内のオーケストレーションの内部状態が非常に小さいため、1 回シリアル化のサイズが 8 kb 未満である場合、**行内テキスト**手法は、DynamicStateInfo_HostA テーブルに正常に適用できます。 そのためのオーケストレーションの内部状態できるだけ小さくするままことをお勧めします。 この手法では、シリアル化、永続化、逆シリアル化および永続化ポイントが発生した場合、オーケストレーションの内部状態を復元するには、XLANG エンジンによって費やされた時間を大幅に短縮できます。  
  
  ラボ テストの結果で、次の設定を使いました。  
  
- EXEC sp_tableoption N'Spool'、'text in row'、'6000'  
  
- EXEC sp_tableoption N'Parts'、'text in row'、'6000'  
  
## <a name="define-auto-growth-settings-for-biztalk-server-databases-to-a-fixed-value-instead-of-a-percentage-value"></a>パーセント値ではなく固定値に BizTalk Server データベースの自動拡張設定を定義します。  
  
-   SQL Server データベースの自動拡張は、BizTalk Server データベースのパフォーマンスの低下、ブロッキング操作です。 そのためデータベース自動拡張の発生を最小限に抑えるには、事前に、BizTalk Server データベースに対して十分な領域を割り当てることが重要です。  
  
-   データベース自動拡張は、固定数の割合の代わりにメガバイト単位に設定する必要があります (ファイルの拡張を指定**メガバイト単位で**)。 これは、測定された方式では自動拡張が発生した場合されるように行う必要があります。 これにより、過剰なデータベース サイズの増加が発生する可能性が減少します。 BizTalk Server データベースの拡張増分値通常 100 MB 以上必要があります。  
  
## <a name="pre-size-biztalk-server-databases-to-appropriate-size-with-multiple-data-files"></a>複数のデータ ファイルの適切なサイズに事前にサイズの BizTalk Server データベース  
 SQL Server には、ファイルのサイズが大きくとき、は、新しいスペースまず初期化を可能にする前に、必要があります。 これは、空のページで、新しい領域の入力を含むブロッキング操作です。 SQL Server 2005 またはそれ以降を実行している Windows Server 2003 またはそれ以降は、「ファイルの瞬時初期化します」をサポートしています これは、ファイルの拡張操作のパフォーマンスに与える影響を大幅に削減できます。 詳細については、次を参照してください。[データベース ファイルの初期化](http://go.microsoft.com/fwlink/?LinkId=132063)(http://go.microsoft.com/fwlink/?LinkId=132063) (SQL Server オンライン ブック)。 このトピックでは、ファイルの瞬時初期化を有効にするための手順を説明します。  
  
 ラボ テストで使用される BizTalk Server データベースの構成は次のとおりです。  
  
- **BizTalk DTADB (BizTalk 追跡データベースのファイル):** と 100 MB の増加に 1024 MB のログ ファイルのファイル サイズが 100 MB の増加に 2048 MB のデータ ファイル。  
  
- **BizTalkMgmtdb (BizTalk 管理データベースのファイル):** データ ファイルが 100 MB の増加に 512 MB のファイル サイズと 512 MB のログ ファイルを 100 MB に拡張します。  
  
- **SSODB:** データ ファイルが 100 MB の増加に 512 MB のファイル サイズと 512 MB のログ ファイルを 100 MB に拡張します。  
  
- **BizTalkMsgBoxDb (BizTalk メッセージ ボックス データベース):** 8 データ ファイル、ファイル サイズ 2 GB、100 MB の成長と 20 gb、100 MB の成長のログ ファイルは、それぞれが。 BizTalk メッセージ ボックス データベースは、最もアクティブであるために、データ ファイルとディスク I/O の競合に関する問題の可能性を低減する専用のドライブ上のトランザクション ログ ファイルを配置するをお勧めします。 このラボ環境では、次のそれぞれの 1 つのドライブを使いました。  
  
  -   メッセージ ボックス データ ファイル  
  
  -   メッセージ ボックス データベースのトランザクション ログ ファイル  
  
  ドライブ J (J:\BizTalkMsgBoxDb.mdf) 上のデータ ファイルとログ ファイル ドライブ K (K:\BizTalkMsgBoxDb_log の最初にある BizTalkMsgBoxDb のサイズを事前に次の SQL スクリプトを使用できます。LDF):  
  
> [!IMPORTANT]  
>  このスクリプトは、デモまたは教育目的にのみのためのものでは、ご自身の責任で使用される「とは、」です。 、Microsoft では、このスクリプトの使用はサポートされていないと、このスクリプトの適合性に関する Microsoft の保証がありません。  
  
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
  
## <a name="move-the-backup-biztalk-server-output-directory-to-a-dedicated-lun"></a>BizTalk Server のバックアップの出力ディレクトリを専用の LUN に移動します。  
 バックアップ BizTalk (フル インストール オプションとログ バックアップ) の出力ディレクトリを専用の LUN に移動して、専用の LUN をポイントする BizTalk Server のバックアップ ジョブを編集します。 読み取りは専用 LUN に BizTalk Server のバックアップの出力ディレクトリは、ジョブとは異なるディスクに書き込むことで、ジョブの実行時にディスク I/O の競合を減らすが移動します。 BizTalk Server のバックアップ ジョブの構成の詳細については、次を参照してください。 [Backup BizTalk Server ジョブを構成する方法](http://go.microsoft.com/fwlink/?LinkID=153813)(http://go.microsoft.com/fwlink/?LinkID=153813) BizTalk Server 2010 のヘルプ。  
  
## <a name="verify-that-the-biztalk-server-sql-agent-jobs-are-running"></a>BizTalk Server の SQL エージェント ジョブが実行されていることを確認します。  
 BizTalk Server には、動作状況と状態、サーバーを保持する重要な機能を実行するいくつかの SQL Server エージェント ジョブが含まれています。 これらのジョブの正常性を監視し、エラーなしで実行されていることを確認する必要があります。 BizTalk Server のパフォーマンスの問題の最も一般的な原因の 1 つは、BizTalk Server の SQL エージェント ジョブではなく、実行中、メッセージ ボックスがさらに可能性があるあり、データベースをオフに拡張するトラッキングします。 BizTalk Server の SQL エージェント ジョブが問題なく実行されていることを確認する次の手順に従います。  
  
1.  **SQL Server エージェント サービスが実行されていることを確認します。** します。  
  
2.  **BizTalk Server によってインストールされる SQL Server エージェント ジョブが有効になっていることを確認し、正常に実行されている**します。  
    BizTalk Server SQL Server エージェント ジョブは非常に重要です。 時間の経過と共に実行されていない場合、システムのパフォーマンスが低下します。  
  
3.  **適切なタイミングで、BizTalk Server SQL Server エージェント ジョブが完了することを確認します。** します。   
    ジョブを監視する、Microsoft System Center Operations Manager の最新バージョンを設定します。  
    特定のジョブを特定のスケジュールの注意する必要があります。  
  
    -   既定では、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブが継続的に実行されます。 ソフトウェアを監視、このスケジュールを考慮に入れてし、警告を生成しない必要があります。  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb ジョブは有効、またはスケジュール設定をされませんが、10 秒ごと、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブによって起動されました。 そのため、このジョブする必要がありますいない有効、スケジュールまたは手動で開始されました。  
  
4.  **SQL Server エージェント サービスのスタートアップの種類が正しく構成されていることを確認します。** します。  
    SQL Server エージェント サービスが構成されていることを確認、**スタートアップの種類**の**自動**SQL Server エージェント サービスが Windows Server クラスターでクラスター リソースとして構成されていない場合。 SQL Server エージェント サービスがクラスター リソースとして構成されているかどうかは、構成する必要があります、**スタートアップの種類**として**手動**サービスは、クラスター サービスによって管理されるためです。  
  
## <a name="configure-purging-and-archiving-of-tracking-data"></a>構成の削除と追跡データのアーカイブ  
 削除と追跡データのアーカイブが正しく構成されていることを確認する次の手順に従います。  
  
1.  SQL エージェント ジョブ「DTA の消去およびアーカイブ」が適切に構成された、有効化、および正常に完了することを確認します。 詳細については、[DTA Purge and Archive ジョブを構成する方法](http://go.microsoft.com/fwlink/?LinkID=153814)(http://go.microsoft.com/fwlink/?LinkID=153814) 、BizTalk Server のドキュメントにを参照してください。  
  
2.  ジョブが速やかに受信した追跡データが生成されると、追跡データを消去することを確認します。 詳細については、[維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815) 、BizTalk Server のドキュメントにを参照してください。  
  
3.  論理削除と時間の最適な長さのデータを保持することを確認する物理削除パラメーターを確認します。 詳細については、[アーカイブおよび BizTalk 追跡データベースの削除](http://go.microsoft.com/fwlink/?LinkID=153816)(http://go.microsoft.com/fwlink/?LinkID=153816) 、BizTalk Server のドキュメントにを参照してください。  
  
4.  古いデータを消去しないだけの場合必要があります、最初の変更を保存する SQL エージェント ジョブ"dtasp_PurgeTrackingDatabase"ストアド プロシージャを呼び出す 詳細については、[BizTalk 追跡データベースからのデータの削除方法](http://go.microsoft.com/fwlink/?LinkID=153817)(http://go.microsoft.com/fwlink/?LinkID=153817) 、BizTalk Server のドキュメントにを参照してください。  
  
## <a name="monitor-and-reduce-dtc-log-file-disk-io-contention"></a>監視し、DTC ログ ファイルのディスク I/O の競合の削減  
 分散トランザクション コーディネーター (DTC) ログ ファイルは、トランザクション処理を要する環境でディスク I/O のボトルネックになります。 これは、トランザクション、またはマルチ メッセージ ボックス環境で SQL Server、MSMQ、MQSeries などをサポートするアダプターを使用する場合に特に当てはまります。 トランザクション アダプターが DTC トランザクションを使用し、メッセージ ボックスの複数の環境によって、DTC トランザクションを広範に使用します。 DTC ログ ファイルがディスク I/O のボトルネックにならないことを確認するには、ディスクの SQL Server のデータベース サーバーでは、DTC ログ ファイルが存在する場所、ディスク I/O の使用量を監視する必要があります。 ディスク I/O、DTC ログ ファイルがあるディスクの使用量が過剰になると、DTC ログ ファイルを高速ディスクに移行を検討してください。 SQL Server がクラスター化された環境でない問題の多くが複数のスピンドルを備えた高速な SAN ドライブ、共有ドライブ ログ ファイルが既に存在するためです。 それでもまだディスク I/O の使用状況を監視する必要があります。 非クラスター化の環境または DTC ログ ファイルが他のハード ディスク ファイルと共有ディスクであるときにボトルネックになるためにです。  
  
## <a name="separate-the-messagebox-and-tracking-databases"></a>メッセージ ボックス データベースと追跡データベースを分離します。  
 BizTalk メッセージ ボックスおよび BizTalk 追跡データベースは、最もアクティブであるために、ディスク I/O の競合に関する問題の可能性を低減する専用のドライブにこれらの各データ ファイルとトランザクション ログ ファイルを配置するをお勧めします。 たとえば、次の各メッセージ ボックス データベースと BizTalk 追跡データベース ファイルの 4 つのドライブ、1 つのドライブを必要があります。  
  
- メッセージ ボックス データ ファイル  
  
- メッセージ ボックス データベースのトランザクション ログ ファイル  
  
- データ ファイルを BizTalk 追跡 (DTA)  
  
- トランザクション ログ ファイルの BizTalk 追跡 (DTA)  
  
  BizTalk メッセージ ボックスおよび BizTalk 追跡データベースを分離し、データベース ファイルとトランザクション ログ ファイルの異なる物理ディスクを分離することは、ディスク I/O の競合を減らすためのベスト プラクティスと見なされます。 できるだけ多くの物理スピンドルにディスク I/O を分散しようとしてください。 専用の SQL Server で、BizTalk 追跡データベースを配置することで、ディスク I/O の競合を削減することもただし、まだデータ ファイルとトランザクション ログ ファイルを分離することに関しては、上記のプラクティスに従ってください。  
  
## <a name="optimize-filegroups-for-the-biztalk-server-databases"></a>BizTalk Server データベースのファイル グループを最適化します。  
 次の手順では、 [、Databases2 のファイル グループを最適化する](../technical-guides/optimizing-filegroups-for-the-databases2.md)と[BizTalk Server データベースの最適化](http://go.microsoft.com/fwlink/?LinkId=101578)ホワイト ペーパー ([http://go.microsoft.com/fwlink/?LinkId=101578](http://go.microsoft.com/fwlink/?LinkId=101578)) 追加して作成するにはファイル グループと BizTalk Server データベース用のファイルです。 これにより、1 つのディスク構成から BizTalk Server データベースのパフォーマンスが大幅に増加します。  
  
## <a name="see-also"></a>参照  
 [データベース パフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)