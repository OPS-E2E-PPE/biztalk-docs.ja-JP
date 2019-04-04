---
title: インストールして、BizTalk Server で使用するため、HYPER-V 仮想マシンの構成 |Microsoft Docs
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
ms.openlocfilehash: 2c961b30fab2787426fe2f944b8721e5ddd23896
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630415"
---
# <a name="installing-and-configuring-a-hyper-v-virtual-machine-for-use-with-biztalk-server"></a>インストールして、BizTalk Server で使用するため、HYPER-V 仮想マシンの構成
このトピックをインストールして、BizTalk Server と HYPER-V 仮想マシンのインストールと構成について推奨事項を BizTalk Server をインストールするための推奨事項を含む、HYPER-V 環境の構成の推奨事項を提供します。HYPER-V 仮想マシン。  

## <a name="installing-and-configuring-hyper-v"></a>インストールと HYPER-V の構成  
 HYPER-V をインストールする前に、[Windows Server 2008 R2 で Hyper-v の新](http://go.microsoft.com/fwlink/?LinkID=202427)を参照してください。 「Microsoft HYPER-V Server 2008 R2 入門」ガイド インストールして構成する方法の詳細については、 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] HYPER-V。 このガイドは[ http://go.microsoft.com/fwlink/?LinkID=202431](http://go.microsoft.com/fwlink/?LinkID=202431)します。  

 「Windows Server 2008 R2 のパフォーマンス チューニング ガイドライン」のドキュメントの調整に関する詳細を提供する[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]具体的 Hyper-v 重点を置いてセクションにはが含まれています。 ドキュメントについては、「 [ http://go.microsoft.com/fwlink/?LinkID=202087](http://go.microsoft.com/fwlink/?LinkID=202087)します。  

### <a name="hyper-v-platform-prerequisites"></a>HYPER-V プラットフォームの前提条件  
 HYPER-V は 64 ビット版とのすべてのエディションの使用可能なサーバーの役割[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]は 64 ビットのみです。 また、物理ハードウェアでは、ハードウェア支援による仮想化をサポートする必要があります。 つまり、プロセッサは Intel Virtualization Technology (Intel VT) または AMD Virtualization (AMD-V) テクノロジと互換性がある、システム BIOS でデータ実行防止 (DEP) をサポートする必要があります、DEP を有効にする必要があります。 具体的には、Intel XD ビットが有効にする必要があります (execute disable bit) または AMD NX ビット (no execute bit)。  

> [!NOTE]  
>  システム BIOS でこれらのオプションを有効にした後、コンピューターの電源を完全に有効にして、これらの設定が適用されるようにするコンピューターを再起動します。  

#### <a name="determining-hardware-requirements"></a>ハードウェア要件の決定  
 サーバーの統合の確認要求のため、HYPER-V サーバーは、CPU とメモリを消費する傾向し、比較可能なコンピューティングの読み込みを伴う物理サーバーよりも大きい値のディスク I/O 帯域幅が必要です。 期待を満たす環境をデプロイするには、サーバーの正確なハードウェア要件を決定するのには、次の要因を検討してください。  

##### <a name="storage-configuration-options"></a>記憶域構成オプション  
 記憶域ハードウェアは、十分な I/O 帯域幅、ストレージ容量を開催を予定している仮想マシンの現在および将来のニーズを満たすためを提供する必要があります。 容量の使用状況と、パフォーマンスの間、HYPER-V の記憶域構成の選択はトレードオフが行われます。  

 記憶域の構成を計画するときは、プロビジョニングする環境の要件を検討してください。 運用環境、運用前、および開発環境の要件が大幅に異なる場合があります。  

 運用環境の HYPER-V での BizTalk Server 環境を展開する場合は、パフォーマンスが、重要な要件になります。 ディスクがビジー状態の実稼働システムで I/O の競合を避けるためには、ホストとゲストの両方のオペレーティング システム上の integration services のインストールし、代理の SCSI コント ローラーとデータ ボリュームのディスクを構成します。 複数のデータ ドライブにまたがる高負荷の高いストレージ I/O ワークロードでは、全体的なパフォーマンスを向上させる統合独立した SCSI コント ローラーに各 VHD をアタッチする必要があります。 さらに、各 VHD は、個別の物理ディスクに格納する必要があります。 合成の SCSI コント ローラーでボリュームをデータ ディスクの構成の詳細については、トピックの「ディスクのパフォーマンスを最適化する」セクションを参照してください[チェックリスト: hyper-v のパフォーマンスの最適化](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)します。  

 通常、メインの優先順位にする傾向があるリソース使用率を最大化するため、開発環境には厳しいパフォーマンス要件はありません。 開発環境は 1 つの物理ドライブ上の複数の VHD ファイルをホストするときに指定のパフォーマンスが通常は許容します。  

 HYPER-V には、さまざまな種類のストレージ ディスクのオプションがサポートしています。 マシンの各ストレージ オプション、IDE または SCSI コント ローラー経由で接続することができます。 SCSI コント ローラーを使用して、IDE コント ローラー上の潜在的な利点は、ことのみで正しく動作するオペレーティング システムの統合コンポーネントの正しいバージョンがゲスト仮想マシンにインストールされている場合です。 これは、ゲスト オペレーティング システムに正しいオペレーティング システムの統合コンポーネントがインストールされていることを確認する簡単な方法です。  

> [!NOTE]  
>  Microsoft 仮想化テクノロジの以前のバージョンとは異なり、仮想 IDE コント ローラーまたは仮想 SCSI コント ローラーを使用して仮想ハード_ディスクにアクセスするときのパフォーマンスの違いはありません。  

 集中型の読み取り/書き込みアクティビティのホストなど[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]固定仮想ハード ドライブ (VHD) のディスクのパフォーマンスの利点のデータベース、パススルー ディスクのオプションを提供します。 パススルー オプションにより、物理ディスクに直接アクセスする仮想マシンと、ルート パーティションで NTFS ファイル システムをバイパスするが、仮想ディスクを仮想マシンのスナップショットとクラスタ リングなどの特定の機能をサポートしていませんサポート。 したがってマージナル パフォーマンス上の利点が相殺機能不足しているために、BizTalk または SQL Server 環境でパススルー ディスクの機能の使用は推奨されません。  

 次の表は、長所と短所の使用可能な HYPER-V ストレージのオプションをまとめたものです。 します。  


|    **HYPER-V の記憶域の種類**     |  **プロフェッショナル**  |  **短所**  |  **BizTalk Server に関する考慮事項**  |
|---|---|----|---|
|      **容量固定のディスク**       | 物理ハード ドライブに作成されたとき、VHD ファイルがその最大サイズで初期化されるため、容量可変の VHD より良い成績を実行します。<br /><br /> これにより断片化小さい可能性があり、そのためが 1 つの I/O が複数の I/o に分割するシナリオを軽減できます。 読み取りと書き込みブロックのマッピングを検索する必要はないため、VHD の種類の最も低い CPU オーバーヘッドがあります。 |  完全なディスク領域の初期量の割り当てが必要です。  |  オペレーティング システム ボリュームをで使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 **重要:** HYPER-V ゲスト パーティションの起動ディスクは、IDE コント ローラーに接続する必要があります。  |
| **可変のディスク** |  VHD ファイルのサイズは、仮想マシン自体に多くのデータが格納されている、ディスクを作成するときに指定されたサイズに増加します。 これには、使用可能記憶域の最も効率的な使用が対応しています。 | 固定サイズの VHD とは実行されません。 これは、ディスク内のブロックがゼロのブロックとして起動、VHD ファイルにある実際の領域に基づいていないためです。 このようなブロックの戻り値からゼロのブロックを読み取ります。 ブロックが最初に書き込まれ、仮想化スタックする必要がありますブロックに VHD ファイル内の領域を割り当てるし、対応するメタデータを更新します。 これだけでなく既存のブロックが参照されるたび、ブロックのマッピングする必要がありますで検索メタデータ。 読み取りの数が向上し、結果、書き込みアクティビティは、CPU 使用率を増加します。<br /><br /> 動的な増加では、サーバーの管理者が記憶域の要件が増加のための十分なディスク記憶域があることを確認するディスク容量を監視することも必要です。 |  固定サイズの VHD とは実行されません。<br /><br /> パフォーマンスが重要でない場合は、たとえば、開発環境でことが考えられますオペレーティング システムのハード ドライブの最適なオプションです。<br /><br /> ブロックのマッピングの参照のための追加の CPU オーバーヘッドを発生します。   |
|     **差分ディスク**      | これは、差分ディスクが、ベース VHD とベース VHD の基準としたすべての変更を格納する場所、親子構成は変わりません。 したがって、親から異なるブロックだけは差分 VHD の子に格納される必要があります。  |  読み取り/書き込みは、固定/動的な親 VHD と差分ディスクにアクセスする必要があるために、パフォーマンスが低下することができます。 これは、CPU 使用率とディスク I/O のオーバーヘッドが増加します。  |  大量のマシン固有の設定は BizTalk Server のインストールに必要なと子 VHD ファイルはこのディスク構成を使用する利点を最小限に抑えるは大幅になることがあります。 このシナリオでの複数の VHD からの読み取りは、追加の CPU とディスク I/O オーバーヘッドが発生します。  |
|      **パススルー ディスク**      | これらは、物理ディスクに設定されている*オフライン*ルート パーティションと物理ディスクに排他読み取り/書き込みアクセスがある、HYPER-V を有効にします。  |  仮想マシンに割り当てるために、完全に専用のディスクまたは LUN が必要です。<br /><br /> 物理ディスクでは、VHD ファイルとマシン間を移動することは困難です。  | 場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスが、HYPER-V で実行されている、パススルー ディスクを使用して、BizTalk Server のデータ ボリュームの固定のバーチャル ハード_ディスク (VHD) を使用する場合より、増分のパフォーマンスの向上を取得することがあります。<br /><br /> ローカル ファイルをホストしている場合は、BizTalk Server 上の場所を受信または処理中にディスクにサイズの大きいメッセージをストリーミングするには、固定容量仮想ハード_ディスク (VHD) を使用するパススルー ディスクを使用して増分のパフォーマンスの向上を入手できます。 |

 ディスクと、HYPER-V と記憶域の実装の詳細については、[を実装するディスクとストレージ](http://go.microsoft.com/fwlink/?LinkID=142362)(http://go.microsoft.com/fwlink/?LinkID=142362)を参照してください。  

##### <a name="networking"></a>ネットワーク  
 BizTalk Server では、高いネットワーク使用率が発生する傾向があります。 そのため、ネットワークのパフォーマンスに問題がある場合は、仮想マシンごとに別個の物理ネットワーク カードを割り当てることを検討します。  

 仮想マシンを構成する場合は、レガシ ネットワーク アダプターではなく、ネットワーク アダプターを使用することを確認します。 レガシ ネットワーク アダプターは、統合コンポーネントをサポートしないオペレーティング システムを対象としています。  

 ネットワーク パフォーマンスの使用状況を測定する、 **"\Network インターフェイス \Bytes total/sec"** と **\Network Interface (\*)\Output Queue Length** 運用ホストにパフォーマンス モニター カウンターネットワーク カードの全体的なパフォーマンスを測定するシステムです。 物理ネットワークがビジー状態として識別されているが場合に、使用して、 **"\Hyper-V 仮想ネットワーク アダプター (\*) \Bytes/sec"** どのバーチャル マシン ネットワーク アダプターを識別するために、ホスト オペレーティング システムのカウンターは、高負荷を生成しています。  

 HYPER-V 環境でネットワーク パフォーマンスの評価の詳細については、、**ネットワーク パフォーマンスを測定する**のセクション[チェックリスト: Hyper-v のパフォーマンスを測定する](../technical-guides/checklist-measuring-performance-on-hyper-v.md)を参照してください。  

##### <a name="cpu"></a>CPU  
 HYPER-V は、さまざまなゲスト オペレーティング システムの仮想プロセッサの数が異なるをサポートしています次の表にまとめたようです。 BizTalk Server の CPU リソースの最大値を割り当てることでインストール、[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]ゲスト オペレーティング システムは、仮想マシンあたり 4 つの仮想プロセッサをサポートしています。  

 論理プロセッサが過剰なコンテキストの切り替えを防ぐために、ホスト オペレーティング システムを使用できるゲスト オペレーティング システムでは、仮想プロセッサの 1 対 1 の割り当てを構成します。 コンテキスト切り替えのプロセッサ間でパフォーマンスの低下が発生します。 仮想プロセッサと論理プロセッサの割り当てに関する詳細については、トピックの「プロセッサのパフォーマンスを最適化する」セクションを参照してください。[チェックリスト: hyper-v のパフォーマンスの最適化](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)します。  

 "\Hyper-V ハイパーバイザー論理 processor (_total)\\% の合計実行時間"パフォーマンス モニター カウンターは、すべてのゲスト マシンと HYPER-V ホスト上のハイパーバイザーの全体的なリソース使用率を測定します。 最大容量は; で、サーバーが実行されているこの値が 90% を超える場合は、このシナリオで仮想マシンに割り当ての追加仮想プロセッサは、システム全体のパフォーマンスが低下することができ、避ける必要があります。 HyperV のパフォーマンス カウンターの使用の詳細については、、[を評価する BizTalk Server のパフォーマンス、Hyper-v を](../technical-guides/evaluating-biztalk-server-performance-on-hyper-v.md)このガイドの「を参照してください。  


|  オペレーティング システム | 仮想プロセッサ数の上限 |
|---|---|
| [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 。 すべてのエディション[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]は 64 ビットのみです。 |            4            |
|  [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 64 ビット  |            4            |
|  [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 32 ビット  |            4            |
|  Windows 7 64 ビット  |            4            |
|  Windows 7 32 ビット  |            4            |
|  Windows Vista 64 ビット  |            2            |
|  Windows Vista 32 ビット  |            2            |

> [!NOTE]  
>  HYPER-V でサポートされているゲスト オペレーティング システムの詳細については、[ http://go.microsoft.com/fwlink/?LinkID=118347](http://go.microsoft.com/fwlink/?LinkID=118347)を参照してください。  

##### <a name="memory"></a>Memory  
 物理サーバーでは、ルート パーティションと、サーバーで実行されているすべてのバーチャル マシンのための十分なメモリが必要です。 テスト中に、2 GB のメモリの最小値は、ルート パーティションに割り当てられた、 **Mbytes**パフォーマンス モニター カウンターが監視され、メモリ不足が発生しないことを確認します。  

 BizTalk Server 環境では、各仮想マシンに割り当てる必要があるメモリの量が、ワークロードに依存し、処理の種類が行われます。 BizTalk Server などのメモリ要件に影響を与える多くの要素があります。  

- 処理されたメッセージのサイズ  

- メッセージのスループット  

- オーケストレーション デザイン  

- パイプライン処理  

- 仮想マシン内で実行する BizTalk ホストの数  

  メモリに影響する要因の包括的な一覧で BizTalk Server パフォーマンス最適化ガイドの「パフォーマンスの要因」セクションを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=122587](http://go.microsoft.com/fwlink/?LinkId=122587)します。  

  積極的に監視して、 **Mbytes**から各仮想マシンと、ルート パーティション自体内でカウンター。 次のガイドライン[チェックリスト: HYPER-V のパフォーマンスを測定する](../technical-guides/checklist-measuring-performance-on-hyper-v.md)十分なの物理メモリ、仮想マシンをルート パーティションがあるかどうかを判断するために使用する必要があります。  

- 使用可能な空きメモリの 50% 以上 = 正常  

- 使用可能な空きメモリの 25% = 監視  

- 空きメモリ 10% = 警告  

- 使用可能な空きメモリの 5% 未満 = 重大、パフォーマンスが悪影響を受ける  

#### <a name="choosing-root-operating-system-version"></a>ルート オペレーティング システムのバージョンを選択します。  
 HYPER-V が Server Core とフル インストールでサポートされている[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]します。 ルート パーティションのオーバーヘッドを最小限に抑えるには、Server Core インストールに HYPER-V をインストール[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]します。 HYPER-V の役割は、別のシステムで HYPER-V マネージャーからリモートで管理できます。 仮想マシンで使用できるその他のリソースを離れることより小さいディスクとメモリ プロファイルをそのための server Core に提供します。 詳細については、Server Core インストール オプションの使用可能な[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]を参照してください[ http://go.microsoft.com/fwlink/?LinkID=202439](http://go.microsoft.com/fwlink/?LinkID=202439)します。  

 フル インストールを使用する場合[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]、ルート パーティションが、HYPER-V サーバーの役割のみを行う、ことを確認します。 追加のサーバーの役割を実行しているメモリ、ディスク、プロセッサ、およびネットワーク リソースを消費し、パフォーマンスが低下します。  

#### <a name="creating-your-virtual-machines"></a>仮想マシンを作成します。  
 インストールされているが、HYPER-V サーバーの役割を構成して後、は、仮想マシンを作成する必要があります。 これを行う前に、次の質問に回答すると便利です。  

- どのような記憶域の構成が使用されますか。  

- ゲスト オペレーティング システムは仮想プロセッサの数をサポートしますか。  

- メモリの量は、仮想マシンに割り当てられるでしょうか。  

- 仮想マシンの数、HYPER-V サーバーで実行できますか。  

- コンピューターにオペレーティング システムをインストールする方法は?  

  作成して、仮想マシンを構成する方法の詳細については、[仮想マシンの作成](http://go.microsoft.com/fwlink/?LinkID=202440)を参照してください。  

##### <a name="installing-the-base-operating-system"></a>基本のオペレーティング システムをインストールします。  
 物理サーバーのインストールに使用できるすべてのオプションは、HYPER-V で使用できます。 起動可能な CD または DVD-ROM メディアまたは ISO イメージは手動インストールを実行するために使用できます。 仮想マシンが ISO イメージをホストするサーバーと同じネットワークに接続されているネットワーク アダプターに構成されている場合、ネットワーク インストールを実行できます。  

> [!IMPORTANT]  
>  HYPER-V で実行されている各仮想マシンのオペレーティング システムの統合コンポーネントをインストールする重要なパフォーマンス上の理由から、いずれのインストール方法が選択されます。 統合コンポーネントは、ドライバーとサービスを統合デバイスを使用して実行するゲスト マシンのセットを提供します。 統合デバイスは、統合コンポーネントをサポートしないオペレーティング システムで使用される、エミュレートされたデバイスの必要性を回避します。 エミュレートされたデバイスでは、統合デバイスと比較して大きいシステムのオーバーヘッドが発生します。  

 インストールし、このラボで使用するコンピューターの構成は、初期の基本イメージが固定サイズの VHD に作成されました。 手動でインストールする必要[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]します。 すべての適切な更新プログラムをインストールすると、ベースの仮想マシン %WINDIR%\system32\sysprep ディレクトリに、Windows Server 2008 と共にインストールされている sysprep ユーティリティを使用してイメージを作成されました。  

> [!NOTE]
>  Sysprep を実行している BizTalk Server にインストールされ、サーバーで構成した後は、Sysprep 応答ファイルおよび BizTalk Server に付属のスクリプトを使用して実現できます。 これらのサンプル スクリプトにインストールされている BizTalk Server で使用するために設計された[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]します。 詳細については、BizTalk Server のオンライン ドキュメントを参照してください。  

## <a name="installing-and-configuring-biztalk-server"></a>BizTalk Server のインストールと構成  

- 仮想マシンをインストールに必要な時間を最小限に抑えるには、ゲスト オペレーティング システムとソフトウェアの前提条件のみで構成される基本イメージを作成します。 SysPrep を使用して、再利用するため、VHD イメージを準備し、基にしてこの VHD に、すべての仮想マシン (Vm)。  

  > [!NOTE]
  >  BizTalk Server で、基本イメージに対して Sysprep を実行することが*後*BizTalk Server がインストールされ、サーバーで構成されています。 これは、Sysprep 応答ファイルおよび BizTalk Server に付属のスクリプトを使用して実現できます。 これらのサンプル スクリプトにインストールされている BizTalk Server で使用するために設計された[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]します。 詳細については、BizTalk Server のオンライン ドキュメントを参照してください。  
  > 
  >  無人 Windows セットアップのリファレンスについては、「 [ http://go.microsoft.com/fwlink/?LinkId=142364](http://go.microsoft.com/fwlink/?LinkId=142364)します。  

- 次の推奨事項、「ときにインストールおよび構成する BizTalk Server…」 」の「[チェックリスト: インストールすると、Hyper-v 上の BizTalk Server 構成のベスト プラクティス](../technical-guides/checklist-best-practices-to-install-and-configure-biztalk-server-on-hyper-v.md)します。  

- サポート状況について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 環境で、[付録 c: BizTalk Server と SQL Server、Hyper-v のサポート性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)を参照してください。
