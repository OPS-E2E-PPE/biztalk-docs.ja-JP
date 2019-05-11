---
title: 手順 3 a:ファイル受信場所を追加、InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5579375-8c05-4583-bcaa-b483ac275d8a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 776a5b8c708e9b86c6bd844fc2dcb46aed9efe40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365672"
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario"></a><span data-ttu-id="78adf-102">手順 3 a:ファイル受信場所を追加、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="78adf-102">Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="78adf-103">検証用にテスト ファイルを簡単に削除することができます、受信場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="78adf-103">Set up a receive location that enables you to easily drop test files for validation.</span></span> <span data-ttu-id="78adf-104">シナリオをテストするのにには、この場所を使用します。</span><span class="sxs-lookup"><span data-stu-id="78adf-104">You use this location to test the scenario.</span></span>  
  
## <a name="add-a-file-receive-location"></a><span data-ttu-id="78adf-105">ファイル受信場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="78adf-105">Add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="78adf-106">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="78adf-106">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="78adf-107">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="78adf-107">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="78adf-108">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="78adf-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="78adf-109">**受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_InputRequest_RealTime**します。</span><span class="sxs-lookup"><span data-stu-id="78adf-109">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_InputRequest_RealTime**.</span></span>  
  
5.  <span data-ttu-id="78adf-110">**受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="78adf-110">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="78adf-111">**受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="78adf-111">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="78adf-112">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに「 **C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime**、順にクリックします**Ok**します。</span><span class="sxs-lookup"><span data-stu-id="78adf-112">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="78adf-113">**受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="78adf-113">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="78adf-114">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="78adf-114">**Use this**</span></span>|<span data-ttu-id="78adf-115">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="78adf-115">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="78adf-116">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="78adf-116">**Receive handler**</span></span>|<span data-ttu-id="78adf-117">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="78adf-117">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="78adf-118">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="78adf-118">**Receive pipeline**</span></span>|<span data-ttu-id="78adf-119">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="78adf-119">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="78adf-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78adf-120">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78adf-121">参照</span><span class="sxs-lookup"><span data-stu-id="78adf-121">See Also</span></span>  
 <span data-ttu-id="78adf-122">[ステップ 3:作成する送信と受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="78adf-122">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="78adf-123">[手順 3 b:INTERACT の受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="78adf-123">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="78adf-124">[手順 3 C:用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="78adf-124">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="78adf-125">[手順 3 D:用に Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="78adf-125">[Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span></span>  
 [<span data-ttu-id="78adf-126">手順 3 e:用の INTERACT 送信ポートを追加、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="78adf-126">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)