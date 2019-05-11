---
title: 手順 3 a:ファイル受信 InterAct ストア アンド フォワード シナリオ用の場所の追加 |Microsoft Docs
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
ms.openlocfilehash: 9fb4594877cb4679bbb355d8ea9ee66041c12dfc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365924"
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="66563-102">手順 3 a:InterAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="66563-102">Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="66563-103">完全な[手順 2。InterAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)この手順を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="66563-103">Complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md) before you begin this step.</span></span>
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="66563-104">ファイル受信場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="66563-104">Add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="66563-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="66563-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="66563-106">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="66563-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="66563-107">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="66563-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="66563-108">**受信ポートのプロパティ**ウィンドウで、名前、受信ポート Tutorial_IA_InputRequest_SnF します。</span><span class="sxs-lookup"><span data-stu-id="66563-108">In the **Receive Port Properties** window, name the receive port, Tutorial_IA_InputRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="66563-109">**受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="66563-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="66563-110">**受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="66563-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="66563-111">**FILE トランスポートのプロパティ** ダイアログ ボックスでは、C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF を入力して、クリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="66563-111">In the **FILE Transport Properties** dialog box, type C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="66563-112">**受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="66563-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="66563-113">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="66563-113">**Use this**</span></span>|<span data-ttu-id="66563-114">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="66563-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="66563-115">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="66563-115">**Receive handler**</span></span>|<span data-ttu-id="66563-116">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="66563-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="66563-117">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="66563-117">**Receive pipeline**</span></span>|<span data-ttu-id="66563-118">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="66563-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="66563-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66563-119">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="66563-120">手順を完了します</span><span class="sxs-lookup"><span data-stu-id="66563-120">Complete steps</span></span>
 <span data-ttu-id="66563-121">[ステップ 3:送信ポートの作成し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="66563-121">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="66563-122">[手順 3 b:INTERACT の受信場所 InterAct ストア アンド フォワード シナリオ用の追加します。](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="66563-122">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="66563-123">手順 3 C:InterAct ストア アンド フォワード シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="66563-123">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [<span data-ttu-id="66563-124">手順 3 D:InterAct ストア アンド フォワード シナリオ用に INTERACT 送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="66563-124">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)