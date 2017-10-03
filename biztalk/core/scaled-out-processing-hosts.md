---
title: "スケール アウトされた処理ホスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- high availability
- hosts, processing
- hosts, high availability
- scaling, hosts
- hosts, planning
- hosts, scaling
- clustering
ms.assetid: c72ce8fc-7593-4700-8398-23d1a20515c3
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ee36777a5c64713fd31e86fe6ef2a1886b3348
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-out-processing-hosts"></a><span data-ttu-id="5cf6b-102">スケールアウトした処理ホスト</span><span class="sxs-lookup"><span data-stu-id="5cf6b-102">Scaled-Out Processing Hosts</span></span>
<span data-ttu-id="5cf6b-103">スケールアウトした処理ホストでは、オーケストレーション機能を 2 台以上のホスト コンピューターに分離することで、パフォーマンスの向上と高可用性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="5cf6b-103">A scaled-out processing host improves performance and provides high availability by isolating orchestration functionality onto two or more separate host computers.</span></span> <span data-ttu-id="5cf6b-104">この分離により、複数のコンピューターを処理ホストに追加して冗長性を持たせることができます。</span><span class="sxs-lookup"><span data-stu-id="5cf6b-104">This isolation lets you add multiple computers to a processing host for redundancy.</span></span> <span data-ttu-id="5cf6b-105">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の処理ホストは、各種ビジネス プロセスの調整を行うホスト インスタンスを 1 つ以上実行し、オーケストレーション用にプログラムで使用するオブジェクトのインスタンスを 1 つ作成します。</span><span class="sxs-lookup"><span data-stu-id="5cf6b-105">A processing host in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runs one or more host instances that coordinate various business processes and creates an instance of programmatic objects for orchestrations.</span></span>  
  
 <span data-ttu-id="5cf6b-106">次の図は、処理ホストのインスタンスを実行する 2 台のコンピューターを使用して処理ホストの高可用性を実現した、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を示しています。</span><span class="sxs-lookup"><span data-stu-id="5cf6b-106">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability for the processing host by having two computers that are running instances of the processing host.</span></span> <span data-ttu-id="5cf6b-107">この図に示されている受信ホストおよび送信ホストの可用性は高くないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5cf6b-107">Note that in this figure the receiving and sending hosts are not highly available.</span></span>  
  
 <span data-ttu-id="5cf6b-108">![スケール アウトされた処理ホスト](../core/media/tdi-ha-scaleprocess.gif "TDI_HA_ScaleProcess")</span><span class="sxs-lookup"><span data-stu-id="5cf6b-108">![Scaled Out Processing Host](../core/media/tdi-ha-scaleprocess.gif "TDI_HA_ScaleProcess")</span></span>  
  
 <span data-ttu-id="5cf6b-109">この構成では、処理ホストのインスタンスを個別に実行している 2 台の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターに、オーケストレーション処理の負荷が分散されます。</span><span class="sxs-lookup"><span data-stu-id="5cf6b-109">In this configuration, the work for processing orchestrations is load balanced between two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers that have instances of the processing host and run independently of each other.</span></span> <span data-ttu-id="5cf6b-110">一方のコンピューターでエラーや障害が発生した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、他方のコンピューターのホスト インスタンスを使用して残りのオーケストレーションを処理します。</span><span class="sxs-lookup"><span data-stu-id="5cf6b-110">If one computer encounters errors or fails, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically uses the host instance on the other computer to process remaining orchestrations.</span></span>  
  
## <a name="maintaining-orchestration-state"></a><span data-ttu-id="5cf6b-111">オーケストレーションの状態の保存</span><span class="sxs-lookup"><span data-stu-id="5cf6b-111">Maintaining Orchestration State</span></span>  
 <span data-ttu-id="5cf6b-112">BizTalk Server では、オーケストレーションの状態が Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] で一元的に保存されます。ローカルの各 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターには保存されません。</span><span class="sxs-lookup"><span data-stu-id="5cf6b-112">BizTalk Server maintains orchestration state centrally in Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and not locally on each [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span> <span data-ttu-id="5cf6b-113">メッセージ ボックス データベースの状態を保存することで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、単一の処理ホスト インスタンスに依存することなく、どの処理ホスト インスタンスでもオーケストレーションを処理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5cf6b-113">By persisting the state in the MessageBox database, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] overcomes the limitation of relying on a single processing host instance to process the orchestration, and lets any processing host instance process the orchestration.</span></span> <span data-ttu-id="5cf6b-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のオーケストレーション処理中にエラーが発生した場合、同じ処理ホストの別のインスタンスが、最後に保存した状態からオーケストレーションを処理できます。</span><span class="sxs-lookup"><span data-stu-id="5cf6b-114">If an error occurs while [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes an orchestration, another instance of the same processing host can complete the orchestration from the last persisted state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cf6b-115">参照</span><span class="sxs-lookup"><span data-stu-id="5cf6b-115">See Also</span></span>  
 [<span data-ttu-id="5cf6b-116">BizTalk ホストの高可用性</span><span class="sxs-lookup"><span data-stu-id="5cf6b-116">Providing High Availability for BizTalk Hosts</span></span>](../core/providing-high-availability-for-biztalk-hosts.md)