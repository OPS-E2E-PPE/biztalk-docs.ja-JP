---
title: BizTalk Server ログ配布が Windows クラスター名と IP アドレスを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82ef6908-6009-4d06-8315-0bc85a0aad18
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1b3df08da6753a7f936bfca54ecfb69b86d058c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023424"
---
# <a name="biztalk-server-log-shipping-using-a-windows-cluster-name-and-ip-address"></a><span data-ttu-id="f8586-102">BizTalk Server ログ配布、Windows クラスター名と IP アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f8586-102">BizTalk Server Log Shipping Using a Windows Cluster Name and IP Address</span></span>
<span data-ttu-id="f8586-103">簡略化することは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つのインスタンスを使用してログ配布、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター内の元と移行先サーバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布シナリオ。</span><span class="sxs-lookup"><span data-stu-id="f8586-103">It is possible to simplify [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping by using two instances of a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster as the source and destination servers in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping scenario.</span></span> <span data-ttu-id="f8586-104">次に、障害復旧イベントが発生した場合データベースの回復が簡略化だけで、名前と、クラスターに関連付けられている IP アドレス リソースを切り替えることで[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]以下に示すようにインスタンスします。</span><span class="sxs-lookup"><span data-stu-id="f8586-104">Then, in the event of a disaster recovery event, database recovery is simplified by merely switching the name and IP address resources associated with the clustered [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances as described below.</span></span> <span data-ttu-id="f8586-105">このアプローチを使用する場合は、トピックで説明したように、UpdateDatabase.vbs スクリプトを実行する必要はありません[Backup BizTalk Server ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)のため、データベース名は変更されません。</span><span class="sxs-lookup"><span data-stu-id="f8586-105">When using this approach there is no need to run the UpdateDatabase.vbs script as described in the topic [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md) because the database name is unchanged.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8586-106">クラスター化のフォールト トレランスを強化する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスをクラスター化された[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスを地理的に区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8586-106">To increase fault tolerance for the clustered [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances, the clustered [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances should be geographically separated.</span></span>  
  
### <a name="to-implement-biztalk-server-log-shipping-using-a-windows-server-cluster-name-and-ip-address-resource"></a><span data-ttu-id="f8586-107">Windows Server クラスターの名前と IP を使用して配布を BizTalk Server のログを実装するには、アドレスのリソース</span><span class="sxs-lookup"><span data-stu-id="f8586-107">To implement BizTalk Server log shipping using a Windows Server Cluster name and IP address resource</span></span>  
  
1. <span data-ttu-id="f8586-108">運用環境の BizTalk server を停止します。</span><span class="sxs-lookup"><span data-stu-id="f8586-108">Stop the production BizTalk servers.</span></span>  
  
2. <span data-ttu-id="f8586-109">実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セカンダリに配布の復元をログイン[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター。</span><span class="sxs-lookup"><span data-stu-id="f8586-109">Perform a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping restore to the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster.</span></span>  
  
3. <span data-ttu-id="f8586-110">トピックで説明されている手順に従います[を構成する BizTalk Server のログ配布](../technical-guides/configuring-biztalk-server-log-shipping.md)を再構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布できるように、セカンダリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスがソース グループになり、プライマリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスが移動先のグループではようになりました。</span><span class="sxs-lookup"><span data-stu-id="f8586-110">Follow the steps described in the topic [Configuring BizTalk Server Log Shipping](../technical-guides/configuring-biztalk-server-log-shipping.md) to reconfigure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping so that the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance is now the source group and the primary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance is now the destination group.</span></span>  
  
4. <span data-ttu-id="f8586-111">Ip アドレスを停止し、ネットワーク名リソース PublicSQLClustername プライマリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンス。</span><span class="sxs-lookup"><span data-stu-id="f8586-111">Stop the IP and network name resource PublicSQLClustername on the primary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance.</span></span>  
  
5. <span data-ttu-id="f8586-112">構成して、セカンダリで PublicSQLClustername IP とネットワーク名クラスター リソースを開始[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンス。</span><span class="sxs-lookup"><span data-stu-id="f8586-112">Configure and start the PublicSQLClustername IP and network name cluster resources on the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance.</span></span>  
  
6. <span data-ttu-id="f8586-113">運用環境の BizTalk server を起動します。</span><span class="sxs-lookup"><span data-stu-id="f8586-113">Start the production BizTalk servers.</span></span>  
  
7. <span data-ttu-id="f8586-114">ログ配布の復元を確認します。</span><span class="sxs-lookup"><span data-stu-id="f8586-114">Verify the log-shipping restore.</span></span>  
  
8. <span data-ttu-id="f8586-115">開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働サイト上のサービスに関連します。</span><span class="sxs-lookup"><span data-stu-id="f8586-115">Start [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] related services on the production site.</span></span>  
  
   <span data-ttu-id="f8586-116">次の手順を実行した後は、BizTalk グループがセカンダリを指している[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスの次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="f8586-116">After performing these steps, the BizTalk group is pointing to the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance as illustrated in the following figure.</span></span>  
  
   <span data-ttu-id="f8586-117">次の図は、構成する方法を示しています。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つのクラスター化されたインスタンスを使用してログ配布[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]移動、クラスター化された名前と IP アドレス リソースとします。</span><span class="sxs-lookup"><span data-stu-id="f8586-117">The following figure illustrates how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping by using two clustered instances of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and moving the clustered name and IP address resource.</span></span>  
  
   <span data-ttu-id="f8586-118">![クラスター名と IP を使用して BizTalk ログ配布](../technical-guides/media/5055689e-c26b-4077-a531-74a50fec1393.gif "5055689e-c26b-4077-a531-74a50fec1393")</span><span class="sxs-lookup"><span data-stu-id="f8586-118">![BizTalk Log Shipping using a Cluster name and IP](../technical-guides/media/5055689e-c26b-4077-a531-74a50fec1393.gif "5055689e-c26b-4077-a531-74a50fec1393")</span></span>  
  
   <span data-ttu-id="f8586-119">**Windows Server クラスターの名前と IP アドレス リソースを使用して BizTalk Server のログ配布の実装**</span><span class="sxs-lookup"><span data-stu-id="f8586-119">**BizTalk Server Log Shipping implementation using Windows Server cluster name and IP address resources**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8586-120">参照</span><span class="sxs-lookup"><span data-stu-id="f8586-120">See Also</span></span>  
 <span data-ttu-id="f8586-121">[データベースの高可用性](../technical-guides/high-availability-for-databases.md) </span><span class="sxs-lookup"><span data-stu-id="f8586-121">[High Availability for Databases](../technical-guides/high-availability-for-databases.md) </span></span>  
 <span data-ttu-id="f8586-122">[ログ配布の BizTalk Server の構成](../technical-guides/configuring-biztalk-server-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="f8586-122">[Configuring BizTalk Server Log Shipping](../technical-guides/configuring-biztalk-server-log-shipping.md) </span></span>  
 [<span data-ttu-id="f8586-123">バックアップ BizTalk Server ジョブでデータベースを復元する方法</span><span class="sxs-lookup"><span data-stu-id="f8586-123">How to Restore Databases in the Backup BizTalk Server Job</span></span>](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)