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
ms.openlocfilehash: 0d314e032030f7db644f8f0e180f92d963127752
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386980"
---
# <a name="how-to-configure-a-biztalk-host-as-a-cluster-resource"></a>BizTalk ホストをクラスター リソースとして構成する方法
このトピックでは、BizTalk ホストをクラスター リソースとして構成する手順について説明します。 このトピックの手順を完了するには、必要がありますとしてあらかじめ構成して、少なくとも 2 つの BizTalk Server BizTalk グループに、Windows Server クラスターのメンバー。 Windows Server クラスターを構成する方法の詳細については、Windows Server のオンライン ヘルプを参照してください。  
  
## <a name="prerequisites"></a>前提条件  
 クラスター化またはホスト クラスターを解除する BizTalk Administrators グループのメンバーとしてログオンする必要があります。  
  
## <a name="considerations-and-known-issues"></a>考慮事項と既知の問題  
  
- BizTalk Server は、BizTalk Server のクラスター化された BizTalk ホストのインスタンスを実行する前に、Windows Server フェールオーバー クラスター内のノードとして構成する必要があります。 サーバー クラスターでクラスター ノードを構成する方法の詳細については、Windows Server のオンライン ヘルプを参照してください。  
  
- オプションを持つホスト インスタンスをクラスター化された BizTalk ホストをフェールオーバーすることはできません**無効にするホスト インスタンスの開始**を設定します。 クラスター化された BizTalk ホストのすべてのホスト インスタンスでは、このオプションを有効にないことを確認します。 このオプションを on に設定、BizTalk Server 管理コンソールで、**ホスト インスタンスのプロパティ**ページ。  
  
- BizTalk ホストをクラスター化するときに、対応するクラスター リソースは、指定されたクラスター リソース グループに作成されます。 クラスター リソースが作成されたときに、クラスターの使用可能な各ノードは、クラスター リソースの実行可能な所有者として追加されます。 クラスター リソースは、実行可能な所有者の一覧で任意のノードにフェールオーバーできる、ので、BizTalk ホストをクラスタ リングする前にクラスターの使用可能なすべてのノードのホストのインスタンスを追加する必要があります。 クラスター化された BizTalk ホストをフェールオーバーしようとしています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストのインスタンスがないコンピューターは失敗します。  
  
  > [!NOTE]
  >  クラスター化された BizTalk ホストの実行を防止または BizTalk ホストをクラスター化するときに作成されるクラスター化されたリソースの実行可能所有者の一覧からノードを削除する特定のクラスター ノードにフェールオーバーする場合は。 Windows Server フェールオーバー クラスター管理インターフェイスを使用してクラスター リソースの実行可能所有者の一覧を変更することができます。  
  
- BizTalk ホストをクラスター化するホストを追加するクラスター グループ、クラスター化されたサービスまたはアプリケーションに、ネットワーク名と IP アドレス リソースが含まれているを確認します。 対象のクラスター グループにネットワーク名と IP アドレス リソースが含まれている場合、ネットワーク名リソースに追加されます、依存関係としてクラスター化された BizTalk ホスト。 これらのリソースが利用できない場合、BizTalk ホストが正しく機能しません、クラスター リソースとして。  
  
- クラスター化された BizTalk ホストの実行可能な所有者として一覧表示される BizTalk server/クラスター ノードの構成を解除するホスト インスタンスのクラスター リソースが Windows クラスターでオフラインします。 構成を解除する必要がある場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト インスタンスのクラスター リソースをオフラインにせずにクラスター化された BizTalk ホストの実行可能な所有者として表示されているコンピューターに次の手順します。  
  
  - クラスター化されたホストをフェールオーバー、Windows Server フェールオーバー クラスター管理インターフェイスで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以外のコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成を解除しているコンピューター。  
  
  - BizTalk Server 管理コンソールに対応するクラスター化された BizTalk ホストのインスタンスを選択、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]するコンピューター構成を解除します。  
  
  - ホスト インスタンスを削除します。 エラーが表示された場合は、ホスト インスタンスを強制的に削除するオプションを選択します。  
  
  - 構成を解除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
