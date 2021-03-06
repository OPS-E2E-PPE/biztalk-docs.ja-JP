---
title: オペレーティング システムのパフォーマンスを向上させるための一般的なガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc9ca38e-1feb-4f34-a64b-d04566e85db9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6263e9af9ce9ec826c887e04b398fa862edf0332
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392014"
---
# <a name="general-guidelines-for-improving-operating-system-performance"></a>オペレーティング システムのパフォーマンスを向上させるための一般的なガイドライン
次の一般的なガイドラインは、オペレーティング システムのパフォーマンスを向上させるために後にする必要があります。  
  
## <a name="install-the-latest-bios-storage-area-network-san-drivers-network-adapter-firmware-and-network-adapter-drivers"></a>最新の BIOS、記憶域エリア ネットワーク (SAN) ドライバー、ネットワーク アダプターのファームウェアおよびネットワーク アダプター ドライバーをインストールします。  
 ハードウェアの製造元は、関連付けられたハードウェアのパフォーマンスと可用性を向上できる BIOS、ファームウェア、およびドライバーの更新プログラムを定期的にリリースします。 ダウンロードして、BizTalk Server 環境内の各コンピューターで、次のハードウェア コンポーネントの更新プログラムを適用するハードウェアの製造元の Web サイトを参照してください。  
  
1.  BIOS の更新プログラム  
  
2.  SAN のドライバー (この場合、SAN の使用)  
  
3.  NIC ファームウェア  
  
4.  NIC ドライバー  
  
