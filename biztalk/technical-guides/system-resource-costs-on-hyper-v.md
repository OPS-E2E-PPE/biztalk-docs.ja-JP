---
title: "HYPER-V のシステム リソース コスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f25a76c-1c41-41c0-b28d-d7473dbe1cd1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20f9707b8606e64773d42c480735d3f876f1c3ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="system-resource-costs-on-hyper-v"></a>HYPER-V のシステム リソースのコスト
## <a name="system-resource-costs-associated-with-running-a-guest-operating-system-on-hyper-v"></a>HYPER-V でゲスト オペレーティング システムを実行しているに関連付けられたシステム リソースのコスト  
 すべてのサーバー仮想化ソフトウェアは、一定のオーバーヘッドが HYPER-V で実行されているゲスト オペレーティング システムをサポートするために必要な仮想化のコードの実行に関連付けられています。 次の一覧は、HYPER-V 仮想マシンでゲスト オペレーティング システムを実行すると、特定のリソースに関連するオーバーヘッドをまとめたものです。  
  
### <a name="cpu-overhead"></a>CPU のオーバーヘッド  
 9 ~ 12% の範囲に、HYPER-V 仮想マシンでゲスト オペレーティング システムを実行しているにオーバーヘッドが関連付けられている CPU が見つかりました。  たとえば、通常、HYPER-V 仮想マシンで実行されているゲスト オペレーティング システムには、物理ハードウェア上で実行されている対応するオペレーティング システムに使用できる CPU リソースの使用可能な 88 91% が必要があります。  
  
### <a name="memory-overhead"></a>メモリのオーバーヘッド  
 約 300 MB、ハイパーバイザーと最初 GB の RAM が、各仮想マシンに割り当てられるに 32 MB ともう 1 つの 8 MB である、HYPER-V ホスト コンピューターに HYPER-V 仮想マシンでゲスト オペレーティング システムを実行しているに関連付けられているメモリ コストが検出されましたすべて追加 GB の RAM の各仮想マシンに割り当てられています。 HYPER-V 仮想マシンで実行されているゲスト オペレーティング システムにメモリの割り当てに関する詳細についてを参照してください「メモリのパフォーマンスを最適化する」[チェックリスト: HYPER-V でのパフォーマンスの最適化](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)です。  
  
### <a name="network-overhead"></a>ネットワークのオーバーヘッド  
 ネットワーク待機時間が検出された HYPER-V 仮想マシンでゲスト オペレーティング システムを実行しているに起因する直接 1 未満である ms、およびゲスト オペレーティング システムは通常維持未満である 1 つのネットワークの出力キューの長さ。 詳細については、ネットワークの出力キューの長さの測定についてを参照してください「ネットワークのパフォーマンスを測定する」[チェックリスト: HYPER-V でのパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)です。  
  
### <a name="disk-overhead"></a>ディスクのオーバーヘッド  
 HYPER-V では、パススルー ディスク機能を使用して、ディスク I/O のオーバーヘッドが HYPER-V 仮想マシンでゲスト オペレーティング システムを実行しているに関連付けられているが 6 ~ 8% の範囲が判明しました。 たとえば、通常の HYPER-V で実行されているゲスト オペレーティング システムには、ディスク ベンチマーク ツール IOMeter オープン ソースのディスクのパフォーマンスで測定された物理ハードウェア上で実行されている対応するオペレーティング システムを使用可能な I/O の使用可能な 92 94% が必要があります。  
  
 パフォーマンス モニターを使用して HYPER-V ホストまたはゲスト オペレーティング システム上のディスク待機時間の計測については、「ディスク I/O パフォーマンスの測定」セクションを参照してください。[チェックリスト: Hyper-v でパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)です。  
  
 このセクションの残りの部分は、ディスクのパフォーマンスを BizTalk Server の背景情報を提供、テスト構成パラメーターを使用するを説明し、得られたテスト結果の概要を示します。  
  