- BizTalk ホストをクラスター化されたホストとして構成すると、指定したクラスターのリソース グループ、クラスターに対応するクラスター リソースが作成されます。  
  
   次の再起動値で、Windows Server フェールオーバー クラスター上で利用できる既定では、クラスター化された BizTalk ホスト リソースが構成されている、**ポリシー**のタブ、**プロパティ** ダイアログ ボックスクラスター リソース。  
  
  |オプション|値|  
  |------------|-----------|  
  |リソースが失敗した場合、現在のノードで再起動を試みる。|**True** <br />クラスター サービスは、リソースの再起動が失敗した場合に試行されます。|  
  |再起動 (mm:ss) 期間:|**15:00** <br />試行回数をカウントする再起動中に、期間を指定します。|  
  |指定した期間の再起動の試行回数:|**1** <br />再起動を試行中に許可される最大数を指定します、**再起動 (mm:ss) 期間**します。|  
  |再起動が失敗した場合は、このサービスまたはアプリケーションのすべてのリソースをフェールオーバーします。|**True** <br />クラスター サービスは別のクラスター ノード全体のリソース グループのフェールオーバーでリソースを再起動しようとします。|  
  |再起動の試みすべてが失敗した場合、指定した期間 (hh:mm) 後にもう一度再起動を開始します。|**1:00** <br />クラスター サービスが別の一連の再起動を試行を開始するまで追加の待ち時間を指定します。|  
  |保留タイムアウト (mm:ss):|**3:00** <br />クラスター サービスが失敗した状態で、リソースを配置する前に、オンラインとオフラインの間で状態を変更するのに時間の長さを指定します。|  
  
   既定の再起動値、Windows Server フェールオーバー クラスターはクラスター化された BizTalk ホストの失敗したインスタンスを再起動しようとしているインスタンスの 15 分の時間内に 1 回。 以降、**再起動が失敗した場合はこのサービスまたはアプリケーションのすべてのリソースをフェールオーバー**値に設定されて**True**、再起動しようとするとは別のクラスターにクラスター リソース グループのフェールオーバーも失敗ノードです。 かどうかには、指定した時間間隔の指定した回数でクラスター化された BizTalk ホストの失敗したインスタンスを再起動することはできませんし、クラスター化された BizTalk ホストの状態を想定は**Failed**フェールオーバー クラスターの管理インターフェイスです。 クラスター化された BizTalk ホストの状態を前提として 場合**失敗**フェールオーバー クラスターの管理に手動で開始する必要があります。  
  
   次の再起動値でサーバー クラスター上で利用できる既定では、クラスター化された BizTalk ホスト リソースが構成されている、 **[詳細設定]** のタブ、**プロパティ**クラスターのダイアログ ボックスリソース:  
  
  |**Option**|**[値]**|  
  |----------------|---------------|  
  |再起動|**True**<br /><br /> クラスター サービスは、リソースの再起動が失敗した場合に試行されます。|  
  |グループに適用します。|**True**<br /><br /> クラスター サービスは別のクラスター ノード全体のリソース グループのフェールオーバーでリソースを再起動しようとします。|  
  |[Restart Threshold]|**3**<br /><br /> 再起動を試行中に許可される最大数を指定します、 **Restart Period**します。 再起動の試行回数を超えた場合、 **Restart Threshold**中に、 **Restart Period**クラスター リソースの状態を前提としていますし、 **Failed**とクラスターサービスでは、それ以上再起動は試行しません。|  
  |[Restart Period]|**900 秒**<br /><br /> 試行回数をカウントする再起動中に、期間を指定します。 **Restart Period**最初の再起動の試行時に初期化されます。 再起動の試行回数は場合は 0 にリセット、 **Restart Threshold**の期間を超えていない、 **Restart Period**します。|  
  
   既定では、Windows Server クラスターの再開を試み、失敗したインスタンスのクラスター化された BizTalk ホスト インスタンスの最大 3 回 900 秒間の時間内の値に応じてを再起動します。 以降、 **、グループには影響**値に設定されて**True**、再起動しようとするとは別のクラスター ノードをクラスター リソース グループのフェールオーバーも失敗します。 かどうかには、指定した数の指定した期間中に試行に失敗したクラスター化された BizTalk ホストのインスタンスを再起動することはできませんし、クラスター化された BizTalk ホストの状態を想定は**Failed**クラスター アドミニストレーターでします。 場合、クラスター化された BizTalk ホストの状態を前提としています**Failed**、その必要があります手動で開始するクラスター アドミニストレーターでします。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-configure-a-biztalk-host-as-a-cluster-resource"></a>BizTalk ホストをクラスター リソースとして構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして展開**BizTalk Server 管理**をクリックして展開**BizTalk グループ [\<servername\>:\<管理データベース\>]** をクリックして展開**プラットフォームの設定**をクリックして展開と**ホスト**します。 フォルダーの下にホストの一覧が表示されます。  
  
2. ホスト クラスターを選びたいを右クリックして**クラスター**します。  
  
   > [!NOTE]
   >  BizTalk ホストをクラスター グループを追加する前に、クラスター グループの実行可能な所有者であるすべてのメンバー ノードで、ホストのインスタンスを作成したことを確認します。  
  
3. 使用可能なクラスター グループのドロップダウン リストから、ホストを実行するにはクラスター グループを選択します。  
  
   > [!NOTE]
   >  ホストがクラスター化するようになりますがオンラインになり、アダプター ハンドラーまたはオーケストレーションのホストで実行するように構成のドキュメントの処理が開始されます。  
  
#### <a name="to-uncluster-a-clustered-biztalk-host"></a>クラスター化された BizTalk ホストをクラスター解除するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして展開**BizTalk Server 管理**をクリックして展開**BizTalk グループ [\<servername\>:\<管理データベース\>]** をクリックして展開**プラットフォームの設定**をクリックして展開と**ホスト**します。 フォルダーの下にホストの一覧が表示されます。  
  
2. クラスター化されたホストをクラスター化を解除しを選択するを右クリックして**クラスター解除**します。  
  
   > [!NOTE]
   >  クラスター化されたホストがクラスター化できない場合は、クラスター化されたホストに関連付けられているすべてのホスト インスタンスが停止し、ホストのアダプター ハンドラーまたはオーケストレーション、ホストで実行するように構成されているドキュメントの処理は停止します。