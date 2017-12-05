---
title: "手順 2: SWIFTNet の構成を追加、Paramfile InterAct ストアと転送シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a18a43c-1dd9-4113-bf32-8bc7bf9338b0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05524abd4cd57b8d804ab5995072905392fd3645
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="93fe2-102">手順 2: SWIFTNet の構成を追加、Paramfile InterAct ストアと転送シナリオ</span><span class="sxs-lookup"><span data-stu-id="93fe2-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="93fe2-103">SAG で作成されたサーバー メッセージのパートナーは、これらの値で初期化するために受信者を有効にする SWIFTNet paramfile で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93fe2-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
 <span data-ttu-id="93fe2-104">この手順を開始する前に行う必要があります[手順 1: SWIFT アダプター InterAct ストア アンド フォワード シナリオ用に構成](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="93fe2-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="93fe2-105">Paramfile SWIFTNet 構成を追加するには</span><span class="sxs-lookup"><span data-stu-id="93fe2-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="93fe2-106">メモ帳などのテキスト エディターで、paramfile を開きます。</span><span class="sxs-lookup"><span data-stu-id="93fe2-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="93fe2-107">Paramfile がある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile です。</span><span class="sxs-lookup"><span data-stu-id="93fe2-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile.</span></span>  
  
2.  <span data-ttu-id="93fe2-108">Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示された変更を行います。</span><span class="sxs-lookup"><span data-stu-id="93fe2-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
     <span data-ttu-id="93fe2-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="93fe2-109">username:snlowner</span></span>  
  
     <span data-ttu-id="93fe2-110">subsystem_name:InteractStub</span><span class="sxs-lookup"><span data-stu-id="93fe2-110">subsystem_name:InteractStub</span></span>  
  
     <span data-ttu-id="93fe2-111">\#subsystem_group:Interactsnf</span><span class="sxs-lookup"><span data-stu-id="93fe2-111">\#subsystem_group:Interactsnf</span></span>  
  
     <span data-ttu-id="93fe2-112">\#subsystem_dependency:Support、群</span><span class="sxs-lookup"><span data-stu-id="93fe2-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="93fe2-113">subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="93fe2-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="93fe2-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="93fe2-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="93fe2-115">**起動"snlreceiver - SagMessagePartner \<Interact SnF 用サーバー MessagePartnerName\> AdapterMode Interact"**</span><span class="sxs-lookup"><span data-stu-id="93fe2-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for Interact SnF\> -AdapterMode Interact"**</span></span>  
  
     <span data-ttu-id="93fe2-116">* 終了</span><span class="sxs-lookup"><span data-stu-id="93fe2-116">*END</span></span>  
  
     <span data-ttu-id="93fe2-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="93fe2-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="93fe2-118">* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="93fe2-118">*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="93fe2-119">* 終了</span><span class="sxs-lookup"><span data-stu-id="93fe2-119">*END</span></span>  
  
     <span data-ttu-id="93fe2-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="93fe2-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="93fe2-121">* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="93fe2-121">*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="93fe2-122">* 終了</span><span class="sxs-lookup"><span data-stu-id="93fe2-122">*END</span></span>  
  
     <span data-ttu-id="93fe2-123">start_event:SNL001:subsystem InteractStubSnF が稼働</span><span class="sxs-lookup"><span data-stu-id="93fe2-123">start_event:SNL001:subsystem InteractStubSnF is up</span></span>  
  
     <span data-ttu-id="93fe2-124">stop_event:SNL002:subsystem InteractStubSnF がダウンしています。</span><span class="sxs-lookup"><span data-stu-id="93fe2-124">stop_event:SNL002:subsystem InteractStubSnF is down</span></span>  
  
     <span data-ttu-id="93fe2-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="93fe2-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="93fe2-126">\## subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="93fe2-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="93fe2-127">\## subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="93fe2-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="93fe2-128">\#subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="93fe2-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="93fe2-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="93fe2-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="93fe2-130">\#* 終了</span><span class="sxs-lookup"><span data-stu-id="93fe2-130">\#*END</span></span>  
  
     <span data-ttu-id="93fe2-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="93fe2-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="93fe2-132">\#* 終了</span><span class="sxs-lookup"><span data-stu-id="93fe2-132">\#*END</span></span>  
  
     <span data-ttu-id="93fe2-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="93fe2-133">\#subsystem_status:</span></span>  
  
     <span data-ttu-id="93fe2-134">\#* 終了</span><span class="sxs-lookup"><span data-stu-id="93fe2-134">\#*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="93fe2-135">ユーザーが稼働 start_event:SNL001:subsystem です。</span><span class="sxs-lookup"><span data-stu-id="93fe2-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="93fe2-136">ユーザーがダウンして stop_event:SNL002:subsystem</span><span class="sxs-lookup"><span data-stu-id="93fe2-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93fe2-137">参照</span><span class="sxs-lookup"><span data-stu-id="93fe2-137">See Also</span></span>  
 <span data-ttu-id="93fe2-138">[ストアと順方向 (プッシュ) シナリオを対話します。](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="93fe2-138">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="93fe2-139">[手順 1: InterAct ストアと転送シナリオ SWIFT のアダプターを構成します。](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="93fe2-139">[Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="93fe2-140">[手順 3: 送信ポートを作成し、対話ストアと転送シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="93fe2-140">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="93fe2-141">手順 4: InterAct ストア アンド フォワード エンド ツー エンド シナリオをテストする</span><span class="sxs-lookup"><span data-stu-id="93fe2-141">Step 4: Test the InterAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)