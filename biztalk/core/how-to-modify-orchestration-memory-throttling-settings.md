---
title: オーケストレーション メモリ制限の設定を変更する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostInstanceOrchestration
ms.assetid: f6953c68-7809-4518-87ec-e75c98884af3
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c48f1ec5e74ae577a7c1d130e22f3b4a1b53874c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-orchestration-memory-throttling-settings"></a>オーケストレーション メモリの制限の設定を変更する方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のホスト インスタンス メモリ制限メカニズムは、制限の条件を継続的に監視し、制限の条件の重大度を評価し、評価された重大度に応じてホスト インスタンス メモリ制限を段階的に適用します。 このトピックでは、設定ダッシュボードを使用して、この操作を変更する手順について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す操作を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-modify-the-orchestration-memory-throttling-settings-of-a-host-instance"></a>ホスト インスタンスのオーケストレーション メモリ制限の設定を変更するには  
  
1.  **BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**設定**です。  
  
2.  **BizTalk 設定ダッシュ ボード** ダイアログ ボックスで、**ホスト インスタンス** ページで、をクリックして、**オーケストレーション メモリ制限**タブです。  
  
3.  クリックして、次の操作、**適用**を変更を適用し、別のタブに進みます。をクリックしてまたは**OK**を変更を適用し、設定ダッシュ ボードを終了します。  
  
    |プロパティ|目的|境界値|既定値|  
    |--------------|----------------|---------------------|-------------------|  
    |**ホスト インスタンス**|ドロップダウン ボックスから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューター上のホストで実行中のインスタンスを選択します。|-|-|  
  
     **物理**  
  
    |プロパティ|目的|境界値|既定値|  
    |--------------|----------------|---------------------|-------------------|  
    |**最適使用量**|退避制限を有効にする物理メモリの使用量をパーセンテージで指定します。 これはホスト インスタンスに使用する物理メモリの最適なパーセンテージです。|[0 – 100]|70|  
    |**最大使用量**|退避制限が最大になる物理メモリの使用量をパーセンテージで指定します。 これはホスト インスタンスに使用する物理メモリの最大のパーセンテージです。<br /><br /> 最小値**maximalusage**する必要があります**最適使用量**です。|(最適使用量 - 100]<br /><br /> 両方が 0 または 100 の場合は除外します。|85|  
  
     **仮想**  
  
    |プロパティ|目的|境界値|既定値|  
    |--------------|----------------|---------------------|-------------------|  
    |**最適使用量**|退避制限を有効にする仮想メモリの使用量をパーセンテージで指定します。<br /><br /> この時点では、 **TestThreshold**プロパティ値を持つ**MaxThreshold**と、メモリ使用量を超える**OptimalUsage**により**TestThreshold**するより小さい**MaxThreshold**です。|[0 – 100]|65|  
    |**最大使用量**|退避制限が最大になる仮想メモリの使用量をパーセンテージで指定します。<br /><br /> この時点では、 **TestThreshold**プロパティ値を持つ**MinThreshold**とメモリ使用量より小さい**MaximalUsage**により**TestThreshold**大きくなければ**MinThreshold**です。|(最適使用量 - 100]<br /><br /> 両方が 0 または 100 の場合は除外します。|85|  
  
    > [!NOTE]
    >  既定の設定を復元する をクリックして**既定値に戻す**です。  
  
## <a name="see-also"></a>参照  
 [ホスト インスタンスの設定を変更する方法](../core/how-to-modify-host-instance-settings.md)