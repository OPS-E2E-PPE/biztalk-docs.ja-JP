---
title: '手順 1: 構成ファイルの受信場所 |Microsoft ドキュメント'
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
ms.openlocfilehash: 78f8bccc187bf310b8426fc3d5fee36add44a9f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278258"
---
# <a name="step-1-configure-a-file-receive-location"></a><span data-ttu-id="d62ff-102">手順 1: 構成ファイルの受信場所</span><span class="sxs-lookup"><span data-stu-id="d62ff-102">Step 1: Configure a FILE Receive Location</span></span>
<span data-ttu-id="d62ff-103">このトピックでは、送信ポートを呼び出すためにファイル フォルダーにドロップするダミーの要求メッセージを処理する FILE 受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="d62ff-103">In this topic, you configure a FILE receive location that consumes the dummy request message that you drop to a file folder to invoke the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d62ff-104">このチュートリアルの手順は、既定のアプリケーションを使用することを想定しています (**BizTalk アプリケーション 1**)、ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d62ff-104">The steps in this tutorial assume that you use the default application (**BizTalk Application 1**) to create the solution.</span></span> <span data-ttu-id="d62ff-105">別のアプリケーションを作成して、そのアプリケーションで同じステップを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="d62ff-105">You can also create another application and perform the same steps in any that application.</span></span>  
  
### <a name="to-configure-a-file-receive-location"></a><span data-ttu-id="d62ff-106">FILE 受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="d62ff-106">To configure a FILE receive location</span></span>  
  
1.  <span data-ttu-id="d62ff-107">BizTalk Server 管理コンソールから下にある、 **BizTalk アプリケーション 1**  ノードを右クリックして**受信ポート**、 をポイント**新規**、順にクリック**一方向受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="d62ff-107">From BizTalk Server Administration Console, under the **BizTalk Application 1** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="d62ff-108">[全般] タブには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d62ff-108">On the General tab, do the following:</span></span>  
  
    |<span data-ttu-id="d62ff-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d62ff-109">Use this</span></span>|<span data-ttu-id="d62ff-110">目的</span><span class="sxs-lookup"><span data-stu-id="d62ff-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d62ff-111">**名前**</span><span class="sxs-lookup"><span data-stu-id="d62ff-111">**Name**</span></span>|<span data-ttu-id="d62ff-112">型**ReceivePortRestAzureMarketPlace**です。</span><span class="sxs-lookup"><span data-stu-id="d62ff-112">Type **ReceivePortRestAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="d62ff-113">**失敗したメッセージのルーティングを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="d62ff-113">**Enable routing for failed messages**</span></span>|<span data-ttu-id="d62ff-114">(選択解除)</span><span class="sxs-lookup"><span data-stu-id="d62ff-114">(clear)</span></span>|  
  
3.  <span data-ttu-id="d62ff-115">をクリックして**受信場所**、クリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="d62ff-115">Click **Receive Locations**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="d62ff-116">[Receive Location1 - 受信場所のプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d62ff-116">From Receive Location1 – Receive Location Properties, do the following:</span></span>  
  
    |<span data-ttu-id="d62ff-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d62ff-117">Use this</span></span>|<span data-ttu-id="d62ff-118">目的</span><span class="sxs-lookup"><span data-stu-id="d62ff-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d62ff-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="d62ff-119">**Name**</span></span>|<span data-ttu-id="d62ff-120">型**ReceiveLocationAzureMarketPlace**です。</span><span class="sxs-lookup"><span data-stu-id="d62ff-120">Type **ReceiveLocationAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="d62ff-121">**型**</span><span class="sxs-lookup"><span data-stu-id="d62ff-121">**Type**</span></span>|<span data-ttu-id="d62ff-122">選択**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="d62ff-122">Select **FILE**.</span></span>|  
    |<span data-ttu-id="d62ff-123">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="d62ff-123">**Receive handler**</span></span>|<span data-ttu-id="d62ff-124">[ **BizTalkServerApplication**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d62ff-124">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="d62ff-125">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="d62ff-125">**Receive pipeline**</span></span>|<span data-ttu-id="d62ff-126">選択**PassThruReceive**です。</span><span class="sxs-lookup"><span data-stu-id="d62ff-126">Select **PassThruReceive**.</span></span>|  
  
5.  <span data-ttu-id="d62ff-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="d62ff-127">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="d62ff-128">[FILE トランスポートのプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d62ff-128">From File Transport Properties, do the following:</span></span>  
  
    |<span data-ttu-id="d62ff-129">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d62ff-129">Use this</span></span>|<span data-ttu-id="d62ff-130">目的</span><span class="sxs-lookup"><span data-stu-id="d62ff-130">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d62ff-131">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="d62ff-131">**Receive folder**</span></span>|<span data-ttu-id="d62ff-132">ダミーの要求メッセージをドロップする場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="d62ff-132">Type a location where you will drop the dummy request message.</span></span>|  
    |<span data-ttu-id="d62ff-133">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="d62ff-133">**File name**</span></span>|<span data-ttu-id="d62ff-134">保持します。`*.xml`</span><span class="sxs-lookup"><span data-stu-id="d62ff-134">Retain `*.xml`</span></span>|  
  
7.  <span data-ttu-id="d62ff-135">をクリックして**OK**すべてのダイアログ ボックスを終了するまでです。</span><span class="sxs-lookup"><span data-stu-id="d62ff-135">Click **OK** until you exit all the dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d62ff-136">参照</span><span class="sxs-lookup"><span data-stu-id="d62ff-136">See Also</span></span>  
 [<span data-ttu-id="d62ff-137">チュートリアル 5: BizTalk Server を使用して REST インターフェイスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="d62ff-137">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)