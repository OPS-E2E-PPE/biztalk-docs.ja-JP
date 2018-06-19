---
title: Tutorial1 を使用する準備 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4a792b2-8351-4ae8-9d7c-75420c00af03
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efedfeb184b8b0105b8622b6b3f068faffd6a906
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225210"
---
# <a name="preparing-to-use-the-tutorial"></a><span data-ttu-id="57f47-102">このチュートリアルを使用する準備をしています</span><span class="sxs-lookup"><span data-stu-id="57f47-102">Preparing to Use the Tutorial</span></span>
<span data-ttu-id="57f47-103">A4SWIFT のアダプターのエンド ツー エンド チュートリアルを使用する前に、次を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57f47-103">You must do the following before using the A4SWIFT adapter end-to-end tutorial.</span></span>  
  
1.  <span data-ttu-id="57f47-104">このチュートリアルでは、次の迅速な成果物を必要となります。</span><span class="sxs-lookup"><span data-stu-id="57f47-104">You will need the following SWIFT artifacts for this tutorial:</span></span>  
  
    -   <span data-ttu-id="57f47-105">SWIFT Alliance ゲートウェイ (SAG) 6.1</span><span class="sxs-lookup"><span data-stu-id="57f47-105">SWIFT Alliance Gateway (SAG) 6.1</span></span>  
  
    -   <span data-ttu-id="57f47-106">リモート アクセス (RA) 6.1</span><span class="sxs-lookup"><span data-stu-id="57f47-106">Remote Access (RA) 6.1</span></span>  
  
    -   <span data-ttu-id="57f47-107">SWIFT WebStation 6.0</span><span class="sxs-lookup"><span data-stu-id="57f47-107">SWIFT WebStation 6.0</span></span>  
  
    -   <span data-ttu-id="57f47-108">SWIFTNet リンク (SNL) 6.1</span><span class="sxs-lookup"><span data-stu-id="57f47-108">SWIFTNet Link (SNL) 6.1</span></span>  
  
2.  <span data-ttu-id="57f47-109">SAG を構成する必要があります: SAG で MessagePartners、終点、およびルーティング規則を作成し、アダプターをインストールするコンピューターで SAG 接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="57f47-109">You must configure SAG: create the MessagePartners, End Points, and Routing Rules in SAG, and test SAG connectivity on the computer where you install the adapters.</span></span> <span data-ttu-id="57f47-110">については、SAG ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="57f47-110">For information, see the SAG documentation.</span></span>  
  
