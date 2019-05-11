---
title: Tutorial1 を使用する準備 |Microsoft Docs
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
ms.openlocfilehash: 8bc4614d82471f6573134c6da47966bf8ca57330
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366574"
---
# <a name="preparing-to-use-the-tutorial"></a><span data-ttu-id="ecd04-102">チュートリアルを使用する準備をしています</span><span class="sxs-lookup"><span data-stu-id="ecd04-102">Preparing to Use the Tutorial</span></span>
<span data-ttu-id="ecd04-103">A4SWIFT アダプターのエンド ツー エンド チュートリアルを使用する前に、次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecd04-103">You must do the following before using the A4SWIFT adapter end-to-end tutorial.</span></span>  
  
1.  <span data-ttu-id="ecd04-104">このチュートリアルでは、次の SWIFT 成果物を必要となります。</span><span class="sxs-lookup"><span data-stu-id="ecd04-104">You will need the following SWIFT artifacts for this tutorial:</span></span>  
  
    -   <span data-ttu-id="ecd04-105">SWIFT Alliance ゲートウェイ (SAG) 6.1</span><span class="sxs-lookup"><span data-stu-id="ecd04-105">SWIFT Alliance Gateway (SAG) 6.1</span></span>  
  
    -   <span data-ttu-id="ecd04-106">リモート アクセス (RA) 6.1</span><span class="sxs-lookup"><span data-stu-id="ecd04-106">Remote Access (RA) 6.1</span></span>  
  
    -   <span data-ttu-id="ecd04-107">SWIFT WebStation 6.0</span><span class="sxs-lookup"><span data-stu-id="ecd04-107">SWIFT WebStation 6.0</span></span>  
  
    -   <span data-ttu-id="ecd04-108">SWIFTNet リンク (SNL) 6.1</span><span class="sxs-lookup"><span data-stu-id="ecd04-108">SWIFTNet Link (SNL) 6.1</span></span>  
  
2.  <span data-ttu-id="ecd04-109">SAG を構成する必要があります: SAG で MessagePartners、終点、およびルーティング規則を作成し、アダプターをインストールするコンピューターで SAG 接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="ecd04-109">You must configure SAG: create the MessagePartners, End Points, and Routing Rules in SAG, and test SAG connectivity on the computer where you install the adapters.</span></span> <span data-ttu-id="ecd04-110">については、SAG ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecd04-110">For information, see the SAG documentation.</span></span>  
  
