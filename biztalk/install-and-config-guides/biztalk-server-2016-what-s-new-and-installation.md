---
title: "BizTalk Server 2016: の新機能、およびインストール |Microsoft ドキュメント"
description: "新しい、およびインストールを実行すると BizTalk Server 2016 にアップグレードの概要"
ms.custom: 
ms.prod: biztalk-server
ms.date: 08/10/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 229043b3-b1a4-47e9-9c0e-1fba5ec5b417
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 212eee411c78bacd3d46ca66762fc8fc0f25fa05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-2016-whats-new-and-installation"></a><span data-ttu-id="19548-103">BizTalk Server 2016: 新機能およびインストール</span><span class="sxs-lookup"><span data-stu-id="19548-103">BizTalk Server 2016: What's New, and Installation</span></span>

## <a name="get-started-with-biztalk-server-2016"></a><span data-ttu-id="19548-104">BizTalk Server 2016 の概要</span><span class="sxs-lookup"><span data-stu-id="19548-104">Get started with BizTalk Server 2016</span></span>

[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]<span data-ttu-id="19548-105"> は、オンプレミスの最新リリースです。</span><span class="sxs-lookup"><span data-stu-id="19548-105"> is the latest on-premises release.</span></span> <span data-ttu-id="19548-106">この新しいバージョンでは、新しい Logic Apps アダプターを使用して緊密に Azure と統合することを想定し、ファイル アダプターや WCF-SQL アダプターを使用して Azure リソースに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="19548-106">With this new version, you can expect closer integration with Azure using the new Logic Apps adapter, and connect to Azure resources using the File and WCF-SQL adapters.</span></span> 

<span data-ttu-id="19548-107">最大の変更点の 1 つは、SQL Server 2016 AlwaysOn 可用性グループ (AG) のサポートです。</span><span class="sxs-lookup"><span data-stu-id="19548-107">One of the biggest changes is support for SQL Server 2016 AlwaysOn Availability Groups (AG).</span></span> <span data-ttu-id="19548-108">このサポートには、オンプレミスの BizTalk Server の使用、および BizTalk Server の Azure Virtual Machines の使用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="19548-108">This support covers using BizTalk Server on-premises, and using BizTalk Server Azure virtual machines.</span></span> <span data-ttu-id="19548-109">AlwaysOn では、Azure Virtual Machines を使用して高可用性ソリューションを実現できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="19548-109">With AlwaysOn, you can now have a highly-available solution using Azure virtual machines.</span></span>

<span data-ttu-id="19548-110">SHA-2 サポート、パーティ用のバインドのインポートおよびエクスポート オプション、管理コンソールの改善など、さまざまな更新プログラムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="19548-110">There have also been updates to SHA-2 support, import and export binding options for parties, Administration console improvements, and much much more.</span></span> 

<span data-ttu-id="19548-111">この [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] のトピックでは、変更点やインストールなど、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] の特定のドキュメントに注目しています。</span><span class="sxs-lookup"><span data-stu-id="19548-111">In this [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] set of topics, we focus on the specific documentation for [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], including what's changed, and the installation.</span></span> <span data-ttu-id="19548-112">そのため、高可用性、BizTalk 環境の監視などの詳細を閲覧する必要がある場合は、「[BizTalk Server の主要なドキュメント](../core/biztalk-server-core-documentation.md)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="19548-112">So, if you want to read about high availability, monitoring your BIzTalk environment, and more, then go to the [BizTalk Server core documentation](../core/biztalk-server-core-documentation.md).</span></span> <span data-ttu-id="19548-113">BizTalk Server を構成する必要がある場合は、「[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19548-113">If you want to configure BizTalk Server, then go [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span> <span data-ttu-id="19548-114">新機能を閲覧して、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] をインストールする必要がある場合は、次のリンクから作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="19548-114">If you want to read about what's new, and install [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], then get started with the following links:</span></span>  

* [<span data-ttu-id="19548-115">新機能</span><span class="sxs-lookup"><span data-stu-id="19548-115">What's New</span></span>](../install-and-config-guides/what-s-new-in-biztalk-server-2016.md)  
* [<span data-ttu-id="19548-116">ハードウェアとソフトウェアの要件</span><span class="sxs-lookup"><span data-stu-id="19548-116">Hardware and Software Requirements</span></span>](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
* [<span data-ttu-id="19548-117">前提条件の設定とインストール</span><span class="sxs-lookup"><span data-stu-id="19548-117">Set up and install prerequisites</span></span>](../install-and-config-guides/set-up-and-install-prerequisites-for-biztalk-server-2016.md)  
* [<span data-ttu-id="19548-118">BizTalk Server のインストール</span><span class="sxs-lookup"><span data-stu-id="19548-118">Install BizTalk Server</span></span>](../install-and-config-guides/install-biztalk-server-2016.md)
* [<span data-ttu-id="19548-119">BizTalk Server のアップグレード</span><span class="sxs-lookup"><span data-stu-id="19548-119">Upgrade BizTalk Server</span></span>](../install-and-config-guides/upgrade-to-biztalk-server-2016.md)
  
## <a name="more-good-stuff"></a><span data-ttu-id="19548-120">便利な機能</span><span class="sxs-lookup"><span data-stu-id="19548-120">More good stuff</span></span>
[<span data-ttu-id="19548-121">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="19548-121">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)

[<span data-ttu-id="19548-122">BizTalk Server のクラスター構成</span><span class="sxs-lookup"><span data-stu-id="19548-122">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)

[<span data-ttu-id="19548-123">環境を最適化するための構成後の手順</span><span class="sxs-lookup"><span data-stu-id="19548-123">Post-configuration steps to optimize your environment</span></span>](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)

[<span data-ttu-id="19548-124">BizTalk Server 構成の操作</span><span class="sxs-lookup"><span data-stu-id="19548-124">Import and Export BizTalk Server Configuration</span></span>](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)

[<span data-ttu-id="19548-125">BizTalk Server データベースの統合</span><span class="sxs-lookup"><span data-stu-id="19548-125">Consolidate the BizTalk Server Databases</span></span>](../install-and-config-guides/consolidate-the-biztalk-server-databases2.md)

[<span data-ttu-id="19548-126">構成フレームワークを使用した作業</span><span class="sxs-lookup"><span data-stu-id="19548-126">Working with the Configuration Framework</span></span>](../install-and-config-guides/working-with-the-configuration-framework.md)

[<span data-ttu-id="19548-127">BizTalk Server の安全な展開</span><span class="sxs-lookup"><span data-stu-id="19548-127">Securing Your BizTalk Server Deployment</span></span>](../install-and-config-guides/securing-your-biztalk-server-deployment.md)

[<span data-ttu-id="19548-128">BizTalk Server の削除 (アンインストールおよび構成の解除)</span><span class="sxs-lookup"><span data-stu-id="19548-128">Uninstall and unconfigure BizTalk Server to remove it</span></span>](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)