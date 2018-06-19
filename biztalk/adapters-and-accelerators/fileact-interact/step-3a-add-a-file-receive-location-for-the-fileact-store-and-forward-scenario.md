---
title: '手順 3: ファイルの受信場所が FileAct ストア アンド フォワードのシナリオの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67ecbf4a-a2b4-4534-8ca1-3bfbb6a697bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e02f636500ed21d4442a43078bcd407c91d69d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224050"
---
# <a name="step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="e2f9f-102">手順 3: ファイルの受信場所が FileAct ストア アンド フォワードのシナリオを追加</span><span class="sxs-lookup"><span data-stu-id="e2f9f-102">Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="e2f9f-103">この手順を開始する前に行う必要があります[手順 2: FileAct ストア アンド フォワードのシナリオの Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2f9f-103">Before you begin this step, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="e2f9f-104">ファイルの受信場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="e2f9f-104">To add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="e2f9f-105">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="e2f9f-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e2f9f-106">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="e2f9f-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="e2f9f-107">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="e2f9f-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="e2f9f-108">**受信ポートのプロパティ**ウィンドウで、受信ポート名 Tutorial_FA_InputRequest_SnF です。</span><span class="sxs-lookup"><span data-stu-id="e2f9f-108">In the **Receive Port Properties** window, name the receive port, Tutorial_FA_InputRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="e2f9f-109">**受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="e2f9f-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="e2f9f-110">**受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e2f9f-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="e2f9f-111">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF を入力し、をクリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="e2f9f-111">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="e2f9f-112">**受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e2f9f-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="e2f9f-113">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="e2f9f-113">**Use this**</span></span>|<span data-ttu-id="e2f9f-114">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="e2f9f-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="e2f9f-115">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="e2f9f-115">**Receive handler**</span></span>|<span data-ttu-id="e2f9f-116">ドロップダウン リストから選択**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="e2f9f-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="e2f9f-117">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="e2f9f-117">**Receive pipeline**</span></span>|<span data-ttu-id="e2f9f-118">ドロップダウン リストから選択**XMLReceive**です。</span><span class="sxs-lookup"><span data-stu-id="e2f9f-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="e2f9f-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2f9f-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f9f-120">参照</span><span class="sxs-lookup"><span data-stu-id="e2f9f-120">See Also</span></span>  
 <span data-ttu-id="e2f9f-121">[手順 3: 送信ポートを作成し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="e2f9f-121">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="e2f9f-122">[手順 3 b: FILEACT の受信場所が FileAct ストア アンド フォワードのシナリオを追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="e2f9f-122">[Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="e2f9f-123">[手順 3 C: Sw:HandleFileRequest と Sw:HandleSnFRequest FileAct ストア アンド フォワードのシナリオについてメッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md) </span><span class="sxs-lookup"><span data-stu-id="e2f9f-123">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md) </span></span>  
 [<span data-ttu-id="e2f9f-124">ステップ 3 D: FileAct ストア アンド フォワードのシナリオの FILEACT 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="e2f9f-124">Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)