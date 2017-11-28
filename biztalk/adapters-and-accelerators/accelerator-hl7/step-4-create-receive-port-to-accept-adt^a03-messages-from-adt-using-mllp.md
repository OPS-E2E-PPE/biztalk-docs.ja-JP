---
title: "手順 4: 作成、ADT を受け入れるための受信ポート ^ MLLP アダプターを使用して ADT システムから A03 メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports
- end-to-end tutorial, receive ports
- creating, receive ports
ms.assetid: 3c4192d5-d011-48b0-a3f9-47c5225780ee
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 865675e12609beea4c909d19a74d3e0ec4f38715
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-the-receive-port-for-accepting-adta03-messages-from-adt-systems-using-the-mllp-adapter"></a><span data-ttu-id="2367b-102">手順 4: 作成、ADT を受け入れるための受信ポート ^ MLLP アダプターを使用して ADT システムから A03 メッセージ</span><span class="sxs-lookup"><span data-stu-id="2367b-102">Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter</span></span>
<span data-ttu-id="2367b-103">受信ポートを使用して、受信メッセージの受信場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="2367b-103">You use the receive port to specify the receive location for incoming messages.</span></span> <span data-ttu-id="2367b-104">ADT を受け付ける受信ポートを作成する次の手順に従います ^ MLLP アダプターを使用して、ADT システムから A03 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2367b-104">Use the following procedure to create the receive port for accepting ADT^A03 messages from the ADT System using the MLLP adapter.</span></span>  
  
## <a name="create-the-receive-port"></a><span data-ttu-id="2367b-105">受信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="2367b-105">Create the receive port</span></span>  
  
1.  <span data-ttu-id="2367b-106">開いている**BizTalk Server 管理コンソール**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開し、 **BizTalk アプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-106">Open **BizTalk Server Administration**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2367b-107">BizTalk Server 管理コンソール開くこともできますから Visual Studio 内をクリックして**BizTalk Server 管理コンソール**で、**ツール**メニュー。</span><span class="sxs-lookup"><span data-stu-id="2367b-107">The BizTalk Server Administration Console can also be opened from within Visual Studio by clicking **BizTalk Server Administration** in the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="2367b-108">右クリック**受信ポート****新規**、し、**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-108">Right-click **Receive Ports**, select **New**, and then select **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="2367b-109">**名前**、入力**Tutorial_1WayReceive**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-109">For the **Name**, enter **Tutorial_1WayReceive**.</span></span>  
  
4.  <span data-ttu-id="2367b-110">選択**適用**、ポートをバインドし、選択**受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-110">Select **Apply** to bind the port, and then select **Receive Locations**.</span></span>  
  
5.  <span data-ttu-id="2367b-111">選択**新しい**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-111">Select **New**.</span></span>  
  
6.  <span data-ttu-id="2367b-112">**名前**、入力**Tutorial_MLLPReceive**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-112">For the **Name**, enter **Tutorial_MLLPReceive**.</span></span>  
  
7. <span data-ttu-id="2367b-113">**トランスポート**セクションで、**型**、し、 **MLLP**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="2367b-113">In the **Transport** section, select **Type**, and then select **MLLP** from the drop-down list.</span></span>  
  
