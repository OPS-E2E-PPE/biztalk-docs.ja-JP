---
title: "チェックリスト: インストールして、HYPER-V の BizTalk Server を構成するためのベスト プラクティスの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b5ddbb5-3752-4294-ae6a-c14363b3ddc9
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edfc6a24053579ca7dfdd4d0ad64173b962d3c0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-best-practices-for-installing-and-configuring-biztalk-server-on-hyper-v"></a>インストールして、HYPER-V の BizTalk Server を構成するためのベスト プラクティスのチェックリスト:
以下のセクションでは、インストールの概要と、構成の要件、 [HYPER-V 上の BizTalk Server の展開](../technical-guides/deploying-biztalk-server-on-hyper-v.md)このガイドの「します。 これらのインストール、構成および展開するときに、クイック リファレンスとして使用する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 環境でします。 詳細については、関連するセクションへのリンクが提供されます。  
  
## <a name="before-installing-hyper-v"></a>前に、HYPER-V をインストールしています.  
  
|手順|リファレンス|  
|----------|---------------|  
|HYPER-V は 64 ビットおよびすべてのエディションの使用可能なサーバーの役割[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]は 64 ビットのみです。|トピックを参照して**HYPER-V は、インストールの前提条件**いただけます[http://go.microsoft.com/fwlink/?LinkId=142350](http://go.microsoft.com/fwlink/?LinkId=142350)です。|  
|プロセッサがハードウェア依存の仮想化し、データ実行防止 (DEP) をサポートしていると、これらの機能が有効になっていることを確認します。 これには、Intel バーチャライゼーション テクノロジ (Intel VT) または AMD Virtualization (AMD-V) と互換性があるプロセッサが必要です。|トピックを参照して**HYPER-V は、インストールの前提条件**いただけます[http://go.microsoft.com/fwlink/?LinkId=142350](http://go.microsoft.com/fwlink/?LinkId=142350)です。|  
|使用して[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]ルート パーティション用のコア エディションです。 サーバーのオーバーヘッドを最小限に抑える、HYPER-V は、パフォーマンスが向上します。|トピックを参照して**、Server Core インストールの Windows Server 2008 R2 で HYPER-V の役割をインストール**いただけます[http://go.microsoft.com/fwlink/?LinkID=202131](http://go.microsoft.com/fwlink/?LinkID=202131)です。|  
|ルート パーティションにのみ、Hyper-v サーバーの役割を実行します。|**仮想化サーバーのパフォーマンスの調整**のセクションで、**パフォーマンス チューニング ガイドラインの Windows Server 2008 R2**でダウンロードできるホワイト ペーパー [http://go.microsoft.com/fwlink/ しますか。LinkID = 202087](http://go.microsoft.com/fwlink/?LinkID=202087):<br />**専用サーバー ロール**<br />ルート パーティションを専用の仮想化サーバーの役割にする必要があります。 追加のサーバー役割に悪影響を与える、仮想化サーバーのパフォーマンス大幅な CPU、メモリ、または I/O 帯域幅を使用する場合に特にです。 ルート パーティション内のサーバー ロールを最小限に抑えると、攻撃や更新の頻度を減らすことなどの他の利点があります。 システム管理者は、ルート パーティションにどのようなソフトウェアがインストールされているため、一部のソフトウェア仮想化サーバーの全体的なパフォーマンスに悪影響慎重に検討する必要があります。|  
  
## <a name="when-creating-hyper-v-virtual-machines"></a>HYPER-V の仮想マシンを作成するときにしています.  
  
|手順|リファレンス|  
|----------|---------------|  
|固定サイズの仮想ハード_ディスクを使用して (VHD) は、オペレーティング システム ドライブの Vhd を動的にサイズ変更と比較してパフォーマンスの向上を提供します。|**仮想化サーバーのパフォーマンスの調整**のセクションで、**パフォーマンス チューニング ガイドラインの Windows Server 2008 R2**でダウンロードできるホワイト ペーパー [http://go.microsoft.com/fwlink/ しますか。LinkID = 202087](http://go.microsoft.com/fwlink/?LinkID=202087): <br />**固定サイズの VHD**<br />VHD のスペースは最初に、VHD ファイルが作成されるときに割り当てられました。 この種類の VHD は、1 つの I/O が複数の I/o に分割すると、I/O スループットを減らすこと、フラグメント化する傾向です。 読み取りと書き込みが、ブロックのマッピングを検索する必要はないために、VHD の 3 種類の最小の CPU のオーバーヘッドがあります。|  
|頻繁なディスク I/O アクティビティに固定サイズの仮想ハード ドライブ (VHD) のディスクを使用して、SCSI コント ローラーを使用して、データ ボリュームのディスクを構成します。 高負荷の高いストレージの I/O ワークロードの複数のデータ ドライブに配置されている場合に、全体的なパフォーマンスを向上させるため代理個別の SCSI コント ローラーに各 VHD をアタッチする必要があります。 さらに、各 VHD は、個別の物理ディスクに保存する必要があります。|**仮想化サーバーのパフォーマンスの調整**のセクションで、**パフォーマンス チューニング ガイドラインの Windows Server 2008 R2**でダウンロードできるホワイト ペーパー [http://go.microsoft.com/fwlink/ しますか。LinkID = 202087](http://go.microsoft.com/fwlink/?LinkID=202087):<br />**統合 SCSI コント ローラー**<br />統合記憶域コント ローラーは、エミュレートされた IDE デバイスよりも CPU のオーバーヘッドを削減によるストレージの I/o でパフォーマンスが著しく向上を提供します。 VM 統合サービスは、この記憶域デバイスの有効化されたドライバーが含まれてし、ゲスト オペレーティング システムで検出するために必要なです。 正常に起動するオペレーティング システムの IDE デバイスにオペレーティング システム ディスクをマウントする必要がありますが、VM 統合サービスが代理記憶装置に IDE デバイスの I/o に再ルーティングするフィルター ドライバーをロードします。<br />その構成には、CPU のオーバーヘッドが少なくなっているために、合成の SCSI コント ローラーに直接データ ドライブをマウントすることを強くお勧めします。 必要な I/O 率が高い場合もログ ファイルと合成の SCSI コント ローラーに直接オペレーティング システムのページング ファイルをマウントする必要があります。<br />高負荷の高いストレージの I/O ワークロードの複数のデータ ドライブに配置されている場合に、全体的なパフォーマンスを向上させるため代理個別の SCSI コント ローラーに各 VHD をアタッチする必要があります。 さらに、各 VHD は、個別の物理ディスクに保存する必要があります。|  
|SQL Server データ ファイルとログ ファイルの高い I/O アクティビティ VHD ディスクをアタッチするのにには、SCSI コント ローラーを使用します。 **注:** SCSI コント ローラーのシステム ディスクをアタッチできません。 IDE コント ローラーには、オペレーティング システムを含むバーチャル ハード ディスクをアタッチする必要があります。|HYPER-V は、IDE コント ローラーと SCSI コント ローラーと同等のパフォーマンスを提供して、場合でも、SCSI コント ローラーのみインストールできます HYPER-V 統合サービスがインストールされている場合。 したがって、パススルー ディスクをアタッチする、SCSI コント ローラーの使用では、HYPER-V 統合サービスがインストールされている必要がさらに、最適なディスク I/O パフォーマンスを確認します。|  
|仮想マシンのネットワークを構成するときに、レガシ ネットワーク アダプターではなくネットワーク アダプターを使用します。 レガシ ネットワーク アダプターは統合コンポーネントをサポートしないオペレーティング システム用に設計されています。|**仮想化サーバーのパフォーマンスの調整**のセクションで、**パフォーマンス チューニング ガイドラインの Windows Server 2008 R2**でダウンロードできるホワイト ペーパー [http://go.microsoft.com/fwlink/ しますか。LinkID = 202087](http://go.microsoft.com/fwlink/?LinkID=202087):<br />**統合ネットワーク アダプター**<br />HYPER-V の機能は大幅に実現するために Vm で特に設計された統合ネットワーク アダプターでは減って CPU オーバーヘッドはネットワーク I/O の既存のハードウェアを模倣したエミュー レートされたネットワーク アダプターと比較されます。 統合ネットワーク アダプターは、パーティション間で子とルート VMBus 経由で共有メモリをより効率的なデータの転送を使用して通信します。 エミュレートされたネットワーク アダプターの VM 設定 ダイアログ ボックスを使用して削除し、統合ネットワーク アダプターに置き換えられます必要があります。 ゲストは、VM 統合サービスをインストールすることが必要です。|  
|統合サービスが任意の有効化されたゲスト オペレーティング システムにインストールされて、integration services の最新バージョンがインストールされていることを確認するようにします。 Integration services の最新バージョンを確認するに接続[http://go.microsoft.com/fwlink/?LinkID=202449](http://go.microsoft.com/fwlink/?LinkID=202449)実行または**Windows Update**から、**開始**メニュー。|**仮想化サーバーのパフォーマンスの調整**のセクションで、**パフォーマンス チューニング ガイドラインの Windows Server 2008 R2**でダウンロードできるホワイト ペーパー [http://go.microsoft.com/fwlink/ しますか。LinkID = 202087](http://go.microsoft.com/fwlink/?LinkID=202087):<br />**有効化されたゲスト**<br />オペレーティング システムのカーネル[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]、 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]、vm の場合、操作を最適化するエンライトメントが機能します。 使用することお勧めを最適なパフォーマンスを[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]ゲスト オペレーティング システムとして。 エンライトメントは、VM で実行されている Windows の CPU のオーバーヘッドを小さきます。 統合サービスは、I/O に対してその他のエンライトメントを提供します。 サーバーの負荷によってはパフォーマンス向上のための Windows Server 2008 ゲストでサーバー アプリケーションをホストする適切なことができます。|  
|可能な限り、使用可能な論理プロセッサに仮想プロセッサの 1 対 1 の割り当てを構成します。|使用可能な論理プロセッサに仮想プロセッサの 1 対 1 の割り当てを構成する方法についてを参照してください「プロセッサのパフォーマンスを最適化する」[チェックリスト: HYPER-V でのパフォーマンスの最適化](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)です。|  
|変換または Microsoft Virtual PC、Microsoft Virtual Server、または HYPER-V を実行する VMWare ESX サーバーで実行されている仮想マシンを移行します。|変換するか、HYPER-V を実行する仮想マシンを移行する用 System Center Virtual Machine Manager 2008 R2。 詳細についてを参照してください"V2V:: への変換、バーチャル マシンを VMM Virtual Machine"に[http://go.microsoft.com/fwlink/?LinkId=146342](http://go.microsoft.com/fwlink/?LinkId=146342)です。<br />-必要な場合、Microsoft Virtual PC または Microsoft Virtual Server で実行されている仮想マシンを変換するプロセスを手動で行うことができます。 詳細についてを参照してください"仮想マシンの移行ガイド:: 方法に移行から仮想サーバーに HYPER-V"で[http://go.microsoft.com/fwlink/?LinkID=137258](http://go.microsoft.com/fwlink/?LinkID=137258)です。<br />-サンプル ツール**VMC2Hyper V** HYPER-V には、Microsoft Virtual PC または Microsoft Virtual Server で実行されているバーチャル マシンの移行にも使用できます。 VMC2Hyper V サンプル ツールの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=135683](http://go.microsoft.com/fwlink/?LinkID=135683)です。 **注:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。|  
  
## <a name="when-installing-and-configuring-biztalk-server"></a>インストールして、BizTalk Server を構成するときにしています.  
 インストールするときに[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]仮想環境で同じ実習を物理環境と同様に従う必要があります。 インストールするときの構成中に、次のリソースを使用する必要があります[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]:  
  
|手順|リファレンス|  
|----------|---------------|  
|インストールする方法の詳細について[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]、ゲスト オペレーティング システムで、次を参照してください。、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]環境向けインストール ガイドです。|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境向けインストール ガイドはいただけます[http://go.microsoft.com/fwlink/?LinkID=191321](http://go.microsoft.com/fwlink/?LinkID=191321)です。|  
|実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]完成した上のベスト プラクティス アナライザー (BPA) ツール[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]インストールします。|BPA ツールは[http://go.microsoft.com/fwlink/?LinkID=196491](http://go.microsoft.com/fwlink/?LinkID=196491)です。|  
|場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]に入れるしようとしているデータベース[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]、実行、[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]上のベスト プラクティス アナライザー (BPA) ツール、[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]インスタンスを構成する前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]ベスト プラクティス アナライザーは、「 [http://go.microsoft.com/fwlink/?LinkID=202133](http://go.microsoft.com/fwlink/?LinkID=202133)です。|  
|Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operations guide の「が必要なすべての前提条件ソフトウェアがインストールされていることを確認するに使用できる運用の準備のチェックリストを示します。 チェックリストを提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の一部として必要なすべてのコンポーネントの特定の構成情報が提供されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オペレーティング システム、IIS、および SQL Server を含むスタック。 さらに、高可用性の BizTalk Server を構成する方法に関するガイダンスが提供します。|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operations guide の「は、「 [http://go.microsoft.com/fwlink/?LinkId=110533](http://go.microsoft.com/fwlink/?LinkId=110533)です。|  
|「のパフォーマンスの最適化」」のガイダンスに従って、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のパフォーマンスを調整のパフォーマンス最適化ガイド、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]インストールします。|ハイパーリンク"http://msdn.microsoft.com/en-us/library/cc296643.aspx"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ハイパーリンク"http://msdn.microsoft.com/en-us/library/cc558617.aspx"のパフォーマンス最適化ガイドについては、「 [http://go.microsoft.com/fwlink/?LinkId=122579](http://go.microsoft.com/fwlink/?LinkId=122579)です。|  
|インストールと実行を分析し、BizTalk Server メッセージ ボックス データベースの構成を検証するには、BizTalk MsgBoxViewer ユーティリティを検討してください。|BizTalk MsgBoxViewer ユーティリティは、「 [http://go.microsoft.com/fwlink/?LinkID=117289](http://go.microsoft.com/fwlink/?LinkID=117289)です。 **注:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。|  
|CPU を HYPER-V で実行されているゲスト オペレーティング システムに正しく割り当てていることを確認します。|「プロセッサのパフォーマンスを測定」セクション[チェックリスト: HYPER-V でのパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)です。|