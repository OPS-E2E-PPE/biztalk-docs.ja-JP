---
title: "ファイル グループを最適化する、Databases2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d7fa4c9-e504-4f43-a308-517a4a574c26
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2f3ffab64795f8000af37cdc07c3754bb1fb5bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-filegroups-for-the-databases"></a>データベースのファイル グループを最適化します。
ファイルは、入出力 (I/O) の競合が頻繁に限定要素、または実稼働環境の BizTalk Server 環境で、ボトルネックです。 BizTalk Server は非常にデータベースの処理を要するアプリケーションと、さらに、大量の I/O を非常にファイルは、BizTalk Server によって使用される SQL Server データベース。 このトピックでは、ファイルおよびファイル I/O の競合の発生を最小限に抑えるし、BizTalk Server ソリューションの全体的なパフォーマンスを向上する SQL Server のファイル グループの機能の使用を最適化する方法について説明します。  
  
## <a name="overview"></a>概要  
 すべての BizTalk Server ソリューションでは、スループットが増加するにつれて、ファイル I/O の競合が最終的に発生します。 I/O サブシステムまたはストレージ エンジンは、任意のリレーショナル データベースの主要コンポーネントです。 通常、データベースの実装を成功させるには、プロジェクトの初期段階で慎重に計画を立てる必要があります。 計画では、次の問題について検討する必要があります。  
  
