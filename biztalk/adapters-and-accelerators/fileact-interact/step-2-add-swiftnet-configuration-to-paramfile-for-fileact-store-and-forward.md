---
title: "手順 2: FileAct ストア アンド フォワードのシナリオの Paramfile に SWIFTNet 構成を追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 088ab41f-8325-4330-b6f2-0164aa1911b1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394e570ad9bd1c0e7532923dac9c2cc702f2f567
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="f8694-102">手順 2: FileAct ストア アンド フォワードのシナリオの Paramfile に SWIFTNet 構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="f8694-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="f8694-103">SAG で作成されたサーバー メッセージのパートナーは、これらの値で初期化するために受信者を有効にする SWIFTNet paramfile で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8694-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
<span data-ttu-id="f8694-104">完全な[手順 1: SWIFT アダプター FileAct ストア アンド フォワード シナリオ用に構成](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="f8694-104">Complete [Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) before you begin this step.</span></span>
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="f8694-105">SWIFTNet 構成、paramfile を追加します。</span><span class="sxs-lookup"><span data-stu-id="f8694-105">Add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="f8694-106">メモ帳などのテキスト エディターで、paramfile を開きます。</span><span class="sxs-lookup"><span data-stu-id="f8694-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
2.  <span data-ttu-id="f8694-107">Paramfile がある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="f8694-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
3.  <span data-ttu-id="f8694-108">Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示された変更を行います。</span><span class="sxs-lookup"><span data-stu-id="f8694-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
    
     <span data-ttu-id="f8694-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="f8694-109">username:snlowner</span></span>  
  
     <span data-ttu-id="f8694-110">subsystem_name:FileactStub</span><span class="sxs-lookup"><span data-stu-id="f8694-110">subsystem_name:FileactStub</span></span>  
  
     <span data-ttu-id="f8694-111">\#subsystem_group:fileactsnf</span><span class="sxs-lookup"><span data-stu-id="f8694-111">\#subsystem_group:fileactsnf</span></span>  
  
     <span data-ttu-id="f8694-112">\#subsystem_dependency:Support、群</span><span class="sxs-lookup"><span data-stu-id="f8694-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="f8694-113">subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="f8694-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="f8694-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="f8694-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="f8694-115">**起動"snlreceiver - SagMessagePartner \<fileact SnF 用サーバー MessagePartnerName\> -AdapterMode fileact"**</span><span class="sxs-lookup"><span data-stu-id="f8694-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for fileact SnF\> -AdapterMode fileact"**</span></span>  
  
     <span data-ttu-id="f8694-116">* 終了</span><span class="sxs-lookup"><span data-stu-id="f8694-116">*END</span></span>  
  
     <span data-ttu-id="f8694-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="f8694-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="f8694-118">* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="f8694-118">*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="f8694-119">* 終了</span><span class="sxs-lookup"><span data-stu-id="f8694-119">*END</span></span>  
  
     <span data-ttu-id="f8694-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="f8694-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="f8694-121">* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="f8694-121">*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="f8694-122">* 終了</span><span class="sxs-lookup"><span data-stu-id="f8694-122">*END</span></span>  
  
     <span data-ttu-id="f8694-123">start_event:SNL001:subsystem FileactStubSnF が稼働</span><span class="sxs-lookup"><span data-stu-id="f8694-123">start_event:SNL001:subsystem FileactStubSnF is up</span></span>  
  
     <span data-ttu-id="f8694-124">stop_event:SNL002:subsystem FileactStubSnF がダウンしています。</span><span class="sxs-lookup"><span data-stu-id="f8694-124">stop_event:SNL002:subsystem FileactStubSnF is down</span></span>  
  
     <span data-ttu-id="f8694-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="f8694-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="f8694-126">\## subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="f8694-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="f8694-127">\## subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="f8694-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="f8694-128">\#subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="f8694-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="f8694-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="f8694-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="f8694-130">\#* 終了</span><span class="sxs-lookup"><span data-stu-id="f8694-130">\#*END</span></span>  
  
     <span data-ttu-id="f8694-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="f8694-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="f8694-132">\#* 終了</span><span class="sxs-lookup"><span data-stu-id="f8694-132">\#*END</span></span>  
  
     <span data-ttu-id="f8694-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="f8694-133">\#subsystem_status:</span></span>  
  
     <span data-ttu-id="f8694-134">\#* 終了</span><span class="sxs-lookup"><span data-stu-id="f8694-134">\#*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="f8694-135">ユーザーが稼働 start_event:SNL001:subsystem です。</span><span class="sxs-lookup"><span data-stu-id="f8694-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="f8694-136">ユーザーがダウンして stop_event:SNL002:subsystem</span><span class="sxs-lookup"><span data-stu-id="f8694-136">stop_event:SNL002:subsystem User is down</span></span>  
    
  
## <a name="complete-steps"></a><span data-ttu-id="f8694-137">詳細な手順</span><span class="sxs-lookup"><span data-stu-id="f8694-137">Complete steps</span></span>
 <span data-ttu-id="f8694-138">[FileAct ストア アンド フォワードのシナリオ](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f8694-138">[FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="f8694-139">[手順 1: FileAct ストア アンド フォワードのシナリオ用 SWIFT アダプターを構成します。](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f8694-139">[Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="f8694-140">[手順 3: 送信ポートを作成し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="f8694-140">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="f8694-141">手順 4: FileAct ストア アンド フォワード エンド ツー エンド シナリオをテストする</span><span class="sxs-lookup"><span data-stu-id="f8694-141">Step 4: Test FileAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)