---
title: "BizTalk Server を実行しているコンピューターの災害復旧 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10a2c26d-55d5-45d1-9fb1-e0664f005c21
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0ca86ef9a412514fdf3f30f0a38cbac710e0f59
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="disaster-recovery-for-computers-running-biztalk-server"></a><span data-ttu-id="b51c1-102">BizTalk Server を実行しているコンピューターの災害復旧</span><span class="sxs-lookup"><span data-stu-id="b51c1-102">Disaster Recovery for Computers Running BizTalk Server</span></span>
<span data-ttu-id="b51c1-103">組織内の BizTalk Server を実行しているコンピューターで、復旧不可能なハードウェア障害が発生した場合、同等のコンピューターに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="b51c1-103">If the computer running BizTalk Server in your organization suffers an unrecoverable hardware failure, you should replace it with an identical computer.</span></span> <span data-ttu-id="b51c1-104">これは、BizTalk Server データベースは破損しておらず、障害は BizTalk Server を実行しているコンピューターのいずれかで発生したことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b51c1-104">This assumes that the BizTalk Server databases are intact, and that the failure is in any one of the computers running BizTalk Server.</span></span>  
  
 <span data-ttu-id="b51c1-105">このような場合の災害復旧の方法の 1 つは、環境内の BizTalk Server を実行しているすべてのコンピューターの更新されたイメージを保持しておくことです。</span><span class="sxs-lookup"><span data-stu-id="b51c1-105">One possible approach is to maintain an updated image of every computer running BizTalk Server in your installation.</span></span> <span data-ttu-id="b51c1-106">イメージを保存しておけば、コンピューターにハードウェア障害が発生したとき、復旧操作は保存されているイメージを新しいコンピューターに展開するのと同様に簡単です。</span><span class="sxs-lookup"><span data-stu-id="b51c1-106">When a computer suffers a hardware failure, the recovery action is as simple as deploying the stored image on a new computer.</span></span> <span data-ttu-id="b51c1-107">ディザスター リカバリーのトピックでは、そのようなイメージを保存しておくことができない場合について説明します。</span><span class="sxs-lookup"><span data-stu-id="b51c1-107">The disaster recovery topics address the case where storing such images is not feasible.</span></span>  
