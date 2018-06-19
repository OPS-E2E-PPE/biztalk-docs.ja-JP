---
title: '手順 5: 作成、彼のメッセージを受け入れるための受信ポート |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, receive ports
ms.assetid: c0b311d8-541c-4c21-a514-c93092c36fe2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0df326e3b08438f7a1eb7d3a2df3c5a816e79bc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207250"
---
# <a name="step-5-create-the-receive-port-for-accepting-his-messages"></a><span data-ttu-id="f037b-102">手順 5: 作成、彼のメッセージを受け入れるための受信ポート</span><span class="sxs-lookup"><span data-stu-id="f037b-102">Step 5: Create the Receive Port for Accepting HIS Messages</span></span>
<span data-ttu-id="f037b-103">この手順では、病院情報システム (HIS) によって送信される受信メッセージの場所を指定する受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f037b-103">In this step you create a receive port to specify the location for incoming messages sent by the Hospital Information System (HIS).</span></span> <span data-ttu-id="f037b-104">次の手順を使用すると、最小限の下位層プロトコル (MLLP) アダプターを使用して、ADT システムからクエリ応答メッセージを受け入れるため、受信ポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f037b-104">Use the following procedure to create the receive port for accepting query response messages from the ADT system using the Minimal Lower Layer Protocol (MLLP) adapter.</span></span>  
  
## <a name="create-the-hisreceiveport-receive-port"></a><span data-ttu-id="f037b-105">作成、HIS_ReceivePort 受信ポート</span><span class="sxs-lookup"><span data-stu-id="f037b-105">Create the HIS_ReceivePort receive port</span></span>  

1.  <span data-ttu-id="f037b-106">開いている**BizTalk Server 管理コンソール**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開し、 **BizTalk アプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-106">Open **BizTalk Server Administration**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="f037b-107">右クリック**受信ポート****新規**、し、**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-107">Right-click **Receive Ports**, select **New**, and then select **One-way Receive Port**.</span></span>   
  
3.  <span data-ttu-id="f037b-108">**名前**、入力**HIS_ReceivePort**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-108">For the **Name**, enter **HIS_ReceivePort**.</span></span>  

4.  <span data-ttu-id="f037b-109">選択**適用**、ポートをバインドし、選択**受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-109">Select **Apply** to bind the port, and then select **Receive Locations**.</span></span>  
  
5.  <span data-ttu-id="f037b-110">選択**新しい**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-110">Select **New**.</span></span>  
  
6.  <span data-ttu-id="f037b-111">**名前**、入力**HIS_Receive**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-111">For the **Name**, enter **HIS_Receive**.</span></span>  

7. <span data-ttu-id="f037b-112">**トランスポート**セクションで、**型**、し、 **MLLP**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="f037b-112">In the **Transport** section, select **Type**, and then select **MLLP** from the drop-down list.</span></span>  
  
