---
title: BtarnClean |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BtarnClean utility
- assemblies, undeploying
- BTARN, deleting artifacts
- orchestrations, unenlisting
- ports, stopping
- orchestrations, stopping
- ports, deleting
- BTARN, BtarnClean utility
ms.assetid: fbecbb88-9b18-4b4b-a286-0bfa783f2320
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa8e448d4799329a798cc7b33f222b42c4a28b4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="btarnclean"></a><span data-ttu-id="6056c-102">BtarnClean</span><span class="sxs-lookup"><span data-stu-id="6056c-102">BtarnClean</span></span>
<span data-ttu-id="6056c-103">BtarnClean ユーティリティは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] のアイテムをコンピューターから削除するために使用します。</span><span class="sxs-lookup"><span data-stu-id="6056c-103">You use the BtarnClean utility to clean [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] artifacts off a computer.</span></span> <span data-ttu-id="6056c-104">以下の処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="6056c-104">This includes the following actions:</span></span>  
  
-   <span data-ttu-id="6056c-105">すべての [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] オーケストレーションを停止し、登録を解除する</span><span class="sxs-lookup"><span data-stu-id="6056c-105">Stopping and unenlisting all the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] orchestrations</span></span>  
  
-   <span data-ttu-id="6056c-106">関連するすべてのポートを停止し、削除する</span><span class="sxs-lookup"><span data-stu-id="6056c-106">Stopping and deleting all the associated ports</span></span>  
  
-   <span data-ttu-id="6056c-107">すべての [!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.BTARN.\* アセンブリの展開を解除する</span><span class="sxs-lookup"><span data-stu-id="6056c-107">Undeploying all the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.BTARN.\* assemblies</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="6056c-108">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="6056c-108">Location in SDK</span></span>  
 <span data-ttu-id="6056c-109">\<*drive*\>\Program Files\ Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK</span><span class="sxs-lookup"><span data-stu-id="6056c-109">\<*drive*\>\Program Files\ Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  
  
## <a name="running-btarnclean"></a><span data-ttu-id="6056c-110">BtarnClean の実行</span><span class="sxs-lookup"><span data-stu-id="6056c-110">Running BtarnClean</span></span>  
  
#### <a name="to-run-btarnclean"></a><span data-ttu-id="6056c-111">BtarnClean を実行するには</span><span class="sxs-lookup"><span data-stu-id="6056c-111">To run BtarnClean</span></span>  
  
1.  <span data-ttu-id="6056c-112">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="6056c-112">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="6056c-113">移動\<*ドライブ*\>\ Program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\です。</span><span class="sxs-lookup"><span data-stu-id="6056c-113">Move to \<*drive*\>\ Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  
  
3.  <span data-ttu-id="6056c-114">コマンド プロンプトで次のように入力します。 **BtarnClean**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6056c-114">At the command prompt, type **BtarnClean**, and then press ENTER.</span></span>  
  
     <span data-ttu-id="6056c-115">コマンドの実行を確認するプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6056c-115">The utility prompts you to verify that you want to continue.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6056c-116">解説</span><span class="sxs-lookup"><span data-stu-id="6056c-116">Remarks</span></span>  
 <span data-ttu-id="6056c-117">他のアイテムに依存する BizTalk アイテムのあるコンピューターで BtarnClean ユーティリティを実行しようとすると、そのアイテムは削除できないというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6056c-117">If you run the BtarnClean utility on a computer that has a BizTalk artifact that depends on other artifacts, BtarnClean will indicate that it cannot remove the artifact.</span></span> <span data-ttu-id="6056c-118">該当するアイテムはそのままで、引き続きその他のアイテムが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6056c-118">The utility will leave that artifact in place and continue to remove other artifacts.</span></span> <span data-ttu-id="6056c-119">依存関係を削除した後で、ユーティリティを再度実行できます。</span><span class="sxs-lookup"><span data-stu-id="6056c-119">You can remove dependencies, and then run the utility again.</span></span>  
  
 <span data-ttu-id="6056c-120">複数コンピュータ展開の一部であるコンピュータで BtarnClean ユーティリティを実行した場合、アイテムを削除すると、同じ展開のその他のサーバーにも影響が及びます。</span><span class="sxs-lookup"><span data-stu-id="6056c-120">If you run the BtarnClean utility on a computer that is part of a multi-computer deployment, removing the artifacts will affect the rest of the servers in that deployment.</span></span>  
  
 <span data-ttu-id="6056c-121">開発者によって作成された複数のプロセスが存在する場合に BtarnClean ユーティリティを実行すると、使用中のプロセスは削除されません。</span><span class="sxs-lookup"><span data-stu-id="6056c-121">If you run the BtarnClean utility when multiple processes created by developers exist, the utility will not remove processes that are still in use.</span></span>  
  
 <span data-ttu-id="6056c-122">ユーザーのアイテムが主要な受信場所を使用する場合、BtarnClean ユーティリティではその受信場所は削除されません。</span><span class="sxs-lookup"><span data-stu-id="6056c-122">The BtarnClean utility will not remove a primary receive location if a user's artifact uses that receive location.</span></span> <span data-ttu-id="6056c-123">その場合は、受信ポートを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6056c-123">If this is the case, you must delete the receive port.</span></span>  
  
 <span data-ttu-id="6056c-124">このユーティリティを実行した後で [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] の構成を解除する場合は、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] フォルダーから Configuration.exe /u を実行します。</span><span class="sxs-lookup"><span data-stu-id="6056c-124">If you want to unconfigure [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] after running the utility, run Configuration.exe /u from the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6056c-125">参照</span><span class="sxs-lookup"><span data-stu-id="6056c-125">See Also</span></span>  
 [<span data-ttu-id="6056c-126">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="6056c-126">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)