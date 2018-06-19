---
title: クラスター Resource1 として BizTalk ホストを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installation, high availability
- clustering, servers
- hosts, multiple
- hosts, high availability
- Windows Server cluster
- databases, clustering
- clustering, fail-overs
- Windows Server cluster, about Windows Server cluster
- installation, planning
- clustering, databases
- clustering, best practices
- clustering, unclustering
- clustering, configuring
- installation, clustering
ms.assetid: bcd656d2-8dd6-49fc-9c42-ef5c884e52c4
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a18548394980912796daf1100f700fd03e72f294
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970560"
---
# <a name="how-to-configure-a-biztalk-host-as-a-cluster-resource"></a>BizTalk ホストをクラスター リソースとして構成する方法
このトピックでは、BizTalk ホストをクラスター リソースとして構成する手順について説明します。 このトピックの手順を完了するには、BizTalk グループの少なくとも 2 つの BizTalk Server を Windows Server クラスターのメンバーとしてあらかじめ構成しておく必要があります。 Windows Server クラスターの構成の詳細については、Windows Server のオンライン ヘルプを参照してください。  
  
## <a name="prerequisites"></a>前提条件  
 ホストをクラスター化またはクラスター化解除するには、BizTalk 管理者グループのメンバーとしてログオンする必要があります。  
  
## <a name="considerations-and-known-issues"></a>考慮事項と既知の問題  
  
-   BizTalk Server 上でクラスター化されている BizTalk ホストのインスタンスを実行するには、BizTalk Server を Windows Server フェールオーバー クラスター内のノードとして構成しておく必要があります。 サーバー クラスター内のクラスター ノードの構成の詳細については、Windows Server のオンライン ヘルプを参照してください。  
  
-   クラスター化された BizTalk ホストのオプションが存在するホスト インスタンスにフェールオーバーすることはできません**無効にするホスト インスタンスの開始を**を設定します。 クラスター化された BizTalk ホストのすべてのホスト インスタンスでは、このオプションを有効にないことを確認します。 このオプションを on に設定、BizTalk Server 管理コンソールで、**ホスト インスタンスのプロパティ**ページ。  
  
