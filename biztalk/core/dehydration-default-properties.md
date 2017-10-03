---
title: "既定の退避プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68c59def-d73b-4880-9884-ccbe5d982f4b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff78b1e096f1a73675ffc02550794f5a300f5614
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="dehydration-default-properties"></a>既定の退避プロパティ
退避プロパティの名前とその既定値は次のとおりです。 これらのプロパティは、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用するか、または XML として BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) で構成可能です。 BizTalk 構成ファイルの値が先に適用されます。 次に、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] の設定が適用されます。 退避プロパティは、オーケストレーションを含んでいるすべてのホスト インスタンスの開始時に読み取られます。  
  
> [!IMPORTANT]
>  すべてのオーケストレーション設定が [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] で公開されているわけではありません。 これらの設定については、BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) が使用されます。 BizTalk 構成ファイルを使用する場合、多くのプロパティは一覧に表示されません。 これらのプロパティおよび既定値は、構成ファイルで明示的に指定されていない場合でも常に適用されています。  
  
 既定値を変更するには、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用するか、BizTalk 構成ファイルに明示的に追加します。 詳細については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)と[BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)です。  
  
 **退避**  
  
-   **MaxThreshold** 1800 を =  
  
-   **MinThreshold** = 1  
  
-   **ConstantThreshold** -1 を =  
  
 **VirtualMemoryThrottlingCriteria**  
  
-   **OptimalUsage** 900 を =  
  
-   **MaximalUsage** 1300 を =  
  
-   **IsActive** = true  
  
 **PrivateMemoryThrottlingCriteria**  
  
-   **OptimalUsage** 50 を =  
  
-   **MaximalUsage** 350 を =  
  
-   **IsActive** = true  
  
 **PhysicalMemoryThrottlingCriteria**  
  
-   **OptimalUsage** = 90  
  
-   **MaximalUsage** 95 を =  
  
-   **IsActive** = false  
  
 次に、これらの各プロパティについて詳しく説明します。  
  
## <a name="dehydration"></a>退避  
 **MaxThreshold**と**MinThreshold**が、上限と下限で退避されるまで (つまり、受信、待ち受け、または遅延によってブロックされている) サブスクリプションでオーケストレーションがブロックされている時間 (秒)。 あります値呼び出されて、実行時に計算**TestThreshold**、秒単位で、その値は、間と**MinThreshold**と**MaxThreshold**です。  
  
 既定の-1 以外の値を設定するかどうかは**ConstantThreshold**、実行時値されません**TestThreshold**です。 ときに、サブスクリプションでオーケストレーションがブロックされているし、そのサブスクリプションでそのオーケストレーションのすべてのインスタンスがブロックされた時間の履歴がの値より大きい**TestThreshold**オーケストレーションは、退避します。 それ以外の場合は、履歴はより小さい**TestThreshold**値は、オーケストレーションは退避されません。 また、場合でも、履歴を示します、退避は行われません、現在のブロック時間が 2 に達すると ***TestThreshold**、退避が行われます。 履歴は秒単位の最後の 10 待機時間の平均、または、待機時間の数が 10 未満の場合は履歴内に存在する待機時間の数の平均によって定義されます。  
  
 ときに、値の**TestThreshold**に近づく**MinThreshold**メモリ使用量が増加するにつれて、呼び出された「メモリ ベースの退避制限します」。 メモリ ベースの退避制限では、より多くのオーケストレーション インスタンスをライブにできます。これらのインスタンスのいずれかがブロックされて作業を待機 (メッセージの待機または遅延) するとき、これらを退避させたりメモリから消去したりできるためです。 **TestThreshold**単調に減少する関数は、メモリ使用量がメモリ使用量に反比例します。  
  
 次に、Dehydration の各プロパティの説明を示します。  
  
-   **MaxThreshold**: 上限の境界、退避前に、サブスクリプションでオーケストレーションがブロックされている時間 (秒)。  
  
-   **MinThreshold**: 下位の境界、退避前に、サブスクリプションでオーケストレーションがブロックされている時間 (秒)。  
  
-   **ConstantThreshold**: 動的なしきい値は、通常、最小値および最大値の間で変動します。 ただし、このプロパティを設定するとしきい値を固定することができます。 値 -1 は、固定しきい値を使用しないようにエンジンに通知します。 ベースの退避制限が無効になりますので、このプロパティを-1 以外の値に設定しません。  
  
