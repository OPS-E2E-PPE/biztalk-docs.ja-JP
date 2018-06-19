---
title: インストールして、BizTalk Server で使用する HYPER-V 仮想マシンの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86add392-3cde-432d-95d6-c81d68716537
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b973053d3afa9c6d0b61de111d9da1c4fb7a0fb1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010971"
---
# <a name="installing-and-configuring-a-hyper-v-virtual-machine-for-use-with-biztalk-server"></a>インストールして、BizTalk Server で使用する HYPER-V 仮想マシンの構成
このトピックの内容をインストールして、HYPER-V 仮想マシンのインストールと構成に関する推奨事項を BizTalk Server をインストールするための推奨事項など、HYPER-V 環境で BizTalk Server の構成に関する推奨事項を提供する、HYPER-V バーチャル マシンです。  
  
## <a name="installing-and-configuring-hyper-v"></a>インストールして、HYPER-V を構成します。  
 HYPER-V をインストールする前に、次を参照してください。 [Windows Server 2008 R2 で Hyper-v の新](http://go.microsoft.com/fwlink/?LinkID=202427)です。 "Microsoft HYPER-V Server 2008 R2 Getting Started"を説明し、インストールして構成する方法の詳細について[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]HYPER-V です。 このガイドでは[http://go.microsoft.com/fwlink/?LinkID=202431](http://go.microsoft.com/fwlink/?LinkID=202431)です。  
  
 「Windows Server 2008 R2 のパフォーマンス チューニング ガイドライン」のドキュメントは、チューニングに関する詳細を提供[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]Hyper-v 重点セクションが含まれています。 このドキュメントでは[http://go.microsoft.com/fwlink/?LinkID=202087](http://go.microsoft.com/fwlink/?LinkID=202087)です。  
  
### <a name="hyper-v-platform-prerequisites"></a>HYPER-V プラットフォームの前提条件  
 HYPER-V は 64 ビットおよびすべてのエディションの使用可能なサーバーの役割[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]は 64 ビットのみです。 また、物理ハードウェアがハードウェア支援による仮想化をサポートする必要があります。 つまり、プロセッサは、Intel バーチャライゼーション テクノロジ (Intel VT) または AMD Virtualization (AMD-V) テクノロジと互換性のあるである必要があります、システム BIOS でデータ実行防止 (DEP) をサポートする必要があります、DEP を有効にする必要があります。 具体的には、Intel XD ビットを有効にする必要があります (execute disable bit) または AMD NX ビット (no execute bit)。  
  
> [!NOTE]  
>  システム BIOS でこれらのオプションを有効にした後に、完全にコンピューターをオフにしてこれらの設定が適用されていることを確認するコンピューターを再起動します。  
  
#### <a name="determining-hardware-requirements"></a>ハードウェア要件の決定  
 によりサーバーの統合の確認要求は、HYPER-V サーバーでは、複数の CPU やメモリを消費する傾向があり、比較可能なコンピューティングの読み込みを伴う物理サーバーよりも大きい値のディスク I/O 帯域幅を必要とします。 条件を満たしている環境をデプロイするのには、サーバーの正確なハードウェア要件を決定するのには、以下の要因を検討してください。  
  
##### <a name="storage-configuration-options"></a>記憶域構成オプション  
 十分な I/O 帯域幅と記憶域容量をホストする予定の仮想マシンの現在および将来のニーズを満たすために記憶域のハードウェアを提供します。 トレードオフがある容量の使用状況とを提供するパフォーマンスの HYPER-V の記憶域の構成を選択するときにします。  
  
 記憶域の構成を計画するときは、プロビジョニングする環境の要件を検討してください。 実稼働環境、実稼働前、および開発環境の要件が大きく異なる場合があります。  
  
 運用環境の HYPER-V での BizTalk Server 環境を展開する場合は、パフォーマンスが重要な要件になります。 ディスク使用中の実稼働システムで I/O の競合を避けるためには、ホストとゲストの両方のオペレーティング システムに統合サービスをインストールし、合成の SCSI コント ローラーとデータ ボリュームのディスクを構成します。 高負荷の高いストレージの I/O ワークロードの複数のデータ ドライブに配置されている場合に、全体的なパフォーマンスを向上させるため代理個別の SCSI コント ローラーに各 VHD をアタッチする必要があります。 さらに、各 VHD は、個別の物理ディスクに保存する必要があります。 データ ディスクの構成の詳細については、合成の SCSI コント ローラーでボリュームを参照してください「ディスクのパフォーマンスを最適化する」トピックの[チェックリスト: HYPER-V でのパフォーマンスの最適化](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)です。  
  
 通常、リソース使用率を最大化するメインの優先度傾向がありますので、開発環境には厳しいパフォーマンス要件はありません。 開発環境の 1 つの物理ドライブ上の複数の VHD ファイルをホストしているときに指定パフォーマンスは、通常は許容されます。  
  
 HYPER-V では、さまざまな種類の記憶域ディスク オプションをサポートします。 各ストレージ オプションは、コンピューターに、IDE または SCSI コント ローラーを使用して接続できます。 SCSI コント ローラーを使用して、IDE コント ローラー上の潜在的な利点は、ことのみが正しく機能するオペレーティング システムの統合コンポーネントの正しいバージョンは、ゲスト仮想マシンにインストールされている場合です。 これは、ゲスト オペレーティング システムに正しいオペレーティング システムの統合コンポーネントがインストールされていることを確認する簡単な方法です。  
  
> [!NOTE]  
>  以前のバージョンの Microsoft 仮想化テクノロジとは異なり、仮想 IDE コント ローラーまたは仮想 SCSI コント ローラーを使用してバーチャル ハード_ディスクにアクセスするときのパフォーマンスの違いはありません。  
  
 読み取り/書き込みアクティビティの処理を要する場合などをホストしている[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]固定バーチャル ハード ドライブ (VHD) ディスクのパフォーマンスの利点データベース、パススルー ディスク オプションを提供します。 パススルー オプションにより、物理ディスクに直接アクセスする仮想マシンと、ルート パーティション内の NTFS ファイル システムをバイパスするが、仮想ディスクを仮想マシンのスナップショットとクラスタ リングなどの特定の機能をサポートしていませんサポートしてください。 したがってマージナル パフォーマンス上の利点は、複数の不足している機能のオフセットために、BizTalk または SQL Server 環境でパススルー ディスクの機能の使用は推奨されません。  
  
 次の表では、長所と短所の使用可能な HYPER-V の記憶域オプションをまとめたものです。 します。  
  
|**HYPER-V の記憶域の種類**|**担当者**|**短所**|**BizTalk Server に関する考慮事項**|  
|-------------------------------|--------------|--------------|-------------------------------------------|  
|**容量固定のディスク**|物理ハード ドライブに作成されたときに、VHD ファイルはその最大サイズに初期化されるためより容量可変の VHD を実行します。<br /><br /> これにより断片化小さい可能性があり、したがって、1 つの I/O が複数の I/o を分割のシナリオを軽減できます。 これは、読み取りと書き込みが、ブロックのマッピングを検索する必要はないために、VHD の種類の最小の CPU のオーバーヘッドです。|最初に必要なディスク領域の全容量の割り当てが必要です。|オペレーティング システムのボリュームを使用で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 **重要:** HYPER-V ゲストのパーティションの起動ディスクは、IDE コント ローラーに接続する必要があります。|  
|**容量可変の拡張ディスク**|VHD ファイルのサイズより多くのデータが、仮想マシン自体に格納されている、ディスクを作成するときに、指定したサイズに増加します。 これには、最も効率的に使用可能記憶域の使用が対応しています。|固定サイズの VHD およびは実行されません。 これは、ディスク内のブロックがゼロのブロックとして開始、VHD ファイル内の実際の領域でバックアップされていないためです。 このようなブロックの戻り値から、ゼロのブロックを読み取ります。 ブロックが最初に書き込まれ、仮想化スタック必要がありますブロックに VHD ファイル内の領域を割り当てる、対応するメタデータを更新します。 これだけでなく既存のブロックが参照されるたびにブロック マッピングする必要がありますで検索することメタデータ。 読み取りの数が増加し、これにより、さらに書き込み活動は、CPU 使用率を向上します。<br /><br /> 動的な増加には、サーバーの管理者が記憶域の要件の増大として十分なディスクの記憶域があることを確認するディスク容量を監視することも必要です。|固定サイズの VHD およびは実行されません。<br /><br /> パフォーマンス問題がない場合は、インスタンスの開発環境でこれがありますにオペレーティング システムのハード ドライブの最適なオプション。<br /><br /> ブロック マッピング参照により追加の CPU オーバーヘッドが発生します。|  
|**差分ディスク**|これは、差分ディスクが、ベース VHD とベース VHD に関連のすべての変更を保存する場所、親子構成は静的です。 したがっては親と異なるブロックだけでは、差分 VHD の子に格納する必要があります。|読み取り/書き込みは、固定/動的親 VHD と差分ディスクにアクセスする必要があるために、パフォーマンスが低下することができます。 これは、CPU 使用率とディスク I/O のオーバーヘッドが増加します。|大量のマシン固有の設定は BizTalk Server のインストールに必要なと子の VHD ファイルはこのディスク構成を使用する利点を最小限に抑えるが大幅になることがあります。 このシナリオでの複数の VHD からの読み取りは、追加の CPU とディスク I/O のオーバーヘッドが生じます。|  
|**パススルー ディスク**|これらは、物理ディスクに設定されている*オフライン*ルート パーティションと読み取り/書き込みを排他的に物理ディスクにアクセスするには、有効にする HYPER-V にします。|仮想マシンに割り当てられるために、完全に専用のディスクまたは LUN が必要です。<br /><br /> 物理ディスクは、VHD ファイルよりもコンピューター間で移動することは困難です。|場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスが、HYPER-V で実行されている、BizTalk Server のデータ ボリュームの固定容量仮想ハード_ディスク (VHD) を使用する場合よりパススルー ディスクを使用して増分パフォーマンスの向上を取得することがあります。<br /><br /> ローカル ファイルをホストしている場合は、BizTalk Server 上の場所を受信またはを処理中にディスク サイズの大きいメッセージをストリーミングするには、固定容量仮想ハード_ディスク (VHD) を使用するパススルー ディスクを使用して増分パフォーマンスの向上を取得することがあります。|  
  
 ディスクと hyper-v の記憶域の実装の詳細については、次を参照してください。[を実装するディスクおよび記憶域](http://go.microsoft.com/fwlink/?LinkID=142362)(http://go.microsoft.com/fwlink/?LinkID=142362)。  
  
##### <a name="networking"></a>ネットワーク  
 BizTalk Server は、高いネットワーク使用率が発生する傾向があります。 したがって、ネットワークのパフォーマンスに問題がある場合は、仮想マシンごとに別個の物理ネットワーク カードを割り当てることを検討します。  
  
 仮想マシンを構成する場合は、レガシ ネットワーク アダプターではなく、ネットワーク アダプターを使用することを確認します。 レガシ ネットワーク アダプターは、統合コンポーネントをサポートしないオペレーティング システム向けです。  
  
 ネットワーク パフォーマンスの使用状況を測定する、 **"\Network インターフェイス \Bytes total/sec"** と**\Network インターフェイス (\*) \Output Queue Length**ホスト オペレーティングにパフォーマンス モニター カウンターネットワーク カードの全体的なパフォーマンスを測定するシステムです。 物理ネットワークが使用中として識別される場合を使用して、 **"\Hyper-V 仮想ネットワーク アダプター (\*) \Bytes/sec"** どのバーチャル マシン ネットワーク アダプターを識別する、ホスト オペレーティング システムのカウンターは、高負荷を生成しています。  
  
 HYPER-V 環境でネットワーク パフォーマンスの評価の詳細については、次を参照してください。、**ネットワーク パフォーマンスの測定**のセクション[チェックリスト: Hyper-v でのパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)です。  
  
##### <a name="cpu"></a>CPU  
 HYPER-V は、さまざまなゲスト オペレーティング システムの仮想プロセッサの数が異なるをサポートしています次の表にまとめるとおりです。 BizTalk Server の CPU リソースの最大値を割り当てることでインストール、[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]ゲスト オペレーティング システムは、仮想マシンあたり 4 つの仮想プロセッサをサポートします。  
  
 コンテキストの過度の切り替えを防ぐためにホスト オペレーティング システムが利用できる論理プロセッサにゲスト オペレーティング システムで仮想プロセッサの 1 対 1 の割り当てを構成します。 コンテキストの過度のプロセッサ間の切り替えがパフォーマンスの低下が発生します。 仮想プロセッサと論理プロセッサの割り当てに関する詳細については、トピックの「プロセッサのパフォーマンスを最適化する」セクションを参照して[チェックリスト: HYPER-V でパフォーマンスの最適化](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)です。  
  
 "\Hyper-V ハイパーバイザー論理 processor (_total)\\% の合計実行時間"のパフォーマンス モニター カウンターはすべてのゲスト マシンと HYPER-V ホスト上のハイパーバイザーの全体的なリソース使用率を測定します。 最大容量です。 サーバーが実行されている場合、この値は、90% 以上が、このシナリオで仮想マシンに割り当ての追加仮想プロセッサでは、システム全体のパフォーマンスが低下することができ、避ける必要があります。 HyperV のパフォーマンス カウンターの使用の詳細については、次を参照してください。、 [Hyper-v 上の BizTalk サーバー パフォーマンスの評価](../technical-guides/evaluating-biztalk-server-performance-on-hyper-v.md)このガイドの「します。  
  
|オペレーティング システム|仮想プロセッサ数の上限|  
|----------------------|-----------------------------|  
|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]」をご覧ください。 すべてのエディション[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]は 64 ビットのみです。|4|  
|[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]64 ビット|4|  
|[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]32 ビット|4|  
|Windows 7 64 ビット|4|  
|Windows 7 32 ビット|4|  
|Windows Vista 64 ビット|2|  
|Windows Vista 32 ビット|2|  
  
> [!NOTE]  
>  HYPER-V でサポートされているゲスト オペレーティング システムの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=118347](http://go.microsoft.com/fwlink/?LinkID=118347)です。  
  
##### <a name="memory"></a>[メモリ]  
 物理サーバーでは、ルート パーティションと、サーバーで実行されているすべてのバーチャル マシンのための十分なメモリが必要です。 テスト中に、2 GB のメモリの最小値は、ルート パーティションに割り当てられた、**メモリ/利用可能領域のメガバイト数**パフォーマンス モニター カウンターを監視したメモリ不足が発生しましたないことを確認します。  
  
 BizTalk Server 環境では、各仮想マシンに割り当てる必要があるメモリの量は、ワークロードによって異なります、処理の種類が行われます。 これには多くの要因に影響を与えるような BizTalk Server のメモリ要件があります。  
  
-   処理されるメッセージのサイズ  
  
-   メッセージのスループット  
  
-   オーケストレーションのデザイン  
  
-   パイプライン処理  
  
-   仮想マシン内で実行しようとする BizTalk ホストの数  
  
 メモリに影響する要因の包括的な一覧で BizTalk Server のパフォーマンス最適化ガイド 』 の「パフォーマンスの要因」セクションを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=122587](http://go.microsoft.com/fwlink/?LinkId=122587)です。  
  
 事前対応的に監視、**メモリ/利用可能領域のメガバイト数**各仮想マシンと、ルート パーティション自体内からカウンターです。 次のガイドライン[チェックリスト: HYPER-V でのパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)に十分な物理メモリ、仮想マシンと、ルート パーティションがあるかどうかを判断するために使用する必要があります。  
  
-   使用可能な空きメモリの 50% より = 正常または  
  
-   使用可能な空きメモリの 25% = モニター  
  
-   使用可能な空きメモリの 10% = 警告  
  
-   使用可能な空きメモリの 5% 未満 ="重大"、パフォーマンスが悪影響を受ける  
  
#### <a name="choosing-root-operating-system-version"></a>ルートのオペレーティング システムのバージョンを選択します。  
 Server Core とフル インストールに HYPER-V がサポートされている[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]です。 ルート パーティションのオーバーヘッドを最小限に抑えるには、Server Core インストールに HYPER-V をインストール[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]です。 HYPER-V の役割は、別のシステムで HYPER-V マネージャーからリモートで管理できます。 Server Core では、仮想マシンで使用できる多くのリソースを残して、小さいディスクとメモリ プロファイル、したがってを提供します。 詳細については、Server Core インストール オプションの使用可能な[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]を参照してください[http://go.microsoft.com/fwlink/?LinkID=202439](http://go.microsoft.com/fwlink/?LinkID=202439)です。  
  
 完全インストールを使用する場合[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]、HYPER-V サーバー ロールにのみ、ルート パーティションは専用のことを確認してください。 追加のサーバー役割を実行しているメモリ、ディスク、プロセッサ、およびネットワーク リソースを消費し、パフォーマンスが低下します。  
  
#### <a name="creating-your-virtual-machines"></a>仮想マシンを作成します。  
 インストールし、HYPER-V サーバーの役割を構成したが後、は、仮想マシンを作成する必要があります。 これを行う前に、次の質問に答える便利です。  
  
-   どのような記憶域の構成が使用されますか。  
  
-   ゲスト オペレーティング システムは仮想プロセッサの数をサポートしますか。  
  
-   メモリの量は、仮想マシンに割り当てられるか。  
  
-   仮想マシンの数、HYPER-V サーバーで実行できますか  
  
-   コンピューターにオペレーティング システムをインストールする方法は?  
  
 作成して、仮想マシンを構成する方法の詳細については、次を参照してください。[仮想マシンを作成](http://go.microsoft.com/fwlink/?LinkID=202440)です。  
  
##### <a name="installing-the-base-operating-system"></a>ベースのオペレーティング システムをインストールします。  
 物理サーバー インストールで使用できるすべてのオプションは、HYPER-V で使用できます。 手動インストールを実行するのには、起動可能な CD または DVD-ROM メディアまたは ISO イメージを使用できます。 仮想マシンは、ISO イメージをホストするサーバーと同じネットワークに接続されたネットワーク アダプターで構成されている場合、ネットワークのインストールを実行できます。  
  
> [!IMPORTANT]  
>  HYPER-V で実行されている各仮想マシンのオペレーティング システムの統合コンポーネントをインストールする重要なパフォーマンス向上のため、どちらのインストール方法が選択されます。 統合コンポーネントは、一連のドライバーと統合デバイスを使用して実行するゲスト マシンを有効にするサービスを提供します。 統合デバイスは、エミュレートされたデバイスは、統合コンポーネントをサポートしないオペレーティング システムで使用する必要を避けるようにします。 エミュレートされたデバイスでは、統合デバイスと比較して大きくのシステム オーバーヘッドが発生します。  
  
 インストールして、このラボで使用するコンピューターの構成、初期の基本イメージは、固定サイズの VHD に作成されました。 手動インストールが関係しているこの[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]です。 すべての適切な更新プログラムがインストールされていたと基本の仮想マシン イメージを作成した %WINDIR%\system32\sysprep ディレクトリに、Windows Server 2008 と共にインストールされる sysprep ユーティリティを使用します。  
  
> [!NOTE]  
>  BizTalk Server をインストールし、サーバー上で構成した後、Sysprep を実行しているが、Sysprep 応答ファイルおよび BizTalk Server で提供するスクリプトを使用して実現できます。 これらのサンプル スクリプトが使用できるように設計にインストールされている BizTalk Server と[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]です。 詳細については、BizTalk Server のオンライン マニュアルを参照してください。  
  
## <a name="installing-and-configuring-biztalk-server"></a>BizTalk Server のインストールと構成  
  
-   仮想マシンをインストールに必要な時間を最小限に抑えるには、ゲスト オペレーティング システムとソフトウェアの前提条件のみで構成される基本イメージを作成します。 SysPrep を使用して、再利用するため、VHD イメージを準備し、基にしてこの VHD にすべての仮想マシン (Vm)。  
  
    > [!NOTE]  
    >  BizTalk Server では、基本イメージに対して Sysprep を実行すること*後*BizTalk Server がインストールされているし、サーバーで構成されています。 これは、Sysprep 応答ファイルおよび BizTalk Server で提供するスクリプトを使用して実現できます。 これらのサンプル スクリプトが使用できるように設計にインストールされている BizTalk Server と[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]です。 詳細については、BizTalk Server のオンライン マニュアルを参照してください。  
    >   
    >  Windows の無人セットアップ リファレンスについては、「 [http://go.microsoft.com/fwlink/?LinkId=142364](http://go.microsoft.com/fwlink/?LinkId=142364)です。  
  
-   次の推奨事項、「ときにインストールしを構成する BizTalk Server…」に 」の「[チェックリスト: インストールと Hyper-v での BizTalk Server 構成のベスト プラクティス](../technical-guides/checklist-best-practices-to-install-and-configure-biztalk-server-on-hyper-v.md)です。  
  
-   サポート状況について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 環境で、次を参照してください。[付録 c: BizTalk Server と SQL Server の Hyper-v でサポート性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)です。