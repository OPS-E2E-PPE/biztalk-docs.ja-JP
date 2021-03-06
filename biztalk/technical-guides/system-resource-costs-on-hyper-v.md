---
title: HYPER-V のシステム リソース コスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f25a76c-1c41-41c0-b28d-d7473dbe1cd1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 768b34b6b1a51768f1c0070c961749e1975015f9
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753058"
---
# <a name="system-resource-costs-on-hyper-v"></a>HYPER-V のシステム リソース コスト
## <a name="system-resource-costs-associated-with-running-a-guest-operating-system-on-hyper-v"></a>HYPER-V でゲスト オペレーティング システムを実行に関連付けられているシステム リソース コスト  
 任意のサーバー仮想化ソフトウェアと同様、一定量の HYPER-V で実行されているゲスト オペレーティング システムをサポートするために必要な仮想化コードの実行に関連するオーバーヘッドがあります。 次の一覧は、HYPER-V 仮想マシンでゲスト オペレーティング システムを実行すると、特定のリソースに関連するオーバーヘッドをまとめたものです。  
  
### <a name="cpu-overhead"></a>CPU のオーバーヘッド  
 9 ~ 12% の範囲を HYPER-V 仮想マシンでゲスト オペレーティング システムを実行にオーバーヘッドが関連付けられている CPU が見つかりました。  たとえば、通常、HYPER-V 仮想マシンで実行されているゲスト オペレーティング システムには、対応する物理ハードウェアで実行されているオペレーティング システムで使用できる CPU リソースの使用可能な 88 91% が必要があります。  
  
### <a name="memory-overhead"></a>メモリのオーバーヘッド  
 HYPER-V ホスト コンピューターの HYPER-V 仮想マシンでゲスト オペレーティング システムを実行に関連付けられているメモリのコストが、ハイパーバイザーの約 300 MB に加えて 32 MB、最初 GB の ram を各仮想マシンに割り当てられているともう 1 つの 8 MB にする監視すべて追加 GB の ram を各仮想マシンに割り当てられています。 HYPER-V 仮想マシンで実行されているゲスト オペレーティング システムにメモリの割り当ての詳細については、「メモリのパフォーマンスの最適化」セクションを参照してください。[チェックリスト: hyper-v のパフォーマンスの最適化](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)します。  
  
### <a name="network-overhead"></a>ネットワークのオーバーヘッド  
 検出された HYPER-V 仮想マシンでゲスト オペレーティング システムを実行していることに起因する直接のネットワーク待機時間 1 未満にする ms とゲスト オペレーティング システムは通常維持 1 未満のネットワークの出力キューの長さ。 ネットワークの出力キューの長さを測定する詳細については、「ネットワーク パフォーマンスを測定する」セクションを参照してください。[チェックリスト: Hyper-v パフォーマンスを測定する](../technical-guides/checklist-measuring-performance-on-hyper-v.md)します。  
  
### <a name="disk-overhead"></a>ディスクのオーバーヘッド  
 パススルー ディスクの機能を使用して、HYPER-V で、ディスクに関連付けられた、HYPER-V 仮想マシンでゲスト オペレーティング システムを実行している I/O オーバーヘッドが 6 ~ 8% の範囲が判明しました。 たとえば、通常、HYPER-V で実行されているゲスト オペレーティング システムには、ディスクでベンチマーク ツール IOMeter オープン ソースのディスクのパフォーマンス測定された物理ハードウェアで実行されている同等のオペレーティング システムに使用可能な I/O の使用可能な 92 94% が必要があります。  
  
 パフォーマンス モニターを使用して、HYPER-V ホストまたはゲスト オペレーティング システム上のディスク待機時間の計測については、「ディスク I/O パフォーマンスの測定」のセクションを参照してください。[チェックリスト: Hyper-v パフォーマンスを測定する](../technical-guides/checklist-measuring-performance-on-hyper-v.md)します。  
  
 このセクションの残りの部分は、ディスクのパフォーマンスを BizTalk Server の背景情報を提供します、使用すると、テスト構成パラメーターをについて説明し、得られたテスト結果の概要を示します。  
  