#### <a name="disk-performance-when-running-a-biztalk-server-solution-on-hyper-v"></a>HYPER-V で、BizTalk Server ソリューションを実行している場合、ディスク パフォーマンス  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]非常に高くデータベース処理を要するアプリケーションの SQL Server での最大 13 個のデータベースの作成が必要な場合があります。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]優れた頻度でデータをディスクが引き続き発生して、さらに、MSDTC トランザクションのコンテキスト内で処理が実行します。 そのため、データベースのパフォーマンスは、BizTalk Server ソリューションの全体的なパフォーマンスが非常に重要です。 HYPER-V は統合 SCSI コント ローラーを提供し、Virtual Server 2005 の両方を提供するパフォーマンスが大幅などを使用して、エミュレートされた IDE デバイス経由で IDE フィルター ドライバーを提供します。  
  
 SCSI コント ローラーを使用して、データ ボリュームのディスクを構成します。 これにより、SCSI コント ローラーは、HYPER-V 統合サービスをインストールしなくても、エミュレートされた IDE コント ローラーは使用可能な HYPER-V 統合サービスがインストールされている場合にのみインストールするため、統合サービスがインストールされていることが保証されます。 SCSI コント ローラーまたは integration services に用意されている IDE フィルター ドライバーを使用して実行されるディスク I/O は、ディスク I/O のパフォーマンスをエミュレートされた IDE コント ローラーに用意されているよりも大幅に向上します。 そのため、最適なディスク I/O パフォーマンス、HYPER-V 仮想化環境でデータ ファイルには、ホストとゲストの両方のオペレーティング システムに統合サービスをインストールし、合成の SCSI コント ローラーとデータ ボリュームのディスクを構成します。 高負荷の高いストレージの I/O ワークロードの複数のデータ ドライブに配置されている場合に、全体的なパフォーマンスを向上させるため代理個別の SCSI コント ローラーに各 VHD をアタッチする必要があります。 さらに、各 VHD は、個別の物理ディスクまたは Lun に保存する必要があります。  
  
#### <a name="measuring-passthrough-disk-performance"></a>パススルー ディスクのパフォーマンスの測定  
 任意の統合手順中には、使用可能なリソースを最大限に使用する必要があります。 前述のように、SQL データ ボリューム上の記憶域 I/O がの全体的なパフォーマンスがかなりの部分を再生する[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ソリューションです。 そのため、このガイドの一部として hyper-v パススルー ディスクのパフォーマンスへの物理ディスクの相対的なパフォーマンスをテストしました。 Physical_SQL01 におけるメッセージ ボックス データの相対的なパフォーマンスを向上し、Virtual_SQL01 を使用して測定 IOMeter オープン ソース ツールでは、Intel Corporation によって開発されたおよび保持されるようになりましたが、オープン ソース開発ラボ (OSDL)。 IOMeter の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=122412](http://go.microsoft.com/fwlink/?LinkId=122412)です。  
  
 次の表では、テスト環境、使用された IOMeter 構成オプションで、実行されたテストの説明を結果の概要で使用される物理および仮想のハードウェア構成について説明します。  
  
#### <a name="configuration-used-for-testing"></a>テストするために使用される構成  
  
### <a name="physicalsql01"></a>Physical_SQL01  
  
|||  
|-|-|  
|**[モデル]**|HP DL580|  
|**プロセッサ**|2.4 Ghz クアッド コア Intel Xeon クアッド プロセッサ|  
|**[メモリ]**|8 GB|  
|**ネットワー キング**|HP NC3T3i 多機能ギガビット Server アダプター|  
|**SAN の構成**|直接には、SAN 記憶域が接続されている (次の表を参照してください)|  
  
### <a name="physicalsql01--san-configuration"></a>Physical_SQL01 – SAN の構成  
  
|ドライブ文字|Description|LUN のサイズ|RAID 構成|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|私：|Data_TempDb|50|RAID 0 + 1|  
|-J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
### <a name="hyper-vhostsql01"></a>ハイパー V_Host_SQL01  
  
|||  
|-|-|  
|**[モデル]**|HP DL580|  
|**プロセッサ**|2.4 Ghz クアッド コア Intel Xeon クアッド プロセッサ|  
|**[メモリ]**|32 GB|  
|**ネットワー キング**|Broadcom BCM5708C NetXtreme II GigEHP DL380 G5|  
  
### <a name="virtualsql01---virtual-machine-configuration"></a>Virtual_SQL01 - 仮想マシンの構成  
  
|||  
|-|-|  
|**仮想プロセッサ**|割り当てられている 4|  
|**[メモリ]**|8 GB|  
|**ネットワー キング**|仮想マシンはネットワークに接続されています。<br />Broadcom BCM5708C NetXtreme II GigE|  
|**ハード_ディスク上の構成**|**IDE コント ローラー** – 30 GB のオペレーティング システムの vhd を修正しました。<br />**SCSI コント ローラー** -7 直接接続されたパススルー SAN の Lun (次の表を参照してください)|  
  
### <a name="virtualsql01--san-configuration"></a>Virtual_SQL01 – SAN の構成  
  
|ドライブ文字|Description|LUN のサイズ|RAID 構成|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|私：|Data_TempDb|50|RAID 0 + 1|  
|-J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
#### <a name="iometer-configuration"></a>IOMeter の構成  
 IOMeter ツールは、アプリケーションの読み取り/書き込みのパフォーマンスをレプリケートすることによって、ベンチマークおよびトラブルシューティング ツールとして使用できます。 IOMeter は、さまざまな種類のパフォーマンスをシミュレートするために使用できる構成可能なツールです。 両方物理に関する次の表で説明した、IOMeter 構成パラメーターの設定のこのテスト シナリオの目的で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]がテストされているコンピューターで、ゲスト オペレーティング システムを実行していた[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]HYPER-V 仮想マシンで:  
  
