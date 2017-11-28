---
title: "ループバック チュートリアル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- loopbacks, tutorial
- loopback tutorial, about the loopback tutorial
- loopback tutorial
- tutorials, loopback tutorial
ms.assetid: 0f69c1f1-4039-4949-8eed-127ceabbc3cc
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3b013eb65320dc36dd1319d7332e45ed54b2444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="loopback-tutorial"></a><span data-ttu-id="bc6fc-102">ループバック チュートリアル</span><span class="sxs-lookup"><span data-stu-id="bc6fc-102">Loopback Tutorial</span></span>
<span data-ttu-id="bc6fc-103">このチュートリアルでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] を使用して、ホーム組織と取引先組織間のプロセス実装を 1 台のコンピューター上でシミュレートするための手順を詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-103">This tutorial contains detailed steps that describe how you can use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to simulate a process implementation between the home and partner organization on a single computer.</span></span>  
  
 <span data-ttu-id="bc6fc-104">実際の運用環境では、取引先組織はリモート コンピューターに実装されます。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-104">In a real production environment, your partner organization implementation resides on a remote computer.</span></span> <span data-ttu-id="bc6fc-105">このチュートリアルでは、ループバック ユーティリティを使用して、同じコンピューター上で取引先をシミュレートするためのミラー取引アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-105">This tutorial uses the Loopback utility to create a mirror trading agreement to simulate the trading partner on the same computer.</span></span> <span data-ttu-id="bc6fc-106">1 台のコンピューターでループバックを行うシナリオの使用は、開発とテストを目的としたものです。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-106">Using a single computer loop-back scenario works for development and test purposes.</span></span> <span data-ttu-id="bc6fc-107">運用環境ではループバック ユーティリティを使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-107">It is recommended that you do not to use the Loopback utility in a production environment.</span></span>  
  
 <span data-ttu-id="bc6fc-108">このループバック シナリオでは署名メッセージはサポートされないため、否認不可もサポートされません。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-108">This loopback scenario does not support signing messages, and thus does not support non-repudiation.</span></span>  
  
 <span data-ttu-id="bc6fc-109">証明機関が構成されており、テスト目的に使用できる暗号化用の秘密キーがある場合は、このシナリオではメッセージの暗号化がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-109">This scenario supports encryption of messages if you have a certification authority configured, and you have a private key for encryption available for test purposes.</span></span>  
  
 <span data-ttu-id="bc6fc-110">このチュートリアルでは、ホーム組織、取引先組織、取引アグリーメントを作成し、ループバック ユーティリティを使用してミラー アグリーメントを作成し、次にサンプル プロセスを実行してループバック シナリオを検証します。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-110">In this tutorial, you create a home organization, a partner organization, a trade agreement, use the Loopback utility to create a mirror agreement, and then run a sample process to verify the loop-back scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc6fc-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bc6fc-111">In This Section</span></span>  
  
-   [<span data-ttu-id="bc6fc-112">チュートリアルの準備</span><span class="sxs-lookup"><span data-stu-id="bc6fc-112">Preparing for the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-tutorial.md)  
  
-   [<span data-ttu-id="bc6fc-113">手順 1: ホーム組織を作成します。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-113">Step 1: Create the Home Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-the-home-organization.md)  
  
-   [<span data-ttu-id="bc6fc-114">手順 2: パートナー組織を作成します。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-114">Step 2: Create the Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-the-partner-organization.md)  
  
-   [<span data-ttu-id="bc6fc-115">手順 3: Partner Interface Process を編集します。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-115">Step 3: Edit the Partner Interface Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)  
  
-   [<span data-ttu-id="bc6fc-116">手順 4: 取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-116">Step 4: Create a Trade Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)  
  
-   [<span data-ttu-id="bc6fc-117">手順 5: ミラー アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-117">Step 5: Create a Mirror Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)  
  
-   [<span data-ttu-id="bc6fc-118">手順 6: オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-118">Step 6: Start Orchestrations</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)  
  
-   [<span data-ttu-id="bc6fc-119">手順 7: サンプル LOB メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc6fc-119">Step 7: Create a Sample LOB Message</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-create-a-sample-lob-message.md)  
  
-   [<span data-ttu-id="bc6fc-120">手順 8: BTARN データベース内のメッセージの表示</span><span class="sxs-lookup"><span data-stu-id="bc6fc-120">Step 8: View Messages in the BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)