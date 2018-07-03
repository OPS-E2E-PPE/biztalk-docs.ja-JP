---
title: BizTalk ホストをクラスター Resource1 として構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 53df974ec3b0fdf93b4e1cd59c9144b5b33af424
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981987"
---
# <a name="how-to-configure-a-biztalk-host-as-a-cluster-resource"></a>BizTalk ホストをクラスター リソースとして構成する方法
このトピックでは、BizTalk ホストをクラスター リソースとして構成する手順について説明します。 このトピックの手順を完了するには、BizTalk グループの少なくとも 2 つの BizTalk Server を Windows Server クラスターのメンバーとしてあらかじめ構成しておく必要があります。 Windows Server クラスターの構成の詳細については、Windows Server のオンライン ヘルプを参照してください。  
  
## <a name="prerequisites"></a>前提条件  
 ホストをクラスター化またはクラスター化解除するには、BizTalk 管理者グループのメンバーとしてログオンする必要があります。  
  
## <a name="considerations-and-known-issues"></a>考慮事項と既知の問題  
  
- BizTalk Server 上でクラスター化されている BizTalk ホストのインスタンスを実行するには、BizTalk Server を Windows Server フェールオーバー クラスター内のノードとして構成しておく必要があります。 サーバー クラスター内のクラスター ノードの構成の詳細については、Windows Server のオンライン ヘルプを参照してください。  
  
- オプションを持つホスト インスタンスをクラスター化された BizTalk ホストをフェールオーバーすることはできません**無効にするホスト インスタンスの開始**を設定します。 クラスター化された BizTalk ホストのすべてのホスト インスタンスでは、このオプションを有効にないことを確認します。 このオプションを on に設定、BizTalk Server 管理コンソールで、**ホスト インスタンスのプロパティ**ページ。  
  