3.  <span data-ttu-id="57f47-111">「を作成、新しいホストにする方法」Microsoft BizTalk Server ヘルプのトピックに記載の手順に従います ([http://go.microsoft.com/fwlink/?LinkId = 100422](http://go.microsoft.com/fwlink/?LinkId=100422)) という名前の InterAct アダプターの 1 つのインプロセス ホストを作成する*interacthost*、インプロセス ホスト FileAct アダプターは、という名前のいずれかと*fileacthost*です。</span><span class="sxs-lookup"><span data-stu-id="57f47-111">Follow the instructions listed in the topic “How to Create a New Host” in Microsoft BizTalk Server Help ([http://go.microsoft.com/fwlink/?LinkId=100422](http://go.microsoft.com/fwlink/?LinkId=100422)) to create one in-process Host for the InterAct adapter, named *interacthost*, and one in-process Host for the FileAct adapter, named *fileacthost*.</span></span> <span data-ttu-id="57f47-112">アダプターのハンドラーを作成するときに、これらのホストを使用します。</span><span class="sxs-lookup"><span data-stu-id="57f47-112">You will use these hosts while creating handlers for the adapters.</span></span>  
  
4.  <span data-ttu-id="57f47-113">チュートリアルでは、次のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="57f47-113">Create the following folders for the tutorial:</span></span>  
  
    -   <span data-ttu-id="57f47-114">c:\SWIFTAdapterTutorial\Fileact\ClientLocation</span><span class="sxs-lookup"><span data-stu-id="57f47-114">c:\SWIFTAdapterTutorial\Fileact\ClientLocation</span></span>  
  
    -   <span data-ttu-id="57f47-115">c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime</span><span class="sxs-lookup"><span data-stu-id="57f47-115">c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime</span></span>  
  
    -   <span data-ttu-id="57f47-116">c:\SWIFTAdapterTutorial\Fileact\ResponseClient</span><span class="sxs-lookup"><span data-stu-id="57f47-116">c:\SWIFTAdapterTutorial\Fileact\ResponseClient</span></span>  
  
    -   <span data-ttu-id="57f47-117">c:\SWIFTAdapterTutorial\Fileact\ResponseServer</span><span class="sxs-lookup"><span data-stu-id="57f47-117">c:\SWIFTAdapterTutorial\Fileact\ResponseServer</span></span>  
  
    -   <span data-ttu-id="57f47-118">c:\SWIFTAdapterTutorial\Fileact\ServerLocation</span><span class="sxs-lookup"><span data-stu-id="57f47-118">c:\SWIFTAdapterTutorial\Fileact\ServerLocation</span></span>  
  
    -   <span data-ttu-id="57f47-119">c:\SWIFTAdapterTutorial\Fileact\StatusEvents</span><span class="sxs-lookup"><span data-stu-id="57f47-119">c:\SWIFTAdapterTutorial\Fileact\StatusEvents</span></span>  
  
    -   <span data-ttu-id="57f47-120">c:\SWIFTAdapterTutorial\Fileact\PullRequest</span><span class="sxs-lookup"><span data-stu-id="57f47-120">c:\SWIFTAdapterTutorial\Fileact\PullRequest</span></span>  
  
    -   <span data-ttu-id="57f47-121">c:\SWIFTAdapterTutorial\Fileact\PullResponse</span><span class="sxs-lookup"><span data-stu-id="57f47-121">c:\SWIFTAdapterTutorial\Fileact\PullResponse</span></span>  
  
    -   <span data-ttu-id="57f47-122">c:\SWIFTAdapterTutorial\Interact\HandleRequest</span><span class="sxs-lookup"><span data-stu-id="57f47-122">c:\SWIFTAdapterTutorial\Interact\HandleRequest</span></span>  
  
    -   <span data-ttu-id="57f47-123">c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime</span><span class="sxs-lookup"><span data-stu-id="57f47-123">c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime</span></span>  
  
    -   <span data-ttu-id="57f47-124">c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span><span class="sxs-lookup"><span data-stu-id="57f47-124">c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span></span>  
  
    -   <span data-ttu-id="57f47-125">c:\SWIFTAdapterTutorial\Interact\Response</span><span class="sxs-lookup"><span data-stu-id="57f47-125">c:\SWIFTAdapterTutorial\Interact\Response</span></span>  
  
    -   <span data-ttu-id="57f47-126">c:\SWIFTAdapterTutorial\Interact\PullRequest</span><span class="sxs-lookup"><span data-stu-id="57f47-126">c:\SWIFTAdapterTutorial\Interact\PullRequest</span></span>  
  
    -   <span data-ttu-id="57f47-127">c:\SWIFTAdapterTutorial\Interact\Pullresponse</span><span class="sxs-lookup"><span data-stu-id="57f47-127">c:\SWIFTAdapterTutorial\Interact\Pullresponse</span></span>  
  
5.  <span data-ttu-id="57f47-128">SWIFT ITB への接続またはアダプターをテストする実際の環境が必要です。</span><span class="sxs-lookup"><span data-stu-id="57f47-128">You must have a connection to SWIFT ITB or live environment to test the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f47-129">参照</span><span class="sxs-lookup"><span data-stu-id="57f47-129">See Also</span></span>  
 <span data-ttu-id="57f47-130">[BizTalk FileAct と対話するアダプターのエンド ツー エンドのチュートリアル](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="57f47-130">[BizTalk FileAct and InterAct Adapters End-to-End Tutorial](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md) </span></span>  
 <span data-ttu-id="57f47-131">[リアルタイムのシナリオを対話します。](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="57f47-131">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="57f47-132">[ストアと順方向 (プッシュ) シナリオを対話します。](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="57f47-132">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="57f47-133">[FileAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="57f47-133">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="57f47-134">FileAct ストア アンド フォワードのシナリオ</span><span class="sxs-lookup"><span data-stu-id="57f47-134">FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)