#### <a name="disk-performance-when-running-a-biztalk-server-solution-on-hyper-v"></a>Hyper V 上の BizTalk Server ソリューションを実行している場合、ディスク パフォーマンス  
 BizTalk Server は、非常にデータベース処理を要するアプリケーションで SQL Server の最大 13 個のデータベースを作成することがあります。 BizTalk Server では、優れた頻度でディスクにデータを永続化し、さらに、MSDTC トランザクションのコンテキスト内では。 したがって、データベースのパフォーマンスは、BizTalk Server ソリューションの全体的なパフォーマンスが非常に重要です。 HYPER-V は統合 SCSI コント ローラーを提供し、両方を提供する大幅なパフォーマンス上の利点をエミュレートした IDE デバイスを使用して IDE フィルター ドライバーは Virtual Server 2005 に付属します。  
  
 SCSI コント ローラーを使用してデータ ボリュームのディスクを構成します。 これにより、SCSI コント ローラーが、エミュレートされた IDE コント ローラーで、HYPER-V 統合サービスをインストールせずに、HYPER-V 統合サービスがインストールされている場合にのみインストールできる統合サービスがインストールされていることが保証されます。 SCSI コント ローラーまたは integration services で提供される IDE フィルター ドライバーのいずれかを使用して実行するディスク I/O、ディスク I/O パフォーマンスがエミュレートされた IDE コント ローラーで提供されるよりも大幅に向上します。 そのため、最適なディスクを HYPER-V 仮想環境でのデータ ファイルの I/O パフォーマンスを確保するには、ホストとゲストの両方のオペレーティング システムに統合サービスをインストールし、統合 SCSI コント ローラーとデータ ボリュームのディスクを構成します。 複数のデータ ドライブにまたがる高負荷の高いストレージ I/O ワークロードでは、全体的なパフォーマンスを向上させる統合独立した SCSI コント ローラーに各 VHD をアタッチする必要があります。 さらに、別の物理ディスクまたは Lun の各 VHD を格納する必要があります。  
  
