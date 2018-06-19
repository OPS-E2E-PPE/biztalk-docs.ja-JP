---
title: BizTalk Server Databases1 をクラスタ リング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, how to
- clustering, SQL Servers
- SQL Server, clustering
- BizTalk Server Configuration Wizard
- high availability, databases
- clustering, BizTalk Server Configuration Wizard
- clustering, databases
- clustering, prerequisites
ms.assetid: 9a1ed843-483b-4a56-961b-bc6801a07b64
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 983023ceb88618a540d922481c4cb185a076ae3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232434"
---
# <a name="clustering-the-biztalk-server-databases"></a><span data-ttu-id="0b889-102">BizTalk Server データベースのクラスター化</span><span class="sxs-lookup"><span data-stu-id="0b889-102">Clustering the BizTalk Server Databases</span></span>
<span data-ttu-id="0b889-103">このセクションでは、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションに高可用性を導入するためのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="0b889-103">This section provides guidelines for deploying a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution with high availability.</span></span> <span data-ttu-id="0b889-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースに障害が発生すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境は正常に機能することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="0b889-104">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases become unavailable, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment will not function correctly.</span></span> <span data-ttu-id="0b889-105">次の図に示すように、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースに対して、Microsoft SQL Server クラスターを作成することによって高可用性を確保できます。</span><span class="sxs-lookup"><span data-stu-id="0b889-105">To provide high availability, you can create a Microsoft SQL Server cluster for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="0b889-106">![BizTalk Server のデータベース層](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span><span class="sxs-lookup"><span data-stu-id="0b889-106">![BizTalk Server Database Tier](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span></span>  
  
 <span data-ttu-id="0b889-107">高可用性を実現する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、Windows Server フェールオーバー クラスターで SQL Server および使用するための共有ディスク アレイを実行するには、少なくとも 2 台のコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b889-107">To provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must have at least two computers that are running SQL Server and a shared disk array for use by a  Windows Server Failover Cluster.</span></span>  
  
## <a name="procedures-for-clustering-the-databases"></a><span data-ttu-id="0b889-108">データベースをクラスター化するための手順</span><span class="sxs-lookup"><span data-stu-id="0b889-108">Procedures for Clustering the Databases</span></span>  
  
#### <a name="before-you-start"></a><span data-ttu-id="0b889-109">開始前の準備</span><span class="sxs-lookup"><span data-stu-id="0b889-109">Before you start</span></span>  
  
1.  <span data-ttu-id="0b889-110">BizTalk Server 環境のドメイン グループを作成する場合は、Active Directory ドメイン グローバル グループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b889-110">When you create the domain groups for your BizTalk Server environment, you must create Active Directory domain global groups.</span></span>  
  
2.  <span data-ttu-id="0b889-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールして構成する前に、SQL Server クラスターを構成します。</span><span class="sxs-lookup"><span data-stu-id="0b889-111">Configure the SQL Server cluster before you install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0b889-112">SQL Server をクラスタ リングの詳細については、次を参照してください。 [Always On フェールオーバー クラスター インスタンス](https://technet.microsoft.com/library/ms189134.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="0b889-112">For more information about clustering SQL Server, see [Always On Failover Cluster Instances](https://technet.microsoft.com/library/ms189134.aspx).</span></span>  
  
3.  <span data-ttu-id="0b889-113">さらに、マスター シークレット サーバーをクラスター化する場合は、マスター シークレット サーバーを最初に構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b889-113">If you are also clustering the master secret server, configure that server first.</span></span> <span data-ttu-id="0b889-114">エンタープライズ シングル サインオンの高可用性の詳細については、次を参照してください。[エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)です。</span><span class="sxs-lookup"><span data-stu-id="0b889-114">For more information about high availability for Enterprise Single Sign-On, see [High Availability for Enterprise Single Sign-On](../core/high-availability-for-enterprise-single-sign-on.md).</span></span>  
  
#### <a name="to-run-the-biztalk-server-configuration-wizard"></a><span data-ttu-id="0b889-115">BizTalk Server の構成ウィザードを実行するには</span><span class="sxs-lookup"><span data-stu-id="0b889-115">To run the BizTalk Server Configuration Wizard</span></span>  
  
1.  <span data-ttu-id="0b889-116">ランタイム サーバーに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0b889-116">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a runtime server.</span></span>  
  
2.  <span data-ttu-id="0b889-117">BizTalk 構成プログラムを起動します。</span><span class="sxs-lookup"><span data-stu-id="0b889-117">Launch the BizTalk Configuration Program.</span></span> <span data-ttu-id="0b889-118">をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 構成**です。</span><span class="sxs-lookup"><span data-stu-id="0b889-118">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
3.  <span data-ttu-id="0b889-119">手順に従います[のインポートとエクスポートの BizTalk Server 構成](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)カスタム構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="0b889-119">Follow the steps in [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md) to apply a custom configuration.</span></span> <span data-ttu-id="0b889-120">BizTalk データベースの SQL Server クラスターを指定するには、SQL Server クラスターの名前を入力、**データベース**」の説明に従って、構成プログラムのダイアログ ボックス、**データベースの編集**セクションこのトピックではします。</span><span class="sxs-lookup"><span data-stu-id="0b889-120">To specify the SQL Server cluster for the BizTalk databases, enter the name of the SQL Server cluster in the **Databases** dialog of the configuration program as described in the **Editing Databases** section of this topic.</span></span>  
  
4.  <span data-ttu-id="0b889-121">次の手順で BizTalk Server の構成を完了[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="0b889-121">Complete the BizTalk Server configuration by following the instructions in [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b889-122">参照</span><span class="sxs-lookup"><span data-stu-id="0b889-122">See Also</span></span>  
 [<span data-ttu-id="0b889-123">高可用性の BizTalk Server 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="0b889-123">Creating a Highly Available BizTalk Server Environment</span></span>](../core/creating-a-highly-available-biztalk-server-environment.md)