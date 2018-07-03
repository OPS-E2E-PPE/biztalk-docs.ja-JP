---
title: 既定の退避プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68c59def-d73b-4880-9884-ccbe5d982f4b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 907bd9f9b47db10a199f5a93a828558dfb3ae210
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981963"
---
# <a name="dehydration-default-properties"></a>既定の退避プロパティ
退避プロパティの名前とその既定値は次のとおりです。 これらのプロパティは、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用するか、または XML として BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) で構成可能です。 BizTalk 構成ファイルの値が先に適用されます。 次に、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] の設定が適用されます。 退避プロパティは、オーケストレーションを含んでいるすべてのホスト インスタンスの開始時に読み取られます。  
  
> [!IMPORTANT]
>  すべてのオーケストレーション設定が [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] で公開されているわけではありません。 これらの設定については、BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) が使用されます。 BizTalk 構成ファイルを使用する場合、多くのプロパティは一覧に表示されません。 これらのプロパティおよび既定値は、構成ファイルで明示的に指定されていない場合でも常に適用されています。  
  
 既定値を変更するには、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用するか、BizTalk 構成ファイルに明示的に追加します。 詳細については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニングを使用して](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)と[BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)します。  
  
 **退避**  
  
- **MaxThreshold** = 1800  
  
- **MinThreshold** = 1  
  
- **ConstantThreshold** =-1  
  
  **VirtualMemoryThrottlingCriteria**  
  
- **OptimalUsage** 900 を =  
  
- **MaximalUsage** 1300 を =  
  
- **IsActive** = true  
  
  **PrivateMemoryThrottlingCriteria**  
  
- **OptimalUsage** = 50  
  
- **MaximalUsage** = 350  
  
- **IsActive** = true  
  
  **PhysicalMemoryThrottlingCriteria**  
  
- **OptimalUsage** = 90  
  
- **MaximalUsage** = 95  
  
- **IsActive** = false  
  
  次に、これらの各プロパティについて詳しく説明します。  
  
## <a name="dehydration"></a>退避  
 **MaxThreshold**と**MinThreshold**上には、下位の境界をオーケストレーションが退避されるまで (つまり、受信、待ち受け、または遅延によってブロックされている) サブスクリプションでブロックされて時間 (秒)。 あります値を実行時に計算される、という**TestThreshold**、秒単位で、その値が**MinThreshold**と**MaxThreshold**します。  
  
 既定の-1 以外の値を設定するかどうかは**ConstantThreshold**、実行時値されません**TestThreshold**します。 サブスクリプションでオーケストレーションがブロックされているし、オーケストレーションのすべてのインスタンスをサブスクリプションでブロックされているどのくらいの期間の履歴がの値より大きい**TestThreshold**オーケストレーションは、退避します。 それ以外の場合、履歴がある場合より小さい**TestThreshold**値は、オーケストレーションは退避されません。 また、場合でも、履歴、退避は行われません、現在のブロック時間が 2 に達する場合を示します<em>**TestThreshold</em>*、退避が行われます。 履歴は秒単位の最後の 10 待機時間の平均、または、待機時間の数が 10 未満の場合は履歴内に存在する待機時間の数の平均によって定義されます。  
  
 ときの値**TestThreshold**に向かって傾向**MinThreshold**メモリ使用量が増加すると呼び出されます「メモリ ベースの退避制限します」。 メモリ ベースの退避制限では、より多くのオーケストレーション インスタンスをライブにできます。これらのインスタンスのいずれかがブロックされて作業を待機 (メッセージの待機または遅延) するとき、これらを退避させたりメモリから消去したりできるためです。 **TestThreshold**が 1 ずつ減少関数のメモリ使用量、メモリ使用量に反比例します。  
  
 次に、Dehydration の各プロパティの説明を示します。  
  
-   **MaxThreshold**: オーケストレーションが退避される前に、サブスクリプションでブロックされて時間 (秒) の上限。  
  
-   **MinThreshold**: オーケストレーションが退避される前に、サブスクリプションでブロックされて時間 (秒) の下限。  
  
-   **ConstantThreshold**: 動的なしきい値は、通常、指定した最小値と最大値の間で変動します。 ただし、このプロパティを設定するとしきい値を固定することができます。 値 -1 は、固定しきい値を使用しないようにエンジンに通知します。 ベースの退避制限が無効になりますので、このプロパティを-1 以外の値に設定はありません。  
  
