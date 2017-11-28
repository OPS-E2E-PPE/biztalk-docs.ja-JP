---
title: "高可用性を実現して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9240e776-555c-4c38-8b59-8fef1ba6a567
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4521981bc3df67553c244a55c91c1eb045c8e0d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="providing-high-availability"></a><span data-ttu-id="f23f2-102">高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="f23f2-102">Providing High Availability</span></span>
<span data-ttu-id="f23f2-103">高可用性が提供される、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境内の各機能コンポーネントの冗長性を実装することによって環境。</span><span class="sxs-lookup"><span data-stu-id="f23f2-103">High availability is provided for a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment by implementing redundancy for each functional component in the environment.</span></span> <span data-ttu-id="f23f2-104">実行している複数のコンピューターをインストールすることで、BizTalk ホストの冗長性を実現できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk グループとで実行しているコンピューターの 1 つ以上を実行するホストのインスタンスを構成してから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループにします。</span><span class="sxs-lookup"><span data-stu-id="f23f2-104">Redundancy for a BizTalk Host can be accomplished by installing multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a BizTalk group and then configuring instances of the host to run on more than one of the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="f23f2-105">その他のコンポーネントの冗長性、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境でリソースとして、コンポーネントを構成することによって実現できます、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター。</span><span class="sxs-lookup"><span data-stu-id="f23f2-105">Redundancy for other components in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment can be accomplished by configuring the components as resources in a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f23f2-106">リソースとして BizTalk ホストの構成にも対応して、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスターで、特定の BizTalk アダプターの高可用性を実現することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f23f2-106"> also accommodates configuring BizTalk Hosts as resources in a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster, which is recommended to provide high availability for certain BizTalk adapters.</span></span>  
  
 <span data-ttu-id="f23f2-107">このセクションの機能コンポーネントの高可用性を実現する方法について説明、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="f23f2-107">This section describes how to provide high availability for the functional components in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f23f2-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f23f2-108">In This Section</span></span>  
  
-   [<span data-ttu-id="f23f2-109">高 Availability2 の計画</span><span class="sxs-lookup"><span data-stu-id="f23f2-109">Planning for High Availability2</span></span>](../technical-guides/planning-for-high-availability2.md)  
  
-   [<span data-ttu-id="f23f2-110">BizTalk ホストの高可用性</span><span class="sxs-lookup"><span data-stu-id="f23f2-110">High Availability for BizTalk Hosts</span></span>](../technical-guides/high-availability-for-biztalk-hosts.md)  
  
-   [<span data-ttu-id="f23f2-111">データベースの高可用性</span><span class="sxs-lookup"><span data-stu-id="f23f2-111">High Availability for Databases</span></span>](../technical-guides/high-availability-for-databases.md)  
  
-   [<span data-ttu-id="f23f2-112">マスター シークレット サーバーの高可用性</span><span class="sxs-lookup"><span data-stu-id="f23f2-112">High Availability for the Master Secret Server</span></span>](../technical-guides/high-availability-for-the-master-secret-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="f23f2-113">参照</span><span class="sxs-lookup"><span data-stu-id="f23f2-113">See Also</span></span>  
 [<span data-ttu-id="f23f2-114">災害復旧</span><span class="sxs-lookup"><span data-stu-id="f23f2-114">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)