- BizTalk ホストをクラスター化すると、指定したクラスター リソース グループに、対応するクラスター リソースが作成されます。 クラスター リソースの作成時には、クラスターの使用可能な各ノードが、クラスター リソースの実行可能な所有者として追加されます。 クラスター リソースは実行可能な所有者の一覧内のどのノードにもフェールオーバーできるので、BizTalk ホストをクラスター化する前に、ホストのインスタンスをクラスターの使用可能なノードすべてに追加する必要があります。 対応するホスト インスタンスの存在しない [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターに、クラスター化された BizTalk ホストをフェールオーバーしようとすると失敗します。  
  
  > [!NOTE]
  >  クラスター化された BizTalk ホストの実行や、特定のクラスター ノードへのフェールオーバーを阻止するには、BizTalk ホストをクラスター化するときに作成されるクラスター化リソースの実行可能な所有者の一覧からそのノードを削除します。 クラスター リソースの実行可能な所有者の一覧は、Windows Server フェールオーバー クラスター管理インターフェイスを使用して変更できます。  
  
- BizTalk ホストをクラスター化するときは、ホストの追加先のクラスター グループ、クラスター化されたサービス、またはアプリケーションにネットワークの名前と ID アドレス リソースが含まれていることを確認してください。 対象のクラスター グループにネットワークの名前と IP アドレス リソースが含まれている場合、ネットワークの名前は、クラスター化された BizTalk ホストに依存関係として追加されます。 これらのリソースを使用できない場合、BizTalk ホストはクラスター化されたリソースとして正しく機能しません。  
  
- クラスター化された BizTalk ホストの実行可能な所有者として一覧表示される BizTalk server/クラスター ノードの構成を解除するホスト インスタンスのクラスター リソースが Windows クラスターでオフラインします。 ホスト インスタンスのクラスター リソースをオフラインにせずに、クラスター化された BizTalk ホストの実行可能な所有者として一覧に含まれている [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターの構成を解除する必要がある場合は、次の手順を実行します。  
  
  - Windows Server フェールオーバー クラスター管理インターフェイスで、構成を解除する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター以外の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターに、クラスター化されたホストをフェールオーバーします。  
  
  - BizTalk Server 管理コンソールに対応するクラスター化された BizTalk ホストのインスタンスを選択、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]するコンピューター構成を解除します。  
  
  - ホスト インスタンスを削除します。 エラーが表示された場合は、ホスト インスタンスを強制的に削除するオプションを選択します。  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成を解除します。  
  
- BizTalk ホストをクラスター化されたホストとして構成すると、クラスターの指定したクラスター リソース グループに、対応するクラスター リソースが作成されます。  
  
   次の再起動値で、Windows Server フェールオーバー クラスター上で利用できる既定では、クラスター化された BizTalk ホスト リソースが構成されている、**ポリシー**のタブ、**プロパティ** ダイアログ ボックスクラスター リソース。  
  
  |オプション|値|  
  |------------|-----------|  
  |リソースが失敗状態になった場合は、現在のノードで再起動を試みる|**True** <br />リソースが失敗した場合、クラスター サービスでリソースの再起動が試行されます。|  
  |再起動期間 (mm:ss):|**15:00** <br />再起動の試行回数をカウントする期間を指定します。|  
  |指定期間内での再起動の試行回数:|**1** <br />再起動を試行中に許可される最大数を指定します、**再起動 (mm:ss) 期間**します。|  
  |再起動が失敗した場合は、このサービスまたはアプリケーションのすべてのリソースをフェールオーバーします。|**True** <br />リソース グループ全体が別のクラスター ノードにフェールオーバーされ、クラスター サービスでリソースの再起動が試行されます。|  
  |再起動の試みすべてが失敗した場合、指定した期間 (hh:mm) 後にもう一度再起動を開始します。|**1:00** <br />クラスター サービスが別の一連の再起動を試行を開始するまで追加の待ち時間を指定します。|  
  |保留タイムアウト (mm:ss):|**3:00** <br />クラスター サービスが失敗した状態で、リソースを配置する前に、オンラインとオフラインの間で状態を変更するのに時間の長さを指定します。|  
  
   既定の再起動値を使用すると、クラスター化された BizTalk ホスト インスタンスのインスタンスが失敗した場合に、Windows Server フェールオーバー クラスターはインスタンスの再起動を 15 分間に 1 回試行します。 以降、**再起動が失敗した場合はこのサービスまたはアプリケーションのすべてのリソースをフェールオーバー**値に設定されて**True**、再起動しようとするとは別のクラスターにクラスター リソース グループのフェールオーバーも失敗ノードです。 かどうかには、指定した時間間隔の指定した回数でクラスター化された BizTalk ホストの失敗したインスタンスを再起動することはできませんし、クラスター化された BizTalk ホストの状態を想定は**Failed**フェールオーバー クラスターの管理インターフェイスです。 クラスター化された BizTalk ホストの状態を前提として 場合**失敗**フェールオーバー クラスターの管理に手動で開始する必要があります。  
  
   次の再起動値でサーバー クラスター上で利用できる既定では、クラスター化された BizTalk ホスト リソースが構成されている、 **[詳細設定]** のタブ、**プロパティ**クラスターのダイアログ ボックスリソース:  
  
  |**オプション**|**[値]**|  
  |----------------|---------------|  
  |[再起動]|**True**<br /><br /> リソースが失敗した場合、クラスター サービスでリソースの再起動が試行されます。|  
  |[グループに適用する]|**True**<br /><br /> リソース グループ全体が別のクラスター ノードにフェールオーバーされ、クラスター サービスでリソースの再起動が試行されます。|  
  |[Restart Threshold]|**3**<br /><br /> 再起動を試行中に許可される最大数を指定します、 **Restart Period**します。 再起動の試行回数を超えた場合、 **Restart Threshold**中に、 **Restart Period**クラスター リソースの状態を前提としていますし、 **Failed**とクラスターサービスでは、それ以上再起動は試行しません。|  
  |[Restart Period]|**900 秒**<br /><br /> 再起動の試行回数をカウントする期間を指定します。 **Restart Period**最初の再起動の試行時に初期化されます。 再起動の試行回数は場合は 0 にリセット、 **Restart Threshold**の期間を超えていない、 **Restart Period**します。|  
  
   既定の再起動値を使用すると、クラスター化された BizTalk ホスト インスタンスのインスタンスが失敗した場合に、Windows Server クラスターはインスタンスの再起動を 900 秒間に 3 回試行します。 以降、 **、グループには影響**値に設定されて**True**、再起動しようとするとは別のクラスター ノードをクラスター リソース グループのフェールオーバーも失敗します。 かどうかには、指定した数の指定した期間中に試行に失敗したクラスター化された BizTalk ホストのインスタンスを再起動することはできませんし、クラスター化された BizTalk ホストの状態を想定は**Failed**クラスター アドミニストレーターでします。 場合、クラスター化された BizTalk ホストの状態を前提としています**Failed**、その必要があります手動で開始するクラスター アドミニストレーターでします。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-configure-a-biztalk-host-as-a-cluster-resource"></a>BizTalk ホストをクラスター リソースとして構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして展開**BizTalk Server 管理**をクリックして展開**BizTalk グループ [\<servername\>:\<管理データベース\>]** をクリックして展開**プラットフォームの設定**をクリックして展開と**ホスト**します。 フォルダーの下にホストの一覧が表示されます。  
  
2. ホスト クラスターを選びたいを右クリックして**クラスター**します。  
  
   > [!NOTE]
   >  BizTalk ホストをクラスター グループに追加する前に、クラスター グループの実行可能な所有者のすべてのメンバー ノードにホスト インスタンスを作成しておきます。  
  
3. 利用可能なクラスター グループのドロップダウン リストから、ホストを実行させるクラスター グループを選択します。  
  
   > [!NOTE]
   >  ホストがクラスター化するようになりますがオンラインになり、アダプター ハンドラーまたはオーケストレーションのホストで実行するように構成のドキュメントの処理が開始されます。  
  
#### <a name="to-uncluster-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストをクラスター解除するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして展開**BizTalk Server 管理**をクリックして展開**BizTalk グループ [\<servername\>:\<管理データベース\>]** をクリックして展開**プラットフォームの設定**をクリックして展開と**ホスト**します。 フォルダーの下にホストの一覧が表示されます。  
  
2. クラスター化されたホストをクラスター化を解除しを選択するを右クリックして**クラスター解除**します。  
  
   > [!NOTE]
   >  クラスター化されているホストのクラスター化が解除されると、クラスター化されたホストに関連付けられているホスト インスタンスが停止し、ホストで実行するように構成されているアダプター ハンドラーまたはオーケストレーションのドキュメントの処理も停止します。