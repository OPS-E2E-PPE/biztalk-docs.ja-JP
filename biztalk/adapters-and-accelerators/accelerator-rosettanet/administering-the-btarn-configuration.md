---
title: "BTARN 構成の管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for RosettaNet, administering
- administering
ms.assetid: 8db2851e-6aaf-49d9-a3f0-dee187595c01
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48df2985716fe4ab1d94ba695dba5f4e108dc42b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="administering-the-btarn-configuration"></a><span data-ttu-id="bc50d-102">BTARN 構成の管理</span><span class="sxs-lookup"><span data-stu-id="bc50d-102">Administering the BTARN Configuration</span></span>
<span data-ttu-id="bc50d-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールでは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成のあらゆる要素を 1 つのユーザー インターフェイスで管理できます。</span><span class="sxs-lookup"><span data-stu-id="bc50d-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console lets you administer all facets of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration from one user interface.</span></span> <span data-ttu-id="bc50d-104">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成には、プロセス構成、ホーム組織、パートナー、および取引先アグリーメントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc50d-104">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration includes process configurations, home organizations, partners, and trading partner agreements.</span></span> <span data-ttu-id="bc50d-105">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールで、管理することも、証明書のインスタンスの管理[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]™ イベントを表示し、パフォーマンスの表示、ログと警告します。</span><span class="sxs-lookup"><span data-stu-id="bc50d-105">From the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, you can also manage certificates, administer instances of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]™, view events, and view performance logs and alerts.</span></span>  
  
 <span data-ttu-id="bc50d-106">実行できるすべての操作の概要については、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールを参照してください[BTARN 管理コンソールを使用して](../../adapters-and-accelerators/accelerator-rosettanet/using-the-btarn-management-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc50d-106">For an overview of all operations that you can perform from the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, see [Using the BTARN Management Console](../../adapters-and-accelerators/accelerator-rosettanet/using-the-btarn-management-console.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc50d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bc50d-107">In This Section</span></span>  
  
-   [<span data-ttu-id="bc50d-108">BTARN 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="bc50d-108">Using the BTARN Management Console</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/using-the-btarn-management-console.md)  
  
-   [<span data-ttu-id="bc50d-109">BTARN 送信を設定し、受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="bc50d-109">Setting BTARN Send and Receive Pipelines</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-btarn-send-and-receive-pipelines.md)  
  
-   [<span data-ttu-id="bc50d-110">BAM 追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="bc50d-110">Enabling BAM Tracking</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)  
  
-   [<span data-ttu-id="bc50d-111">作成またはプロセス構成を編集します。</span><span class="sxs-lookup"><span data-stu-id="bc50d-111">Creating or Editing a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-process-configuration.md)  
  
-   [<span data-ttu-id="bc50d-112">作成またはホーム組織を編集します。</span><span class="sxs-lookup"><span data-stu-id="bc50d-112">Creating or Editing a Home Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)  
  
-   [<span data-ttu-id="bc50d-113">作成またはパートナーを編集します。</span><span class="sxs-lookup"><span data-stu-id="bc50d-113">Creating or Editing a Partner</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)  
  
-   [<span data-ttu-id="bc50d-114">作成するか、契約の編集</span><span class="sxs-lookup"><span data-stu-id="bc50d-114">Creating or Editing an Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)