## <a name="virtualmemorythrottlingcriteria"></a>VirtualMemoryThrottlingCriteria  
 現在は、アンマネージ ヒープの断片化のため、仮想メモリが 32 ビット マシンのボトルネックとなる可能性があります。このため、このリソースも制限する必要があります。 /3GB が設定されている場合、またはホストが 64 ビット プラットフォーム上で実行されている場合は、再構成する必要があります。 最適使用量と最大使用量は MB 単位です。  
  
 次に、VirtualMemoryThrottlingCriteria の各プロパティの説明を示します。  
  
-   **OptimalUsage**: の退避制限を有効にするが、仮想メモリ使用量。 この時点では、 **TestThreshold** 、値を持つ**MaxThreshold**メモリ使用量を超える**OptimalUsage**により**TestThreshold**をより小さい**MaxThreshold**します。  
  
-   **MaximalUsage**: 仮想メモリ使用量の制限が最大時点では、退避の量。 この時点では、 **TestThreshold** 、値を持つ**MinThreshold**メモリ使用量より小さい**MaximalUsage**により**TestThreshold**超える**MinThreshold**します。  
  
-   **IsActive**: 仮想メモリの制限がアクティブかどうかを示すブール値。  
  
## <a name="privatememorythrottlingcriteria"></a>PrivateMemoryThrottlingCriteria  
 このプロパティは制限のために役立つ条件ですが、コンピューター上で他の Windows サービスが実行されているかどうかによって適切な値が異なります。 コンピューターに大量のメモリがあり、他の Windows サービスと共有していない場合、これらの値を大幅に増やすことができます。  
  
 次に、PrivateMemoryThrottlingCriteria の各プロパティの説明を示します。  
  
-   **OptimalUsage**: の退避制限が適用されますを有効にする (mb) のプライベート メモリ使用量。 この時点で**TestThreshold** 、値を持つ**MaxThreshold**メモリ使用量を超える**OptimalUsage**により**TestThreshold**をより小さい**MaxThreshold**します。  
  
-   **MaximalUsage**: mb、最大で退避制限が、プライベート メモリ使用量。 この時点で**TestThreshold** 、値を持つ**MinThreshold**メモリ使用量より小さい**MaximalUsage**により**TestThreshold**超える**MinThreshold**します。  
  
-   **IsActive**: プライベート メモリ制限がアクティブかどうかを示すブール値。  
  
## <a name="physicalmemorythrottlingcriteria"></a>PhysicalMemoryThrottlingCriteria  
 メモリ使用量を MB 単位ではなくパーセンテージで表す、物理メモリ制限もあります。 このプロパティは既定で無効になっていますが、必要に応じて有効にできます。  
  
 次に、PhysicalMemoryThrottlingCriteria の各プロパティの説明を示します。  
  
-   **OptimalUsage**: ホストのインスタンスに使用する物理メモリの最適なパーセンテージ。  
  
-   **MaximalUsage**: ホストのインスタンスに使用する物理メモリの最大パーセンテージ。  
  
-   **IsActive**: 物理メモリの制限がアクティブなを示すブール値。  
  
## <a name="dehydration-properties-behavior"></a>退避プロパティの動作  
 BizTalk Server はこれらの退避プロパティを使用して、オーケストレーションをいつ退避および復元するかを決定します。 標準の負荷状態では、既定の復元値で十分です。しかし、負荷が高い状態で実行していてパフォーマンス特性を変更する場合、自分でチューニングを行う必要があります。  
  
 BizTalk Server の復元動作は、使用可能なメモリ量と使用されているメモリ量に完全に依存します。 復元動作は、メモリ量によって異なります。また、32 ビットと 64 ビットのホスト間のメモリ使用の違いによっても異なります。  
  
 復元プロパティでは、オーケストレーション ホストのプライベート バイトと仮想バイトが、次のように識別されます。  
  
-   **仮想バイト**します。 使用して、プロセス仮想アドレス空間のバイト単位の現在のサイズです。 仮想アドレス空間を使用していても、ディスク ページまたはメイン メモリ ページを使用しているとは限りません。 仮想空間は有限であり、プロセスではライブラリ読み込み機能を制限できます。  
  
-   **Private Bytes**します。 これは、このプロセスによって割り当てられ、他のプロセスと共有できないメモリの現在のサイズ (バイト単位) です。