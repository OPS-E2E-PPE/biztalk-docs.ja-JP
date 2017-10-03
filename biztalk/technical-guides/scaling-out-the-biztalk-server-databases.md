---
title: "スケール アウトは、BizTalk Server データベース |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18853ceb-7975-4c30-878f-6b162005f795
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3116b7aae087e74ade089c8020a7d35c883cd2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-out-the-biztalk-server-databases"></a>BizTalk Server データベースのスケール アウト
高可用性を実現する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、構成を実行している 2 台のコンピューター[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]または[!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]Windows クラスターでします。 これらのコンピューターは、アクティブ/アクティブ、アクティブ/パッシブまたはアクティブ/アクティブ/パッシブ (3 台のコンピューターが必要です) で実行できる冗長性の構成を共有ドライブ上のデータを格納できます (RAID など 1 + 0 SCSI ディスク アレイ) またはストレージ エリア ネットワーク (SAN)。  
  
 場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]何らかの理由でサービスが使用できなくなった、データベース クラスターは、リソースを active コンピューターからパッシブ側コンピューターに転送します。 このフェールオーバー処理中に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス インスタンスがデータベース接続エラーが発生し、データベースへの再接続を自動的に再起動します。 正常に動作しているデータベース コンピューター (先ほどまでパッシブ側であったコンピューター) が、フェールオーバーでリソースを引き継いだ後、データベース接続の処理を開始します。  
  
 クラスタ リング、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは、後ほど[BizTalk Server Databases2 をクラスタ リング](../technical-guides/clustering-the-biztalk-server-databases2.md)です。 このセクションでは、スケール アウト重点的、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを高可用性を提供します。  
  
## <a name="providing-high-availability-for-the-biztalk-messagebox-database"></a>BizTalk メッセージ ボックス データベースの高可用性を実現します。  
 このセクションを高可用性のための BizTalk メッセージ ボックス データベースを構成する情報を提供します。  
  
### <a name="running-multiple-messagebox-databases"></a>複数のメッセージ ボックス データベースの実行  
 スケーラビリティを強化するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースとアドレス CPU 使用率が高く、メッセージ ボックス データベースに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、コンピューターを構成できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を複数のメッセージ ボックス データベース間でデータを格納します。 最初のメッセージ ボックス データベースは、構成ウィザードの実行時に作成されます。 このメッセージ ボックス データベースは、マスターのメッセージ ボックス データベースです。 内の単一のマスター メッセージ ボックス データベースがある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。 マスターのメッセージ ボックス データベースは、マスターのサブスクリプション情報を含み、メッセージを適切なメッセージ ボックス データベースにルーティングします。 通常、する専用のルーティングのみを行うマスター メッセージ ボックス データベースに対して処理を実行して、他のメッセージ ボックス データベースを使用できます。 メッセージ ボックス データベースをルーティングのみを行うには、次のように選択します。**新しいメッセージの公開を無効にする**BizTalk 管理コンソールで、メッセージ ボックス プロパティです。  
  
 メッセージ ボックス データベースの処理フローの例は次のとおりです。  
  
1.  マスター メッセージ ボックス データベースが新しいアクティベーション メッセージを受信すると、ビジネス プロセスまたはサブスクリプションのメッセージの新しいインスタンス — マスター メッセージ ボックス データベースは、[次へ] の使用可能なメッセージ ボックス データベースにアクティブ化メッセージを配信します。 たとえば、1 つのマスター メッセージ ボックス データベースと 2 つのメッセージ ボックス データベースを使用する場合、マスター メッセージ ボックス データベースは、ラウンドロビン方式で、最初のアクティベーション メッセージをメッセージ ボックス データベース 1 に、2 つ目のアクティベーション メッセージをメッセージ ボックス データベース 2 に、3 つ目のアクティベーション メッセージをメッセージ ボックス データベース 1 に送信します。 マスターのメッセージ ボックス データベースでは、負荷分散のロジックを組み込んでいるので、追加の負荷分散メカニズムは必要ありません。  
  
