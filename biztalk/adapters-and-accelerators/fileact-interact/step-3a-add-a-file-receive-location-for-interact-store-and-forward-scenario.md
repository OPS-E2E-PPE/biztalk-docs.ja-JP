---
title: '手順 3: ファイルの受信場所が、対話ストアと転送シナリオの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f4bae51-6869-4334-a3a1-ef7e662197ca
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d2027878771249ceb2dcb45683a71b4475a75cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224178"
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="9fc7f-102">手順 3: ファイルの受信場所が、対話ストアと転送シナリオの追加</span><span class="sxs-lookup"><span data-stu-id="9fc7f-102">Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="9fc7f-103">完全な[手順 2: InterAct ストアと転送シナリオ Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-103">Complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) before you begin this step.</span></span>
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="9fc7f-104">ファイルの受信場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-104">Add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="9fc7f-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9fc7f-106">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="9fc7f-107">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="9fc7f-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="9fc7f-108">**受信ポートのプロパティ**ウィンドウで、受信ポート名 Tutorial_IA_InputRequest_SnF です。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-108">In the **Receive Port Properties** window, name the receive port, Tutorial_IA_InputRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="9fc7f-109">**受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="9fc7f-110">**受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="9fc7f-111">**FILE トランスポートのプロパティ** ダイアログ ボックスが C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF を入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-111">In the **FILE Transport Properties** dialog box, type C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="9fc7f-112">**受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="9fc7f-113">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="9fc7f-113">**Use this**</span></span>|<span data-ttu-id="9fc7f-114">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="9fc7f-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="9fc7f-115">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="9fc7f-115">**Receive handler**</span></span>|<span data-ttu-id="9fc7f-116">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="9fc7f-117">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="9fc7f-117">**Receive pipeline**</span></span>|<span data-ttu-id="9fc7f-118">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="9fc7f-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fc7f-119">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="9fc7f-120">詳細な手順</span><span class="sxs-lookup"><span data-stu-id="9fc7f-120">Complete steps</span></span>
 <span data-ttu-id="9fc7f-121">[手順 3: 送信ポートを作成し、対話ストアと転送シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9fc7f-121">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="9fc7f-122">[手順 3 b: 追加、対話の受信場所が、対話ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9fc7f-122">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="9fc7f-123">手順 3 C: InterAct ストアと転送シナリオ Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="9fc7f-123">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [<span data-ttu-id="9fc7f-124">ステップ 3 D: InterAct ストアと転送シナリオの対話の送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="9fc7f-124">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)