## <a name="enable-the-high-performance-power-plan-on-all-biztalk-server-and-sql-server-computers"></a>「高パフォーマンス」を有効にするすべての BizTalk Server と SQL Server コンピューターの電源プランします。  
 既定では、Windows Server 2008/2008 R2 セット (推奨) バランス電源プランで、電力の節約できますしますが、できます待機時間の増加 (いくつかのタスクの低速の応答時間) が発生して CPU 負荷の高いアプリケーションでパフォーマンスの問題が発生します。  
  
 待機時間を短縮するために BizTalk Server を実行しているすべてのサーバーと SQL Server、Windows であることを確認する必要があります**電源プラン**設定**高性能**します。 切り替える方法について、**高性能**電源プラン、サポート技術情報の記事を参照してください。2207548 [Windows Server 2008 R2 での全体的なパフォーマンスの低下](http://go.microsoft.com/fwlink/?LinkID=219677)(http://go.microsoft.com/fwlink/?LinkID=219677)します。  
  
## <a name="evaluate-the-usage-of-intel-hyper-threading-on-biztalk-server-and-sql-server-computers"></a>Intel ハイパー スレッディングの BizTalk Server と SQL Server のコンピューターで評価します。  
  
-   **プレ Nehalem ハイパースレッディング**:  
  
    -   ハイパー スレッディングをオフにするのには、BizTalk Server コンピューター。 これは、通常、BIOS setup のプロセッサの設定にある、BIOS 設定です。 実際には; よりもより多くのプロセッサまたはプロセッサ コアと表示され、サーバーは、ハイパー スレッドただし、ハイパー スレッド プロセッサは、物理プロセッサまたはプロセッサ コアのパフォーマンスの 20 ~ 30% の間で通常提供します。 BizTalk Server では、その自動調整アルゴリズムを調整するプロセッサの数をカウント、ハイパー スレッド プロセッサには、負の値の全体的なパフォーマンスになることができます、傾斜させるには、この調整が発生します。  
  
    -   ハイパー スレッディングをオフにする SQL Server コンピューターで高レベルの (BizTalk Server) などの競合を引き起こす可能性のあるアプリケーションでは、SQL Server コンピューター上のハイパー スレッド環境でパフォーマンスの低下が生じるためです。  
  
-   **Nehalem ハイパースレッディング**:異なり、旧式のアーキテクチャで Intel microarchitecture"Nehalem"プロセッサでハイパー スレッディングの有効化を提供できますまでほぼ線形の容量の増加。 最適なパフォーマンスの結果、"Nehalem"プロセッサを展開するときにお勧めのスループットが大幅に増加するためのテクノロジの Intel ハイパー スレッド (H T) を有効にすると、コンピューターの BIOS を構成すること。  
  
-   **ハードウェア仮想化**:ハードウェア仮想化を使用する場合、仮想マシンは仮想プロセッサを使用しています。 利用可能な Cpu の数は、仮想マシンを構成するときに選択した設定に基づきます。 ハードウェアが、ハイパー スレッドの場合、仮想マシンはわかりませんがハイパー スレッドします。  
  
## <a name="assign-the-msdtc-log-file-directory-to-a-separate-dedicated-drive"></a>MSDTC ログ ファイルのディレクトリを別の専用のドライブに割り当てる  
 別の SQL Server コンピューターで複数のメッセージ ボックス データベースを使用する BizTalk Server 環境では、Microsoft 分散トランザクション コーディネーター (MSDTC) に関連付けられている追加のオーバーヘッドが発生します。 既定では、MSDTC ログ ファイルは、DTC サービスを実行しているコンピューターの %systemdrive%\windows\system32\msdtc ディレクトリにあります。 DTC ログ記録がパフォーマンスのボトルネックになる可能性を軽減するために高速ディスク ドライブに、MSDTC ログ ファイル ディレクトリの移動を検討してください。  
  
 MSDTC ログ ファイルのディレクトリを変更するを参照してください。 [DTC ログを構成](http://go.microsoft.com/fwlink/?LinkID=204107)(http://go.microsoft.com/fwlink/?LinkID=204107)します。  
  
## <a name="configure-antivirus-software-to-avoid-real-time-scanning-of-biztalk-server-executables-and-file-drops"></a>BizTalk Server 実行可能ファイルのリアルタイム スキャンを回避するために、ウイルス対策ソフトウェアを構成し、ファイルを削除します  
 ウイルス対策ソフトウェアのリアルタイム スキャン、BizTalk Server 実行可能ファイルおよびフォルダーやファイルの BizTalk Server によって監視される共有の場所を受信する BizTalk Server のパフォーマンスが低下することができます。 ウイルス対策ソフトウェアは、BizTalk Server コンピューターにインストールされて場合の BizTalk Server によって参照される非実行可能ファイルの種類のリアルタイム スキャンを無効にする受信場所 (通常は。XML、.csv、.txt などにすることもできます)。BizTalk Server 実行可能ファイルのスキャンを除外するウイルス対策ソフトウェアと構成  
  
## <a name="disable-intrusion-detection-network-scanning-between-computers-in-the-biztalk-server-environment"></a>侵入検出のネットワークに BizTalk Server 環境内のコンピューター間でのスキャンを無効にします。  
 侵入検知ソフトウェアでは、速度が低下したり、でも、ネットワーク経由で有効な通信を防止することができます。 侵入検出ソフトウェアがインストールされている場合は、BizTalk Server コンピューターと外部データのリポジトリ (SQL Server) コンピューターでスキャンやメッセージング サービス (メッセージ キューは、WebSphere MQSeries) などのコンピューターのネットワークを無効にします。  
  
## <a name="defragment-all-disks-in-the-biztalk-server-environment-on-a-regular-basis"></a>定期的に BizTalk Server 環境のすべてのディスクを最適化します。  
 BizTalk Server 環境での過剰なディスクの断片化には、パフォーマンスに悪影響が。 BizTalk Server 環境でのディスクの断片化を解消するこれらの手順に従います。  
  
1.  すべてのディスクの最適化 (ローカルと SAN/NAS) ピーク時間外のディスクの最適化をスケジュールして定期的にします。  
  
2.  Windows ページファイルを最適化およびシステム全体のパフォーマンスを向上させるため、BizTalk Server 環境では、各ディスクのマスター ファイル テーブルを事前に割り当てます。  
  
    > [!NOTE]  
    >  マスター ファイル テーブルを事前に割り当てて、サポート技術情報記事 961095 を参照してください[「Windows Vista および Windows Server 2008 で予約をゾーンのマスター ファイル テーブルについて」](http://go.microsoft.com/fwlink/?LinkID=204563) (http://go.microsoft.com/fwlink/?LinkID=204563)します。  
  
## <a name="if-antivirus-software-is-installed-on-the-sql-server-computer-disable-real-time-scanning-of-data-and-transaction-files"></a>SQL Server コンピューターのウイルス対策ソフトウェアがインストールされている場合、は、データとトランザクションのファイルのリアルタイム スキャンを無効にします。  
 (.Mdf、.ndf、.ldf、.mdb ファイル) の SQL Server データとトランザクション ファイルのリアルタイム スキャン、ディスク I/O の競合が増加し、SQL Server のパフォーマンスが低下することができます。 SQL Server のデータとトランザクションのファイルの名前は、BizTalk Server 環境間で異なる場合がありますに注意してください。 既定の BizTalk Server 構成で作成されたデータとトランザクションのファイルの詳細については、次を参照してください。 [、Databases2 のファイル グループを最適化する](../technical-guides/optimizing-filegroups-for-the-databases2.md)します。  
  
## <a name="configure-msdtc-for-biztalk-server-and-sql-server"></a>BizTalk Server と SQL Server の MSDTC を構成します。  
 SQL Server と BizTalk Server 間のトランザクションを促進するには、Microsoft 分散トランザクション コーディネーター (MSDTC) を有効にする必要があります。  
  
#### <a name="to-configure-distributed-transaction-coordinator-dtc"></a>分散トランザクション コーディネーター (DTC) を構成するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**dcomcnfg**、順にクリックします**ok**を開く**コンポーネント サービス**.  
  
2.  コンソール ツリーで、**[コンポーネント サービス]**、**[コンピューター]**、**[マイ コンピューター]**、**[分散トランザクション コーディネーター]** の順に展開し、**[ローカル DTC]** をクリックします。  
  
3.  右クリック**ローカル DTC**、 をクリックし、**プロパティ**を表示する、**ローカル DTC のプロパティ** ダイアログ ボックス。  
  
4.  **トレース** タブの **出力オプション** セクションで、クリア、**トレース出力**ボックス。  
  
5.  **[セキュリティ]** タブをクリックします。  
  
6.  次の 4 つのオプションが選択されていることと、それ以外はすべて選択が解除されていることを確認してください。  
  
    -   **ネットワーク DTC アクセス**  
  
    -   **受信を許可する**  
  
    -   **送信を許可する**  
  
    -   **認証を必要としない**  
  
7.  クリックして**OK**を閉じる、**ローカル DTC のプロパティ** ダイアログ ボックス。 MSDTC サービスを再起動するメッセージが表示されたら、クリックして**はい**します。  
  
8.  **[コンポーネント サービス]** を閉じます。  
  
9. クリックして**開始**、 をポイント**管理ツール**、順にクリックします**セキュリティが強化された Windows ファイアウォール**します。  
  
10. セキュリティが強化された Windows ファイアウォールで次のようにクリックします。**受信の規則**します。  
  
11. **受信の規則**ウィンドウで、右クリックして**分散トランザクション コーディネーター*** (必要に応じて)、順にクリックします**規則の有効化**します。  
  
12. セキュリティが強化された Windows ファイアウォールで次のようにクリックします。**送信の規則**します。  
  
13. **送信の規則**ウィンドウで、右クリックして**分散トランザクション コーディネーター*** (必要に応じて)、順にクリックします**規則の有効化**します。  
  
14. **コントロール パネルの **、ダブルクリックして**管理ツール**します。  
  
15. 右側のウィンドウでダブルクリック**サービス**します。  
  
16. 右側のウィンドウで**サービス (ローカル)**、右クリックして**COM + システム アプリケーション**、 をクリックして**再起動**、し、サービスを再起動するまで待ちます。  
  
17. **[分散トランザクション コーディネーター]** サービスを右クリックして再起動します。  
  
18. **[SQL Server (MSSQLSERVER)]** サービスを右クリックして再起動します。  
  
19. **[サービス (ローカル)]** を閉じ、**[管理ツール]** を閉じます。  
  
## <a name="configure-firewalls-for-biztalk-server"></a>BizTalk server 上を構成します。  
  
> [!NOTE]  
>  この手順はのみかどうか 1 つまたは複数のファイアウォールは、BizTalk Server 環境で必要です。  
  
 BizTalk Server の上を構成するのには、次の情報を確認します。  
  
- [BizTalk Server のポートに必要な](http://go.microsoft.com/fwlink/?LinkID=153238)(http://go.microsoft.com/fwlink/?LinkID=153238)します。  
  
- ファイアウォールで動作する RPC 動的ポート割り当てを構成するには、サポート技術情報記事 929851 を参照してください["TCP/IP の既定の動的なポート範囲は Windows Vista および Windows Server 2008 has changed"](http://go.microsoft.com/fwlink/?LinkID=204568) (HYPERLINK"<http://go.microsoft.com/fwlink/?LinkID=204568>"。<http://go.microsoft.com/fwlink/?LinkID=204568>). 必要なポートを対応するために Windows ファイアウォールを構成する方法については、次を参照してください。 [Windows ファイアウォールと IPsec ポリシーの展開ステップ バイ ステップ ガイド](http://go.microsoft.com/fwlink/?LinkID=204569)(<http://go.microsoft.com/fwlink/?LinkID=204569>)。  
  
## <a name="install-appropriate-com-and-msdtc-hotfix-rollup-packages"></a>COM +、MSDTC の適切な修正プログラムのロールアップ パッケージをインストールします。  
 適切な COM + および MS DTC の修正プログラム ロールアップ パッケージをインストールするには、次の情報を確認します。  
  
-   MS DTC の修正プログラムは Microsoft サポート技術情報 article978476 で見つかる[「は、Windows Server 2008 R2 MS DTC の修正プログラム ロールアップ パッケージ 1 で修正 MS DTC の問題」](http://go.microsoft.com/fwlink/?LinkID=204109) (http://go.microsoft.com/fwlink/?LinkID=204109)します。  
  
-   検索することにより最新 DTC の修正プログラム ロールアップ パッケージ KB 記事が見つかります[ http://support.microsoft.com ](http://go.microsoft.com/fwlink/?LinkID=96185) (http://go.microsoft.com/fwlink/?LinkID=96185) (引用符を含む) という語句。  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     次のクエリは、この検索をします。 最新のものを選択します。   
    [http://support.microsoft.com/search/default.aspx?query="MS + DTC + 修正プログラム + ロールアップ + パッケージ"](http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package")  
  
## <a name="use-the-interrupt-affinity-policy-tool-to-bind-network-adapter-interrupts-to-specific-processors-on-multiprocessor-computers"></a>割り込みアフィニティ ポリシー ツールを使用して、ネットワーク アダプターの割り込みをマルチプロセッサ コンピューターで特定のプロセッサにバインドするには  
 割り込みアフィニティ ポリシー (IntPolicy) は、特定のプロセッサまたはマルチプロセッサのコンピューター上のプロセッサを使用すると、「バインド」または (ネットワーク アダプター) などの特定のデバイスの割り込みの CPU 関係を変更するツールです。 このバインディングは、パーティション分割とも呼ばれます。 特定のネットワーク アダプターからの割り込みをマルチプロセッサ コンピューターで特定のプロセッサをバインドでは、実行中の遅延プロシージャ呼び出し (Dpc) と指定されたプロセッサ上のネットワーク アダプターの割り込みサービス ルーチン (Isr) を適用します。 割り込みアフィニティをシングル プロセッサ コンピューターで構成できないことに注意してください。  
  
> [!NOTE]  
>  DPC は、キューに置かれた後で通常実行されるカーネル モード関数呼び出しとして定義されます。 ISR は、その目的は、割り込みを生成するときに、デバイスをサービス ルーチンとして定義されます。 遅延プロシージャ呼び出しと割り込みサービス ルーチンの詳細については、次を参照してください。、 [Windows Driver Kit ドキュメント](http://go.microsoft.com/fwlink/?LinkId=84418)(http://go.microsoft.com/fwlink/?LinkId=84418)します。  
  
 ![割り込み&#45;アフィニティ ポリシー ツール](../technical-guides/media/interrupt-affinitypolicytool.gif "割り込み AffinityPolicyTool")  
Interrupt-Affinity Policy ツール  
  
 ベースの Windows Server 2008 のマルチプロセッサ コンピューターでは、割り込みコント ローラーの既定の動作は、使用可能なプロセッサに割り込みのデバイスを割り当てるには。 ときにネットワーク接続と特定のネットワーク アダプターのファイル サーバーのセッションには、特定のプロセッサ、セットで実行するバインド/パーティション分割ではなく使用可能なプロセッサ、パフォーマンス、および関連付けられているネットワーク処理のスケーラビリティが向上します。 大規模な BizTalk Server ソリューションの割り込みバインディングが特に有用あります複数のネットワーク アダプターを備えた SQL Server コンピューターをマルチプロセッサの使用を使用します。   
割り込みバインド IntPolicy を使用して常に評価する必要があるテスト環境で実稼働環境で採用する前にします。 ハードウェア、オペレーティング システム、およびテスト環境のアプリケーションの構成する必要がありますおおよその運用環境にできるだけできます。 これにより、割り込みバインディングのさまざまな順列をテストおよび範囲を判断する割り込みバインディングがパフォーマンスが向上します。  
 ハイパー スレッディングをサポートする cpu を搭載したコンピューターで IntPolicy を構成する前に、ハイパースレッディングを無効にすることをお勧めします。 これにより、論理プロセッサではなく、物理プロセッサに割り込みが割り当てられていることが保証されます。 同じ物理プロセッサを参照するための論理プロセッサに割り込みアフィニティを割り当てでは、パフォーマンスは向上しませんし、システムのパフォーマンスが低下する可能性がありますもします。    HYPERLINK"The"、[割り込みアフィニティ ポリシー ツール](http://go.microsoft.com/fwlink/?LinkID=204111)(http://go.microsoft.com/fwlink/?LinkID=204111) WHDC web サイトからダウンロードできます。  
  
## <a name="use-the-ntfs-file-system-on-all-volumes"></a>すべてのボリュームで NTFS ファイル システムを使用します。  
 Windows Server は、ドライブ、NTFS、FAT および FAT32 を書式設定するための複数のファイル システムの種類を提供します。 NTFS はサーバーの任意のファイル システムには常にします。  
NTFS、FAT および FAT32 ファイル システム上の大幅なパフォーマンスの利点し、Windows サーバー上で排他的に使用する必要があります。 さらに、NTFS では、FAT および FAT32 に多くのセキュリティ、拡張性、安定性と回復性の利点を備えています。  
以前のバージョンの Windows では、FAT および FAT32 多くの場合、実装された小さいボリュームの (たとえば < 500 MB) 抱えている多くの場合、このような状況で高速化します。 比較的安価な現在のディスク記憶域とオペレーティング システム ドライブの容量を最大にプッシュするアプリケーションと、このような小さなボリュームが使用中である可能性が高いことはできません。 FAT32 では、大量スケール FAT よりも優れていますが、まだは、適切なファイル システムの Windows サーバーにありません。  
FAT および FAT32 多くの場合に実装されている過去としてより簡単に回復可能なボリュームに問題が発生した場合、ネイティブの DOS ツールを使用して管理しやすい、説明されたようです。 今日と NTFS 回復性のさまざまなツールはビルド、オペレーティング システムにネイティブの両方と使用可能なサード パーティのユーティリティとして使用可能ながありますする必要がありますできなくファイル システムを NTFS を使用していないに対して有効な引数。  
  
## <a name="do-not-use-ntfs-file-compression"></a>NTFS ファイル圧縮を使用しないでください。  
 ボリューム上の領域を削減する簡単な方法が NTFS ファイル システム圧縮を使用して、企業のファイル サーバーの適切ではありません。 圧縮の実装では、すべてのディスク操作の cpu 使用率に余分なオーバーヘッドを配置し、避けることが最善です。 追加のディスクを追加するためのオプションについて考える、ニアライン記憶域またはファイル システム圧縮を真剣に検討する前にデータをアーカイブすることです。  
  
## <a name="review-disk-controller-stripe-size-and-volume-allocation-units"></a>ディスク コント ローラー ストライプ サイズとボリュームの割り当て用のユニットを確認してください。  
 構成のドライブ アレイやハードウェア ドライブ コント ローラー内の論理ドライブを確認するときに、アロケーション ユニット サイズでは、ボリュームをフォーマットすると、コント ローラーのストライプ サイズが一致します。 ディスクの読み取りを確認し、書き込みパフォーマンスは最適なされ、サーバー全体のパフォーマンス向上が提供されます。  
大きな割り当てユニット (クラスターまたはブロック) のサイズの構成によって、あまり効率的に使用するディスク領域が各読み取り操作中にディスク ヘッドがより多くのデータで読み取ることができますのディスク I/O パフォーマンスの向上も提供されます。  
コント ローラーを構成してでディスクをフォーマットする最適な設定を確認するのには、ようなファイル システムの特性を持つサーバーのディスク サブシステム上の平均ディスク転送サイズを決定します。 Windows パフォーマンス モニター ツールを使用して、論理ディスク オブジェクトのカウンターの平均を監視するにはディスク読み取りバイト数/と平均バイト/書き込みを使用する最適な値を判断するための通常のアクティビティの期間にわたってディスクします。  
アロケーション ユニット サイズが小さい可能性がある条件を満たしている、システムが多数の小さなファイルまたはレコードにアクセスするかどうかは 64 KB のアロケーション ユニット サイズは、サウンドのパフォーマンスとほとんどの状況、I/O スループットを提供します。 チューニングされたアロケーション ユニット サイズでパフォーマンスの向上は、ディスクの負荷が増えたときに特に注意することができます。  
  
> [!NOTE]  
>  ボリュームをフォーマットするときに 4096 バイト (KB) を超えるアロケーション ユニット サイズを指定するには、形式のコマンド ライン ツールまたはディスク管理ツールのいずれかが必要です。 Windows エクスプ ローラーは、このしきい値まで書式はのみです。 CHKDSK コマンドは、(各アロケーション ユニットでは、バイトとして表示)、必要な情報が表示される前に、ボリューム全体をスキャンする必要があるボリュームの現在のアロケーション ユニット サイズの確認に使用できます。  
  
## <a name="monitor-drive-space-utilization"></a>ドライブの領域使用率を監視します。  
 低いデータ ディスクが、速度は速く動作します。 これは、ディスクの外側のエッジの近くに、最適化後も、ドライブにデータが書き込まれるため、可能であれば、これは、ディスクが回転する高速であり、最高のパフォーマンスが得られます。  
ディスクのシーク時間よりも通常かなり長い読み取りまたは書き込み操作です。 前述のように、データが最初に、ディスクの外側の端に書き込まれます。 ディスク ストレージが増加し、空き領域の需要が減るデータがディスクの中央に近い書き込まれます。 ディスクのシーク、読み取りに時間がかかり、時間の増加の外側、ヘッドの移動とデータの検索し検出されたときにディスク I/O パフォーマンスが低下します。  
つまり、ディスク領域使用率の監視が重要であるだけでなく容量の問題により、パフォーマンスもします。  
経験上、としては、ディスクの空き領域の間で 20% から 25% のディスク領域の合計を保持するための目標達成に向けた動作します。 空きディスク容量を下回るし、このしきい値をディスク I/O パフォーマンスが悪影響を及ぼす影響をかどうか。  
  
## <a name="implement-a-strategy-to-avoid-disk-fragmentation"></a>ディスクの断片化を回避するための戦略を実装します。  
 パフォーマンスの低下を防ぐために、ルート ドライブを含む、ディスクに定期的にデフラグ ツール ユーティリティを実行します。 この毎週ビジー状態のディスク上の操作を行います。 ディスク デフラグ ツールは Windows と共にインストールされ、指定した間隔でスケジュールされたタスクから実行することができます。  
  
## <a name="optimize-windows-server-performance-for-background-services"></a>バック グラウンド サービス用の Windows Server のパフォーマンスを最適化します。  
 BizTalk Server プロセス (BTSNTSVC.exe) は、バック グラウンド サービスとして実行されます。   
Windows Server 2008 は、プリエンプティブなマルチタスクを使用して、CPU に出席はプロセス スレッドの優先順位を設定します。 これにより、プロセスの実行は停止され、オペレーティング システムの判断で別のプロセスを開始する方法は、プリエンプティブなマルチタスクします。 このスキームでは、1 つのスレッドが CPU を占有していることを防ぎます。  
次の 1 つのプロセスを実行してから、CPU の切り替えは、コンテキストの切り替えと呼ばれます。 Windows オペレーティング システムには、コンテキストの切り替えが発生し、次のスレッドが処理される前に、CPU 上で実行する個々 のスレッドを許可する長さを決定する設定が含まれています。 この時間は、"クォンタム"と呼ばれます。 この設定では、フォア グラウンド プログラムとバック グラウンド サービス間でプロセッサのクォンタムを共有する方法を選択できます。 通常、サーバーのバック グラウンド サービスよりも割り当てられているより多くの CPU 時間をフォア グラウンド プログラムを許可する必要はありません。 すべてのアプリケーションやプロセス サーバーで実行されている必要があります考慮して等しいの CPU 時間。  
 BizTalk ホスト インスタンスのようなバック グラウンド サービスのパフォーマンスを向上させるには、次の手順に従います。  
  
1.  クリックして**開始**、] をクリックして**コントロール パネルの [**、順にクリックします**システム**します。  
  
2.  をクリックして、 **[詳細設定]** ] タブをクリックして**設定**[**パフォーマンス**します。  
  
3.  をクリックして、 **[詳細設定]** ] タブで [**バック グラウンド サービス**、順にクリックします **[ok]** 2 回です。  
  
## <a name="disable-non-essential-services"></a>不要なサービスを無効にします。  
 Windows Server 2008 の既定のインストールでは、BizTalk Server 環境でないために必要ないくつかのサービスを使用します。 各実行中のサービスがシステム リソースを消費し、全体的なパフォーマンスを向上させるために不要なサービスを無効にする必要があります。  
サービスを無効にすると、十分に注意してください。 について十分にように Windows Server では、特定のサービスが実行されている必要があります、サービスを無効にする前に、サービスの目的を調査します。 Windows Server 2008 に必要なサービスが無効になっている、オペレーティング システムは、操作不能である、起動できないことでも、おそらくになる可能性があります。  
専用の BizTalk Server の必要のない Windows Server 2008 のサービスを無効にするには、次の手順を実行します。  
  
1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**コンピュータの管理**します。  
  
2.  [**コンピューターの管理 (ローカル)**、展開**サービスとアプリケーション**、] をクリックし、**サービス**。  
    **状態**列で実行されている各サービスのラベルは「開始」にします。 停止し、不必要に開始される任意のサービスを無効にするなど、次のサービスは、専用の BizTalk Server の必要はありません。  
  
    -   警告  
  
    -   クリップ  
  
    -   DHCP サーバー  
  
    -   Fax サービス  
  
    -   ファイル レプリケーション  
  
    -   赤外線モニター  
  
    -   インターネット接続の共有  
  
    -   メッセンジャー  
  
    -   NetMeeting のリモート デスクトップの共有  
  
    -   Network DDE  
  
    -   Network DDE DSDM  
  
    -   NWLink NetBIOS  
  
    -   NWLink IPX/SP  
  
    -   印刷スプーラー  
  
    -   Telephony  
  
    -   Telnet  
  
    -   無停電電源装置  
  
3.  無効にする各サービスに依存するサービスに注意してください。 これを行うには、次の手順を実行します。  
  
    1.  無効にサービスをダブルクリックします。  
  
    2.  をクリックして、**依存関係**タブ。  
  
    3.  **このサービスは、次のシステム コンポーネントに依存**一覧で、このサービスに依存するサービスに注意してください。  
  
    4.  **、次のシステム コンポーネントがこのサービスに依存**一覧で、サービスをクリックして、このサービスなしで開始ことはできません**OK**します。  
  
4.  1 つずつには、選択した各サービスが無効にします。 これを行うには、次の手順を実行します。  
  
    1.  を無効にする をクリックするサービスを右クリックして**プロパティ**します。  
  
    2.  **スタートアップの種類**一覧で、**無効**します。  
  
    3.  サービスをすぐに停止する場合は、クリックして**停止**します。  
  
         場合、**その他のサービスの停止**注されるその他の依存サービスは停止しても、クリックしてダイアログ ボックスが表示されます**はい**、順にクリックします**OK**。  
  
5.  手順 4 をその他の不要なサービスを無効にする.  
  
> [!NOTE]  
>  引き続き使用する必要があるサービスを無効にしなかったかどうかを確認するには、各サービスを無効にした後、サーバーの正しい動作をテストします。   
> サーバーが BizTalk Server は多くの場合は、Windows Server 2008 のドメインのメンバーである場合は、グループ ポリシーをコンピューターに正しく適用するために TCP/IP helper サービスが必要です。   
> DHCP クライアントを無効にすると、DHCP クライアントが DNS 動的更新プロトコルの登録を停止し、このクライアントの DNS サーバーに追加する手動の DNS レコードが必要です。  
  
## <a name="manually-load-microsoft-certificate-revocation-lists"></a>Microsoft 証明書失効リストを手動で読み込む  
 .NET アプリケーションを開始するときに、.NET Framework は、署名されたアセンブリ用の証明書失効リスト (CRL) をダウンロードしようとします。 場合は、システムは、インターネットに直接アクセスできないまたは Microsoft.com ドメインへのアクセス制限は、この BizTalk Server の起動が遅くなる可能性があります。 アプリケーションの起動時にこの遅延を避けるためには、手動でダウンロードして、コード、システム上の証明書失効リストの署名をインストールする、次の手順を使用することができます。  
  
1. 最新の CRL の更新プログラムをダウンロード[ http://crl.microsoft.com/pki/crl/products/CodeSignPCA.crl ](http://go.microsoft.com/fwlink/?LinkID=117794) (http://go.microsoft.com/fwlink/?LinkID=117794)と[ http://crl.microsoft.com/pki/crl/products/CodeSignPCA2.crl ](http://go.microsoft.com/fwlink/?LinkId=117795) (http://go.microsoft.com/fwlink/?LinkId=117795)します。  
  
2. CodeSignPCA.crl と CodeSignPCA2.crl のファイルを分離されたシステムに移動します。  
  
3. コマンド プロンプトで、certutil ユーティリティを使用して、手順 1. でダウンロード、CRL のローカル証明書ストアを更新する次のコマンドを入力します。  
  
    certutil –addstore CA c:\CodeSignPCA.crl  
  
   CRL ファイルは、ダウンロードの繰り返しのタスクを設定する必要があり、更新、CRL をインストールするため、定期的に更新されます。 次の更新時刻の表示を .crl ファイルをダブルクリックしての値を表示、 **[次へ] を更新**フィールド。  
  
## <a name="synchronize-time-on-all-servers"></a>すべてのサーバー上の時刻を同期します。  
 チケットに関連する多くの操作では、配信確認メッセージとログ記録は、正確なされているローカル システム クロックに依存します。 これはシステムの間に不一致がログを同期または期限切れとして別に拒否される 1 つのシステムによって発行されたチケットを発生可能性があります、分散環境で特にまたは有効化されていません。  
  
 時刻を自動的に同期するサーバーの設定の詳細については、次を参照してください。[自動ドメイン時刻の同期用のクライアント コンピューターを構成](http://go.microsoft.com/fwlink/?LinkId=99420)(http://go.microsoft.com/fwlink/?LinkId=99420)します。  
  
## <a name="configure-the-windows-pagefile-for-optimal-performance"></a>最適なパフォーマンス、Windows ページファイルを構成します。  
 最適なパフォーマンスには、Windows ページファイル (ページング ファイル) を構成する次のガイドラインに従います。  
  
1.  **ページング ファイルをディスクの競合を削減し、ディスクのパフォーマンスを向上させる、オペレーティング システムがインストールされている物理ドライブから別の物理ボリュームを移動**- BizTalk Server コンピューター、移動に関連するパフォーマンスの向上、ページング ファイルは、ドキュメント処理の負荷によって異なります。 SQL Server のコンピューターで、ページング ファイルを別のボリュームに移動するが、SQL Server のディスクの処理を要する性質により、すべてのシナリオでのベスト プラクティスと見なされます。  
  
2.  **1 つまたは複数専用物理ドライブには、RAID 0 (ストライピング) または RAID 1 (ミラー) の配列のいずれかとして、または RAID でない 1 つのディスク上に構成されているページング ファイルの分離**- 専用のディスクまたはドライブの配列を使用して、ページファイル。SYS は唯一のファイル ボリューム全体で、ページング ファイルは断片化がパフォーマンスが向上します。 ほとんどのディスク配列と同様、配列内の物理ディスクの数が増加するにつれて、配列のパフォーマンスが向上しました。 ページング ファイルはディスク アレイで複数の物理ドライブ上の複数のボリューム間で分散している場合、ページング ファイルのサイズが、配列内の各ドライブ上の同じサイズにあります。 ディスク アレイを構成するときに容量と速度が同じである物理ドライブを使用するもお勧めします。 冗長性がページング ファイルは通常必要でないことに注意してください。  
  
3.  **RAID 5 アレイ上のページング ファイルを構成しない**-集中的に使用し、RAID 5 アレイがより適切な読み取りパフォーマンスの書き込みのパフォーマンスよりも書き込みファイルのアクティビティをページングするため、RAID 5 アレイ上のページング ファイルの構成は推奨されません。  
  
4.  **オペレーティング システムをインストールする以外の物理ボリュームにページング ファイルを移動するリソースがない、構成、オペレーティング システムと同じ論理ボリューム上に存在するページング ファイル**の上に存在するページング ファイルの構成、オペレーティング システムはディスクを増やすと、同じ物理ディスク上にある別の論理ボリュームのシーク時間とシステムのパフォーマンスが低下するようにディスク ドライブのプラッター ヘッドが、ボリューム、またはページのファイルにアクセスする間継続的に移動します。オペレーティング システム ファイル、アプリケーション ファイル、およびデータ ファイル。 また、オペレーティング システムは通常、これは通常、最も近い物理ディスクの外側の物理ディスクの最初のパーティションにインストールし、ディスク速度し、パフォーマンスに関連するには、ディスクに最適なします。  
  
    > [!IMPORTANT]  
    >  Windows がブート パーティションからページング ファイルを削除しないで場合に、クラッシュ ダンプ ファイル (メモリを作成できません。DMP) すると、カーネル モードを停止するデバッグ情報の書き込みでエラーが発生します。 クラッシュ ダンプ ファイルが必要なかどうかは、ことはありませんが、少なくとものページング ファイルのままにするオプション、ブート パーティション上の物理メモリ + 1 MB のサイズ。  
  
5.  **ページング ファイルのサイズを手動で設定**-手動でサイズを自動的にサーバーを許可またはページング ファイルをまったくがないよりも優れたパフォーマンスを提供する通常のページング ファイルのサイズを設定します。 チューニングのベスト プラクティスは、同じ値を初期 (最小) と、ページング ファイルの最大サイズ設定を設定します。 これにより、処理リソースが多く消費できるページング ファイルの動的なサイズ変更に失われないこと。 これは、システムのメモリ リソースが既に制限になるときに通常このサイズ変更アクティビティが発生したことに特に当てはまります。 値がディスクにページング領域は、ディスクの向上、1 つ、1 つの連続した領域を確認しても、同一の最小と最大のページ ファイル サイズのシークの時刻を設定します。 Windows Server 2008 には、自動的にインストールされている RAM の容量の 1.5 倍に等しい合計ページング ファイル サイズがお勧めします。 十分なディスク領域のサーバーでは、最適なパフォーマンスを 2 倍の物理メモリまで組み合わせるすべてのディスクにページング ファイルを構成してください。  
  
## <a name="remove-cpu-intensive-screen-savers"></a>CPU 負荷の高いスクリーン セーバーを削除します。  
 CPU 負荷の高い実行されている場合は、重要なシステム リソースを使用でき、3 D や OpenGL スクリーン セーバーが呼ばれます。 サーバー ビルド時に、オプションとして、これらすべてをインストールしないようにして、またはインストールされている場合は、それらを削除するにはお勧めします。 基本的な"Windows Server 2008"または空のスクリーン セーバーは、CPU を消費するスクリーン セーバーを使用して優れた代替機能です。  
  
## <a name="see-also"></a>参照  
 [オペレーティング システムのパフォーマンスの最適化](../technical-guides/optimizing-operating-system-performance.md)