## <a name="virtualmemorythrottlingcriteria"></a>VirtualMemoryThrottlingCriteria  
 現在は、アンマネージ ヒープの断片化のため、仮想メモリが 32 ビット マシンのボトルネックとなる可能性があります。このため、このリソースも制限する必要があります。 /3GB が設定されている場合、またはホストが 64 ビット プラットフォーム上で実行されている場合は、再構成する必要があります。 最適使用量と最大使用量は MB 単位です。  
  
 次に、VirtualMemoryThrottlingCriteria の各プロパティの説明を示します。  
  
-   **OptimalUsage**: 開始位置と退避制限を有効にする仮想メモリ使用量。 この時点では、 **TestThreshold**プロパティ値を持つ**MaxThreshold**と、メモリ使用量を超える**OptimalUsage**により**TestThreshold**するより小さい**MaxThreshold**です。  
  
-   **MaximalUsage**: で退避制限が最大限になった仮想メモリ使用量。 この時点では、 **TestThreshold**プロパティ値を持つ**MinThreshold**とメモリ使用量より小さい**MaximalUsage**により**TestThreshold**大きくなければ**MinThreshold**です。  
  
-   **IsActive**: 仮想メモリの制限がアクティブなかどうかを示すブール値。  
  
## <a name="privatememorythrottlingcriteria"></a>PrivateMemoryThrottlingCriteria  
 このプロパティは制限のために役立つ条件ですが、コンピューター上で他の Windows サービスが実行されているかどうかによって適切な値が異なります。 コンピューターに大量のメモリがあり、他の Windows サービスと共有していない場合、これらの値を大幅に増やすことができます。  
  
 次に、PrivateMemoryThrottlingCriteria の各プロパティの説明を示します。  
  
-   **OptimalUsage**: の mb、開始位置と退避制限を有効にする、プライベート メモリ使用量。 この時点で**TestThreshold**プロパティ値を持つ**MaxThreshold**と、メモリ使用量を超える**OptimalUsage**により**TestThreshold**するより小さい**MaxThreshold**です。  
  
-   **MaximalUsage**: の mb、最大退避制限が、プライベート メモリ使用量。 この時点で**TestThreshold**プロパティ値を持つ**MinThreshold**とメモリ使用量より小さい**MaximalUsage**により**TestThreshold**大きくなければ**MinThreshold**です。  
  
-   **IsActive**: プライベート メモリ制限がアクティブなかどうかを示すブール値。  
  
## <a name="physicalmemorythrottlingcriteria"></a>PhysicalMemoryThrottlingCriteria  
 メモリ使用量を MB 単位ではなくパーセンテージで表す、物理メモリ制限もあります。 このプロパティは既定で無効になっていますが、必要に応じて有効にできます。  
  
 次に、PhysicalMemoryThrottlingCriteria の各プロパティの説明を示します。  
  
-   **OptimalUsage**: ホスト インスタンスに使用する物理メモリの最適なパーセンテージ。  
  
-   **MaximalUsage**: ホスト インスタンスに使用する物理メモリの最大パーセンテージです。  
  
-   **IsActive**: 物理メモリの制限がアクティブなかどうかを示すブール値。  
  
## <a name="dehydration-properties-behavior"></a>退避プロパティの動作  
 BizTalk Server はこれらの退避プロパティを使用して、オーケストレーションをいつ退避および復元するかを決定します。 標準の負荷状態では、既定の復元値で十分です。しかし、負荷が高い状態で実行していてパフォーマンス特性を変更する場合、自分でチューニングを行う必要があります。  
  
 BizTalk Server の復元動作は、使用可能なメモリ量と使用されているメモリ量に完全に依存します。 復元動作は、メモリ量によって異なります。また、32 ビットと 64 ビットのホスト間のメモリ使用の違いによっても異なります。  
  
 復元プロパティでは、オーケストレーション ホストのプライベート バイトと仮想バイトが、次のように識別されます。  
  
-   **仮想バイト**です。 これは、(バイト単位) を使用して、プロセス仮想アドレス空間の現在のサイズです。 仮想アドレス空間を使用していても、ディスク ページまたはメイン メモリ ページを使用しているとは限りません。 仮想空間は有限であり、プロセスではライブラリ読み込み機能を制限できます。  
  
-   **Private Bytes**です。 これは、このプロセスによって割り当てられ、他のプロセスと共有できないメモリの現在のサイズ (バイト単位) です。