## <a name="recovering-different-editions-of-biztalk-server"></a><span data-ttu-id="b51c1-108">さまざまなエディションの BizTalk Server の復旧</span><span class="sxs-lookup"><span data-stu-id="b51c1-108">Recovering Different Editions of BizTalk Server</span></span>  
 <span data-ttu-id="b51c1-109">復旧方法は、コンピューターで実行している BizTalk Server のエディションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b51c1-109">The recovery approach is different depending on the edition of BizTalk Server running on the computer.</span></span>  
  
 <span data-ttu-id="b51c1-110">BizTalk Server Developer Edition および BizTalk Server Enterprise Edition を実行している複数のコンピューターの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が許可されます。</span><span class="sxs-lookup"><span data-stu-id="b51c1-110">For BizTalk Server Developer Edition and BizTalk Server Enterprise Edition, multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are permitted.</span></span> <span data-ttu-id="b51c1-111">BizTalk Server を実行しているコンピューターのいずれかで障害が発生した場合、代替コンピューターを用意して、そのコンピューターを既存の BizTalk グループに参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="b51c1-111">When one of the computers running BizTalk Server fails, you can prepare a replacement computer and join it to the existing BizTalk group.</span></span> <span data-ttu-id="b51c1-112">この場合、BizTalk グループに参加させるコンピューターの名前は、障害が発生したコンピューターと同じ名前でも別の名前でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="b51c1-112">In this case, you can join a computer with either the same name or a different name to the BizTalk group.</span></span>  
  
 <span data-ttu-id="b51c1-113">上記の方法が適していないための BizTalk Server の Standard Edition では、コンピューターを BizTalk グループに参加できません。</span><span class="sxs-lookup"><span data-stu-id="b51c1-113">For BizTalk Server Standard Edition, you cannot join the computer to a BizTalk group, so the above approach is not suitable.</span></span> <span data-ttu-id="b51c1-114">代わりに、代替コンピューターとして機能させる新しいコンピューターをセットアップして [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成設定を復元します。この操作に必要な手順の概要を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="b51c1-114">Instead, we outline the steps needed to set up a new computer and restore the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration settings so that it can function as a replacement.</span></span> <span data-ttu-id="b51c1-115">詳細については、次を参照してください。 [BizTalk グループを回復する方法](../core/how-to-recover-the-biztalk-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="b51c1-115">For more information, see [How to Recover the BizTalk Group](../core/how-to-recover-the-biztalk-group.md).</span></span>  
  
## <a name="recovery-phases"></a><span data-ttu-id="b51c1-116">復旧フェーズ</span><span class="sxs-lookup"><span data-stu-id="b51c1-116">Recovery Phases</span></span>  
 <span data-ttu-id="b51c1-117">BizTalk Server を実行しているコンピューターの復旧は、次の 3 つのフェーズに分類できます。</span><span class="sxs-lookup"><span data-stu-id="b51c1-117">The recovery of a computer running BizTalk Server can be classified into the following three phases:</span></span>  
  
1.  <span data-ttu-id="b51c1-118">**基本プラットフォームの準備**</span><span class="sxs-lookup"><span data-stu-id="b51c1-118">**Preparing the Base Platform**</span></span>  
  
     <span data-ttu-id="b51c1-119">このフェーズでは、オペレーティング システムなどの基本プラットフォーム、必要なソフトウェア、および適切な BizTalk Server コンポーネントが備わったコンピューターを準備します。</span><span class="sxs-lookup"><span data-stu-id="b51c1-119">This phase includes the preparation of a computer with the base platform including the operating system, software prerequisites and appropriate BizTalk Server components.</span></span> <span data-ttu-id="b51c1-120">このガイドでは、基本プラットフォーム、必要なソフトウェア、および BizTalk Server コンポーネントがインストールされているコンピューターを用意してから、BizTalk Server 構成の復元を試みることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b51c1-120">This guide assumes that before you attempt to restore the BizTalk Server configuration, you have a computer with the base platform, prerequisites, and BizTalk Server components installed.</span></span> <span data-ttu-id="b51c1-121">基本プラットフォームの復元については説明しません。</span><span class="sxs-lookup"><span data-stu-id="b51c1-121">This guide does not cover base platform restoration.</span></span>  
  
2.  <span data-ttu-id="b51c1-122">**BizTalk Server の構成を復元します。**</span><span class="sxs-lookup"><span data-stu-id="b51c1-122">**Restoring the BizTalk Server Configuration**</span></span>  
  
     <span data-ttu-id="b51c1-123">このフェーズでは、障害が発生したコンピューターの BizTalk Server 構成ファイルのコピーなど、そのコンピューターで構成されていた機能を記録していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b51c1-123">This phase assumes that you have a record of the features configured on the failed computer, including a copy of the BizTalk Server configuration file for that computer.</span></span> <span data-ttu-id="b51c1-124">このガイドでは、BizTalk Server 構成を復元する場合に役立つ情報を紹介します。</span><span class="sxs-lookup"><span data-stu-id="b51c1-124">This guide provides guidance for restoring the BizTalk Server configuration.</span></span>  
  
3.  <span data-ttu-id="b51c1-125">**BizTalk アプリケーションの復元**</span><span class="sxs-lookup"><span data-stu-id="b51c1-125">**Restoring BizTalk Applications**</span></span>  
  
     <span data-ttu-id="b51c1-126">このフェーズでは、代替コンピューターの BizTalk Server プロセスによってホストされるアプリケーションに関連付けられた、.NET アセンブリを復元します。</span><span class="sxs-lookup"><span data-stu-id="b51c1-126">This phase involves restoring the .NET assemblies connected with the applications that are hosted by the BizTalk Server processes on the replacement computer.</span></span> <span data-ttu-id="b51c1-127">ユーザー アセンブリなど、BizTalk アセンブリとは別の必要アイテムを、コンピューターの各場所またはグローバル アセンブリ キャッシュ (GAC) にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b51c1-127">Any artifacts that are needed, such as user assemblies apart from BizTalk assemblies, should be installed in their respective locations or the global assembly cache (GAC) on the computer.</span></span> <span data-ttu-id="b51c1-128">このガイドでは、このフェーズの一部の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b51c1-128">This guide provides some guidance on this phase.</span></span> <span data-ttu-id="b51c1-129">ただし、BizTalk アプリケーションを復元するための個別のスクリプトやツールは提供していません。</span><span class="sxs-lookup"><span data-stu-id="b51c1-129">However, there are no separate scripts or tools for restoring BizTalk applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51c1-130">参照</span><span class="sxs-lookup"><span data-stu-id="b51c1-130">See Also</span></span>  
 [<span data-ttu-id="b51c1-131">BizTalk Server のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="b51c1-131">Backing Up and Restoring BizTalk Server</span></span>](../core/backing-up-and-restoring-biztalk-server.md)