3.  <span data-ttu-id="ecd04-111">「を作成、新しいホストにする方法」Microsoft BizTalk Server ヘルプのトピックに記載の指示に従います ([http://go.microsoft.com/fwlink/?LinkId=100422](http://go.microsoft.com/fwlink/?LinkId=100422)) という、InterAct アダプターの 1 つのインプロセス ホストを作成する*interacthost*、インプロセス ホストという名前の FileAct アダプターの 1 つ*fileacthost*します。</span><span class="sxs-lookup"><span data-stu-id="ecd04-111">Follow the instructions listed in the topic “How to Create a New Host” in Microsoft BizTalk Server Help ([http://go.microsoft.com/fwlink/?LinkId=100422](http://go.microsoft.com/fwlink/?LinkId=100422)) to create one in-process Host for the InterAct adapter, named *interacthost*, and one in-process Host for the FileAct adapter, named *fileacthost*.</span></span> <span data-ttu-id="ecd04-112">アダプターのハンドラーを作成するときに、これらのホストを使用します。</span><span class="sxs-lookup"><span data-stu-id="ecd04-112">You will use these hosts while creating handlers for the adapters.</span></span>  
  
4.  <span data-ttu-id="ecd04-113">チュートリアルでは、次のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ecd04-113">Create the following folders for the tutorial:</span></span>  
  
    -   <span data-ttu-id="ecd04-114">c:\SWIFTAdapterTutorial\Fileact\ClientLocation</span><span class="sxs-lookup"><span data-stu-id="ecd04-114">c:\SWIFTAdapterTutorial\Fileact\ClientLocation</span></span>  
  
    -   <span data-ttu-id="ecd04-115">c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime</span><span class="sxs-lookup"><span data-stu-id="ecd04-115">c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime</span></span>  
  
    -   <span data-ttu-id="ecd04-116">c:\SWIFTAdapterTutorial\Fileact\ResponseClient</span><span class="sxs-lookup"><span data-stu-id="ecd04-116">c:\SWIFTAdapterTutorial\Fileact\ResponseClient</span></span>  
  
    -   <span data-ttu-id="ecd04-117">c:\SWIFTAdapterTutorial\Fileact\ResponseServer</span><span class="sxs-lookup"><span data-stu-id="ecd04-117">c:\SWIFTAdapterTutorial\Fileact\ResponseServer</span></span>  
  
    -   <span data-ttu-id="ecd04-118">c:\SWIFTAdapterTutorial\Fileact\ServerLocation</span><span class="sxs-lookup"><span data-stu-id="ecd04-118">c:\SWIFTAdapterTutorial\Fileact\ServerLocation</span></span>  
  
    -   <span data-ttu-id="ecd04-119">c:\SWIFTAdapterTutorial\Fileact\StatusEvents</span><span class="sxs-lookup"><span data-stu-id="ecd04-119">c:\SWIFTAdapterTutorial\Fileact\StatusEvents</span></span>  
  
    -   <span data-ttu-id="ecd04-120">c:\SWIFTAdapterTutorial\Fileact\PullRequest</span><span class="sxs-lookup"><span data-stu-id="ecd04-120">c:\SWIFTAdapterTutorial\Fileact\PullRequest</span></span>  
  
    -   <span data-ttu-id="ecd04-121">c:\SWIFTAdapterTutorial\Fileact\PullResponse</span><span class="sxs-lookup"><span data-stu-id="ecd04-121">c:\SWIFTAdapterTutorial\Fileact\PullResponse</span></span>  
  
    -   <span data-ttu-id="ecd04-122">c:\SWIFTAdapterTutorial\Interact\HandleRequest</span><span class="sxs-lookup"><span data-stu-id="ecd04-122">c:\SWIFTAdapterTutorial\Interact\HandleRequest</span></span>  
  
    -   <span data-ttu-id="ecd04-123">c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime</span><span class="sxs-lookup"><span data-stu-id="ecd04-123">c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime</span></span>  
  
    -   <span data-ttu-id="ecd04-124">c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span><span class="sxs-lookup"><span data-stu-id="ecd04-124">c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span></span>  
  
    -   <span data-ttu-id="ecd04-125">c:\SWIFTAdapterTutorial\Interact\Response</span><span class="sxs-lookup"><span data-stu-id="ecd04-125">c:\SWIFTAdapterTutorial\Interact\Response</span></span>  
  
    -   <span data-ttu-id="ecd04-126">c:\SWIFTAdapterTutorial\Interact\PullRequest</span><span class="sxs-lookup"><span data-stu-id="ecd04-126">c:\SWIFTAdapterTutorial\Interact\PullRequest</span></span>  
  
    -   <span data-ttu-id="ecd04-127">c:\SWIFTAdapterTutorial\Interact\Pullresponse</span><span class="sxs-lookup"><span data-stu-id="ecd04-127">c:\SWIFTAdapterTutorial\Interact\Pullresponse</span></span>  
  
5.  <span data-ttu-id="ecd04-128">SWIFT ITB への接続またはアダプターをテストする実際の環境が必要です。</span><span class="sxs-lookup"><span data-stu-id="ecd04-128">You must have a connection to SWIFT ITB or live environment to test the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecd04-129">参照</span><span class="sxs-lookup"><span data-stu-id="ecd04-129">See Also</span></span>  
 <span data-ttu-id="ecd04-130">[BizTalk FileAct および InterAct アダプターのエンド ツー エンド チュートリアル](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ecd04-130">[BizTalk FileAct and InterAct Adapters End-to-End Tutorial](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md) </span></span>  
 <span data-ttu-id="ecd04-131">[InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ecd04-131">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="ecd04-132">[InterAct ストア アンド フォワード (プッシュ) シナリオ](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ecd04-132">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="ecd04-133">[FileAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ecd04-133">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="ecd04-134">FileAct ストア アンド フォワード シナリオ</span><span class="sxs-lookup"><span data-stu-id="ecd04-134">FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)