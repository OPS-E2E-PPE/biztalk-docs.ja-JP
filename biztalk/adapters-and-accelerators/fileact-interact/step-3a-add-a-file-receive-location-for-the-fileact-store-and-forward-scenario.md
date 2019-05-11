---
title: 手順 3 a:FileAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加する |Microsoft Docs
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
ms.openlocfilehash: d24f40255bd76698a72c614c3ead7cd672ed4b50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365950"
---
# <a name="step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="7e41f-102">手順 3 a:FileAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="7e41f-102">Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="7e41f-103">この手順を開始する前に行う必要があります[手順 2。FileAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e41f-103">Before you begin this step, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="7e41f-104">ファイル受信場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="7e41f-104">To add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="7e41f-105">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="7e41f-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7e41f-106">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="7e41f-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="7e41f-107">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="7e41f-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="7e41f-108">**受信ポートのプロパティ**ウィンドウで、名前、受信ポート Tutorial_FA_InputRequest_SnF します。</span><span class="sxs-lookup"><span data-stu-id="7e41f-108">In the **Receive Port Properties** window, name the receive port, Tutorial_FA_InputRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="7e41f-109">**受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="7e41f-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="7e41f-110">**受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="7e41f-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="7e41f-111">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF を入力し、 をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="7e41f-111">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="7e41f-112">**受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7e41f-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="7e41f-113">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="7e41f-113">**Use this**</span></span>|<span data-ttu-id="7e41f-114">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="7e41f-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="7e41f-115">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="7e41f-115">**Receive handler**</span></span>|<span data-ttu-id="7e41f-116">ドロップダウン リストから選択**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="7e41f-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="7e41f-117">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="7e41f-117">**Receive pipeline**</span></span>|<span data-ttu-id="7e41f-118">ドロップダウン リストから選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="7e41f-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="7e41f-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e41f-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e41f-120">参照</span><span class="sxs-lookup"><span data-stu-id="7e41f-120">See Also</span></span>  
 <span data-ttu-id="7e41f-121">[ステップ 3:送信ポートを作成し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="7e41f-121">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="7e41f-122">[手順 3 b:FileAct ストア アンド フォワード シナリオ用の場所に、FILEACT の受信を追加します。](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7e41f-122">[Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="7e41f-123">[手順 3 C:FileAct ストア アンド フォワード シナリオ用 Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャする FILE 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md) </span><span class="sxs-lookup"><span data-stu-id="7e41f-123">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md) </span></span>  
 [<span data-ttu-id="7e41f-124">手順 3 D:FileAct ストア アンド フォワード シナリオ用 FILEACT 送信ポートの追加します。</span><span class="sxs-lookup"><span data-stu-id="7e41f-124">Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)