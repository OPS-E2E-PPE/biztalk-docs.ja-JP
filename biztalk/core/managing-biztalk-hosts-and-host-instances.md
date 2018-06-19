---
title: BizTalk ホストとホスト インスタンスを管理する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [hosts]
- hosts, managing
- managing [hosts], about managing hosts
ms.assetid: 7f329804-ca44-4799-8a5d-38b3146d8e5e
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e60981f69bc3ff71bdd8581659f9cdd20f87467
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262586"
---
# <a name="managing-biztalk-hosts-and-host-instances"></a><span data-ttu-id="b3edc-102">BizTalk ホストとホスト インスタンスの管理</span><span class="sxs-lookup"><span data-stu-id="b3edc-102">Managing BizTalk Hosts and Host Instances</span></span>
<span data-ttu-id="b3edc-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホストとは、0 個以上の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実行時プロセスの論理的セットです。アダプター ハンドラー、受信場所 (パイプラインを含む)、オーケストレーションなどの各種アイテムをここに展開します。</span><span class="sxs-lookup"><span data-stu-id="b3edc-103">A [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Host is a logical set of zero or more [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time processes in which you deploy items such as adapter handlers, receive locations (including pipelines), and orchestrations.</span></span> <span data-ttu-id="b3edc-104">ホストの詳細については、次を参照してください。[ホスト](../core/hosts.md)です。</span><span class="sxs-lookup"><span data-stu-id="b3edc-104">For more information about hosts, see [Hosts](../core/hosts.md).</span></span>  
  
 <span data-ttu-id="b3edc-105">ホスト インスタンスとは、メッセージの処理や送受信を行うプロセスです。</span><span class="sxs-lookup"><span data-stu-id="b3edc-105">A host instance is the process where the message processing, receiving, and transmitting occurs.</span></span> <span data-ttu-id="b3edc-106">ホスト インスタンスは、1 つ以上のホストがマップされており、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を稼働する各サーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="b3edc-106">You install a host instance on each server running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that has one or more hosts mapped to that server.</span></span> <span data-ttu-id="b3edc-107">ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)です。</span><span class="sxs-lookup"><span data-stu-id="b3edc-107">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
 <span data-ttu-id="b3edc-108">ホストの特性は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3edc-108">Hosts have the following characteristics:</span></span>  
  
-   <span data-ttu-id="b3edc-109">ホストは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オブジェクトの論理的なコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="b3edc-109">Hosts are the logical containers of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="b3edc-110">特定のホストのインスタンスは各サーバーに 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="b3edc-110">Only one instance of a specific host can exist on each server.</span></span>  
  
-   <span data-ttu-id="b3edc-111">1 つのホストを複数のサーバーにマップできます。</span><span class="sxs-lookup"><span data-stu-id="b3edc-111">You can map one host to multiple servers.</span></span>  
  
 <span data-ttu-id="b3edc-112">ホスト インスタンスの特性は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3edc-112">Host instances have the following characteristics:</span></span>  
  
-   <span data-ttu-id="b3edc-113">ホスト インスタンスは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オブジェクトの物理的なコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="b3edc-113">Host instances are the physical containers of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="b3edc-114">サーバーをホストにマップするときに、ホスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3edc-114">You create a host instance when you map a server to a host.</span></span>  
  
-   <span data-ttu-id="b3edc-115">負荷分散目的で、またはフェールオーバー用に、さまざまなホストの複数のホスト インスタンスを 1 台のサーバーに配置できます。</span><span class="sxs-lookup"><span data-stu-id="b3edc-115">Multiple host instances (of different hosts) can exist on a server when load balancing or for failover.</span></span>  
  
 <span data-ttu-id="b3edc-116">次の図に、サーバー、ホスト、およびホスト インスタンスの関係を示します。</span><span class="sxs-lookup"><span data-stu-id="b3edc-116">The following figure shows the relationship between servers, hosts, and host instances.</span></span>  
  
 <span data-ttu-id="b3edc-117">![ホスト、ホスト インスタンス、およびサーバーの関係](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span><span class="sxs-lookup"><span data-stu-id="b3edc-117">![Hosts, host instances, and server relationships](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span></span>  
<span data-ttu-id="b3edc-118">ホスト、ホスト インスタンス、およびサーバー間のリレーションシップ</span><span class="sxs-lookup"><span data-stu-id="b3edc-118">Relationship between hosts, host instances, and servers</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3edc-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b3edc-119">In This Section</span></span>  
  
-   [<span data-ttu-id="b3edc-120">BizTalk Server のホスティング環境を作成する方法</span><span class="sxs-lookup"><span data-stu-id="b3edc-120">How to Create a BizTalk Server Hosting Environment</span></span>](../core/how-to-create-a-biztalk-server-hosting-environment.md)  
  
-   [<span data-ttu-id="b3edc-121">新しいホストを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b3edc-121">How to Create a New Host</span></span>](../core/how-to-create-a-new-host.md)  
  
-   [<span data-ttu-id="b3edc-122">ホストのプロパティを変更する方法</span><span class="sxs-lookup"><span data-stu-id="b3edc-122">How to Modify Host Properties</span></span>](../core/how-to-modify-host-properties.md)  
  
-   [<span data-ttu-id="b3edc-123">ホストを削除する方法</span><span class="sxs-lookup"><span data-stu-id="b3edc-123">How to Delete a Host</span></span>](../core/how-to-delete-a-host.md)  
  
-   [<span data-ttu-id="b3edc-124">ホスト インスタンスを追加する方法</span><span class="sxs-lookup"><span data-stu-id="b3edc-124">How to Add a Host Instance</span></span>](../core/how-to-add-a-host-instance.md)  
  
-   [<span data-ttu-id="b3edc-125">ホスト インスタンスを起動する方法</span><span class="sxs-lookup"><span data-stu-id="b3edc-125">How to Start a Host Instance</span></span>](../core/how-to-start-a-host-instance.md)  
  
-   [<span data-ttu-id="b3edc-126">ホスト インスタンスを停止する方法</span><span class="sxs-lookup"><span data-stu-id="b3edc-126">How to Stop a Host Instance</span></span>](../core/how-to-stop-a-host-instance.md)  
  
-   [<span data-ttu-id="b3edc-127">ホスト インスタンスを削除する方法</span><span class="sxs-lookup"><span data-stu-id="b3edc-127">How to Delete a Host Instance</span></span>](../core/how-to-delete-a-host-instance.md)  
  
-   [<span data-ttu-id="b3edc-128">ホスト インスタンスのプロパティを変更する方法</span><span class="sxs-lookup"><span data-stu-id="b3edc-128">How to Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)