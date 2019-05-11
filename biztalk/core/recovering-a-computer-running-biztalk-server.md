---
title: BizTalk Server を実行しているコンピューターの回復 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a55af6d6-f11a-46e4-9b8e-0a1ca35998c4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f417197e833e314a632351ee309d96ac87556e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398025"
---
# <a name="recovering-a-computer-running-biztalk-server"></a><span data-ttu-id="db8ae-102">BizTalk Server を実行しているコンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="db8ae-102">Recovering a Computer Running BizTalk Server</span></span>
<span data-ttu-id="db8ae-103">BizTalk Server を実行しているコンピュータを復旧するには、BizTalk Server データベースにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="db8ae-103">In order to recover a computer running BizTalk Server, you must be able to access the BizTalk Server databases.</span></span> <span data-ttu-id="db8ae-104">必要であれば、BizTalk Server データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="db8ae-104">If necessary, restore the BizTalk Server databases.</span></span> <span data-ttu-id="db8ae-105">また、BizTalk Server を実行しているコンピュータを復旧するには、BizTalk Server と必要なすべてのコンポーネントを再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db8ae-105">In addition, before you can recover the computer running BizTalk Server, you must reinstall BizTalk Server and all of the prerequisites.</span></span>  
  
 <span data-ttu-id="db8ae-106">以上の手順が完了した後で、ここで説明する手順に従い BizTalk Server を復旧できます。</span><span class="sxs-lookup"><span data-stu-id="db8ae-106">When these steps are complete, you can use the procedures in this section to recover your BizTalk server.</span></span> <span data-ttu-id="db8ae-107">BizTalk Server を復旧する手順は、使用しているエディションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="db8ae-107">The procedures you must follow to recover BizTalk Server depend on the edition you are using.</span></span> <span data-ttu-id="db8ae-108">次の表に、エディションごとの必要な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="db8ae-108">The following table lists the required procedures for each edition.</span></span>  
  
|<span data-ttu-id="db8ae-109">タスク</span><span class="sxs-lookup"><span data-stu-id="db8ae-109">Task</span></span>|<span data-ttu-id="db8ae-110">Standard</span><span class="sxs-lookup"><span data-stu-id="db8ae-110">Standard</span></span>|<span data-ttu-id="db8ae-111">Developer</span><span class="sxs-lookup"><span data-stu-id="db8ae-111">Developer</span></span>|<span data-ttu-id="db8ae-112">Enterprise</span><span class="sxs-lookup"><span data-stu-id="db8ae-112">Enterprise</span></span>|  
|----------|--------------|---------------|----------------|  
|<span data-ttu-id="db8ae-113">**証明書ストアを復元する方法**</span><span class="sxs-lookup"><span data-stu-id="db8ae-113">**How to Restore the Certificate Store**</span></span>|<span data-ttu-id="db8ae-114">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-114">**X**</span></span>|||  
|<span data-ttu-id="db8ae-115">**エンタープライズ シングル サインオン (SSO) を回復する方法**</span><span class="sxs-lookup"><span data-stu-id="db8ae-115">**How to Recover Enterprise Single Sign-On (SSO)**</span></span>|<span data-ttu-id="db8ae-116">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-116">**X**</span></span>|<span data-ttu-id="db8ae-117">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-117">**X**</span></span>|<span data-ttu-id="db8ae-118">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-118">**X**</span></span>|  
|<span data-ttu-id="db8ae-119">**BizTalk グループを回復する方法**</span><span class="sxs-lookup"><span data-stu-id="db8ae-119">**How to Recover the BizTalk Group**</span></span>|<span data-ttu-id="db8ae-120">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-120">**X**</span></span>|<span data-ttu-id="db8ae-121">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-121">**X**</span></span>|<span data-ttu-id="db8ae-122">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-122">**X**</span></span>|  
|<span data-ttu-id="db8ae-123">**BizTalk Server の構成を回復する方法**</span><span class="sxs-lookup"><span data-stu-id="db8ae-123">**How to Recover the BizTalk Server Configuration**</span></span>|<span data-ttu-id="db8ae-124">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-124">**X**</span></span>|<span data-ttu-id="db8ae-125">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-125">**X**</span></span>|<span data-ttu-id="db8ae-126">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-126">**X**</span></span>|  
|<span data-ttu-id="db8ae-127">**BAM 警告を復旧する方法**</span><span class="sxs-lookup"><span data-stu-id="db8ae-127">**How to Recover BAM Alerts**</span></span><br /><br /> <span data-ttu-id="db8ae-128">BAM を使用している場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="db8ae-128">Not required unless you're using BAM.</span></span>|<span data-ttu-id="db8ae-129">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-129">**X**</span></span>|<span data-ttu-id="db8ae-130">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-130">**X**</span></span>|<span data-ttu-id="db8ae-131">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-131">**X**</span></span>|  
|<span data-ttu-id="db8ae-132">**BAM ポータルを復旧する方法**</span><span class="sxs-lookup"><span data-stu-id="db8ae-132">**How to Recover the BAM Portal**</span></span><br /><br /> <span data-ttu-id="db8ae-133">BAM を使用している場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="db8ae-133">Not required unless you're using BAM.</span></span>|<span data-ttu-id="db8ae-134">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-134">**X**</span></span>|<span data-ttu-id="db8ae-135">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-135">**X**</span></span>|<span data-ttu-id="db8ae-136">**X**</span><span class="sxs-lookup"><span data-stu-id="db8ae-136">**X**</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="db8ae-137">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="db8ae-137">In This Section</span></span>  
  
-   [<span data-ttu-id="db8ae-138">証明書ストアを復元する方法</span><span class="sxs-lookup"><span data-stu-id="db8ae-138">How to Restore the Certificate Store</span></span>](../core/how-to-restore-the-certificate-store.md)  
  
-   [<span data-ttu-id="db8ae-139">エンタープライズ シングル サインオンを復旧する方法</span><span class="sxs-lookup"><span data-stu-id="db8ae-139">How to Recover Enterprise Single Sign-On</span></span>](../core/how-to-recover-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="db8ae-140">BizTalk グループを回復する方法</span><span class="sxs-lookup"><span data-stu-id="db8ae-140">How to Recover the BizTalk Group</span></span>](../core/how-to-recover-the-biztalk-group.md)  
  
-   [<span data-ttu-id="db8ae-141">BizTalk Server の構成を回復する方法</span><span class="sxs-lookup"><span data-stu-id="db8ae-141">How to Recover the BizTalk Server Configuration</span></span>](../core/how-to-recover-the-biztalk-server-configuration.md)  
  
-   [<span data-ttu-id="db8ae-142">BAM 警告を復旧する方法</span><span class="sxs-lookup"><span data-stu-id="db8ae-142">How to Recover BAM Alerts</span></span>](../core/how-to-recover-bam-alerts.md)  
  
-   [<span data-ttu-id="db8ae-143">BAM ポータルを復旧する方法</span><span class="sxs-lookup"><span data-stu-id="db8ae-143">How to Recover the BAM Portal</span></span>](../core/how-to-recover-the-bam-portal.md)