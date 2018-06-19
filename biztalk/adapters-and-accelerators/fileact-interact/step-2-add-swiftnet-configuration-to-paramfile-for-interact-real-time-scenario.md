---
title: '手順 2: の Paramfile に SWIFTNet 構成を追加する、リアルタイムのシナリオを対話 |Microsoft ドキュメント'
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
ms.openlocfilehash: 3e33203279e045b28d2098ca78c55403c7070b64
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964608"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-real-time-scenario"></a><span data-ttu-id="4cd29-102">手順 2: の Paramfile に SWIFTNet 構成を追加する、リアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="4cd29-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="4cd29-103">SAG で作成されたサーバー メッセージのパートナーは、これらの値で初期化するために受信者を有効にする SWIFTNet paramfile で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd29-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span> <span data-ttu-id="4cd29-104">手順を完了する必要があります、プロシージャを開始する前に[手順 1: 対話リアルタイム シナリオでは、SWIFT アダプターを構成](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="4cd29-104">Before you begin the procedure, you must complete the instructions in [Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="4cd29-105">Paramfile SWIFTNet 構成を追加するには</span><span class="sxs-lookup"><span data-stu-id="4cd29-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="4cd29-106">メモ帳などのテキスト エディターで、paramfile を開きます。</span><span class="sxs-lookup"><span data-stu-id="4cd29-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
     <span data-ttu-id="4cd29-107">Paramfile がある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="4cd29-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
2.  <span data-ttu-id="4cd29-108">Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示された変更を行います。</span><span class="sxs-lookup"><span data-stu-id="4cd29-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
     <span data-ttu-id="4cd29-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="4cd29-109">username:snlowner</span></span>  
  
     <span data-ttu-id="4cd29-110">subsystem_name:InteractStub</span><span class="sxs-lookup"><span data-stu-id="4cd29-110">subsystem_name:InteractStub</span></span>  
  
     <span data-ttu-id="4cd29-111">\#subsystem_group:InteractRT</span><span class="sxs-lookup"><span data-stu-id="4cd29-111">\#subsystem_group:InteractRT</span></span>  
  
     <span data-ttu-id="4cd29-112">\#subsystem_dependency:Support、群</span><span class="sxs-lookup"><span data-stu-id="4cd29-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="4cd29-113">subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="4cd29-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="4cd29-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="4cd29-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="4cd29-115">**起動"snlreceiver - SagMessagePartner \<Interact RT 用サーバー MessagePartnerName \> AdapterMode Interact"**</span><span class="sxs-lookup"><span data-stu-id="4cd29-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for Interact RT \> -AdapterMode Interact"**</span></span>  
  
     <span data-ttu-id="4cd29-116">\* 終了</span><span class="sxs-lookup"><span data-stu-id="4cd29-116">\*END</span></span>  
  
     <span data-ttu-id="4cd29-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="4cd29-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="4cd29-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="4cd29-118">\*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="4cd29-119">\* 終了</span><span class="sxs-lookup"><span data-stu-id="4cd29-119">\*END</span></span>  
  
     <span data-ttu-id="4cd29-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="4cd29-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="4cd29-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="4cd29-121">\*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="4cd29-122">\* 終了</span><span class="sxs-lookup"><span data-stu-id="4cd29-122">\*END</span></span>  
  
     <span data-ttu-id="4cd29-123">start_event:SNL001:subsystem InteractStub が稼働</span><span class="sxs-lookup"><span data-stu-id="4cd29-123">start_event:SNL001:subsystem InteractStub is up</span></span>  
  
     <span data-ttu-id="4cd29-124">stop_event:SNL002:subsystem InteractStub がダウンしています。</span><span class="sxs-lookup"><span data-stu-id="4cd29-124">stop_event:SNL002:subsystem InteractStub is down</span></span>  
  
     <span data-ttu-id="4cd29-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="4cd29-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="4cd29-126">\## subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="4cd29-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="4cd29-127">\## subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="4cd29-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="4cd29-128">\#subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="4cd29-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="4cd29-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="4cd29-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="4cd29-130">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="4cd29-130">\#\*END</span></span>  
  
     <span data-ttu-id="4cd29-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="4cd29-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="4cd29-132">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="4cd29-132">\#\*END</span></span>  
  
     <span data-ttu-id="4cd29-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="4cd29-133">\#subsystem_status:</span></span>  
  
     #<a name="end"></a><span data-ttu-id="4cd29-134">\* 終了</span><span class="sxs-lookup"><span data-stu-id="4cd29-134">\*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="4cd29-135">ユーザーが稼働 start_event:SNL001:subsystem です。</span><span class="sxs-lookup"><span data-stu-id="4cd29-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="4cd29-136">ユーザーがダウンして stop_event:SNL002:subsystem</span><span class="sxs-lookup"><span data-stu-id="4cd29-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd29-137">参照</span><span class="sxs-lookup"><span data-stu-id="4cd29-137">See Also</span></span>  
 <span data-ttu-id="4cd29-138">[リアルタイムのシナリオを対話します。](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4cd29-138">[InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="4cd29-139">[手順 1: 構成用のアダプターを SWIFT、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4cd29-139">[Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="4cd29-140">[手順 3: が送信を作成し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="4cd29-140">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="4cd29-141">手順 4: InterAct リアルタイム エンド ツー エンド シナリオをテストする</span><span class="sxs-lookup"><span data-stu-id="4cd29-141">Step 4: Test the InterAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)