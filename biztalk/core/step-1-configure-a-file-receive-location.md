---
title: 手順 1:ファイルを構成する受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df591263-964a-4ad8-bc3a-a553de8dae4f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ae1bb74c162a0a61521392fc4cd75e99ba26297
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392826"
---
# <a name="step-1-configure-a-file-receive-location"></a><span data-ttu-id="5255c-102">手順 1:ファイルを構成する受信場所</span><span class="sxs-lookup"><span data-stu-id="5255c-102">Step 1: Configure a FILE Receive Location</span></span>
<span data-ttu-id="5255c-103">このトピックでは、ファイルを構成する送信ポートを呼び出すためにファイル フォルダーにドロップするダミー要求メッセージを使用する受信場所。</span><span class="sxs-lookup"><span data-stu-id="5255c-103">In this topic, you configure a FILE receive location that consumes the dummy request message that you drop to a file folder to invoke the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5255c-104">このチュートリアルの手順では、既定のアプリケーションを使用することを想定しています (**BizTalk アプリケーション 1**) ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="5255c-104">The steps in this tutorial assume that you use the default application (**BizTalk Application 1**) to create the solution.</span></span> <span data-ttu-id="5255c-105">また別のアプリケーションを作成し、そのアプリケーションで同じ手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="5255c-105">You can also create another application and perform the same steps in any that application.</span></span>  
  
### <a name="to-configure-a-file-receive-location"></a><span data-ttu-id="5255c-106">ファイル受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="5255c-106">To configure a FILE receive location</span></span>  
  
1.  <span data-ttu-id="5255c-107">BizTalk Server 管理コンソールから下、 **BizTalk アプリケーション 1**ノードを右クリックして**受信ポート**、 をポイント**新規**、順にクリックします**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="5255c-107">From BizTalk Server Administration Console, under the **BizTalk Application 1** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="5255c-108">[全般] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5255c-108">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="5255c-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5255c-109">Use this</span></span>|<span data-ttu-id="5255c-110">目的</span><span class="sxs-lookup"><span data-stu-id="5255c-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5255c-111">**名前**</span><span class="sxs-lookup"><span data-stu-id="5255c-111">**Name**</span></span>|<span data-ttu-id="5255c-112">型**ReceivePortRestAzureMarketPlace**します。</span><span class="sxs-lookup"><span data-stu-id="5255c-112">Type **ReceivePortRestAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="5255c-113">**失敗したメッセージのルーティングを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="5255c-113">**Enable routing for failed messages**</span></span>|<span data-ttu-id="5255c-114">(選択解除)</span><span class="sxs-lookup"><span data-stu-id="5255c-114">(clear)</span></span>|  
  
3.  <span data-ttu-id="5255c-115">クリックして**受信場所**、 をクリックし、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="5255c-115">Click **Receive Locations**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="5255c-116">[Receive Location1 - 受信場所のプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5255c-116">From Receive Location1 – Receive Location Properties, do the following:</span></span>  
  
    |<span data-ttu-id="5255c-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5255c-117">Use this</span></span>|<span data-ttu-id="5255c-118">目的</span><span class="sxs-lookup"><span data-stu-id="5255c-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5255c-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="5255c-119">**Name**</span></span>|<span data-ttu-id="5255c-120">型**ReceiveLocationAzureMarketPlace**します。</span><span class="sxs-lookup"><span data-stu-id="5255c-120">Type **ReceiveLocationAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="5255c-121">**型**</span><span class="sxs-lookup"><span data-stu-id="5255c-121">**Type**</span></span>|<span data-ttu-id="5255c-122">選択**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="5255c-122">Select **FILE**.</span></span>|  
    |<span data-ttu-id="5255c-123">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="5255c-123">**Receive handler**</span></span>|<span data-ttu-id="5255c-124">**[BizTalkServerApplication]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5255c-124">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="5255c-125">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="5255c-125">**Receive pipeline**</span></span>|<span data-ttu-id="5255c-126">選択**PassThruReceive**です。</span><span class="sxs-lookup"><span data-stu-id="5255c-126">Select **PassThruReceive**.</span></span>|  
  
5.  <span data-ttu-id="5255c-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="5255c-127">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="5255c-128">[FILE トランスポートのプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5255c-128">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="5255c-129">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5255c-129">Use this</span></span>|<span data-ttu-id="5255c-130">目的</span><span class="sxs-lookup"><span data-stu-id="5255c-130">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5255c-131">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="5255c-131">**Receive folder**</span></span>|<span data-ttu-id="5255c-132">ダミー要求メッセージをドロップする場所の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="5255c-132">Type a location where you will drop the dummy request message.</span></span>|  
    |<span data-ttu-id="5255c-133">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="5255c-133">**File name**</span></span>|<span data-ttu-id="5255c-134">保持 `*.xml`</span><span class="sxs-lookup"><span data-stu-id="5255c-134">Retain `*.xml`</span></span>|  
  
7.  <span data-ttu-id="5255c-135">クリックして**OK**すべてのダイアログ ボックスを終了するまでです。</span><span class="sxs-lookup"><span data-stu-id="5255c-135">Click **OK** until you exit all the dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5255c-136">参照</span><span class="sxs-lookup"><span data-stu-id="5255c-136">See Also</span></span>  
 [<span data-ttu-id="5255c-137">チュートリアル 5:BizTalk Server を使用して REST インターフェイスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="5255c-137">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)