2.  マスターのメッセージ ボックス データベースがアクティベーション メッセージを特定のメッセージ ボックス データベース (メッセージ ボックス データベース 1 など) に送信してから、ビジネス プロセスがメモリに読み込まれ、実行されます。  
  
3.  ビジネス プロセスには、メッセージに対して待機すると、待機時間は数秒以上、ビジネス プロセスはメッセージ ボックス データベース 1 に保存されます。 ビジネス プロセスは、関連メッセージを待機しています。  
  
4.  マスター メッセージ ボックス データベースで関連メッセージが到着すると、メッセージ エンジンが (この例では、メッセージ ボックス 1) で関連メッセージの状態を含むメッセージ ボックス データベースのデータベースでルックアップ操作を実行します。 マスター メッセージ ボックス データベースでは、ビジネス プロセスを含むメッセージ ボックス データベースにメッセージが配信されます。  
  
5.  ビジネス プロセスは、完了するまで、または別の関連メッセージを待機する必要がある処理を続行するメモリに戻さはします。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ストア、メッセージ ボックス データベース内のすべての状態および各メッセージ ボックス データベースには、さまざまなビジネス プロセスの状態情報が含まれています。 信頼性を確保するため、マスター メッセージ ボックス データベースおよびセカンダリ メッセージ ボックス データベースを含むすべてのメッセージ ボックス データベースをクラスター化する必要があります。  
  
 使用する複数のメッセージ ボックス データベースを構成するのには[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを実行しているコンピューターの追加を[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]または[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]です。 管理的には、新しいメッセージ ボックス データベースを追加する必要があるだけです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自動的にアクティベーション メッセージのラウンドロビン配信を処理し、正しいメッセージ ボックス データベースに関連付けられたメッセージを送信します。  
  
 環境内で複数のメッセージ ボックス データベースを構成する場合は、3 つのメッセージ ボックス データベースの最小値を作成する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループと、マスター メッセージ ボックス データベースでメッセージの公開を無効にする必要があります。 この推奨事項はメッセージ ボックス データベース間でメッセージのルーティング用のマスター メッセージ ボックス データベースによってオーバーヘッドが追加のメッセージ ボックス データベースを追加するためになります。 2 つのメッセージ ボックス データベースを構成するだけの場合、追加のメッセージ ボックス データベースによって得られる利点のほとんどは、メッセージのルーティングにマスター メッセージ ボックス データベースによって使用されるオーバーヘッドで相殺されます。  
  
> [!IMPORTANT]  
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ストア、メッセージ ボックス データベース内のすべての状態および各メッセージ ボックス データベースには、さまざまなビジネス プロセスの状態情報が含まれています。 信頼性を確保するため、マスター メッセージ ボックス データベースおよびセカンダリ メッセージ ボックス データベースを含むすべてのメッセージ ボックス データベースをクラスター化する必要があります。  
  
### <a name="providing-high-availability-for-multiple-messagebox-databases"></a>複数のメッセージ ボックス データベースの高可用性を実現する  
 メッセージ ボックス データベースを追加するときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開がスケーラビリティを向上させ、各メッセージ ボックス データベースで一意で独立したありの単一障害点になる可能性があるために、高可用性は提供しません、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 冗長性を拡張するには、各メッセージ ボックス データベースについてサーバー クラスターを構成します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのデータを共有またはしないサーバーがクラスター化されていない冗長性を提供するための複数のメッセージ ボックス データベース間でデータを配布します。  
  
## <a name="providing-high-availability-for-the-biztalk-tracking-database"></a>BizTalk 追跡データベースの高可用性を実現する  
 個別に BizTalk 追跡データベースを分離することによって追跡のパフォーマンスを強化するために、特定の展開の要件に応じてする可能性があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター別に作成する、ホストの追跡に専用の BizTalk ホストとします。 次の図は、2 つのホスト インスタンスおよびクラスター化されたデータベースを専用の追跡ホストの一覧です。  
  
 ![追跡データベースのスケール アウト](../technical-guides/media/4fc1d448-2a6c-4cea-ac17-96c1263dfb68.gif "4fc1d448-2a6c-4cea-ac17-96c1263dfb68")  
  
 追跡のオーバーヘッドが実行しているコンピューターで多くのリソースを消費可能性がある場合は、展開には高いスループットがあり、これらのメッセージのデータの大量に追跡、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 このような状況が発生し、受信メッセージの率が高いが引き続き発生する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を処理できない新着メッセージを追跡するために必要なリソースが、他の実行に必要なリソースを超えているため、ポイントに達すると[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネント (メッセージを受信して、それらをメッセージ ボックス データベースに保存する) などです。  
  
 パフォーマンスとセキュリティを向上させるのには、その他の項目 (受信場所、オーケストレーション、パイプラインなど) を含まない追跡ホスト専用の使用してを処理、および送信ホスト、受信からの追跡を無効にすることを勧めします。 追跡ホストの高可用性を実現するには、追跡ホストの複数のインスタンスを作成します。 追跡ホストの作成の詳細については、次を参照してください。[を新しいホストを作成する方法](http://go.microsoft.com/fwlink/?LinkId=156825)(http://go.microsoft.com/fwlink/?LinkId=156825) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、各メッセージ ボックス データベースについて追跡ホスト インスタンスを 1 つだけ使用し、メッセージ ボックス データベースから BizTalk 追跡データベース (BizTalkDTADb) にメッセージを移動します。 追加のコンピューター、追跡ホストのインスタンスを実行する場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡ホストの別のインスタンスには、各メッセージ ボックス データベースの処理を自動的にスケールを設定します。 メッセージ ボックス データベースの数が追跡ホストのインスタンスの数よりも多くなった場合は、1 つまたは複数の追跡ホストのインスタンスが、複数のメッセージ ボックス データベースに対するサービスを提供します。  
  
 BizTalk 追跡データベースの高可用性を実現するを使用して Windows クラスタ リングを実行している 2 つのデータベース コンピューターを構成する[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]または[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]アクティブ/パッシブ構成にします。  
  
## <a name="providing-high-availability-for-the-bam-databases"></a>BAM データベースの高可用性を実現する  
 *ビジネス アクティビティ監視*(BAM) は、IT の実装のや異種 IT 実装間で独立したビジネス プロセスの可視性を提供します。 BAM[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース (BAM スター スキーマ データベース、BAM プライマリ インポート データベース、および BAM アーカイブ データベース) および BAM 分析データベースが運用の監視データとは異なるビジネス アクティビティ データを格納します。 次の図は、BAM データベースのインフラストラクチャです。  
  
 ![BAM データベースのインフラストラクチャ](../technical-guides/media/769c3b7c-fe16-4260-967e-6af003c4f08d.gif "769c3b7c-fe16-4260-967e-6af003c4f08d")  
  
 BAM インフラストラクチャの高可用性を確保するには、次の手順を実行します。  
  
-   **BAM プライマリ インポート データベースおよび BAM 分析データベースをクラスタです。** BAM プライマリ インポート データベースは、ビジネス アクティビティ監視システムの中心です。 このため、Windows クラスタリングを使用してこのデータベースの高可用性を実現し、次の 2 つの推奨方法に従ってこのデータベースがいっぱいになるのを防ぐことが重要です。 BAM 分析データベースは、ビジネス アナリストがアクティビティの集計や OLAP キューブの構築に使用するデータを格納する Analysis Services データベースです。このため、このデータベースのダウンタイムは、生産性に影響します。 BAM アーカイブ データベースをクラスターにはない、ことをお勧め、SQL Server Integration Services (SSIS) パッケージの実行をデータが正常に転送されるかどうかを確認し、データベースのサイズを監視するときに、イベント ログでエラーを監視します。置き換えることができます、前に、塗りつぶしをします。  
  
-   **オンライン ウィンドウを定義します。** パフォーマンス向上のための許可を回避するためダウンタイム、BAM のパーティション、BAM プライマリ インポート データベース内のデータをアクティビティが完了した時点のタイムスタンプに基づいてテーブルにします。 BAM は、完了したテーブルと同一フォーマットの空のテーブルを定期的に交換して、この機能を実現します。 BAM がこの処理を行った後、BAM は、オンライン ウィンドウに定義されている期間、古いパーティションを保存します。また、追加の完了したアクティビティは、新しいパーティション (テーブル) に格納されます。 BAM プライマリ インポート データベースのパーティション数が大きくなりすぎないように、オンライン ウィンドウを定義する必要があります。 オンラインの windows のスケジュール設定に関する詳細については、次を参照してください。[プライマリ インポート データベースのデータのアーカイブ](http://go.microsoft.com/fwlink/?LinkId=156826)(http://go.microsoft.com/fwlink/?LinkId=156826) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
-   **SSIS パッケージを定期的に実行するスケジュールを設定します。** オンライン ウィンドウを定義することにより、古いアクティビティのパーティションで BAM プライマリ インポート データベースがいっぱいになる状態を回避できます。 また、アクティビティ データに対する新しいパーティションを作成して、BAM プライマリ インポート データベースの古いパーティションから BAM アーカイブ データベースにデータを移動する、定期的に実行する SSIS パッケージをスケジュールする必要があります。 SSIS パッケージのスケジュール設定の詳細については、次を参照してください。 [SQL Server Integration Services のパッケージをスケジュール](http://go.microsoft.com/fwlink/?LinkId=156827)(http://go.microsoft.com/fwlink/?LinkId=156827) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
-   **慎重にデータ項目 (チェックポイント) の小さなセットを選択し、アクティビティを定義するときに不要なデータ項目が含まれないようにします。**  
  
-   **スケジュールされたスキャンとリアルタイムの集計、集計をデザインするときに間のトレードオフを理解します。** リアルタイム集計はによって自動的に維持[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]待機時間ゼロとトリガーされます。 一部のミッション クリティカルな待機時間の短いシナリオに最適ですが、パフォーマンス イベントが BAM プライマリ インポート データベースに書き込まれているときにコストが発生します。 スケジュール済みの集計は、その集計データを更新するキューブの SSIS パッケージをスケジュールに依存します。 それらの遅延時間は、SSIS スケジュールの間隔以上が全体的なパフォーマンスの影響は小さく、BAM プライマリ インポート データベースであります。  
  
-   **スケジュール済みの集計を選択する場合は、キューブ SSIS アーカイブ SSIS よりも頻繁に実行をスケジュールすることを確認してください。** アーカイブの SSIS が BAM アーカイブ データベースにスケジュール済みの集計が処理されるアクティビティ データを移動しないためにです。  
  
-   **フェールオーバー機能を取得する複数のコンピューターで BAM イベント バス サービスを有効にします。**  
  
## <a name="providing-high-availability-for-the-other-biztalk-server-databases"></a>他の BizTalk Server データベースの高可用性を実現する  
 他の高可用性を実現する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、構成を実行している 2 台のコンピューター[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]または[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]Windows クラスターでします。 これらのコンピューターは、冗長性では、アクティブ/アクティブまたはアクティブ/パッシブ構成で実行できるし、共有ドライブ上のデータを格納できます (など、RAID 1 + 0 SCSI ディスク アレイ) またはストレージ エリア ネットワーク (SAN)。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server Databases2 をクラスタ リング](../technical-guides/clustering-the-biztalk-server-databases2.md)