8. <span data-ttu-id="f037b-113">**[構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f037b-113">Select **Configure**.</span></span> <span data-ttu-id="f037b-114">**MLLP トランスポートのプロパティ**、次を構成し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-114">In **MLLP Transport Properties**, configure the following, and then select **OK**.</span></span>  

    |<span data-ttu-id="f037b-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f037b-115">Use this</span></span>|<span data-ttu-id="f037b-116">目的</span><span class="sxs-lookup"><span data-stu-id="f037b-116">To do this</span></span>|  
    |---|---|  
    |<span data-ttu-id="f037b-117">**接続再試行時間 (秒)**</span><span class="sxs-lookup"><span data-stu-id="f037b-117">**Connect retry time (sec)**</span></span>|<span data-ttu-id="f037b-118">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f037b-118">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="f037b-119">削除済みまたは閉じている接続の再接続を試行する前に待機する時間の上限。</span><span class="sxs-lookup"><span data-stu-id="f037b-119">The upper limit of time to wait before attempting to reconnect a dropped or closed connection.</span></span> <span data-ttu-id="f037b-120">場合に適用**によって接続が開始される**に設定されている**ローカル**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-120">Applicable when **Connection Initiated by** is set to **Local**.</span></span><br/><br/><span data-ttu-id="f037b-121">既定値は、20 秒です。</span><span class="sxs-lookup"><span data-stu-id="f037b-121">Default is 20 seconds.</span></span>|
    |<span data-ttu-id="f037b-122">**によって開始される接続**</span><span class="sxs-lookup"><span data-stu-id="f037b-122">**Connection initiated by**</span></span>| <span data-ttu-id="f037b-123">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f037b-123">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="f037b-124">入力**ローカル**MLLP の受信場所をリモートの LOB サーバーへの接続を開始します。</span><span class="sxs-lookup"><span data-stu-id="f037b-124">Enter **Local** for the MLLP receive location to initiate the connection to a remote LOB server.</span></span> <span data-ttu-id="f037b-125">これは、新しいオプションです。</span><span class="sxs-lookup"><span data-stu-id="f037b-125">This is the new option.</span></span><br/><br/><span data-ttu-id="f037b-126">入力**リモート**MLLP の受信場所で、リモートの LOB サーバーからの接続をリッスンするように続行します。</span><span class="sxs-lookup"><span data-stu-id="f037b-126">Enter **Remote** for the MLLP receive location to continue to listen for a connection from the remote LOB server.</span></span> <span data-ttu-id="f037b-127">これは、下位互換性のある既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="f037b-127">This is the backwards-compatible default option.</span></span><br/><br/><span data-ttu-id="f037b-128">既定値は Remote です。</span><span class="sxs-lookup"><span data-stu-id="f037b-128">Default is Remote.</span></span>| 
    |<span data-ttu-id="f037b-129">**接続名**</span><span class="sxs-lookup"><span data-stu-id="f037b-129">**Connection Name**</span></span>|<span data-ttu-id="f037b-130">入力**HIS_ReceiveMLLP**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-130">Enter **HIS_ReceiveMLLP**.</span></span>|  
    |<span data-ttu-id="f037b-131">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="f037b-131">**Host name**</span></span>|<span data-ttu-id="f037b-132">特定[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。</span><span class="sxs-lookup"><span data-stu-id="f037b-132">Specific to [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] and older versions.</span></span> <br/><br/><span data-ttu-id="f037b-133">入力**localhost**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-133">Enter **localhost**.</span></span>|  
    |<span data-ttu-id="f037b-134">**ローカルのホスト名**</span><span class="sxs-lookup"><span data-stu-id="f037b-134">**Local Host name**</span></span>|<span data-ttu-id="f037b-135">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f037b-135">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="f037b-136">DNS 名またはローカルの IP アドレスを入力[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f037b-136">Enter the DNS name or IP address of the local [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f037b-137">入力することも**localhost**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-137">You can also enter **localhost**.</span></span>|  
    |<span data-ttu-id="f037b-138">**[ポート]**</span><span class="sxs-lookup"><span data-stu-id="f037b-138">**Port**</span></span>|<span data-ttu-id="f037b-139">特定[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。</span><span class="sxs-lookup"><span data-stu-id="f037b-139">Specific to [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] and older versions.</span></span> <br/><br/><span data-ttu-id="f037b-140">設定**23000**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-140">Set to **23000**.</span></span>|  
    |<span data-ttu-id="f037b-141">**ローカル ポート**</span><span class="sxs-lookup"><span data-stu-id="f037b-141">**Local Port**</span></span>|<span data-ttu-id="f037b-142">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f037b-142">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="f037b-143">LocalHost 接続の TCP ポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="f037b-143">Enter the TCP port number for the LocalHost connection.</span></span> <span data-ttu-id="f037b-144">場合にのみ適用**によって接続が開始される**は**リモート**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-144">Applicable only when **Connection Initiated by** is **Remote**.</span></span> <br/><br/><span data-ttu-id="f037b-145">設定**23000**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-145">Set to **23000**.</span></span>|
    |<span data-ttu-id="f037b-146">**リモート ホスト**</span><span class="sxs-lookup"><span data-stu-id="f037b-146">**Remote Host**</span></span>|<span data-ttu-id="f037b-147">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f037b-147">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="f037b-148">DNS 名またはリモートの LOB サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f037b-148">Enter the DNS name or IP address of the remote LOB server.</span></span> <span data-ttu-id="f037b-149">場合に適用**によって接続が開始される**に設定されている**ローカル**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-149">Applicable when **Connection Initiated by** is set to **Local**.</span></span>|  
    |<span data-ttu-id="f037b-150">**リモートのポート**</span><span class="sxs-lookup"><span data-stu-id="f037b-150">**Remote Port**</span></span>|<span data-ttu-id="f037b-151">始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f037b-151">New starting with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span> <br/><br/><span data-ttu-id="f037b-152">リモート ホスト接続への TCP ポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="f037b-152">Enter the TCP port number for the remote host connection.</span></span> <span data-ttu-id="f037b-153">場合に適用**によって接続が開始される**に設定されている**ローカル**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-153">Applicable when **Connection Initiated by** is set to **Local**.</span></span><br/><br/><span data-ttu-id="f037b-154">設定**23000**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-154">Set to **23000**.</span></span>|  
    
9. <span data-ttu-id="f037b-155">設定、**受信ハンドラー**に**BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-155">Set the **Receive Handler** to **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="f037b-156">設定、**受信パイプライン**に**BTAHL72XPipelines.BTAHL72XReceivePipeline**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-156">Set the **Receive Pipeline** to **BTAHL72XPipelines.BTAHL72XReceivePipeline**.</span></span>  
  
11. <span data-ttu-id="f037b-157">**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="f037b-157">Select **OK** to save your changes.</span></span>  
  
12. <span data-ttu-id="f037b-158">右クリックして、作成した受信場所を有効にし、**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="f037b-158">Enable the receive location you just created by right-clicking it, and then select **Enable**.</span></span>  

## <a name="next-step"></a><span data-ttu-id="f037b-159">次の手順</span><span class="sxs-lookup"><span data-stu-id="f037b-159">Next step</span></span>  
[<span data-ttu-id="f037b-160">手順 6: クエリ メッセージを配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f037b-160">Step 6: Create a Send Port to Deliver Query Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)