---
title: 'チェックリスト: Windows Server を構成する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebd7ea95-cc73-4c98-a796-193f394fb5b8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bffa095c4ed5834f93b3a8634915214ac7b9530
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299850"
---
# <a name="checklist-configuring-windows-server"></a>チェックリスト: Windows Server を構成します。
このトピックは、実稼働環境で使用するための Windows Server を準備する際に従う必要のある手順を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
##  <a name="BKMK_Win2k8"></a>Windows Server を構成します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|MSDTC を構成して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。|-参照[、BizTalk Server で MSDTC を有効にする方法](http://go.microsoft.com/fwlink/?LinkId=153236)(http://go.microsoft.com/fwlink/?LinkId=153236)。<br />-参照[MSDTC に関する問題のトラブルシューティング](http://go.microsoft.com/fwlink/?LinkId=153237)(http://go.microsoft.com/fwlink/?LinkId=153237)。|  
|構成上の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 **注:** のみ、この手順は必要なかどうかは 1 つまたは複数のファイアウォール内の場所、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。|-参照[ポートを BizTalk Server に必要な](http://go.microsoft.com/fwlink/?LinkId=153238)(http://go.microsoft.com/fwlink/?LinkId=153238)。<br />-Microsoft サポート技術情報の記事 154596 を参照して[「ファイアウォールで動作する RPC 動的ポート割り当てを構成する方法」](http://go.microsoft.com/fwlink/?LinkId=153239) (http://go.microsoft.com/fwlink/?LinkId=153239)。|  
|実行しているすべてのコンピューターでのハイパー スレッディングをオフにする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。|はそのハイパー スレッドを実行しているコンピューター オフにする重要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 これは、通常、BIOS setup のプロセッサの設定にある、BIOS 設定です。 ハイパー スレッディングによって; は実際にはよりも多くのプロセッサ/プロセッサ コアが表示されるサーバーただし、ハイパー スレッド プロセッサは、20 ~ 30% の物理プロセッサまたはプロセッサのコアのパフォーマンスで通常提供します。 ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]カウントの自動調整アルゴリズム、ハイパー スレッド プロセッサを調整するプロセッサの数引き起こす誤差が、これらの調整が全体的なパフォーマンスを低下させます。<br />-ハイパー スレッディングをオフにする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューターのための高レベルの競合の可能性があるアプリケーション (など[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]) でのハイパー スレッド環境でパフォーマンスの低下を引き起こすことができます、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。|  
|「バック グラウンド サービス」に設定されている Windows Server のプロセッサのスケジュールを確認します。|この構成オプションは、環境内の Windows Server を実行しているすべてのコンピューターで設定を確保するには、システム全体のパフォーマンスが向上します。 Windows Server がバック グラウンド サービスを優先するように構成されていることを確認する手順に従います。<br /><br /> 1.をクリックして**開始**、 をクリックして**実行**、し、入力**sysdm.cpl**で、**実行**ボックス。<br />2.**システム プロパティ**ダイアログ ボックスで、をクリックして、 **[詳細設定]** ] タブをクリックして**設定**[**パフォーマンス**です。<br />3.**パフォーマンス オプション**ダイアログ ボックスで、をクリックして、 **詳細設定**  タブで、確認、**バック グラウンド サービス**下にあるオプションを選択した**プロセッサスケジュール**、 をクリックして**ok**、順にクリック**ok**閉じます**システムのプロパティ** ダイアログ ボックス。|  
|別のローカル物理ドライブに Windows ページング ファイルを配置します。|Windows Server を実行しているコンピューターのオペレーティング システム以外の別の物理ボリュームに、ページング ファイルを移動すると、ディスクの競合を減らすことによってパフォーマンスが向上させます。<br /><br /> ページング ファイルをオペレーティング システム以外の別の物理ボリュームに移動する手順に従います。<br /><br /> 1.をクリックして**開始**、 をクリックして**実行**、し、入力**sysdm.cpl**で、**開く**ボックス。<br />2.をクリックして、**詳細**] タブをクリックして**設定**[**パフォーマンス**です。<br />3.をクリックして、 **詳細設定**  タブで、をクリックして**変更****仮想メモリ**、ページング ファイルのオプションを指定してクリックし、 **OK**  をクリックし、**OK**システムのプロパティを閉じます。 **注:** 新しい設定を有効にするには、コンピューターを再起動する必要があります。|  
|-すべてのディスクの断片化を解消 (ローカルと SAN/NAS) 営業時間外のディスクの最適化をスケジュールすることによって定期的にします。<br />-Windows ページング ファイルの断片化を解消し、マスター ファイル テーブル内の各ディスクを事前に割り当て、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム全体のパフォーマンスを向上させるための環境。|使用して、 [PageDefrag ユーティリティ](http://go.microsoft.com/fwlink/?LinkId=108976)Windows ページング ファイルの断片化を解消し、マスター ファイル テーブルを事前に割り当て (http://go.microsoft.com/fwlink/?LinkId=108976)。|  
|実行しているコンピューターでウイルス対策ソフトウェアがインストールされている場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データとトランザクションのファイル (.mdf、.ndf、.ldf、.mdb ファイル) のリアルタイム スキャンを無効にします。|リアルタイム スキャン、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データとトランザクションのファイルがディスク I/O の競合が増えるし、削減[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンス。|  
|実行しているコンピューターでウイルス対策ソフトウェアがインストールされている場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、いずれかによって参照される非実行可能ファイルの種類のリアルタイム スキャンを無効に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信場所 (通常はします。XML、.csv、.txt などこともできます。)。|によって参照されている非実行可能ファイルのリアルタイム スキャン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信場所がこれらのファイルの I/O の競合が増えるし、削減[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス。|  
|侵入検知ソフトウェアがインストールされている場合は、スキャンを実行しているコンピューター間でネットワークを無効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と外部データ リポジトリ ([!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]) またはメッセージングのメッセージ キューと WebSphere MQSeries) などのサービスです。|侵入検知ソフトウェアでは、速度が低下したり、でもネットワーク経由で有効な通信を防止することができます。|  
|ネットワーク カード (NIC) ドライバーのすべてのコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスの環境でチューニングする必要があります。|受信および送信の両方、パケットがバッファリングの使用可能なメモリの量を最大化するネットワーク デバイス ドライバーを調整します。 バッファー カウントを最大化、特に転送バッファーおよびバッファーを結合します。 既定値は、これらのパラメーターの値しにも用意されているかどうかは、製造元およびドライバーのバージョン間で異なる場合します。 目標は、ネットワーク インターフェイス カード ハードウェアでは、実行した作業を最大化して、ネットワーク トラフィックの増加および関連付けられている輻輳を軽減するためにネットワーク操作の最大の可能なバッファー領域が確保されます。|  
|ネットワーク カードを固定速度と二重通信形式に設定します。|固定の速度と二重通信形式を使用して (1 ギガビットまたは全二重でそれ以降)、BizTalk と SQL サーバーのネットワーク接続に対してです。 ネットワーク インターフェイスはいない自動ネゴシエーションが低速または双方向の設定は、以前に一部のエンタープライズ スイッチに問題があったようになります。 また、大容量の環境では、ギガビット ネットワークをことをお勧めします。|  
|停止または無効化 (印刷スプーラー Indexing Service など) は必ずしも必要ではないすべての Windows サービスのすべてのコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。|それ以外の場合、使用できるシステム リソースを使用して、実稼働サーバーに不要なサービスを実行している[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [COM + の修正プログラム ロールアップ パッケージをインストールします。](../technical-guides/installing-com-hotfix-rollup-packages.md)  
  
## <a name="see-also"></a>参照  
 [操作のチェックリスト](../technical-guides/operations-checklists.md)