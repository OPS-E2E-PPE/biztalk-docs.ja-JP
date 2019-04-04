---
title: データベース ファイル グループの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d7fa4c9-e504-4f43-a308-517a4a574c26
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e15f03a0891bff6204c6a8d49cae9dc032caef1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022704"
---
# <a name="optimizing-filegroups-for-the-databases"></a>データベースのファイルグループの最適化
ファイルは、入出力 (I/O) の競合が制限要因、または運用環境の BizTalk Server 環境で、ボトルネックが頻繁にです。 BizTalk Server が非常にデータベースの処理を要するアプリケーションと、さらに、BizTalk Server によって使用される SQL Server データベースは、非常にファイル I/O を集中的に使用します。 このトピックでは、ファイルおよびファイル I/O の競合の発生を最小限に抑えるし、BizTalk Server ソリューションの全体的なパフォーマンスを向上する SQL Server のファイル グループの機能の使用を最適化する方法について説明します。  
  
## <a name="overview"></a>概要  
 すべての BizTalk Server ソリューションでは、スループットが増加するにつれて、ファイル I/O の競合が最終的に発生します。 I/O サブシステムまたはストレージ エンジンは、任意のリレーショナル データベースのキー コンポーネントです。 通常、データベースの実装を成功させるには、プロジェクトの初期段階で慎重に計画を立てる必要があります。 計画では、次の問題について検討する必要があります。  
  
- RAID (Redundant Array of Independent Disks) デバイスなど、使用するディスク ハードウェアの種類。 
  
