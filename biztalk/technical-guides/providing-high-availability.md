---
title: 高可用性の実現 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9240e776-555c-4c38-8b59-8fef1ba6a567
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e482709ae5a9c6b1ea67446773eaadcdc26a25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395100"
---
# <a name="providing-high-availability"></a><span data-ttu-id="064a8-102">高可用性の実現</span><span class="sxs-lookup"><span data-stu-id="064a8-102">Providing High Availability</span></span>
<span data-ttu-id="064a8-103">高可用性を実現する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境内の各機能コンポーネントの冗長性を実装することで環境。</span><span class="sxs-lookup"><span data-stu-id="064a8-103">High availability is provided for a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment by implementing redundancy for each functional component in the environment.</span></span> <span data-ttu-id="064a8-104">実行している複数のコンピューターにインストールすることで、BizTalk ホストの冗長性を実現できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk グループで実行しているコンピューターの 1 つ以上を実行するホストのインスタンスの構成で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。</span><span class="sxs-lookup"><span data-stu-id="064a8-104">Redundancy for a BizTalk Host can be accomplished by installing multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a BizTalk group and then configuring instances of the host to run on more than one of the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="064a8-105">他のコンポーネントの冗長性、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にリソースとして、コンポーネントを構成することで環境を実現できます、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター。</span><span class="sxs-lookup"><span data-stu-id="064a8-105">Redundancy for other components in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment can be accomplished by configuring the components as resources in a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="064a8-106">内のリソースとして BizTalk ホストの構成にも対応して、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスターで、特定の BizTalk アダプターの高可用性を実現するをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="064a8-106">also accommodates configuring BizTalk Hosts as resources in a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster, which is recommended to provide high availability for certain BizTalk adapters.</span></span>  
  
 <span data-ttu-id="064a8-107">このセクションの機能コンポーネントの高可用性を実現する方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="064a8-107">This section describes how to provide high availability for the functional components in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="064a8-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="064a8-108">In This Section</span></span>  
  
-   [<span data-ttu-id="064a8-109">高 Availability2 の計画</span><span class="sxs-lookup"><span data-stu-id="064a8-109">Planning for High Availability2</span></span>](../technical-guides/planning-for-high-availability2.md)  
  
-   [<span data-ttu-id="064a8-110">BizTalk ホストの高可用性</span><span class="sxs-lookup"><span data-stu-id="064a8-110">High Availability for BizTalk Hosts</span></span>](../technical-guides/high-availability-for-biztalk-hosts.md)  
  
-   [<span data-ttu-id="064a8-111">データベースの高可用性</span><span class="sxs-lookup"><span data-stu-id="064a8-111">High Availability for Databases</span></span>](../technical-guides/high-availability-for-databases.md)  
  
-   [<span data-ttu-id="064a8-112">マスター シークレット サーバーの高可用性</span><span class="sxs-lookup"><span data-stu-id="064a8-112">High Availability for the Master Secret Server</span></span>](../technical-guides/high-availability-for-the-master-secret-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="064a8-113">参照</span><span class="sxs-lookup"><span data-stu-id="064a8-113">See Also</span></span>  
 [<span data-ttu-id="064a8-114">ディザスター リカバリー</span><span class="sxs-lookup"><span data-stu-id="064a8-114">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)