---
title: '手順 2: SWIFTNet の構成を追加、Paramfile FileAct リアルタイム シナリオ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4feec3f-4755-477e-b3d6-1dd6d075255e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adad4d98be93e17bef4ab5eeb9e49271ffc94b74
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963768"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-real-time-scenario"></a><span data-ttu-id="120c6-102">手順 2: SWIFTNet の構成を追加、Paramfile FileAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="120c6-102">Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="120c6-103">SAG で作成されたサーバー メッセージのパートナーは、これらの値で初期化するために受信者を有効にする SWIFTNet paramfile で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="120c6-103">The Server message partners created in SAG must be specified in the SWIFTNet paramfile to enable Receivers to initialize with these values.</span></span>  
  
 <span data-ttu-id="120c6-104">この手順を開始する前に行う必要があります[手順 1: FileAct リアルタイム シナリオでは、SWIFT アダプターを構成する](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="120c6-104">Before you begin this step, you must complete [Step 1: Configure the SWIFT Adapter for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a><span data-ttu-id="120c6-105">Paramfile SWIFTNet 構成を追加するには</span><span class="sxs-lookup"><span data-stu-id="120c6-105">To add SWIFTNet configuration to the paramfile</span></span>  
  
1.  <span data-ttu-id="120c6-106">メモ帳などのテキスト エディターで、paramfile を開きます。</span><span class="sxs-lookup"><span data-stu-id="120c6-106">Open the paramfile in a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="120c6-107">Paramfile がある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span><span class="sxs-lookup"><span data-stu-id="120c6-107">The paramfile is typically located at: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile</span></span>  
  
2.  <span data-ttu-id="120c6-108">Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示された変更を行います。</span><span class="sxs-lookup"><span data-stu-id="120c6-108">In the paramfile, make the highlighted change to specify the Server Message partner name:</span></span>  
  
     <span data-ttu-id="120c6-109">username:snlowner</span><span class="sxs-lookup"><span data-stu-id="120c6-109">username:snlowner</span></span>  
  
     <span data-ttu-id="120c6-110">subsystem_name:FileactStub</span><span class="sxs-lookup"><span data-stu-id="120c6-110">subsystem_name:FileactStub</span></span>  
  
     <span data-ttu-id="120c6-111">\#subsystem_group:fileact</span><span class="sxs-lookup"><span data-stu-id="120c6-111">\#subsystem_group:fileact</span></span>  
  
     <span data-ttu-id="120c6-112">\#subsystem_dependency:Support、群</span><span class="sxs-lookup"><span data-stu-id="120c6-112">\#subsystem_dependency:Support,Swarm</span></span>  
  
     <span data-ttu-id="120c6-113">subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="120c6-113">subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="120c6-114">subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="120c6-114">subsystem_start:</span></span>  
  
     <span data-ttu-id="120c6-115">**起動"snlreceiver - SagMessagePartner \<fileact RT 用サーバー MessagePartnerName \> -AdapterMode fileact"**</span><span class="sxs-lookup"><span data-stu-id="120c6-115">**spawn "snlreceiver -SagMessagePartner \<Server MessagePartnerName for fileact RT \> -AdapterMode fileact"**</span></span>  
  
     <span data-ttu-id="120c6-116">\* 終了</span><span class="sxs-lookup"><span data-stu-id="120c6-116">\*END</span></span>  
  
     <span data-ttu-id="120c6-117">subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="120c6-117">subsystem_stop:</span></span>  
  
     <span data-ttu-id="120c6-118">\* KILL9:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="120c6-118">\*KILL9:snlreceiver</span></span>  
  
     <span data-ttu-id="120c6-119">\* 終了</span><span class="sxs-lookup"><span data-stu-id="120c6-119">\*END</span></span>  
  
     <span data-ttu-id="120c6-120">subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="120c6-120">subsystem_status:</span></span>  
  
     <span data-ttu-id="120c6-121">\* NB:1:snlreceiver</span><span class="sxs-lookup"><span data-stu-id="120c6-121">\*NB:1:snlreceiver</span></span>  
  
     <span data-ttu-id="120c6-122">\* 終了</span><span class="sxs-lookup"><span data-stu-id="120c6-122">\*END</span></span>  
  
     <span data-ttu-id="120c6-123">start_event:SNL001:subsystem FileactStub が稼働</span><span class="sxs-lookup"><span data-stu-id="120c6-123">start_event:SNL001:subsystem FileactStub is up</span></span>  
  
     <span data-ttu-id="120c6-124">stop_event:SNL002:subsystem FileactStub がダウンしています。</span><span class="sxs-lookup"><span data-stu-id="120c6-124">stop_event:SNL002:subsystem FileactStub is down</span></span>  
  
     <span data-ttu-id="120c6-125">\#subsystem_name:User</span><span class="sxs-lookup"><span data-stu-id="120c6-125">\#subsystem_name:User</span></span>  
  
     <span data-ttu-id="120c6-126">\## subsystem_group:user</span><span class="sxs-lookup"><span data-stu-id="120c6-126">\##subsystem_group:user</span></span>  
  
     <span data-ttu-id="120c6-127">\## subsystem_dependency:</span><span class="sxs-lookup"><span data-stu-id="120c6-127">\##subsystem_dependency:</span></span>  
  
     <span data-ttu-id="120c6-128">\#subsystem_nature: 重大</span><span class="sxs-lookup"><span data-stu-id="120c6-128">\#subsystem_nature:critical</span></span>  
  
     <span data-ttu-id="120c6-129">\#subsystem_start:</span><span class="sxs-lookup"><span data-stu-id="120c6-129">\#subsystem_start:</span></span>  
  
     <span data-ttu-id="120c6-130">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="120c6-130">\#\*END</span></span>  
  
     <span data-ttu-id="120c6-131">\#subsystem_stop:</span><span class="sxs-lookup"><span data-stu-id="120c6-131">\#subsystem_stop:</span></span>  
  
     <span data-ttu-id="120c6-132">\#\* 終了</span><span class="sxs-lookup"><span data-stu-id="120c6-132">\#\*END</span></span>  
  
     <span data-ttu-id="120c6-133">\#subsystem_status:</span><span class="sxs-lookup"><span data-stu-id="120c6-133">\#subsystem_status:</span></span>  
  
     #<a name="end"></a><span data-ttu-id="120c6-134">\* 終了</span><span class="sxs-lookup"><span data-stu-id="120c6-134">\*END</span></span>  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a><span data-ttu-id="120c6-135">ユーザーが稼働 start_event:SNL001:subsystem です。</span><span class="sxs-lookup"><span data-stu-id="120c6-135">start_event:SNL001:subsystem User is up</span></span>  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a><span data-ttu-id="120c6-136">ユーザーがダウンして stop_event:SNL002:subsystem</span><span class="sxs-lookup"><span data-stu-id="120c6-136">stop_event:SNL002:subsystem User is down</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120c6-137">参照</span><span class="sxs-lookup"><span data-stu-id="120c6-137">See Also</span></span>  
 <span data-ttu-id="120c6-138">[FileAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="120c6-138">[FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="120c6-139">[手順 1: FileAct リアルタイム シナリオでは、SWIFT のアダプターを構成します。](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="120c6-139">[Step 1: Configure the SWIFT Adapter for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="120c6-140">[手順 3: 送信ポートを作成し、FileAct リアルタイムのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="120c6-140">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="120c6-141">手順 4: FileAct リアルタイム エンド ツー エンド シナリオをテストする</span><span class="sxs-lookup"><span data-stu-id="120c6-141">Step 4: Test FileAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)