-   RAID (Redundant Array of Independent Disks) デバイスなど、使用するディスク ハードウェアの種類。 詳細については、RAID ハードウェア ソリューションを使用して、次を参照してください。[に関するハードウェア ベースのソリューション](http://go.microsoft.com/fwlink/?LinkID=113944)(http://go.microsoft.com/fwlink/?LinkID=113944)、SQL Server オンライン ブック。  
  
-   ファイルおよびファイル グループを使用してディスク上のデータを分配する方法。 SQL Server 2008 R2 でのファイルおよびファイル グループの使用の詳細については、次を参照してください[ファイルを使用するとファイル グループ](http://go.microsoft.com/fwlink/?LinkID=69369)(http://go.microsoft.com/fwlink/?。LinkID = 69369) および[Understanding ファイルおよびファイル グループ](http://go.microsoft.com/fwlink/?LinkID=96447)(http://go.microsoft.com/fwlink/?LinkID = 96447)、SQL Server オンライン ブック。  
  
-   データにアクセスする場合は、パフォーマンスを向上させるための最適なインデックスの設計を実装します。 インデックスのデザインの詳細については、次を参照してください。[インデックスの設計](http://go.microsoft.com/fwlink/?LinkID=96457)(http://go.microsoft.com/fwlink/?LinkID=96457)、SQL Server Books Online にします。  
  
-   最適なパフォーマンスを SQL Server の構成パラメーターを設定する方法。 SQL Server の最適な構成パラメーターの設定に関する詳細については、次を参照してください。[サーバー パフォーマンスの最適化](http://go.microsoft.com/fwlink/?LinkID=71418)(http://go.microsoft.com/fwlink/?LinkID=71418)、SQL Server Books Online にします。  
  
 BizTalk Server の主な設計目標の 1 つはメッセージであることを確認する**決して**失われます。 メッセージの損失の可能性を軽減するためには、メッセージが処理されるメッセージをメッセージ ボックス データベースに書き込まれます頻繁にします。 オーケストレーションによって処理されるメッセージは、オーケストレーション内のすべての永続化ポイントのメッセージ ボックス データベースに、メッセージが書き込まれます。 これらの永続性ポイントには、メッセージと関連する状態をディスクに書き込む物理メッセージ ボックスがあります。 高いスループットでは、この永続化は、かなりのディスクの競合が生じるし、ボトルネックになる可能性があります。  
  
 ファイルを使用する最適なとを効果的にファイル IO のボトルネックを解決し、BizTalk Server ソリューションの全体的なパフォーマンスを向上させる SQL Server のファイル グループの機能が表示されます。  
  
> [!NOTE]  
>  この最適化は、経験豊富な SQL Server データベース管理者と BizTalk Server データベースを正しくバックアップされている後のすべてのみでのみ実行する必要があります。 BizTalk Server 環境内のすべての SQL Server コンピューター上には、この最適化を実行してください。  
  
 SQL Server のファイルおよびファイル グループは、この機能は、複数のディスク コント ローラーに複数のディスクに作成するデータベースを許可しているので、データベースのパフォーマンスを向上させるために使用できるまたは RAID (独立したディスクの冗長アレイ) システムです。 たとえば、コンピューターにディスクが 4 個ある場合は、データ ファイル 3 つとログ ファイル 1 つから構成されるデータベースを、各ディスクにファイルを 1 つずつ配置して作成できます。 データへのアクセスと 4 つの読み取り/書き込みヘッドは並行してデータを同時にアクセスできます。 これは、ため、速度データベース操作が大幅にします。 SQL Server のディスクのハードウェア ソリューションの実装の詳細については、次を参照してください。[データベースのパフォーマンス](http://go.microsoft.com/fwlink/?LinkID=71419)(http://go.microsoft.com/fwlink/?LinkID=71419)、SQL Server Books Online にします。  
  
 さらに、ファイルおよびファイル グループを有効にするデータの配置、特定のファイル グループ内のテーブルを作成できるためです。 これにより、特定のテーブルのすべてのファイル I/O は、特定のディスクに向けることがあるために、パフォーマンスが向上します。 たとえば、頻繁に使用されるテーブルは、1 つのディスク上にある、ファイル グループ内のファイルに配置できるし、データベース内の他の頻度が低いテーブルは、2 番目のディスク上にある別のファイル グループ内の別のファイルに配置できます。  
  
 ファイル I/O のボトルネックは、トピックの「かなりに詳しく説明[データベース層のボトルネック](../technical-guides/bottlenecks-in-the-database-tier.md)です。 ファイル I/O (ディスク I/O) がボトルネックである最も一般的なインジケーターは、「物理ディスク: 平均ディスク キューの長さ」カウンターの値です。 「物理ディスク: 平均ディスク キューの長さ」カウンターの値が SQL Server を実行しているコンピューター上の特定のディスクの約 3 より大きい場合は、そのファイルの I/O は可能性がありますボトルネックです。  
  
 ファイルまたはファイル グループの最適化を適用することも、ファイル I/O のボトルネックの問題が解決しない場合は、追加の物理マシンまたは SAN ドライブを追加することで、ディスク サブシステムのスループットを増やす必要があります。  
  
 このトピックの内容を手動でファイルおよびファイル グループの最適化を適用する方法を説明しますが、これらの最適化もスクリプトを作成できます。 SQL スクリプトのサンプルがで提供される[BizTalk Server メッセージ ボックス データベースのファイル グループの SQL スクリプト](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)です。  
  
> [!NOTE]  
>  このスクリプトは、ファイル、ファイル グループ、および特定の BizTalk Server ソリューションの SQL Server データベースによって使用されるディスク構成に対応するように変更する必要がある重要です。  
  
> [!NOTE]  
>  このトピックでは、複数のファイルと、BizTalk メッセージ ボックス データベースのファイル グループを作成する方法についても説明します。 推奨されるファイルと、BizTalk Server データベースのすべてのファイル グループの排他的なリストを参照してください"付録 B"の[BizTalk Server データベースの最適化](http://go.microsoft.com/fwlink/?LinkID=101578)ホワイト ペーパー (http://go.microsoft.com/fwlink/?LinkID=101578)。  
  
> [!NOTE]  
>  場合でも、 [BizTalk Server データベースの最適化](http://go.microsoft.com/fwlink/?LinkID=101578)ホワイト ペーパー (http://go.microsoft.com/fwlink/?LinkID=101578) で書き込まれた[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]ことに注意を同じ原則にも適用[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]です。  
  
## <a name="databases-created-with-a-default-biztalk-server-configuration"></a>既定の BizTalk Server の構成で作成されたデータベース  
 これによっては、SQL Server で作成する 13 の異なるデータベースまで BizTalk Server を構成する可能性があり、これらすべてのデータベースが既定のファイル グループの作成時に機能が有効です。 SQL Server の既定のファイル グループは、ALTER DATABASE コマンドを使用して既定のファイル グループが変更されない限り、プライマリ ファイル グループがします。 次の表には、BizTalk Server を構成するときに、すべての機能が有効な場合は、SQL サーバーで作成されるデータベースが一覧表示します。  
  
### <a name="biztalk-server-databases"></a>BizTalk Server データベース  
  
||||  
|-|-|-|  
|**データベース**|**既定のデータベース名**|**Description**|  
|構成データベース|BizTalkMgmtDb|中央のメタ情報は、BizTalk Server グループ内の BizTalk Server のすべてのインスタンスを格納します。|  
|BizTalk メッセージ ボックス データベース|BizTalkMsgBoxDb|サブスクリプションの述語を格納します。 ホストのプラットフォームと、各 BizTalk Server ホストのキューおよび状態テーブルを保持します。 また、メッセージ ボックス データベースには、メッセージおよびメッセージ プロパティが格納されます。|  
|BizTalk 追跡データベース|BizTalkDTADb|ビジネスおよび稼動状況の監視、BizTalk Server 追跡エンジンで追跡したデータを格納します。|  
|BAM 分析データベース|BAMAnalysis|ビジネス アクティビティの集計の履歴データを保持する SQL Server Analysis Services データベースです。|  
|BAM スター スキーマ データベース|BAMStarSchema|OLAP 処理用ビジネス アクティビティ監視から収集されたデータを変換します。 BAM 分析データベースを使用する場合、このデータベースが必要です。|  
|BAM プライマリ インポート データベース|BAMPrimaryImport|アクティビティ インスタンスの後に、ビジネス アクティビティの進行状況とデータのクエリからイベントを格納します。 また、このデータベースは、リアルタイム集計を実行します。|  
|BAM アーカイブ データベース|BAMArchive|サブスクリプションの述語を格納します。 BAM アーカイブ データベースには、BAM プライマリ インポート データベース内のビジネス アクティビティ データの蓄積が最小限に抑えます。|  
|SSO データベース|SSODB|構成は安全に格納の情報を受信場所。 SSO の情報を格納は、すべての関連アプリケーションへの暗号化されたユーザーの資格情報だけでなく、アプリケーションに関連します。|  
|ルール エンジン データベース|BizTalkRuleEngineDb|リポジトリ。<br /><br /> -ポリシーは、関連するルールのセットが生成されます。<br />-ボキャブラリをルール内でのデータ参照のドメイン固有のわかりやすい名前のコレクションであります。|  
|BizTalk ベース EDI データベース|BizTalkEDIDb|EDI ドキュメントの追跡とデータの処理を格納します。|  
|ヒューマン ワークフロー サービス管理データベース|BizTalkHwsDb|BizTalk ヒューマン ワークフロー サービスで必要な管理情報を格納します。|  
|取引先管理データベース|TPM|取引先データのビジネス アクティビティ サービス (BAS) を保存します。|  
|追跡分析サーバーの管理データベース|BizTalkAnalysisDb|ビジネスおよび稼動状況監視 OLAP キューブの両方を格納します。|  
  
## <a name="separation-of-data-files-and-log-files"></a>データ ファイルとログ ファイルの分離  
 前述のように、BizTalk Server の構成の既定値は、既定のファイル グループで単一のファイルに、メッセージ ボックス データベースを配置します。 既定では、メッセージ ボックス データベースのデータとトランザクション ログは、同じドライブおよびパスに配置されます。 これは、1 つのディスクとシステムに対応するためです。 1 つのファイルとファイル グループ/ディスク構成が**最適ではない**実稼働環境でします。 パフォーマンスを最適には、データ ファイルとログ ファイルを別のディスクに配置する必要があります。  
  
> [!NOTE]  
>  ログ ファイルは、ファイル グループに含めることはできます。 ログ領域はデータ領域とは別に管理されます。  
  
## <a name="the-8020-rule-of-distributing-biztalk-server-databases"></a>BizTalk Server データベースを配布する 80/20 規則  
 ほとんどの BizTalk Server ソリューション、ディスク I/O の競合やデータベースの競合が原因で発生する競合の主なソースは、BizTalk Server メッセージ ボックス データベースです。 これは、単一およびマルチ メッセージ ボックスの両方のシナリオでは true です。 BizTalk データベースを配布する値の 80% が最適化されたメッセージ ボックス データ ファイルとログ ファイルから導き出されますことを想定することお勧めします。 次の詳細なシナリオの例は、メッセージ ボックス データベースのデータ ファイルを最適化する重視されています。 必要に応じて、これらの手順を他のデータベースの後に、できます。 たとえば、ソリューションには、広範囲な追跡が必要とする場合、追跡データベース最適化することもできます。  
  
## <a name="manually-adding-files-to-the-messagebox-database-step-by-step"></a>ファイルをメッセージ ボックス データベースは、詳細な手順を手動で追加します。  
 このセクションのトピックでは、メッセージ ボックス データベースにファイルを手動で追加する手順について説明します。 この例では、次の 3 つのファイル グループが追加され、メッセージ ボックスに対して複数のディスクにファイルを配布する各ファイル グループにファイルが追加します。 この例では、手順を実行して、[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]です。  
  
### <a name="manually-adding-files-to-the-messagebox-database-on-sql-server-2008-r2"></a>SQL Server 2008 R2 上のメッセージ ボックス データベースにファイルを手動で追加します。  
 **SQL Server 2008 R2 上のメッセージ ボックス データベースにファイルを手動で追加する手順に従います。**  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント **[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]** 、クリックして**SQL Server Management Studio**を表示する、**サーバーへの接続** ダイアログ ボックス。  
  
     ![SQL Server 2008 R2 &#45;ログイン画面](../technical-guides/media/sqlserver2008r2-loginscreen.gif "SQLServer2008R2 Loginscreen")  
  
2.  **サーバー名**のボックスの編集、**サーバーへの接続** ダイアログ ボックスで、BizTalk Server メッセージ ボックス データベースを格納する SQL Server インスタンスの名前を入力し、をクリックして**の接続**を SQL Server Management Studio を表示します。 **オブジェクト エクスプ ローラー** SQL Server Management Studio のウィンドウが展開**データベース**を SQL Server のこのインスタンスのデータベースを表示します。  
  
     ![SQL Server 2005 Management Studio]、[オブジェクト エクスプ ローラー](../technical-guides/media/81f13912-fedc-48c3-9669-c18863e637b1.gif "81f13912-fedc-48c3-9669-c18863e637b1")  
  
3.  クリックして、ファイルを追加するデータベースを右クリックして**プロパティ**を表示する、**データベース プロパティ**データベース用のダイアログ ボックス。  
  
     ![SQL Server 2005 データベースのプロパティ ダイアログ ボックス](../technical-guides/media/82ae7c11-5b3a-4312-876c-70876abdd65c.gif "82ae7c11-5b3a-4312-876c-70876abdd65c")  
  
4.  **データベース プロパティ**ダイアログ ボックスで、**ファイル グループ**ページ。 BizTalkMsgBoxDb データベースの追加のファイル グループを作成するをクリックして**追加**です。 次の例では、次の 3 つの追加のファイル グループが追加されます。  
  
     ![SQL Server 2005、データベースへのファイル グループの追加](../technical-guides/media/6be47c0e-06c3-45d9-bce2-a42453da7d19.gif "6be47c0e-06c3-45d9-bce2-a42453da7d19")  
  
5.  **[データベースのプロパティ]** ダイアログ ボックスで、 **[ファイル]** ページをクリックします。  
  
     ファイル グループに追加するファイルを作成するをクリックして**追加**、クリックして**OK**です。 メッセージ ボックス データベースは、大幅なパフォーマンス利点は、1 つのディスク構成を提供する複数のディスクに分散されますようになりました。  
  
     次の例を以前に作成されたファイル グループの各ファイルが作成され、各ファイルが別のディスクに配置されます。  
  
     ![SQL Server 2005、ファイル、ファイル グループを追加する](../technical-guides/media/d5d5c5df-d483-4f01-8128-f98228de51b9.gif "d5d5c5df-d483-4f01-8128-f98228de51b9")  
  
## <a name="sample-sql-script-for-adding-filegroups-and-files-to-the-biztalk-messagebox-database"></a>BizTalk メッセージ ボックス データベースにファイルとファイル グループを追加するための SQL スクリプトのサンプル  
 このガイドには、BizTalk Server メッセージ ボックス データベースにファイルとファイル グループを追加するための SQL スクリプトが含まれています。  
  
> [!NOTE]  
>  SQL Server のログ ファイルに書き込むと順番に、ため、SQL Server データベース用の複数のログ ファイルを作成することで実現パフォーマンス上の利点はありません。  
  
 このスクリプトを実行するには、次の手順を実行します。  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント **[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]** 、クリックして**SQL Server Management Studio**を表示する、**サーバーへの接続** ダイアログ ボックス。  
  
2.  **サーバー名**のボックスの編集、**サーバーへの接続** ダイアログ ボックスで、BizTalk Server メッセージ ボックス データベースを格納する SQL Server インスタンスの名前を入力し、をクリックして**の接続** SQL Server Management Studio のダイアログ ボックスを表示します。  
  
3.  SQL Server Management Studio でをクリックして、**ファイル**メニューのをポイント**新規**、順にクリック**現在の接続とクエリ**SQL クエリ エディターを起動します。  
  
4.  サンプル スクリプトをコピー [BizTalk Server メッセージ ボックス データベースのファイル グループの SQL スクリプト](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)をクエリ エディターにします。  
  
5.  BizTalk Server 環境に合わせて、スクリプトでは、パラメーターを編集し、スクリプトを実行します。  
  
 スクリプト作成の利点はスクリプト複数のタスクをすばやく実行することができます、正確には、再現することができます、人的ミスの可能性を低減します。 スクリプト作成の欠点は、正しく記述されていないスクリプトの実行が最初から再度構成する BizTalk Server データベースを必要となる重大な問題になることができます可能性があります。  
  
> [!IMPORTANT]  
>  重要なの SQL スクリプトなど、このガイドのサンプル スクリプトは、運用環境で実行する前に徹底的にテストのことです。  
  
## <a name="see-also"></a>参照  
 [データベースのパフォーマンスを最適化します。](../technical-guides/optimizing-database-performance.md)