---
title: '手順 2: InterAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a18a43c-1dd9-4113-bf32-8bc7bf9338b0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9495d6a53e9048dc5dee839f1dc859c62b4e9187
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014499"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="4108d-102">手順 2: は、InterAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="4108d-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="4108d-103">これらの値で初期化するために受信者を有効にする SWIFTNet に paramfile に SAG で作成したサーバー メッセージのパートナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4108d-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
 <span data-ttu-id="4108d-104">この手順を開始する前に行う必要があります[手順 1: InterAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成する](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="4108d-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="4108d-105">Paramfile に SWIFTNet 構成を追加するには</span><span class="sxs-lookup"><span data-stu-id="4108d-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1. <span data-ttu-id="4108d-106">Paramfile をメモ帳などのテキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="4108d-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4108d-107">位置に paramfile にある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile します。</span><span class="sxs-lookup"><span data-stu-id="4108d-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile.</span></span>  
  
2. <span data-ttu-id="4108d-108">Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示されている変更を行います。</span><span class="sxs-lookup"><span data-stu-id="4108d-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
    <span data-ttu-id="4108d-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="4108d-109">username:snlowner</span></span>  
  
    <span data-ttu-id="4108d-110">subsystem_name:InteractStub</span><span class="sxs-lookup"><span data-stu-id="4108d-110">subsystem_name:InteractStub</span></span>  
  
    <span data-ttu-id="4108d-111">\#subsystem_group:Interactsnf</span><span class="sxs-lookup"><span data-stu-id="4108d-111">\#subsystem_group:Interactsnf</span></span>  
  
    <span data-ttu-id="4108d-112">\#subsystem_dependency:Support、Swarm</span><span class="sxs-lookup"><span data-stu-id="4108d-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
    <span data-ttu-id="4108d-113">subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="4108d-113">subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="4108d-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="4108d-114">subsystem_start:</span></span>  
  
    <span data-ttu-id="4108d-115">**spawn"snlreceiver - SagMessagePartner \<Interact SnF 用サーバー MessagePartnerName\> AdapterMode 対話"**</span><span class="sxs-lookup"><span data-stu-id="4108d-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for Interact SnF\> -AdapterMode Interact"**</span></span>  
  
    <span data-ttu-id="4108d-116">\* 終了</span><span class="sxs-lookup"><span data-stu-id="4108d-116">\*END</span></span>  
  
    <span data-ttu-id="4108d-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="4108d-117">subsystem_stop:</span></span>  
  
    <span data-ttu-id="4108d-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="4108d-118">\*KILL9:snlreceiver</span></span>  
  
    <span data-ttu-id="4108d-119">\* 終了</span><span class="sxs-lookup"><span data-stu-id="4108d-119">\*END</span></span>  
  
    <span data-ttu-id="4108d-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="4108d-120">subsystem_status:</span></span>  
  
    <span data-ttu-id="4108d-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="4108d-121">\*NB:1:snlreceiver</span></span>  
  
    <span data-ttu-id="4108d-122">\* 終了</span><span class="sxs-lookup"><span data-stu-id="4108d-122">\*END</span></span>  
  
    <span data-ttu-id="4108d-123">start_event:SNL001:subsystem InteractStubSnF です。</span><span class="sxs-lookup"><span data-stu-id="4108d-123">start_event:SNL001:subsystem InteractStubSnF is up</span></span>  
  
    <span data-ttu-id="4108d-124">stop_event:SNL002:subsystem InteractStubSnF がダウン</span><span class="sxs-lookup"><span data-stu-id="4108d-124">stop_event:SNL002:subsystem InteractStubSnF is down</span></span>  
  
    <span data-ttu-id="4108d-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="4108d-125">\#subsystem_name:User</span></span>  
  
    <span data-ttu-id="4108d-126">\## subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="4108d-126">\##subsystem_group:user</span></span>  
  
    <span data-ttu-id="4108d-127">\## subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="4108d-127">\##subsystem_dependency:</span></span>  
  
    <span data-ttu-id="4108d-128">\#subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="4108d-128">\#subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="4108d-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="4108d-129">\#subsystem_start:</span></span>  
  
    <span data-ttu-id="4108d-130">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="4108d-130">\#\*END</span></span>  
  
    <span data-ttu-id="4108d-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="4108d-131">\#subsystem_stop:</span></span>  
  
    <span data-ttu-id="4108d-132">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="4108d-132">\#\*END</span></span>  
  
    <span data-ttu-id="4108d-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="4108d-133">\#subsystem_status:</span></span>  
  
    <span data-ttu-id="4108d-134">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="4108d-134">\#\*END</span></span>  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="4108d-135">ユーザーが稼働 start_event:SNL001:subsystem です。</span><span class="sxs-lookup"><span data-stu-id="4108d-135">start_event:SNL001:subsystem User is up</span></span>  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="4108d-136">ユーザーがダウンして stop_event:SNL002:subsystem</span><span class="sxs-lookup"><span data-stu-id="4108d-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4108d-137">参照</span><span class="sxs-lookup"><span data-stu-id="4108d-137">See Also</span></span>  
 <span data-ttu-id="4108d-138">[InterAct ストア アンド フォワード (プッシュ) シナリオ](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4108d-138">[InterAct Store and Forward (Push) Scenario](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md) </span></span>  
 <span data-ttu-id="4108d-139">[手順 1: InterAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成します。](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4108d-139">[Step 1: Configure the SWIFT Adapter for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="4108d-140">[手順 3: 送信ポートの作成し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4108d-140">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="4108d-141">手順 4: InterAct ストア アンド フォワード エンド ツー エンド シナリオをテストする</span><span class="sxs-lookup"><span data-stu-id="4108d-141">Step 4: Test the InterAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)