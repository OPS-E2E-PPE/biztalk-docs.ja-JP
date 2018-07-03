---
title: '手順 2: FileAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 088ab41f-8325-4330-b6f2-0164aa1911b1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a287c6063ff60b08a53ec4f05d45da9225f1c30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998243"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="227e2-102">手順 2: FileAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="227e2-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="227e2-103">これらの値で初期化するために受信者を有効にする SWIFTNet に paramfile に SAG で作成したサーバー メッセージのパートナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="227e2-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
<span data-ttu-id="227e2-104">完全な[手順 1: FileAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成する](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="227e2-104">Complete [Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) before you begin this step.</span></span>
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="227e2-105">Paramfile に SWIFTNet 構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="227e2-105">Add SWIFTNet configuration to the paramfile</span></span>  
  
1. <span data-ttu-id="227e2-106">Paramfile をメモ帳などのテキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="227e2-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
2. <span data-ttu-id="227e2-107">位置に paramfile にある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="227e2-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
3. <span data-ttu-id="227e2-108">Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示されている変更を行います。</span><span class="sxs-lookup"><span data-stu-id="227e2-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
    
    <span data-ttu-id="227e2-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="227e2-109">username:snlowner</span></span>  
  
    <span data-ttu-id="227e2-110">subsystem_name:FileactStub</span><span class="sxs-lookup"><span data-stu-id="227e2-110">subsystem_name:FileactStub</span></span>  
  
    <span data-ttu-id="227e2-111">\#subsystem_group:fileactsnf</span><span class="sxs-lookup"><span data-stu-id="227e2-111">\#subsystem_group:fileactsnf</span></span>  
  
    <span data-ttu-id="227e2-112">\#subsystem_dependency:Support、Swarm</span><span class="sxs-lookup"><span data-stu-id="227e2-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
    <span data-ttu-id="227e2-113">subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="227e2-113">subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="227e2-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="227e2-114">subsystem_start:</span></span>  
  
    <span data-ttu-id="227e2-115">**spawn"snlreceiver - SagMessagePartner \<fileact SnF 用サーバー MessagePartnerName\> -AdapterMode fileact"**</span><span class="sxs-lookup"><span data-stu-id="227e2-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for fileact SnF\> -AdapterMode fileact"**</span></span>  
  
    <span data-ttu-id="227e2-116">\* 終了</span><span class="sxs-lookup"><span data-stu-id="227e2-116">\*END</span></span>  
  
    <span data-ttu-id="227e2-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="227e2-117">subsystem_stop:</span></span>  
  
    <span data-ttu-id="227e2-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="227e2-118">\*KILL9:snlreceiver</span></span>  
  
    <span data-ttu-id="227e2-119">\* 終了</span><span class="sxs-lookup"><span data-stu-id="227e2-119">\*END</span></span>  
  
    <span data-ttu-id="227e2-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="227e2-120">subsystem_status:</span></span>  
  
    <span data-ttu-id="227e2-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="227e2-121">\*NB:1:snlreceiver</span></span>  
  
    <span data-ttu-id="227e2-122">\* 終了</span><span class="sxs-lookup"><span data-stu-id="227e2-122">\*END</span></span>  
  
    <span data-ttu-id="227e2-123">start_event:SNL001:subsystem FileactStubSnF です。</span><span class="sxs-lookup"><span data-stu-id="227e2-123">start_event:SNL001:subsystem FileactStubSnF is up</span></span>  
  
    <span data-ttu-id="227e2-124">stop_event:SNL002:subsystem FileactStubSnF がダウン</span><span class="sxs-lookup"><span data-stu-id="227e2-124">stop_event:SNL002:subsystem FileactStubSnF is down</span></span>  
  
    <span data-ttu-id="227e2-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="227e2-125">\#subsystem_name:User</span></span>  
  
    <span data-ttu-id="227e2-126">\## subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="227e2-126">\##subsystem_group:user</span></span>  
  
    <span data-ttu-id="227e2-127">\## subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="227e2-127">\##subsystem_dependency:</span></span>  
  
    <span data-ttu-id="227e2-128">\#subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="227e2-128">\#subsystem_nature:critical</span></span>  
  
    <span data-ttu-id="227e2-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="227e2-129">\#subsystem_start:</span></span>  
  
    <span data-ttu-id="227e2-130">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="227e2-130">\#\*END</span></span>  
  
    <span data-ttu-id="227e2-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="227e2-131">\#subsystem_stop:</span></span>  
  
    <span data-ttu-id="227e2-132">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="227e2-132">\#\*END</span></span>  
  
    <span data-ttu-id="227e2-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="227e2-133">\#subsystem_status:</span></span>  
  
    <span data-ttu-id="227e2-134">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="227e2-134">\#\*END</span></span>  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="227e2-135">ユーザーが稼働 start_event:SNL001:subsystem です。</span><span class="sxs-lookup"><span data-stu-id="227e2-135">start_event:SNL001:subsystem User is up</span></span>  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="227e2-136">ユーザーがダウンして stop_event:SNL002:subsystem</span><span class="sxs-lookup"><span data-stu-id="227e2-136">stop_event:SNL002:subsystem User is down</span></span>  
    
  
## <a name="complete-steps"></a><span data-ttu-id="227e2-137">手順を完了します</span><span class="sxs-lookup"><span data-stu-id="227e2-137">Complete steps</span></span>
 <span data-ttu-id="227e2-138">[FileAct ストア アンド フォワード シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="227e2-138">[FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="227e2-139">[手順 1: FileAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成します。](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="227e2-139">[Step 1: Configure the SWIFT Adapter for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="227e2-140">[手順 3: 送信ポートを作成し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="227e2-140">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="227e2-141">手順 4: FileAct ストア アンド フォワード エンド ツー エンド シナリオをテストする</span><span class="sxs-lookup"><span data-stu-id="227e2-141">Step 4: Test FileAct Store and Forward End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)