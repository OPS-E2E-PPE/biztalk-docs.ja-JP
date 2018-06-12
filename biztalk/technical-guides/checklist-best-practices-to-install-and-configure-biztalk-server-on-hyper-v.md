---
title: 'チェックリスト: HYPER-V をインストールして構成するベスト プラクティス |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b5ddbb5-3752-4294-ae6a-c14363b3ddc9
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb6f268a532eec3c633197320abb99fff563063b
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34849002"
---
# <a name="checklist-best-practices-for-installing-and-configuring-biztalk-server-on-hyper-v"></a>インストールして、HYPER-V の BizTalk Server を構成するためのベスト プラクティスのチェックリスト:
以下のセクションでは、インストールの概要と、構成の要件、 [HYPER-V 上の BizTalk Server の展開](../technical-guides/deploying-biztalk-server-on-hyper-v.md)このガイドの「します。 これらのインストール、構成および展開するときに、クイック リファレンスとして使用する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 環境でします。 詳細については、関連するセクションへのリンクが提供されます。  
  
## <a name="before-installing-hyper-v"></a>前に、HYPER-V をインストールしています.  
  
|手順|リファレンス|  
|----------|---------------|  
|HYPER-V では、Windows Server の 64 ビット エディションの使用可能なサーバー ロールです。|参照してください[チェックリスト: をインストールして、HYPER-V の BizTalk Server を構成するためのベスト プラクティス](../technical-guides/checklist-best-practices-to-install-and-configure-biztalk-server-on-hyper-v.md)|  
|プロセッサがハードウェア依存の仮想化し、データ実行防止 (DEP) をサポートしていると、これらの機能が有効になっていることを確認します。 これには、Intel バーチャライゼーション テクノロジ (Intel VT) または AMD Virtualization (AMD-V) と互換性があるプロセッサが必要です。|参照してください[HYPER-V の役割をインストール](https://docs.microsoft.com/windows-server/virtualization/hyper-v/get-started/install-the-hyper-v-role-on-windows-server)です。|  
|ルート パーティション用の Windows Server Core Edition を使用します。 サーバーのオーバーヘッドを最小限に抑える、HYPER-V は、パフォーマンスが向上します。|参照してください[Server Core のインストール](https://docs.microsoft.com/windows-server/get-started/getting-started-with-server-core)です。|  
|ルート パーティションにのみ、Hyper-v サーバーの役割を実行します。|参照してください[パフォーマンス チューニングの HYPER-V サーバー](https://docs.microsoft.com/windows-server/administration/performance-tuning/role/hyper-v-server/):<br />**専用サーバー ロール**<br />ルート パーティションを専用の仮想化サーバーの役割にする必要があります。 追加のサーバー役割に悪影響を与える、仮想化サーバーのパフォーマンス大幅な CPU、メモリ、または I/O 帯域幅を使用する場合に特にです。 ルート パーティション内のサーバー ロールを最小限に抑えると、攻撃や更新の頻度を減らすことなどの他の利点があります。 システム管理者は、ルート パーティションにどのようなソフトウェアがインストールされているため、一部のソフトウェア仮想化サーバーの全体的なパフォーマンスに悪影響慎重に検討する必要があります。<br/><br/> 参照してください[HYPER-V 構成](https://docs.microsoft.com/windows-server/administration/performance-tuning/role/hyper-v-server/configuration)のガイダンスについてはします。|  
  
## <a name="when-creating-hyper-v-virtual-machines"></a>HYPER-V の仮想マシンを作成するときにしています.  
  
|手順|リファレンス|  
|----------|---------------|  
|固定サイズの仮想ハード_ディスクを使用して (VHD) は、オペレーティング システム ドライブの Vhd を動的にサイズ変更と比較してパフォーマンスの向上を提供します。|参照してください[HYPER-V 記憶域の I/O パフォーマンス](https://docs.microsoft.com/windows-server/administration/performance-tuning/role/hyper-v-server/storage-io-performance)のガイダンスについては。 <br />**固定サイズの VHD**<br />VHD のスペースは最初に、VHD ファイルが作成されるときに割り当てられました。 この種類の VHD は、1 つの I/O が複数の I/o に分割すると、I/O スループットを減らすこと、フラグメント化する傾向です。 読み取りと書き込みが、ブロックのマッピングを検索する必要はないために、VHD の 3 種類の最小の CPU のオーバーヘッドがあります。|  
|頻繁なディスク I/O アクティビティに固定サイズの仮想ハード ドライブ (VHD) のディスクを使用して、SCSI コント ローラーを使用して、データ ボリュームのディスクを構成します。 高負荷の高いストレージの I/O ワークロードの複数のデータ ドライブに配置されている場合に、全体的なパフォーマンスを向上させるため代理個別の SCSI コント ローラーに各 VHD をアタッチする必要があります。 さらに、各 VHD は、個別の物理ディスクに保存する必要があります。|参照してください[HYPER-V 記憶域の I/O パフォーマンス](https://docs.microsoft.com/windows-server/administration/performance-tuning/role/hyper-v-server/storage-io-performance)のガイダンスについては。<br />**統合 SCSI コント ローラー**<br />統合記憶域コント ローラーは、エミュレートされた IDE デバイスよりも CPU のオーバーヘッドを削減によるストレージの I/o でパフォーマンスが著しく向上を提供します。 VM 統合サービスは、この記憶域デバイスの有効化されたドライバーが含まれてし、ゲスト オペレーティング システムで検出するために必要なです。 正常に起動するオペレーティング システムの IDE デバイスにオペレーティング システム ディスクをマウントする必要がありますが、VM 統合サービスが代理記憶装置に IDE デバイスの I/o に再ルーティングするフィルター ドライバーをロードします。<br />その構成には、CPU のオーバーヘッドが少なくなっているために、合成の SCSI コント ローラーに直接データ ドライブをマウントすることを強くお勧めします。 必要な I/O 率が高い場合もログ ファイルと合成の SCSI コント ローラーに直接オペレーティング システムのページング ファイルをマウントする必要があります。<br />高負荷の高いストレージの I/O ワークロードの複数のデータ ドライブに配置されている場合に、全体的なパフォーマンスを向上させるため代理個別の SCSI コント ローラーに各 VHD をアタッチする必要があります。 さらに、各 VHD は、個別の物理ディスクに保存する必要があります。|  
|SQL Server データ ファイルとログ ファイルの高い I/O アクティビティ VHD ディスクをアタッチするのにには、SCSI コント ローラーを使用します。 **注:** SCSI コント ローラーのシステム ディスクをアタッチできません。 IDE コント ローラーには、オペレーティング システムを含むバーチャル ハード ディスクをアタッチする必要があります。|HYPER-V は、IDE コント ローラーと SCSI コント ローラーと同等のパフォーマンスを提供して、場合でも、SCSI コント ローラーのみインストールできます HYPER-V 統合サービスがインストールされている場合。 したがって、パススルー ディスクをアタッチする、SCSI コント ローラーの使用では、HYPER-V 統合サービスがインストールされている必要がさらに、最適なディスク I/O パフォーマンスを確認します。|  
|仮想マシンのネットワークを構成するときに、レガシ ネットワーク アダプターではなくネットワーク アダプターを使用します。 レガシ ネットワーク アダプターは統合コンポーネントをサポートしないオペレーティング システム用に設計されています。|**統合ネットワーク アダプター**<br />HYPER-V の機能は大幅に実現するために Vm で特に設計された統合ネットワーク アダプターでは減って CPU オーバーヘッドはネットワーク I/O の既存のハードウェアを模倣したエミュー レートされたネットワーク アダプターと比較されます。 統合ネットワーク アダプターは、パーティション間で子とルート VMBus 経由で共有メモリをより効率的なデータの転送を使用して通信します。 エミュレートされたネットワーク アダプターの VM 設定 ダイアログ ボックスを使用して削除し、統合ネットワーク アダプターに置き換えられます必要があります。 ゲストは、VM 統合サービスをインストールすることが必要です。|  
|統合サービスが任意の有効化されたゲスト オペレーティング システムにインストールされて、integration services の最新バージョンがインストールされていることを確認するようにします。 Integration services の最新バージョンを確認するには、実行**Windows Update**です。|参照してください[HYPER-V プロセッサ パフォーマンス](https://docs.microsoft.com/windows-server/administration/performance-tuning/role/hyper-v-server/processor-performance)のガイダンスについては。<br />**有効化されたゲスト**<br />ゲスト オペレーティング システムとして Windows Server を使用して推奨可能性があります。 エンライトメントは、VM で実行されている Windows の CPU のオーバーヘッドを小さきます。 統合サービスは、I/O に対してその他のエンライトメントを提供します。 サーバーの負荷によってはパフォーマンス向上のための Windows サーバーのゲストでサーバー アプリケーションをホストする適切なことができます。|  
|可能な限り、使用可能な論理プロセッサに仮想プロセッサの 1 対 1 の割り当てを構成します。|使用可能な論理プロセッサに仮想プロセッサの 1 対 1 の割り当てを構成する方法についてを参照してください「プロセッサのパフォーマンスを最適化する」[チェックリスト: HYPER-V でのパフォーマンスの最適化](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)です。|  
|変換または Microsoft Virtual PC、Microsoft Virtual Server、または HYPER-V を実行する VMWare ESX サーバーで実行されている仮想マシンを移行します。|-変換するか、HYPER-V を実行する仮想マシンの移行にを使用して System Center Virtual Machine Manager です。 <br />-必要な場合、Microsoft Virtual PC または Microsoft Virtual Server で実行されている仮想マシンを変換するプロセスを手動で行うことができます。 詳細については、次を参照してください。[仮想マシンの移行ガイド: へ移行方法 Virtual Server から Hyper-v へ](http://go.microsoft.com/fwlink/?LinkID=137258)です。<br />-サンプル ツール**VMC2Hyper V** HYPER-V には、Microsoft Virtual PC または Microsoft Virtual Server で実行されているバーチャル マシンの移行にも使用できます。 VMC2Hyper V サンプル ツールの詳細については、次を参照してください。 [Hyper-v インポート ツールの使用可能なに VMC](http://go.microsoft.com/fwlink/?LinkID=135683)です。 |  
  
## <a name="when-installing-and-configuring-biztalk-server"></a>インストールして、BizTalk Server を構成するときにしています.  
 を仮想環境で BizTalk Server をインストールする場合は、物理環境と同様に同じ実習を従う必要があります。 インストールするときに、BizTalk Server の構成中に、次のリソースを使用する必要があります。  
  
|手順|リファレンス|  
|----------|---------------|  
|ゲスト オペレーティング システムに BizTalk Server をインストールする方法については、次を参照してください。、 [BizTalk Server 環境向けインストール ガイド](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)です。| |  
|実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ベスト プラクティス アナライザー (BPA) ツールでは、BizTalk Server のインストールを完了しました。|ダウンロード、 [BPA](https://www.microsoft.com/download/details.aspx?id=43382)|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが SQL Server でホストされています。 構成する前に、SQL Server インスタンスで theSQL Server ベスト プラクティス アナライザー (BPA) ツールを実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。|ダウンロード、 [SQL Server BPA](https://www.microsoft.com/download/details.aspx?id=29302)|  
|Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operations guide の「が必要なすべての前提条件ソフトウェアがインストールされていることを確認するに使用できる運用の準備のチェックリストを示します。 チェックリストを提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の一部として必要なすべてのコンポーネントの特定の構成情報が提供されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オペレーティング システム、IIS、および SQL Server を含むスタック。 さらに、高可用性の BizTalk Server を構成する方法に関するガイダンスが提供します。|読み取り、(../technical-guides/BizTalk operations Guide](biztalk-server-2010-operations-guide.md)|  
|BizTalk Server 環境のパフォーマンスを最適化します。|参照してください[BizTalk Server Performance Optimization Guide](../technical-guides/biztalk-server-2010-performance-optimization-guide.md)のガイダンス|  
|インストールし、BizTalk ヘルス モニターの実行を分析し、BizTalk Server メッセージ ボックス データベースの構成を検証します。|ダウンロード[BHM](https://www.microsoft.com/download/details.aspx?id=43716)|  
|CPU を HYPER-V で実行されているゲスト オペレーティング システムに正しく割り当てていることを確認します。| 参照してください**プロセッサのパフォーマンスを測定**で[チェックリスト: HYPER-V のパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)です。|
