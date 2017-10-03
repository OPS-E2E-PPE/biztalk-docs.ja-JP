---
title: "手順 3: ファイルの受信場所、FileAct リアルタイムのシナリオの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73b044b4-6611-493f-969c-02b52cb56ba7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 266b29281ea7518cffee1461da2a3eaac66d9429
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario"></a><span data-ttu-id="dafbb-102">手順 3: ファイルの受信場所、FileAct リアルタイムのシナリオの追加</span><span class="sxs-lookup"><span data-stu-id="dafbb-102">Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="dafbb-103">この手順を開始する前に行う必要があります[手順 2: FileAct リアルタイム シナリオ Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="dafbb-103">Before you begin this step, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="dafbb-104">ファイルの受信場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="dafbb-104">To add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="dafbb-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="dafbb-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="dafbb-106">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="dafbb-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="dafbb-107">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="dafbb-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="dafbb-108">**受信ポートのプロパティ**ウィンドウで、受信ポート名 Tutorial_FA_InputRequest_RealTime です。</span><span class="sxs-lookup"><span data-stu-id="dafbb-108">In the **Receive Port Properties** window, name the receive port, Tutorial_FA_InputRequest_RealTime.</span></span>  
  
5.  <span data-ttu-id="dafbb-109">**受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="dafbb-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="dafbb-110">**受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="dafbb-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="dafbb-111">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime を入力し、をクリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="dafbb-111">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="dafbb-112">**受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="dafbb-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="dafbb-113">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="dafbb-113">**Use this**</span></span>|<span data-ttu-id="dafbb-114">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="dafbb-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="dafbb-115">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="dafbb-115">**Receive handler**</span></span>|<span data-ttu-id="dafbb-116">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="dafbb-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="dafbb-117">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="dafbb-117">**Receive pipeline**</span></span>|<span data-ttu-id="dafbb-118">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="dafbb-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="dafbb-119">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dafbb-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dafbb-120">参照</span><span class="sxs-lookup"><span data-stu-id="dafbb-120">See Also</span></span>  
 <span data-ttu-id="dafbb-121">[手順 3: 送信ポートを作成し、FileAct リアルタイムのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="dafbb-121">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="dafbb-122">[手順 3 b: FILEACT の受信場所が FileAct リアルタイム シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="dafbb-122">[Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="dafbb-123">[手順 3 C: FileAct リアルタイム シナリオ Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span><span class="sxs-lookup"><span data-stu-id="dafbb-123">[Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span></span>  
 <span data-ttu-id="dafbb-124">[ステップ 3 D: FileAct リアルタイム シナリオ FILEACT 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="dafbb-124">[Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="dafbb-125">ステップ 3 e: FileAct リアルタイム シナリオ Sw:ExchangeFileResponse メッセージをキャプチャする FILE 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="dafbb-125">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)