-   BizTalk ホストをクラスター化すると、指定したクラスター リソース グループに、対応するクラスター リソースが作成されます。 クラスター リソースの作成時には、クラスターの使用可能な各ノードが、クラスター リソースの実行可能な所有者として追加されます。 クラスター リソースは実行可能な所有者の一覧内のどのノードにもフェールオーバーできるので、BizTalk ホストをクラスター化する前に、ホストのインスタンスをクラスターの使用可能なノードすべてに追加する必要があります。 対応するホスト インスタンスの存在しない [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターに、クラスター化された BizTalk ホストをフェールオーバーしようとすると失敗します。  
  
    > [!NOTE]
    >  クラスター化された BizTalk ホストの実行や、特定のクラスター ノードへのフェールオーバーを阻止するには、BizTalk ホストをクラスター化するときに作成されるクラスター化リソースの実行可能な所有者の一覧からそのノードを削除します。 クラスター リソースの実行可能な所有者の一覧は、Windows Server フェールオーバー クラスター管理インターフェイスを使用して変更できます。  
  
-   BizTalk ホストをクラスター化するときは、ホストの追加先のクラスター グループ、クラスター化されたサービス、またはアプリケーションにネットワークの名前と ID アドレス リソースが含まれていることを確認してください。 対象のクラスター グループにネットワークの名前と IP アドレス リソースが含まれている場合、ネットワークの名前は、クラスター化された BizTalk ホストに依存関係として追加されます。 これらのリソースを使用できない場合、BizTalk ホストはクラスター化されたリソースとして正しく機能しません。  
  
-   クラスター化された BizTalk ホストの実行可能な所有者としてリストされている BizTalk server/クラスター ノードの構成を解除すると、ホスト インスタンスのクラスター リソースが Windows クラスターでオフラインです。 ホスト インスタンスのクラスター リソースをオフラインにせずに、クラスター化された BizTalk ホストの実行可能な所有者として一覧に含まれている [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターの構成を解除する必要がある場合は、次の手順を実行します。  
  
    -   Windows Server フェールオーバー クラスター管理インターフェイスで、構成を解除する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター以外の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターに、クラスター化されたホストをフェールオーバーします。  
  
    -   BizTalk Server 管理コンソールに対応するクラスター化された BizTalk ホストのインスタンスを選択、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]するコンピューター構成を解除します。  
  
    -   ホスト インスタンスを削除します。 エラーが表示された場合は、ホスト インスタンスを強制的に削除するオプションを選択します。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成を解除します。  
  
-   BizTalk ホストをクラスター化されたホストとして構成すると、クラスターの指定したクラスター リソース グループに、対応するクラスター リソースが作成されます。  
  
     既定では、クラスター化された BizTalk ホスト リソースが構成されている、次の再起動値を Windows Server フェールオーバー クラスター上で利用できる、**ポリシー**のタブ、**プロパティ** ダイアログ ボックスクラスター リソース。  
  
    |オプション|値|  
    |------------|-----------|  
    |リソースが失敗状態になった場合は、現在のノードで再起動を試みる|**True** <br />リソースが失敗した場合、クラスター サービスでリソースの再起動が試行されます。|  
    |再起動期間 (mm:ss):|**15:00** <br />再起動の試行回数をカウントする期間を指定します。|  
    |指定期間内での再起動の試行回数:|**1** <br />中に許可される再起動の試行の最大数を指定、 **(mm:ss) の再起動の期間**です。|  
    |再起動が失敗した場合は、このサービスまたはアプリケーションのすべてのリソースをフェールオーバーします。|**True** <br />リソース グループ全体が別のクラスター ノードにフェールオーバーされ、クラスター サービスでリソースの再起動が試行されます。|  
    |再起動の試みがすべて失敗した場合、指定した期間 (hh:mm) 後にもう一度再起動を開始します。|**1:00** <br />クラスター サービスが別の一連の再起動の試行を開始するまで延長の待ち時間を指定します。|  
    |保留タイムアウト (mm:ss):|**3:00** <br />リソースは、クラスター サービスでは、リソースを失敗状態にする前に、オンラインとオフラインの間の状態を変更するために行える時間の長さを指定します。|  
  
     既定の再起動値を使用すると、クラスター化された BizTalk ホスト インスタンスのインスタンスが失敗した場合に、Windows Server フェールオーバー クラスターはインスタンスの再起動を 15 分間に 1 回試行します。 以降、**再起動が成功しなかった場合はこのサービスまたはアプリケーションのすべてのリソースをフェールオーバー**に値が設定されている**True**、再起動しようとするとは別のクラスターにクラスター リソース グループのフェールオーバーも失敗ノードです。 指定された数の指定した期間内でクラスター化された BizTalk ホストの失敗したインスタンスを再起動できないかどうかは、クラスター化された BizTalk ホストでの状態は想定**失敗**フェールオーバー クラスターの管理インターフェイスです。 クラスター化された BizTalk ホストの状態のとなった場合**失敗**フェールオーバー クラスター管理で手動で開始する必要があります。  
  
     次の再起動値サーバー クラスター上で使用できるは既定では、クラスター化された BizTalk ホスト リソースが構成されている、**詳細**のタブ、**プロパティ**クラスター ダイアログ ボックスリソース:  
  
    |**オプション**|**値**|  
    |----------------|---------------|  
    |[再起動]|**True**<br /><br /> リソースが失敗した場合、クラスター サービスでリソースの再起動が試行されます。|  
    |[グループに適用する]|**True**<br /><br /> リソース グループ全体が別のクラスター ノードにフェールオーバーされ、クラスター サービスでリソースの再起動が試行されます。|  
    |[Restart Threshold]|**3**<br /><br /> 中に許可される再起動の試行の最大数を指定、 **Restart Period**です。 再起動の試行の数を超えた場合、 **Restart Threshold**中に、 **Restart Period**クラスター リソースの状態を前提として**失敗**とクラスターサービスでは、それ以上再起動は試行されません。|  
    |[Restart Period]|**900 秒**<br /><br /> 再起動の試行回数をカウントする期間を指定します。 **Restart Period**は最初の再起動の試行時に初期化します。 再起動の試行回数が場合は 0 にリセット、 **Restart Threshold**の期間を超えない、 **Restart Period**です。|  
  
     既定の再起動値を使用すると、クラスター化された BizTalk ホスト インスタンスのインスタンスが失敗した場合に、Windows Server クラスターはインスタンスの再起動を 900 秒間に 3 回試行します。 以降、**グループに影響を**に値が設定されている**True**、再起動しようとするとは別のクラスター ノードをクラスター リソース グループのフェールオーバーも失敗します。 指定した期間中に指定した回数で、クラスター化された BizTalk ホストの失敗したインスタンスを再起動できないかどうかは、クラスター化された BizTalk ホストの状態を想定は**失敗**クラスター アドミニストレーターでします。 クラスター化された BizTalk ホストの状態のとなった場合**失敗**を手動で起動クラスター アドミニストレーターで、します。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-configure-a-biztalk-host-as-a-cluster-resource"></a>BizTalk ホストをクラスター リソースとして構成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして展開**BizTalk Server 管理コンソール**をクリックして展開**BizTalk グループ [\<servername\>:\<管理データベース\>]** をクリックして展開**プラットフォームの設定**、クリックして展開し、**ホスト**です。 フォルダーの下にホストの一覧が表示されます。  
  
2.  クラスター、しを選択したいホストを右クリックして**クラスター**です。  
  
    > [!NOTE]
    >  BizTalk ホストをクラスター グループに追加する前に、クラスター グループの実行可能な所有者のすべてのメンバー ノードにホスト インスタンスを作成しておきます。  
  
3.  利用可能なクラスター グループのドロップダウン リストから、ホストを実行させるクラスター グループを選択します。  
  
    > [!NOTE]
    >  ホストがクラスター化されているようになったらがオンラインになり、アダプター ハンドラーまたはホストで実行するように構成されているオーケストレーションのドキュメントの処理が開始されます。  
  
#### <a name="to-uncluster-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストをクラスター解除するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして展開**BizTalk Server 管理コンソール**をクリックして展開**BizTalk グループ [\<servername\>:\<管理データベース\>]** をクリックして展開**プラットフォームの設定**、クリックして展開し、**ホスト**です。 フォルダーの下にホストの一覧が表示されます。  
  
2.  クラスター化を解除し、選択したクラスター化されたホストを右クリックして**クラスター解除**です。  
  
    > [!NOTE]
    >  クラスター化されているホストのクラスター化が解除されると、クラスター化されたホストに関連付けられているホスト インスタンスが停止し、ホストで実行するように構成されているアダプター ハンドラーまたはオーケストレーションのドキュメントの処理も停止します。