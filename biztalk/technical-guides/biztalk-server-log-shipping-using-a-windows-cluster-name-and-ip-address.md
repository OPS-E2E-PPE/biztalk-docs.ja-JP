---
title: "BizTalk Server のログ配布は Windows クラスター名と IP アドレスを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82ef6908-6009-4d06-8315-0bc85a0aad18
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8619ea6c4eea3eefee5b86282a29e0165d0fb074
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-log-shipping-using-a-windows-cluster-name-and-ip-address"></a><span data-ttu-id="303e6-102">BizTalk Server のログ配布の Windows クラスター名と IP アドレスを使用して</span><span class="sxs-lookup"><span data-stu-id="303e6-102">BizTalk Server Log Shipping Using a Windows Cluster Name and IP Address</span></span>
<span data-ttu-id="303e6-103">簡略化することは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つのインスタンスを使用してログ配布、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター内の元と移行先サーバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布のシナリオです。</span><span class="sxs-lookup"><span data-stu-id="303e6-103">It is possible to simplify [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping by using two instances of a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster as the source and destination servers in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping scenario.</span></span> <span data-ttu-id="303e6-104">次に、障害復旧イベントが発生した場合データベースの回復が簡略化だけで、名前と、クラスター化されたに関連付けられている IP アドレス リソースを切り替えることによって[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]以下に示すようをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="303e6-104">Then, in the event of a disaster recovery event, database recovery is simplified by merely switching the name and IP address resources associated with the clustered [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances as described below.</span></span> <span data-ttu-id="303e6-105">このアプローチを使用する場合は、」の説明に従って、UpdateDatabase.vbs スクリプト実行する必要はありません[BizTalk Server のバックアップ ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)のため、データベース名は変更されません。</span><span class="sxs-lookup"><span data-stu-id="303e6-105">When using this approach there is no need to run the UpdateDatabase.vbs script as described in the topic [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md) because the database name is unchanged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="303e6-106">クラスター化されたのフォールト トレランスを向上させる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス、クラスター化された[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスを地理的に区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="303e6-106">To increase fault tolerance for the clustered [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances, the clustered [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances should be geographically separated.</span></span>  
  
### <a name="to-implement-biztalk-server-log-shipping-using-a-windows-server-cluster-name-and-ip-address-resource"></a><span data-ttu-id="303e6-107">Windows Server クラスターの名前と IP を使用して配布を BizTalk Server のログを実装するには、アドレスのリソース</span><span class="sxs-lookup"><span data-stu-id="303e6-107">To implement BizTalk Server log shipping using a Windows Server Cluster name and IP address resource</span></span>  
  
1.  <span data-ttu-id="303e6-108">実稼働の BizTalk サーバーを停止します。</span><span class="sxs-lookup"><span data-stu-id="303e6-108">Stop the production BizTalk servers.</span></span>  
  
2.  <span data-ttu-id="303e6-109">実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セカンダリに配布の復元をログ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター。</span><span class="sxs-lookup"><span data-stu-id="303e6-109">Perform a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping restore to the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster.</span></span>  
  
3.  <span data-ttu-id="303e6-110">トピックで説明した手順を[を構成する BizTalk Server ログ配布](../technical-guides/configuring-biztalk-server-log-shipping.md)を再構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布できるようにセカンダリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスは、ソース グループになり、プライマリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスが、対象のグループです。</span><span class="sxs-lookup"><span data-stu-id="303e6-110">Follow the steps described in the topic [Configuring BizTalk Server Log Shipping](../technical-guides/configuring-biztalk-server-log-shipping.md) to reconfigure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping so that the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance is now the source group and the primary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance is now the destination group.</span></span>  
  
4.  <span data-ttu-id="303e6-111">Ip アドレスを停止し、ネットワーク名リソース PublicSQLClustername プライマリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンス。</span><span class="sxs-lookup"><span data-stu-id="303e6-111">Stop the IP and network name resource PublicSQLClustername on the primary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance.</span></span>  
  
5.  <span data-ttu-id="303e6-112">構成およびセカンダリ PublicSQLClustername IP とネットワーク名クラスター リソースを起動[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンス。</span><span class="sxs-lookup"><span data-stu-id="303e6-112">Configure and start the PublicSQLClustername IP and network name cluster resources on the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance.</span></span>  
  
6.  <span data-ttu-id="303e6-113">運用環境の BizTalk server を起動します。</span><span class="sxs-lookup"><span data-stu-id="303e6-113">Start the production BizTalk servers.</span></span>  
  
7.  <span data-ttu-id="303e6-114">ログ配布の復元を確認します。</span><span class="sxs-lookup"><span data-stu-id="303e6-114">Verify the log-shipping restore.</span></span>  
  
8.  <span data-ttu-id="303e6-115">開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働サイト上のサービスに関連します。</span><span class="sxs-lookup"><span data-stu-id="303e6-115">Start [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] related services on the production site.</span></span>  
  
 <span data-ttu-id="303e6-116">次の手順を実行すると、BizTalk グループが、セカンダリを指して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスに次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="303e6-116">After performing these steps, the BizTalk group is pointing to the secondary [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster instance as illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="303e6-117">次の図は、構成する方法を示しています。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つのクラスター化されたインスタンスを使用してログ配布[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]移動、クラスター化された名前と IP アドレス リソースとします。</span><span class="sxs-lookup"><span data-stu-id="303e6-117">The following figure illustrates how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping by using two clustered instances of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and moving the clustered name and IP address resource.</span></span>  
  
 <span data-ttu-id="303e6-118">![クラスター名と IP を使用して BizTalk ログ配布](../technical-guides/media/5055689e-c26b-4077-a531-74a50fec1393.gif "5055689e-c26b-4077-a531-74a50fec1393")</span><span class="sxs-lookup"><span data-stu-id="303e6-118">![BizTalk Log Shipping using a Cluster name and IP](../technical-guides/media/5055689e-c26b-4077-a531-74a50fec1393.gif "5055689e-c26b-4077-a531-74a50fec1393")</span></span>  
  
 <span data-ttu-id="303e6-119">**Windows Server クラスター名と IP アドレス リソースを使用した BizTalk Server のログ配布の実装**</span><span class="sxs-lookup"><span data-stu-id="303e6-119">**BizTalk Server Log Shipping implementation using Windows Server cluster name and IP address resources**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303e6-120">参照</span><span class="sxs-lookup"><span data-stu-id="303e6-120">See Also</span></span>  
 <span data-ttu-id="303e6-121">[データベースの高可用性](../technical-guides/high-availability-for-databases.md) </span><span class="sxs-lookup"><span data-stu-id="303e6-121">[High Availability for Databases](../technical-guides/high-availability-for-databases.md) </span></span>  
 <span data-ttu-id="303e6-122">[ログ配布の BizTalk Server の構成](../technical-guides/configuring-biztalk-server-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="303e6-122">[Configuring BizTalk Server Log Shipping](../technical-guides/configuring-biztalk-server-log-shipping.md) </span></span>  
 [<span data-ttu-id="303e6-123">バックアップの BizTalk Server のジョブ内のデータベースを復元する方法</span><span class="sxs-lookup"><span data-stu-id="303e6-123">How to Restore Databases in the Backup BizTalk Server Job</span></span>](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)