#### <a name="measuring-passthrough-disk-performance"></a>パススルー ディスクのパフォーマンスを測定します。  
 任意の統合手順中には、使用可能なリソースを最大限に活用してください。 前述のように、SQL データ ボリュームに記憶域 I/O は、BizTalk Server ソリューションの全体的なパフォーマンスでかなりの部分を再生します。 そのため、このガイダンスの一部として、HYPER-V でのパススルー ディスクのパフォーマンスに物理ディスクの相対的なパフォーマンスをテストしました。 メッセージ ボックス データの相対的なパフォーマンスの Physical_SQL01 ドライブし、Virtual_SQL01 を測定したオープン ソース ツールの Intel Corporation によって開発された、保持されるようになりました IOMeter を使用して、オープン ソース開発ラボ (OSDL)。 IOMeter の詳細については、[ http://go.microsoft.com/fwlink/?LinkId=122412](http://go.microsoft.com/fwlink/?LinkId=122412)を参照してください。  
  
 次の表では、テスト環境、IOMeter 構成オプションを使用した、結果の概要と、実行されたテストの説明で使用される物理および仮想ハードウェアの構成について説明します。  
  
#### <a name="configuration-used-for-testing"></a>テストするために使用される構成  
  
### <a name="physicalsql01"></a>Physical_SQL01  
  
|||  
|-|-|  
|**[モデル]**|HP DL580|  
|**プロセッサ**|クアッド コア Intel Xeon 2.4 Ghz のクアッド プロセッサ|  
|**[メモリ]**|8 GB|  
|**ネットワー キング**|HP NC3T3i 多機能ギガビット Server アダプター|  
|**SAN の構成**|Direct には、SAN 記憶域が接続されている (次の表を参照してください)|  
  
### <a name="physicalsql01--san-configuration"></a>Physical_SQL01 – SAN の構成  
  
|ドライブ文字|説明|LUN のサイズ|RAID の構成|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|私：|Data_TempDb|50|RAID 0 + 1|  
|J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
### <a name="hyper-vhostsql01"></a>Hyper-V_Host_SQL01  
  
|||  
|-|-|  
|**[モデル]**|HP DL580|  
|**プロセッサ**|クアッド コア Intel Xeon 2.4 Ghz のクアッド プロセッサ|  
|**[メモリ]**|32 GB|  
|**ネットワー キング**|Broadcom BCM5708C NetXtreme II GigEHP DL380 G5|  
  
### <a name="virtualsql01---virtual-machine-configuration"></a>Virtual_SQL01 - 仮想マシンの構成  
  
|||  
|-|-|  
|**仮想プロセッサ**|割り当てられた 4|  
|**[メモリ]**|8 GB|  
|**ネットワー キング**|仮想マシンはネットワークに接続されています。<br />Broadcom BCM5708C NetXtreme II GigE|  
|**ハード_ディスク上の構成**|**IDE コント ローラー** – 30 GB のオペレーティング システムの vhd を固定<br />**SCSI コント ローラー** -7 に直接 (次の表を参照してください)、パススルー SAN Lun が接続されています。|  
  
### <a name="virtualsql01--san-configuration"></a>Virtual_SQL01 – SAN の構成  
  
|ドライブ文字|説明|LUN のサイズ|RAID の構成|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|私：|Data_TempDb|50|RAID 0 + 1|  
|J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
#### <a name="iometer-configuration"></a>IOMeter の構成  
 IOMeter ツールは、アプリケーションの読み取り/書き込みのパフォーマンスをレプリケートすることによって、ベンチマークとトラブルシューティング ツールとして使用できます。 IOMeter は、さまざまな種類のパフォーマンスをシミュレートするために使用できる構成可能なツールです。 両方の物理に関する次の表で説明した、IOMeter 構成パラメーターの設定このテスト シナリオのために、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]テストされたコンピューターと、ゲスト オペレーティング システムを実行していた[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンで:  
  
### <a name="iometer--passthrough-disk-comparison-test-configuration"></a>IOMeter – パススルー ディスクの比較テストの構成  
  
|                             |                     |
|-----------------------------|---------------------|
|       **テスト時間の長さ**       |     10 分      |
|      **ランプ アップ時間**       |     30 秒      |
|    **ワーカーの数**    |          4          |
|  **転送要求のサイズ**  |        2 KB         |
| **読み取り/書き込みの配布** | 66% の読み取り、書き込みの 33% |
|      **バーストの長さ**       |       1 つの I/o        |
|      **ターゲット ドライブ**       |         K:\         |
  
#### <a name="test-description"></a>テストの説明  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] IOMeter が唯一のプロセスに対するディスク I/O を実行することを確認する両方のサーバーでサービスが停止されました。 LUN が使用このテストの両方に配置されていたこのラボ環境に専用が同じ SAN です。 テストの結果が傾斜がないことを確認中に、SAN に対するその他の I/O アクティビティが実行されません。 各 IOMeter ツールをローカルで実行することによって、テストの実行し、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]次のパフォーマンス モニター カウンターが収集されたとします。  
  
 **Virtual_SQL01 と Physical_SQL01 の両方から収集された**:  
  
- \LogicalDisk (\*)\\\*  
  
- \PhysicalDisk (\*)\\\*  
  
  **ハイパースレッディング V_02 の仮想マシンから収集された**:  
  
- \\HYPER-V 仮想ストレージ デバイス\\\*  
  
### <a name="results"></a>[結果]  
 パススルー ディスクを超える Physical_SQL01 に直接接続されている SAN LUN のスループットの 90% を実現できました。  合計、読み取りと 1 秒あたりの書き込み I/o が 10% 以内のすべてが 1 秒あたりに転送された合計 (mb)。  1 ~ 15 ミリ秒の読み取りと書き込みの間に正常なディスクの応答時間があります。 平均 I/O 応答時間は、両方のディスクに 4 ミリ秒未満でした。 ランダム読み取りの応答時間には、物理と 5.7 ms パススルー ディスク上の 5.4 のミリ秒でした。 書き込みの応答時間は、物理および仮想環境の両方で 0.5 ミリ秒未満でした。  
  
 結果は、対応の SCSI コント ローラーを使用するパススルー ディスクが以上に直接接続されている物理ディスクのパフォーマンスの 90% で提供できることを示します。 I/O サブシステムのパフォーマンスが重要では、BizTalk Server を効率的に操作するには、優れたスループットと応答時間を提供することで、HYPER-V は優秀な候補、BizTalk Server 環境を統合することです。 次の表では、パススルー ディスクを物理ディスクのパフォーマンスを比較するときに、ディスクのテスト結果の概要が観察されたを示します。  
  
|測定|Physical_SQL01 (物理ディスク)|Virtual_SQL01 (パススルー)|物理ディスクへのパススルー ディスクの相対的なパフォーマンス|  
|-----------------|---------------------------------------|------------------------------------|-----------------------------------------------------------------|  
|1 秒あたりの合計 i/o 数|269.73|250.47|92.86%|  
|1 秒あたりの読み取り I/o|180.73|167.60|92.74%|  
|1 秒あたりの書き込み I/o|89.00|82.87|93.11%|  
|1 秒あたりの合計 Mb|0.53|0.49|92.45%|  
|平均応答時間 (ミリ秒) の読み取り|5.4066|5.7797|93.54%|  
|書き込みの平均応答時間 (ミリ秒)|0.2544|0.3716|68.42%**注:** パススルー ディスクの書き込みの平均応答時間がも内がパス スルー ディスクの書き込みの平均応答時間の相対的なパフォーマンスでは、物理ディスクのパフォーマンスの 68.42% でしたが、10 ミリ秒未満の許容範囲を確立します。|  
|I/O の平均応答時間 (ミリ秒)|3.7066|3.9904|93.89%|  
  
> [!NOTE]  
>  1 秒あたりの合計 i/o 数、1 秒あたりの読み取り I/o、1 秒あたりの I/o の書き込み、合計 Mb/秒単位の割合の値が、対応する物理ディスクの値をパススルー ディスクの値を除算して計算されます。  
>   
>  平均の平均割合の値は、応答時間 (ミリ秒) を読み取り、応答時間 (ミリ秒) を記述し、対応するパススルー ディスクの値で物理ディスクの値を除算して平均 I/O 応答時間 (ミリ秒) が計算されます。