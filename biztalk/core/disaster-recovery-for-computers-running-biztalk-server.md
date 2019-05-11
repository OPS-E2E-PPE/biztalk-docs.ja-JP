---
title: BizTalk Server を実行しているコンピューターのディザスター リカバリー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10a2c26d-55d5-45d1-9fb1-e0664f005c21
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7469c97409ce53a995db95b263f5874e737a9905
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350994"
---
# <a name="disaster-recovery-for-computers-running-biztalk-server"></a><span data-ttu-id="83d81-102">BizTalk Server を実行しているコンピューターのディザスター リカバリー</span><span class="sxs-lookup"><span data-stu-id="83d81-102">Disaster Recovery for Computers Running BizTalk Server</span></span>
<span data-ttu-id="83d81-103">組織内の BizTalk Server を実行しているコンピューターに、回復不可能なハードウェア障害が低下した場合は、同一のコンピューターで置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="83d81-103">If the computer running BizTalk Server in your organization suffers an unrecoverable hardware failure, you should replace it with an identical computer.</span></span> <span data-ttu-id="83d81-104">これは、すべての BizTalk Server データベースが破損しておらず、および BizTalk Server を実行しているコンピューターのいずれかでは、障害であると仮定します。</span><span class="sxs-lookup"><span data-stu-id="83d81-104">This assumes that the BizTalk Server databases are intact, and that the failure is in any one of the computers running BizTalk Server.</span></span>  
  
 <span data-ttu-id="83d81-105">方法の 1 つのインストールで BizTalk Server を実行しているすべてのコンピューターの更新されたイメージを維持することです。</span><span class="sxs-lookup"><span data-stu-id="83d81-105">One possible approach is to maintain an updated image of every computer running BizTalk Server in your installation.</span></span> <span data-ttu-id="83d81-106">コンピューターがハードウェア障害が低下したときに復旧アクションは、保存されたイメージを新しいコンピューターに展開するだけです。</span><span class="sxs-lookup"><span data-stu-id="83d81-106">When a computer suffers a hardware failure, the recovery action is as simple as deploying the stored image on a new computer.</span></span> <span data-ttu-id="83d81-107">障害復旧に関するトピックでこのようなイメージを格納することは不可能場合について説明します。</span><span class="sxs-lookup"><span data-stu-id="83d81-107">The disaster recovery topics address the case where storing such images is not feasible.</span></span>  
## <a name="recovering-different-editions-of-biztalk-server"></a><span data-ttu-id="83d81-108">BizTalk Server のさまざまなエディションを回復します。</span><span class="sxs-lookup"><span data-stu-id="83d81-108">Recovering Different Editions of BizTalk Server</span></span>  
 <span data-ttu-id="83d81-109">復旧方法は、コンピューターで実行されている BizTalk Server のエディションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="83d81-109">The recovery approach is different depending on the edition of BizTalk Server running on the computer.</span></span>  
  
 <span data-ttu-id="83d81-110">BizTalk Server Developer Edition および BizTalk Server Enterprise Edition を実行している複数のコンピューターの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が許可されます。</span><span class="sxs-lookup"><span data-stu-id="83d81-110">For BizTalk Server Developer Edition and BizTalk Server Enterprise Edition, multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are permitted.</span></span> <span data-ttu-id="83d81-111">BizTalk Server を実行しているコンピューターのいずれかが失敗した場合、代替コンピューターを準備し、既存の BizTalk グループに参加できます。</span><span class="sxs-lookup"><span data-stu-id="83d81-111">When one of the computers running BizTalk Server fails, you can prepare a replacement computer and join it to the existing BizTalk group.</span></span> <span data-ttu-id="83d81-112">この場合、同じ名前または別の名前を使用しているコンピューターを BizTalk グループに参加できます。</span><span class="sxs-lookup"><span data-stu-id="83d81-112">In this case, you can join a computer with either the same name or a different name to the BizTalk group.</span></span>  
  
 <span data-ttu-id="83d81-113">BizTalk Server の Standard Edition では、上記の方法が適していないために、BizTalk グループにコンピューターを結合できません。</span><span class="sxs-lookup"><span data-stu-id="83d81-113">For BizTalk Server Standard Edition, you cannot join the computer to a BizTalk group, so the above approach is not suitable.</span></span> <span data-ttu-id="83d81-114">代わりに、新しいコンピューターを設定し、復元に必要な手順を説明、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]その代替として機能させるための構成設定。</span><span class="sxs-lookup"><span data-stu-id="83d81-114">Instead, we outline the steps needed to set up a new computer and restore the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration settings so that it can function as a replacement.</span></span> <span data-ttu-id="83d81-115">詳細については、次を参照してください。 [BizTalk グループを回復する方法](../core/how-to-recover-the-biztalk-group.md)します。</span><span class="sxs-lookup"><span data-stu-id="83d81-115">For more information, see [How to Recover the BizTalk Group](../core/how-to-recover-the-biztalk-group.md).</span></span>  
  