- ファイルおよびファイル グループを使用してディスク上のデータを分配する方法。 SQL Server でのファイルおよびファイル グループの使用に関する詳細については、[Database Files and Filegroups](https://docs.microsoft.com/sql/relational-databases/databases/database-files-and-filegroups)を参照してください。
  
- データにアクセスする場合は、パフォーマンスを向上させるための最適なインデックスの設計を実装します。 インデックスのデザインの詳細については、[インデックスの設計](https://docs.microsoft.com/sql/relational-databases/sql-server-index-design-guide)を参照してください。
  
- 最適なパフォーマンスを SQL Server の構成パラメーターを設定する方法。 SQL Server の最適な構成パラメーターの設定の詳細については、[サーバー構成オプションの](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)を参照してください。
  
  BizTalk Server の主な設計目標の 1 つは、メッセージがあることを確認する**決して**失われます。 メッセージの損失の可能性を軽減するためには、メッセージが処理されるメッセージをメッセージ ボックス データベースに書き込まれます頻繁に。 オーケストレーションによって処理されるは、メッセージ、メッセージがオーケストレーション内のすべての永続化ポイントにあるメッセージ ボックス データベースに書き込まれます。 これらの永続性ポイントには、メッセージ ボックスに、物理ディスクへのメッセージと関連する状態の書き込みが発生します。 高いスループットをでは、この永続化は、かなりのディスクの競合が生じるし、ボトルネックになる可能性があることができます。  
  
  ファイルを使用する最適なとを効果的にファイル IO のボトルネックを解決し、BizTalk Server ソリューションの全体的なパフォーマンスを向上させる SQL Server でのファイル グループの機能も示されています。  
  
> [!NOTE]  
>  この最適化は、経験豊富な SQL Server データベース管理者と後のすべての BizTalk Server データベースを正しくバックアップされているだけでのみ実行する必要があります。 この最適化は、BizTalk Server 環境ですべての SQL Server コンピューターで実行する必要があります。  
  
 SQL Server のファイルおよびファイル グループは、この機能により、データベースを複数のディスク コント ローラーに複数のディスクにまたがって作成するためにデータベースのパフォーマンスを向上させるために使用できるまたは RAID (独立したディスクの冗長アレイ) システムです。 たとえば、コンピューターにディスクが 4 個ある場合は、データ ファイル 3 つとログ ファイル 1 つから構成されるデータベースを、各ディスクにファイルを 1 つずつ配置して作成できます。 データへのアクセスが行われると、4 つの読み取り/書き込みヘッドは並行してデータを同時にアクセスできます。 これにより速度が、データベース操作が大幅にします。 SQL Server のディスクのハードウェア ソリューションの実装の詳細については、[データベース パフォーマンス](http://go.microsoft.com/fwlink/?LinkID=71419)(http://go.microsoft.com/fwlink/?LinkID=71419) 、SQL Server Books Online にを参照してください。  
  
 さらに、ファイルおよびファイル グループを有効にする、データの配置で特定のファイル グループにテーブルを作成できるためです。 これにより、指定されたテーブルのすべてのファイル I/O は、特定のディスクに向けることがあるために、パフォーマンスが向上します。 たとえば、使用頻度の高いテーブルは、1 つのディスク上にあるファイル グループ内のファイルを配置でき、データベース内の他の頻度が低いテーブルを 2 番目のディスク上にある別のファイル グループ内の異なるファイルに配置することができます。  
  
 ファイル I/O のボトルネックがでかなり詳しく説明されている[データベース層のボトルネック](../technical-guides/bottlenecks-in-the-database-tier.md)します。 ファイル I/O (ディスク I/O) がボトルネックである最も一般的なインジケーターでは、「物理ディスク: 平均ディスク キューの長さ」カウンターの値です。 「物理ディスク: 平均ディスク キューの長さ」カウンターの値が SQL Server を実行しているコンピューター上の特定のディスクの約 3 より大きい場合、ファイル I/O と思われますボトルネックになっています。  
  
 ファイルまたはファイル グループの最適化を適用することも、ファイル I/O のボトルネックの問題が解決しない場合は、追加の物理または SAN ドライブを追加することで、ディスク サブシステムのスループットを向上させるために必要な場合があります。  
  
 このトピックでは、手動でファイルとファイル グループの最適化を適用する方法を説明しますが、これらの最適化をスクリプト化もできます。 サンプル SQL スクリプトに含まれる[BizTalk Server メッセージ ボックス データベースのファイル グループの SQL スクリプト](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)します。  
  
> [!NOTE]
>  このスクリプトはファイル、ファイル グループ、および任意の BizTalk Server ソリューションの SQL Server データベースによって使用されるディスク構成に合わせて変更する必要があることに注意してください。 重要です。  
> 
> [!NOTE]
>  このトピックでは、複数のファイルと、BizTalk メッセージ ボックス データベースのファイル グループを作成する方法も説明します。 推奨されるファイルと、BizTalk Server データベースのすべてのファイル グループをすべて網羅、用の「付録 B」を参照してください。、 [BizTalk Server データベースの最適化](http://go.microsoft.com/fwlink/?LinkID=101578)ホワイト ペーパー (http://go.microsoft.com/fwlink/?LinkID=101578)します。  
> 
> [!NOTE]
>  場合でも、 [BizTalk Server データベースの最適化](http://go.microsoft.com/fwlink/?LinkID=101578)ホワイト ペーパー (<http://go.microsoft.com/fwlink/?LinkID=101578>) で書き込まれた[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]に注意してください、同じ原則が BizTalk Server に適用します。  
  
## <a name="databases-created-with-a-default-biztalk-server-configuration"></a>既定の BizTalk Server の構成で作成されたデータベース  
 に応じて最大 13 の異なるデータベース、BizTalk Server の構成は SQL Server で作成でき、これらすべてのデータベースが既定のファイル グループの作成時に、機能が有効にします。 SQL Server の既定のファイル グループは、ALTER DATABASE コマンドを使用して既定のファイル グループが変更されない限り、プライマリ ファイル グループです。 次の表は、BizTalk Server を構成するときに、すべての機能が有効な場合は、SQL Server で作成されたデータベースを一覧表示します。  
  
### <a name="biztalk-server-databases"></a>BizTalk Server データベース  
  
||||  
|-|-|-|  
|**[データベース]**|**既定のデータベース名**|**[説明]**|  
|構成データベース|BizTalkMgmtDb|中央メタ情報は、BizTalk Server グループ内の BizTalk Server のすべてのインスタンスを格納します。|  
|BizTalk メッセージ ボックス データベース|BizTalkMsgBoxDb|サブスクリプションの述語を格納します。 ホスト プラットフォームし、各 BizTalk Server ホストのキューおよび状態テーブルを保持します。 また、メッセージ ボックス データベースには、メッセージおよびメッセージ プロパティが格納されます。|  
|BizTalk 追跡データベース|BizTalkDTADb|ビジネスおよび稼動状態の監視、BizTalk Server 追跡エンジンで追跡データを格納します。|  
|BAM 分析データベース|BAMAnalysis|ビジネス アクティビティの集計済み履歴データを保持する SQL Server Analysis Services データベースです。|  
|BAM スター スキーマ データベース|BAMStarSchema|OLAP 処理するために、ビジネス アクティビティの監視から収集されたデータを変換します。 BAM 分析データベースを使用する場合、このデータベースが必要です。|  
|BAM プライマリ インポート データベース|BAMPrimaryImport|アクティビティ インスタンスの後に、ビジネス アクティビティの進行状況とデータのクエリからイベントを格納します。 このデータベースには、リアルタイム集計も実行します。|  
|BAM アーカイブ データベース|BAMArchive|サブスクリプションの述語を格納します。 BAM アーカイブ データベースには、BAM プライマリ インポート データベース内のビジネス アクティビティ データの蓄積が最小限に抑えます。|  
|SSO データベース|SSODB|構成を安全に格納の情報の受信場所。 Sso の情報を格納は、すべての関連アプリケーションに暗号化されたユーザー資格情報だけでなく、アプリケーションに関連します。|  
|ルール エンジン データベース|BizTalkRuleEngineDb|リポジトリ:<br /><br /> -ポリシー、関連するルールのセットであります。<br />-ボキャブラリをルール内でデータの参照をドメイン固有のわかりやすい名前のコレクション。|  
|BizTalk ベース EDI データベース|BizTalkEDIDb|EDI ドキュメントの追跡および処理されたデータを格納します。|  
|ヒューマン ワークフロー サービス管理データベース|BizTalkHwsDb|BizTalk ヒューマン ワークフロー サービスで必要な管理情報を格納します。|  
|取引先管理データベース|TPM|ビジネス アクティビティ サービス (BAS) のパートナーのデータを取引先を保存します。|  
|追跡分析サーバーの管理データベース|BizTalkAnalysisDb|ビジネスおよび稼動状況監視 OLAP キューブの両方を格納します。|  
  
## <a name="separation-of-data-files-and-log-files"></a>データ ファイルとログ ファイルの分離  
 前述のように、既定の BizTalk Server の構成は、既定のファイル グループ内の 1 つのファイルにメッセージ ボックス データベースを配置します。 既定では、メッセージ ボックス データベースのデータとトランザクション ログが同じドライブおよびパスに配置されます。 これは、1 つのディスクを使用したシステムに対応するためです。 1 つのファイルまたはファイル グループ/ディスク構成が**最適ではない**運用環境でします。 最適なパフォーマンス、データ ファイルとログ ファイルを別個のディスクに配置する必要があります。  
  
> [!NOTE]  
>  ログ ファイルは、ファイル グループの一部ではできません。 ログ領域はデータ領域とは別に管理されます。  
  
## <a name="the-8020-rule-of-distributing-biztalk-server-databases"></a>BizTalk Server データベースを配布する 80/20 ルール  
 ディスク I/O の競合またはデータベースの競合のため、ほとんどの BizTalk Server ソリューションでの競合の主なソースは、BizTalk Server メッセージ ボックス データベースです。 これは、単一およびマルチ メッセージ ボックスの両方のシナリオに当てはまります。 BizTalk データベースを配布する値の 80% をメッセージ ボックス データ ファイルとログ ファイルを最適化することから導き出されますことがあると考えることになります。 シナリオの詳細を以下の例はメッセージ ボックス データベースのデータ ファイルの最適化に重点を置いています。 必要に応じて、次の手順を他のデータベースの後にし、できます。 たとえば、ソリューションは、広範な追跡を必要とする場合、追跡データベースを最適化もできます。  
  
## <a name="manually-adding-files-to-the-messagebox-database-step-by-step"></a>ステップ バイ ステップに、メッセージ ボックス データベースにファイルを手動で追加します。  
 このセクションのトピックでは、メッセージ ボックス データベースにファイルを手動で追加する手順について説明します。 この例では、次の 3 つのファイル グループが追加され、メッセージ ボックス データベースの複数のディスク ファイルを配布する各ファイル グループにファイルを追加します。
  
### <a name="manually-adding-files-to-the-messagebox-database-on-sql-server"></a>SQL Server のメッセージ ボックス データベースにファイルを手動で追加します。
   
1.  開いている**SQL Server Management Studio**を表示する、**サーバーへの接続** ダイアログ ボックス。  
  
     ![SQL Server ログイン画面](../technical-guides/media/sqlserver2008r2-loginscreen.gif "SQLServer2008R2 Loginscreen")  
  
2.  **サーバー名**のボックスの編集、**サーバーへの接続** ダイアログ ボックスで、BizTalk Server メッセージ ボックス データベースを格納する SQL Server インスタンスの名前を入力し、をクリックして**の接続**を SQL Server Management Studio を表示します。 **オブジェクト エクスプ ローラー** SQL Server Management Studio でのウィンドウが展開**データベース**を SQL Server のこのインスタンスのデータベースを表示します。  
  
     ![SQL Server 2005 Management Studio、オブジェクト エクスプ ローラー](../technical-guides/media/81f13912-fedc-48c3-9669-c18863e637b1.gif "81f13912-fedc-48c3-9669-c18863e637b1")  
  
3.  クリックして、ファイルを追加するデータベースを右クリックして**プロパティ**を表示する、**データベース プロパティ**データベース用のダイアログ ボックス。  
  
     ![SQL Server 2005 データベースのプロパティ ダイアログ ボックス](../technical-guides/media/82ae7c11-5b3a-4312-876c-70876abdd65c.gif "82ae7c11-5b3a-4312-876c-70876abdd65c")  
  
4.  **データベース プロパティ**ダイアログ ボックスで、**ファイル グループ**ページ。 BizTalkMsgBoxDb データベースの追加のファイル グループを作成する をクリックして**追加**します。 次の例では、次の 3 つの追加のファイル グループが追加されます。  
  
     ![SQL Server 2005、データベース ファイル グループに追加する](../technical-guides/media/6be47c0e-06c3-45d9-bce2-a42453da7d19.gif "6be47c0e-06c3-45d9-bce2-a42453da7d19")  
  
5.  **[データベースのプロパティ]** ダイアログ ボックスで、 **[ファイル]** ページをクリックします。  
  
     ファイル グループに追加するファイルを作成する をクリックして**追加**、 をクリックし、 **OK**。 メッセージ ボックス データベースがパフォーマンスに大きな利点は、1 つのディスク構成を提供する複数のディスクで配布ようになりました。  
  
     次の例では、以前に作成されたファイル グループの各ファイルが作成し、各ファイルが別のディスク上に配置します。  
  
     ![SQL Server 2005、ファイルをファイル グループに追加する](../technical-guides/media/d5d5c5df-d483-4f01-8128-f98228de51b9.gif "d5d5c5df-d483-4f01-8128-f98228de51b9")  
  
## <a name="sample-sql-script-for-adding-filegroups-and-files-to-the-biztalk-messagebox-database"></a>BizTalk メッセージ ボックス データベースにファイル グループとファイルを追加するためのサンプル SQL スクリプト  
 このガイドには、BizTalk Server メッセージ ボックス データベースにファイル グループとファイルの追加の SQL スクリプトが含まれています。  
  
> [!NOTE]  
>  SQL Server のログ ファイルに書き込むと順番に、ために、SQL Server データベースの複数のログ ファイルを作成することに気付きましたパフォーマンス上の利点はありません。  
  
 このスクリプトを実行するには、次の手順を実行します。  
  
1. 開いている**SQL Server Management Studio**を表示する、**サーバーへの接続** ダイアログ ボックス。  
  
2. **サーバー名**のボックスの編集、**サーバーへの接続** ダイアログ ボックスで、BizTalk Server メッセージ ボックス データベースを格納する SQL Server インスタンスの名前を入力し、をクリックして**の接続** SQL Server Management Studio のダイアログ ボックスを表示します。  
  
3. SQL Server Management studio でをクリックして、**ファイル**メニューで、**新規**、順にクリックします**現在の接続を使用したクエリ**SQL クエリ エディターを起動します。  
  
4. サンプル スクリプトをコピー [BizTalk Server メッセージ ボックス データベースのファイル グループの SQL スクリプト](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)をクエリ エディターにします。  
  
5. 、BizTalk Server 環境に合わせてスクリプト内のパラメーターを編集し、スクリプトを実行します。  
  
   スクリプトの利点は、スクリプトに複数のタスクをすばやく実行することができますし、正確に再現することができ、人的ミスの可能性を減らすことです。 スクリプトの欠点は、スクリプトが正しく記述の実行が最初から再度構成する BizTalk Server データベースが必要になる重大な問題になることができます可能性があります。  
  
> [!IMPORTANT]  
>  最も重要なの SQL スクリプトなど、このガイドのサンプル スクリプトは、運用環境で実行する前に徹底的にテストのことです。  
  
## <a name="see-also"></a>参照  
 [データベース パフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)