8. <span data-ttu-id="2367b-114">**[構成]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2367b-114">Select **Configure**.</span></span> <span data-ttu-id="2367b-115">**MLLP トランスポートのプロパティ**、次を構成し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-115">In **MLLP Transport Properties**, configure the following, and then select **OK**.</span></span>  
  
    |<span data-ttu-id="2367b-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2367b-116">Use this</span></span>|<span data-ttu-id="2367b-117">目的</span><span class="sxs-lookup"><span data-stu-id="2367b-117">To do this</span></span>|  
    |---|---|  
    |<span data-ttu-id="2367b-118">**接続再試行時間 (秒)**</span><span class="sxs-lookup"><span data-stu-id="2367b-118">**Connect retry time (sec)**</span></span>|<span data-ttu-id="2367b-119">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2367b-119">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="2367b-120">削除済みまたは閉じている接続の再接続を試行する前に待機する時間の上限。</span><span class="sxs-lookup"><span data-stu-id="2367b-120">The upper limit of time to wait before attempting to reconnect a dropped or closed connection.</span></span> <span data-ttu-id="2367b-121">場合に適用**によって接続が開始される**に設定されている**ローカル**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-121">Applicable when **Connection Initiated by** is set to **Local**.</span></span><br/><br/><span data-ttu-id="2367b-122">既定値は、20 秒です。</span><span class="sxs-lookup"><span data-stu-id="2367b-122">Default is 20 seconds.</span></span>|
    |<span data-ttu-id="2367b-123">**によって開始される接続**</span><span class="sxs-lookup"><span data-stu-id="2367b-123">**Connection initiated by**</span></span>| <span data-ttu-id="2367b-124">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2367b-124">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="2367b-125">入力**ローカル**MLLP の受信場所をリモートの LOB サーバーへの接続を開始します。</span><span class="sxs-lookup"><span data-stu-id="2367b-125">Enter **Local** for the MLLP receive location to initiate the connection to a remote LOB server.</span></span> <span data-ttu-id="2367b-126">これは、新しいオプションです。</span><span class="sxs-lookup"><span data-stu-id="2367b-126">This is the new option.</span></span><br/><br/><span data-ttu-id="2367b-127">入力**リモート**MLLP の受信場所で、リモートの LOB サーバーからの接続をリッスンするように続行します。</span><span class="sxs-lookup"><span data-stu-id="2367b-127">Enter **Remote** for the MLLP receive location to continue to listen for a connection from the remote LOB server.</span></span> <span data-ttu-id="2367b-128">これは、下位互換性のある既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="2367b-128">This is the backwards-compatible default option.</span></span><br/><br/><span data-ttu-id="2367b-129">既定値は Remote です。</span><span class="sxs-lookup"><span data-stu-id="2367b-129">Default is Remote.</span></span>| 
    |<span data-ttu-id="2367b-130">**接続名**</span><span class="sxs-lookup"><span data-stu-id="2367b-130">**Connection Name**</span></span>|<span data-ttu-id="2367b-131">入力**1Way**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-131">Enter **1Way**.</span></span>|  
    |<span data-ttu-id="2367b-132">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="2367b-132">**Host name**</span></span>|<span data-ttu-id="2367b-133">特定[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。</span><span class="sxs-lookup"><span data-stu-id="2367b-133">Specific to [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] and older versions.</span></span> <br/><br/><span data-ttu-id="2367b-134">入力**localhost**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-134">Enter **localhost**.</span></span>|  
    |<span data-ttu-id="2367b-135">**ローカルのホスト名**</span><span class="sxs-lookup"><span data-stu-id="2367b-135">**Local Host name**</span></span>|<span data-ttu-id="2367b-136">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2367b-136">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="2367b-137">DNS 名またはローカルの IP アドレスを入力[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2367b-137">Enter the DNS name or IP address of the local [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="2367b-138">入力することも**localhost**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-138">You can also enter **localhost**.</span></span>|  
    |<span data-ttu-id="2367b-139">**[ポート]**</span><span class="sxs-lookup"><span data-stu-id="2367b-139">**Port**</span></span>|<span data-ttu-id="2367b-140">特定[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。</span><span class="sxs-lookup"><span data-stu-id="2367b-140">Specific to [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] and older versions.</span></span> <br/><br/><span data-ttu-id="2367b-141">既定値は**11000**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-141">Default is **11000**.</span></span>|  
    |<span data-ttu-id="2367b-142">**ローカル ポート**</span><span class="sxs-lookup"><span data-stu-id="2367b-142">**Local Port**</span></span>|<span data-ttu-id="2367b-143">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2367b-143">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="2367b-144">LocalHost 接続の TCP ポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="2367b-144">Enter the TCP port number for the LocalHost connection.</span></span> <span data-ttu-id="2367b-145">場合にのみ適用**によって接続が開始される**は**リモート**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-145">Applicable only when **Connection Initiated by** is **Remote**.</span></span> <br/><br/><span data-ttu-id="2367b-146">既定値は**11000**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-146">Default is **11000**.</span></span>|
    |<span data-ttu-id="2367b-147">**リモート ホスト**</span><span class="sxs-lookup"><span data-stu-id="2367b-147">**Remote Host**</span></span>|<span data-ttu-id="2367b-148">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2367b-148">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="2367b-149">DNS 名またはリモートの LOB サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2367b-149">Enter the DNS name or IP address of the remote LOB server.</span></span> <span data-ttu-id="2367b-150">場合に適用**によって接続が開始される**に設定されている**ローカル**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-150">Applicable when **Connection Initiated by** is set to **Local**.</span></span>|  
    |<span data-ttu-id="2367b-151">**リモートのポート**</span><span class="sxs-lookup"><span data-stu-id="2367b-151">**Remote Port**</span></span>|<span data-ttu-id="2367b-152">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2367b-152">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="2367b-153">リモート ホスト接続への TCP ポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="2367b-153">Enter the TCP port number for the remote host connection.</span></span> <span data-ttu-id="2367b-154">場合に適用**によって接続が開始される**に設定されている**ローカル**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-154">Applicable when **Connection Initiated by** is set to **Local**.</span></span>|  

9. <span data-ttu-id="2367b-155">設定、**受信ハンドラー**に**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-155">Set the **Receive Handler** to **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="2367b-156">設定、**受信パイプライン**に**BTAHL72XPipelines.BTAHL72XReceivePipeline**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-156">Set the **Receive Pipeline** to **BTAHL72XPipelines.BTAHL72XReceivePipeline**.</span></span>  
  
11. <span data-ttu-id="2367b-157">**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="2367b-157">Select **OK** to save your changes.</span></span>  
  
12. <span data-ttu-id="2367b-158">右クリックして、作成した受信場所を有効にし、**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="2367b-158">Enable the receive location you just created by right-clicking it, and then select **Enable**.</span></span>  

## <a name="next-step"></a><span data-ttu-id="2367b-159">次の手順</span><span class="sxs-lookup"><span data-stu-id="2367b-159">Next step</span></span>  
[<span data-ttu-id="2367b-160">手順 5: ファイル アダプタを使用して、ADT システムに受信確認を配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="2367b-160">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)