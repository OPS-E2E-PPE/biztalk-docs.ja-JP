---
title: '手順 2: 用に Paramfile に SWIFTNet 構成を追加する、InterAct リアルタイム シナリオ |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a900a6e-3e08-430a-8766-4a7192adba5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d36758716fb368760e9a93909f70bf4d92c5f840
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992453"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-real-time-scenario"></a><span data-ttu-id="d86b5-102">手順 2: 用に Paramfile に SWIFTNet 構成を追加する、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="d86b5-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="d86b5-103">これらの値で初期化するために受信者を有効にする SWIFTNet に paramfile に SAG で作成したサーバー メッセージのパートナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d86b5-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span> <span data-ttu-id="d86b5-104">手順を完了する必要があります、プロシージャを開始する前に[手順 1: 対話のリアルタイム シナリオ用 SWIFT アダプターを構成](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="d86b5-104">Before you begin the procedure, you must complete the instructions in [Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="d86b5-105">Paramfile に SWIFTNet 構成を追加するには</span><span class="sxs-lookup"><span data-stu-id="d86b5-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1. <span data-ttu-id="d86b5-106">Paramfile をメモ帳などのテキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="d86b5-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
    <span data-ttu-id="d86b5-107">位置に paramfile にある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="d86b5-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
2. <span data-ttu-id="d86b5-108">Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示されている変更を行います。</span><span class="sxs-lookup"><span data-stu-id="d86b5-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
    <span data-ttu-id="d86b5-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="d86b5-109">username:snlowner</span></span>  
  
    <span data-ttu-id="d86b5-110">subsystem_name:InteractStub</span><span class="sxs-lookup"><span data-stu-id="d86b5-110">subsystem_name:InteractStub</span></span>  
  
    <span data-ttu-id="d86b5-111">\#subsystem_group:InteractRT</span><span class="sxs-lookup"><span data-stu-id="d86b5-111">\#subsystem_group:InteractRT</span></span>  
  
    <span data-ttu-id="d86b5-112">\#subsystem_dependency:Support、Swarm</span><span class="sxs-lookup"><span data-stu-id="d86b5-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
    <span data-ttu-id="d86b5-113">subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="d86b5-113">subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="d86b5-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="d86b5-114">subsystem_start:</span></span>  
  
    <span data-ttu-id="d86b5-115">**spawn"snlreceiver - SagMessagePartner \<Interact RT のサーバー MessagePartnerName \> AdapterMode 対話"**</span><span class="sxs-lookup"><span data-stu-id="d86b5-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for Interact RT \> -AdapterMode Interact"**</span></span>  
  
    <span data-ttu-id="d86b5-116">\* 終了</span><span class="sxs-lookup"><span data-stu-id="d86b5-116">\*END</span></span>  
  
    <span data-ttu-id="d86b5-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="d86b5-117">subsystem_stop:</span></span>  
  
    <span data-ttu-id="d86b5-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="d86b5-118">\*KILL9:snlreceiver</span></span>  
  
    <span data-ttu-id="d86b5-119">\* 終了</span><span class="sxs-lookup"><span data-stu-id="d86b5-119">\*END</span></span>  
  
    <span data-ttu-id="d86b5-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="d86b5-120">subsystem_status:</span></span>  
  
    <span data-ttu-id="d86b5-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="d86b5-121">\*NB:1:snlreceiver</span></span>  
  
    <span data-ttu-id="d86b5-122">\* 終了</span><span class="sxs-lookup"><span data-stu-id="d86b5-122">\*END</span></span>  
  
    <span data-ttu-id="d86b5-123">start_event:SNL001:subsystem InteractStub です。</span><span class="sxs-lookup"><span data-stu-id="d86b5-123">start_event:SNL001:subsystem InteractStub is up</span></span>  
  
    <span data-ttu-id="d86b5-124">stop_event:SNL002:subsystem InteractStub がダウン</span><span class="sxs-lookup"><span data-stu-id="d86b5-124">stop_event:SNL002:subsystem InteractStub is down</span></span>  
  
    <span data-ttu-id="d86b5-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="d86b5-125">\#subsystem_name:User</span></span>  
  
    <span data-ttu-id="d86b5-126">\## subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="d86b5-126">\##subsystem_group:user</span></span>  
  
    <span data-ttu-id="d86b5-127">\## subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="d86b5-127">\##subsystem_dependency:</span></span>  
  
    <span data-ttu-id="d86b5-128">\#subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="d86b5-128">\#subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="d86b5-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="d86b5-129">\#subsystem_start:</span></span>  
  
    <span data-ttu-id="d86b5-130">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="d86b5-130">\#\*END</span></span>  
  
    <span data-ttu-id="d86b5-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="d86b5-131">\#subsystem_stop:</span></span>  
  
    <span data-ttu-id="d86b5-132">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="d86b5-132">\#\*END</span></span>  
  
    <span data-ttu-id="d86b5-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="d86b5-133">\#subsystem_status:</span></span>  
  
    # <a name="end"></a><span data-ttu-id="d86b5-134">\* 終了</span><span class="sxs-lookup"><span data-stu-id="d86b5-134">\*END</span></span>  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="d86b5-135">ユーザーが稼働 start_event:SNL001:subsystem です。</span><span class="sxs-lookup"><span data-stu-id="d86b5-135">start_event:SNL001:subsystem User is up</span></span>  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="d86b5-136">ユーザーがダウンして stop_event:SNL002:subsystem</span><span class="sxs-lookup"><span data-stu-id="d86b5-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d86b5-137">参照</span><span class="sxs-lookup"><span data-stu-id="d86b5-137">See Also</span></span>  
 <span data-ttu-id="d86b5-138">[InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d86b5-138">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="d86b5-139">[手順 1: 構成用に SWIFT アダプター、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d86b5-139">[Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="d86b5-140">[手順 3: 作成する送信と受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d86b5-140">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="d86b5-141">手順 4: InterAct リアルタイム エンド ツー エンド シナリオをテストする</span><span class="sxs-lookup"><span data-stu-id="d86b5-141">Step 4: Test the InterAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)