## <a name="recovery-phases"></a><span data-ttu-id="83d81-116">復旧フェーズ</span><span class="sxs-lookup"><span data-stu-id="83d81-116">Recovery Phases</span></span>  
 <span data-ttu-id="83d81-117">BizTalk Server を実行しているコンピューターの回復は、3 つのフェーズを以下に分類できます。</span><span class="sxs-lookup"><span data-stu-id="83d81-117">The recovery of a computer running BizTalk Server can be classified into the following three phases:</span></span>  
  
1.  <span data-ttu-id="83d81-118">**基本プラットフォームの準備**</span><span class="sxs-lookup"><span data-stu-id="83d81-118">**Preparing the Base Platform**</span></span>  
  
     <span data-ttu-id="83d81-119">このフェーズには、オペレーティング システム、ソフトウェアの前提条件および適切な BizTalk Server コンポーネントを含むベースのプラットフォームで、コンピューターの準備が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83d81-119">This phase includes the preparation of a computer with the base platform including the operating system, software prerequisites and appropriate BizTalk Server components.</span></span> <span data-ttu-id="83d81-120">このガイドでは、BizTalk Server の構成を復元しようとすると、前に、基本プラットフォーム、前提条件、および BizTalk Server コンポーネントがインストールされているコンピューターがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="83d81-120">This guide assumes that before you attempt to restore the BizTalk Server configuration, you have a computer with the base platform, prerequisites, and BizTalk Server components installed.</span></span> <span data-ttu-id="83d81-121">このガイドでは、基本プラットフォームの復元は含まれません。</span><span class="sxs-lookup"><span data-stu-id="83d81-121">This guide does not cover base platform restoration.</span></span>  
  
2.  <span data-ttu-id="83d81-122">**BizTalk Server 構成を復元します。**</span><span class="sxs-lookup"><span data-stu-id="83d81-122">**Restoring the BizTalk Server Configuration**</span></span>  
  
     <span data-ttu-id="83d81-123">このフェーズでは、そのコンピューターの BizTalk Server 構成ファイルのコピーを含む、失敗したコンピューターで構成されている機能のレコードがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="83d81-123">This phase assumes that you have a record of the features configured on the failed computer, including a copy of the BizTalk Server configuration file for that computer.</span></span> <span data-ttu-id="83d81-124">このガイドでは、BizTalk Server の構成を復元するためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="83d81-124">This guide provides guidance for restoring the BizTalk Server configuration.</span></span>  
  
3.  <span data-ttu-id="83d81-125">**BizTalk アプリケーションの復元**</span><span class="sxs-lookup"><span data-stu-id="83d81-125">**Restoring BizTalk Applications**</span></span>  
  
     <span data-ttu-id="83d81-126">このフェーズでは、代替コンピューター上の BizTalk Server プロセスによってホストされているアプリケーションで接続されている .NET アセンブリを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83d81-126">This phase involves restoring the .NET assemblies connected with the applications that are hosted by the BizTalk Server processes on the replacement computer.</span></span> <span data-ttu-id="83d81-127">それぞれの場所またはコンピューターのグローバル アセンブリ キャッシュ (GAC) に、BizTalk アセンブリとは別のユーザー アセンブリなど、必要なすべてのアイテムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83d81-127">Any artifacts that are needed, such as user assemblies apart from BizTalk assemblies, should be installed in their respective locations or the global assembly cache (GAC) on the computer.</span></span> <span data-ttu-id="83d81-128">このガイドでは、このフェーズでいくつかのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="83d81-128">This guide provides some guidance on this phase.</span></span> <span data-ttu-id="83d81-129">ただし、ない個別のスクリプトや BizTalk アプリケーションを復元するためのツール。</span><span class="sxs-lookup"><span data-stu-id="83d81-129">However, there are no separate scripts or tools for restoring BizTalk applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d81-130">参照</span><span class="sxs-lookup"><span data-stu-id="83d81-130">See Also</span></span>  
 [<span data-ttu-id="83d81-131">BizTalk Server のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="83d81-131">Backing Up and Restoring BizTalk Server</span></span>](../core/backing-up-and-restoring-biztalk-server.md)