### <a name="iometer--passthrough-disk-comparison-test-configuration"></a>IOMeter – パススルー ディスクの比較テストの構成  
  
|||  
|-|-|  
|**テスト時間の長さ**|10 分|  
|**ごとの傾斜増加時間を**|30 秒|  
|**ワーカーの数**|4|  
|**転送要求のサイズ**|2 KB|  
|**読み取り/書き込みの配布**|66% を読み取り、33% 書き込み|  
|**長さをバーストします。**|1 の i/o 数|  
|**対象となるドライブ**|K:\|  
  
#### <a name="test-description"></a>テストの説明  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] IOMeter 唯一のプロセスに対して、ディスク I/O を実行することを確認する両方のサーバーでサービスが停止します。 LUN が使用このテストの両方に配置されていたが、このラボ環境に専用の同じ SAN にします。 テストの結果が歪曲がないことを確認中に、SAN に対するその他の I/O アクティビティが実行されません。 それぞれから IOMeter ツールをローカルで実行してテストを実行し、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]次のパフォーマンス モニター カウンターが収集されたとします。  
  
 **Virtual_SQL01 と Physical_SQL01 の両方から収集した**:  
  
-   \LogicalDisk(*)\\\*  
  
-   \PhysicalDisk(*)\\\*  
  
 **ハイパースレッディング V_02 のバーチャル マシンから収集された**:  
  
-   \Hyper-V 仮想記憶域デバイス\\*  
  
### <a name="results"></a>[結果]  
 パススルー ディスクは、以上の Physical_SQL01 に直接接続されている SAN LUN のスループットの 90% を活かすことができます。  合計、読み書き可能な 1 秒あたりに転送された合計 MB と同様に、1 秒あたりの i/o 数が 10% 以内のすべてがします。  異常な状態のディスクの応答時間は、1 ~ 15 ミリ秒の読み取りと書き込みの間にする必要があります。 平均 I/O 反応時間は、両方のディスクに 4 ミリ秒未満でした。 応答時間のランダムな読み取りは、物理とパススルー ディスク上の 5.7 ms 5.4 ミリ秒でした。 応答の書き込み時間は、物理および仮想の両方の環境で 0.5 ミリ秒より小さいをでした。  
  
 結果は、直接接続された物理ディスクのパフォーマンスの 90% 以上の対応の SCSI コント ローラーを使用して、パススルー ディスク番号をことができます提供を示します。 I/O サブシステムのパフォーマンスが重要で効率的な[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]操作では優れたスループットと応答時間を提供する HYPER-V はうってつけの統合、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]環境。 次の表では、物理ディスクへのパススルー ディスクのパフォーマンスを比較するときに計測されたディスクのテスト結果の概要を示します。  
  
|測定|Physical_SQL01 (物理ディスク)|Virtual_SQL01 (パススルー)|物理ディスクへのパススルー ディスクの相対的なパフォーマンス|  
|-----------------|---------------------------------------|------------------------------------|-----------------------------------------------------------------|  
|1 秒あたりの合計 i/o 数|269.73|250.47|92.86%|  
|1 秒あたりの読み取り i/o 数|180.73|167.60|92.74%|  
|1 秒あたりの書き込み I/o|89.00|82.87|93.11%|  
|1 秒あたりの合計 Mb|0.53|0.49|92.45%|  
|平均応答時間 (ミリ秒) の読み取り|5.4066|5.7797|93.54%|  
|書き込みの平均応答時間 (ミリ秒)|0.2544|0.3716|68.42%**注:**パススルー ディスクの書き込みの平均応答時間がまだ内でもはパス スルー ディスクの書き込みの平均応答時間の相対的なパフォーマンスでは、物理ディスクのパフォーマンスの 68.42% でしたが、10 ミリ秒の許容範囲を確立します。|  
|I/O の平均応答時間 (ミリ秒)|3.7066|3.9904|93.89%|  
  
> [!NOTE]  
>  1 秒あたりの合計 i/o 数、1 秒あたりの読み取り i/o 数、1 秒あたりの I/o の書き込みおよび 1 秒あたりの合計 Mb の割合の値が、対応する物理ディスクの値をパススルー ディスクの値で割ることによって計算されます。  
>   
>  平均の平均割合の値は、応答時間 (ミリ秒) を読み取り、応答時間 (ミリ秒) を記述し、I/O の平均応答時間 (ミリ秒) が、対応するパススルー ディスク値で物理ディスクの値で割ることによって計算します。