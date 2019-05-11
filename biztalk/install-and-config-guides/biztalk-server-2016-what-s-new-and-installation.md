---
title: BizTalk Server 2016:新機能についてとインストール |Microsoft Docs
description: 新機能、およびインストールを実行して BizTalk Server 2016 にアップグレードの概要
ms.custom: ''
ms.prod: biztalk-server
ms.date: 08/10/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 229043b3-b1a4-47e9-9c0e-1fba5ec5b417
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d877ba2b81a536e8c1818c243cf0eb82e5f2c8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266500"
---
# <a name="biztalk-server-2016-whats-new-and-installation"></a><span data-ttu-id="cf2a8-103">BizTalk Server 2016:新機能、およびインストール</span><span class="sxs-lookup"><span data-stu-id="cf2a8-103">BizTalk Server 2016: What's New, and Installation</span></span>

## <a name="get-started-with-biztalk-server-2016"></a><span data-ttu-id="cf2a8-104">BizTalk Server 2016 を概要します。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-104">Get started with BizTalk Server 2016</span></span>

[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] <span data-ttu-id="cf2a8-105">最新のオンプレミスのリリースです。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-105">is the latest on-premises release.</span></span> <span data-ttu-id="cf2a8-106">この新しいバージョンでは、新しい Logic Apps アダプターを使用して Azure でとの統合を期待でき、ファイルや WCF-SQL アダプターを使用して Azure リソースに接続できます。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-106">With this new version, you can expect closer integration with Azure using the new Logic Apps adapter, and connect to Azure resources using the File and WCF-SQL adapters.</span></span> 

<span data-ttu-id="cf2a8-107">最大の変更点の 1 つは、サポートの SQL Server 2016 AlwaysOn 可用性グループ (AG) です。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-107">One of the biggest changes is support for SQL Server 2016 AlwaysOn Availability Groups (AG).</span></span> <span data-ttu-id="cf2a8-108">このサポートでは BizTalk Server、オンプレミスを使用して、BizTalk Server の Azure 仮想マシンを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-108">This support covers using BizTalk Server on-premises, and using BizTalk Server Azure virtual machines.</span></span> <span data-ttu-id="cf2a8-109">AlwaysOn では、Azure の仮想マシンを使用して高可用性ソリューションようになりましたことができます。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-109">With AlwaysOn, you can now have a highly-available solution using Azure virtual machines.</span></span>

<span data-ttu-id="cf2a8-110">Sha-2 サポート、インポートおよびエクスポートのパーティ、管理コンソールの改善、および多くのオプションをはるかにバインドする更新プログラムもありました。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-110">There have also been updates to SHA-2 support, import and export binding options for parties, Administration console improvements, and much much more.</span></span> 

<span data-ttu-id="cf2a8-111">この[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]の特定のドキュメントに注目のトピックの設定、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]など、変更内容、およびインストールします。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-111">In this [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] set of topics, we focus on the specific documentation for [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], including what's changed, and the installation.</span></span> <span data-ttu-id="cf2a8-112">そのため、高可用性の詳細を表示する場合など、BIzTalk 環境を監視しに移動、 [BizTalk Server 基本ドキュメント](../core/biztalk-server-core-documentation.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-112">So, if you want to read about high availability, monitoring your BIzTalk environment, and more, then go to the [BizTalk Server core documentation](../core/biztalk-server-core-documentation.md).</span></span> <span data-ttu-id="cf2a8-113">BizTalk Server を構成する場合は、やがて[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-113">If you want to configure BizTalk Server, then go [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span> <span data-ttu-id="cf2a8-114">インストールに関する新機能については、必要に応じて[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]、次のリンクを開始します。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-114">If you want to read about what's new, and install [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], then get started with the following links:</span></span>  

* [<span data-ttu-id="cf2a8-115">新機能</span><span class="sxs-lookup"><span data-stu-id="cf2a8-115">What's New</span></span>](../install-and-config-guides/what-s-new-in-biztalk-server-2016.md)  
* [<span data-ttu-id="cf2a8-116">ハードウェアとソフトウェアの要件</span><span class="sxs-lookup"><span data-stu-id="cf2a8-116">Hardware and Software Requirements</span></span>](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
* [<span data-ttu-id="cf2a8-117">セットアップし、インストールの前提条件</span><span class="sxs-lookup"><span data-stu-id="cf2a8-117">Set up and install prerequisites</span></span>](../install-and-config-guides/set-up-and-install-prerequisites-for-biztalk-server-2016.md)  
* [<span data-ttu-id="cf2a8-118">BizTalk Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-118">Install BizTalk Server</span></span>](../install-and-config-guides/install-biztalk-server-2016.md)
* [<span data-ttu-id="cf2a8-119">BizTalk Server をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-119">Upgrade BizTalk Server</span></span>](../install-and-config-guides/upgrade-to-biztalk-server-2016.md)
  
## <a name="more-good-stuff"></a><span data-ttu-id="cf2a8-120">便利な機能</span><span class="sxs-lookup"><span data-stu-id="cf2a8-120">More good stuff</span></span>
[<span data-ttu-id="cf2a8-121">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="cf2a8-121">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)

[<span data-ttu-id="cf2a8-122">BizTalk Server のクラスター構成</span><span class="sxs-lookup"><span data-stu-id="cf2a8-122">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)

[<span data-ttu-id="cf2a8-123">環境を最適化するための構成後の手順</span><span class="sxs-lookup"><span data-stu-id="cf2a8-123">Post-configuration steps to optimize your environment</span></span>](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)

[<span data-ttu-id="cf2a8-124">インポートおよびエクスポートの BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="cf2a8-124">Import and Export BizTalk Server Configuration</span></span>](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)

[<span data-ttu-id="cf2a8-125">BizTalk Server データベースを統合します。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-125">Consolidate the BizTalk Server Databases</span></span>](../install-and-config-guides/consolidate-the-biztalk-server-databases2.md)

[<span data-ttu-id="cf2a8-126">構成フレームワークを使用</span><span class="sxs-lookup"><span data-stu-id="cf2a8-126">Working with the Configuration Framework</span></span>](../install-and-config-guides/working-with-the-configuration-framework.md)

[<span data-ttu-id="cf2a8-127">BizTalk Server の展開をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="cf2a8-127">Securing Your BizTalk Server Deployment</span></span>](../install-and-config-guides/securing-your-biztalk-server-deployment.md)

[<span data-ttu-id="cf2a8-128">アンインストールし、それを削除する BizTalk Server の構成を解除</span><span class="sxs-lookup"><span data-stu-id="cf2a8-128">Uninstall and unconfigure BizTalk Server to remove it</span></span>](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)