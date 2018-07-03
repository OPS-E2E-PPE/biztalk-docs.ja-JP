---
title: 作成する方法、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.createreceiveport
helpviewer_keywords:
- receive ports, creating
- managing [receive ports], creating
- creating, receive ports
ms.assetid: 23fae441-be80-4759-b3d6-74787a40e65b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 194645d9f6f04db6d8005d4ea288a73271260252
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983107"
---
# <a name="how-to-create-a-receive-port"></a><span data-ttu-id="f0c97-102">受信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="f0c97-102">How to Create a Receive Port</span></span>
<span data-ttu-id="f0c97-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-103">This topic describes how to use the BizTalk Server Administration console to create a receive port.</span></span> <span data-ttu-id="f0c97-104">受信ポートとは、サービスがデータを受信する際に、外部パートナーとの対話に使用する一連の受信場所を、同様の特性に基づいて論理的にグループ化したものです。</span><span class="sxs-lookup"><span data-stu-id="f0c97-104">A receive port is a logical grouping of similar receive locations through which services interact with external partners by receiving data.</span></span>  

 <span data-ttu-id="f0c97-105">作成できる受信ポートの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0c97-105">You can create the following types of receive ports:</span></span>  

- <span data-ttu-id="f0c97-106">一方向 — メッセージを渡すだけで、応答を同期的に待機することの不要なアプリケーションに使用します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-106">One-way — used for applications that drop off a message and do not wait synchronously for a reply</span></span>  

- <span data-ttu-id="f0c97-107">要求 - 応答 — メッセージに対する応答が必要なアプリケーションに使用します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-107">Request-response — used with applications that require a response to a message</span></span>  

  <span data-ttu-id="f0c97-108">このトピックで説明されている構成、に加えて指定することも、受信ポートによって処理されるメッセージの追跡オプション」の説明に従って[受信ポートの追跡を構成する方法](../core/how-to-configure-tracking-for-a-receive-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-108">In addition to the configuration described in this topic, you can also specify tracking options for the messages handled by a receive port, as described in [How to Configure Tracking for a Receive Port](../core/how-to-configure-tracking-for-a-receive-port.md).</span></span>  

> [!NOTE]
>  <span data-ttu-id="f0c97-109">リモート コンピューターで受信ポートを作成していて、そのコンピューターではネットワーク DTC が有効になっていない場合は、受信ポートを作成した後で、リモート コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c97-109">If you are creating a receive port on a remote computer and that computer does not have network DTC enabled, you will have to reboot the remote computer after creating the receive port.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="f0c97-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="f0c97-110">Prerequisites</span></span>  
 <span data-ttu-id="f0c97-111">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c97-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f0c97-112">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  

### <a name="to-create-a-receive-port"></a><span data-ttu-id="f0c97-113">受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="f0c97-113">To create a receive port</span></span>  

1. <span data-ttu-id="f0c97-114">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f0c97-115">コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-115">In the console tree, expand the BizTalk group and the BizTalk application for which you want to create a receive port.</span></span>  

3. <span data-ttu-id="f0c97-116">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**または**要求-応答受信ポート**に基づいたポートの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-116">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port** or **Request Response Receive Port**, according to the type of port you want to create.</span></span>  

4. <span data-ttu-id="f0c97-117">**受信ポートのプロパティ**ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f0c97-117">In the **Receive Port Properties** window, do the following:</span></span>  


   |                 <span data-ttu-id="f0c97-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f0c97-118">Use this</span></span>                  |                                                                                                                                                                                                                            <span data-ttu-id="f0c97-119">目的</span><span class="sxs-lookup"><span data-stu-id="f0c97-119">To do this</span></span>                                                                                                                                                                                                                             |
   |-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                 <span data-ttu-id="f0c97-120">**名前**</span><span class="sxs-lookup"><span data-stu-id="f0c97-120">**Name**</span></span>                  |                                                                                                                                                                                                                    <span data-ttu-id="f0c97-121">ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-121">Type the name of the port.</span></span>                                                                                                                                                                                                                     |
   |           <span data-ttu-id="f0c97-122">**認証なし**</span><span class="sxs-lookup"><span data-stu-id="f0c97-122">**No authentication**</span></span>           |                                                                                                                                                                                                 <span data-ttu-id="f0c97-123">認証を無効にする場合は、このオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c97-123">Click this option to disable authentication.</span></span> <span data-ttu-id="f0c97-124">既定値です。</span><span class="sxs-lookup"><span data-stu-id="f0c97-124">This is the default.</span></span>                                                                                                                                                                                                 |
   | <span data-ttu-id="f0c97-125">**認証が失敗した場合は、メッセージを削除します。**</span><span class="sxs-lookup"><span data-stu-id="f0c97-125">**Drop messages if authentication fails**</span></span> |                                                                                                                                                                                         <span data-ttu-id="f0c97-126">認証されていないメッセージをドロップするが、認証を有効にするのには、このオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c97-126">Click this option to enable authentication but to drop unauthenticated messages.</span></span>                                                                                                                                                                                          |
   | <span data-ttu-id="f0c97-127">**認証が失敗した場合は、メッセージを保持します。**</span><span class="sxs-lookup"><span data-stu-id="f0c97-127">**Keep messages if authentication fails**</span></span> |                                                                                                                                                                                           <span data-ttu-id="f0c97-128">認証を有効にして、認証されていないメッセージを保持するには、このオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c97-128">Click this option to enable authentication and keep unauthenticated messages.</span></span>                                                                                                                                                                                           |
   |  <span data-ttu-id="f0c97-129">**失敗したメッセージのルーティングを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="f0c97-129">**Enable routing for failed messages**</span></span>   | <span data-ttu-id="f0c97-130">処理に失敗したメッセージを、他の送信ポートやオーケストレーション スケジュールなど、メッセージをサブスクライブするアプリケーションに回送するよう試行する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f0c97-130">Select this check box to attempt to route any message that fails processing to a subscribing application (such as another receive port or orchestration schedule).</span></span> <span data-ttu-id="f0c97-131">失敗したメッセージを保留し、否定の確認 (NACK) を生成する場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f0c97-131">Clear the check box to suspend failed messages and generate a negative acknowledgment (NACK).</span></span> <span data-ttu-id="f0c97-132">既定値はオフです。</span><span class="sxs-lookup"><span data-stu-id="f0c97-132">The default value is cleared.</span></span> <span data-ttu-id="f0c97-133">詳細については、次を参照してください。[受信ポートの失敗したメッセージのルーティングを有効にする方法](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-133">For more information, see [How to Enable Routing for Failed Messages for a Receive Port](../core/how-to-enable-routing-for-failed-messages-for-a-receive-port.md).</span></span> |


5. <span data-ttu-id="f0c97-134">左側のウィンドウで次のようにクリックします。**受信場所**、新しいを作成してこの受信ポートの受信場所は。</span><span class="sxs-lookup"><span data-stu-id="f0c97-134">In the left pane, click **Receive Locations**, and create a new receive location for this receive port.</span></span> <span data-ttu-id="f0c97-135">手順については、次を参照してください。[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-135">For instructions, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  

6. <span data-ttu-id="f0c97-136">左側のウィンドウで次のようにクリックします。**受信マップ**、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f0c97-136">In the left pane, click **Inbound Maps**, and do the following:</span></span>  


   |      <span data-ttu-id="f0c97-137">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f0c97-137">Use this</span></span>       |                                  <span data-ttu-id="f0c97-138">目的</span><span class="sxs-lookup"><span data-stu-id="f0c97-138">To do this</span></span>                                   |
   |---------------------|-------------------------------------------------------------------------------|
   | <span data-ttu-id="f0c97-139">**ソース ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="f0c97-139">**Source Document**</span></span> |   <span data-ttu-id="f0c97-140">ドロップダウン リストから、このポートで使用する送信元スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-140">From the drop-down list, select the source schema to use with this port.</span></span>    |
   |       <span data-ttu-id="f0c97-141">**マップ**</span><span class="sxs-lookup"><span data-stu-id="f0c97-141">**Map**</span></span>       | <span data-ttu-id="f0c97-142">ドロップダウン リストから、このポートに関連付けるマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-142">From the drop-down list, select the map you want to associate with this port.</span></span> |
   | <span data-ttu-id="f0c97-143">**送信先ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="f0c97-143">**Target Document**</span></span> | <span data-ttu-id="f0c97-144">ドロップダウン リストから、このポートで使用する送信先スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-144">From the drop-down list, select the destination schema to use with this port.</span></span> |


7. <span data-ttu-id="f0c97-145">作成する場合、要求-応答が受信ポートは、左側のウィンドウで、をクリックして**送信マップ**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f0c97-145">If you are creating a request-response receive port, then in the left pane, click **Outbound Maps**, and do the following:</span></span>  


   |      <span data-ttu-id="f0c97-146">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f0c97-146">Use this</span></span>       |                                  <span data-ttu-id="f0c97-147">目的</span><span class="sxs-lookup"><span data-stu-id="f0c97-147">To do this</span></span>                                   |
   |---------------------|-------------------------------------------------------------------------------|
   | <span data-ttu-id="f0c97-148">**ソース ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="f0c97-148">**Source Document**</span></span> |   <span data-ttu-id="f0c97-149">ドロップダウン リストから、このポートで使用する送信元スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-149">From the drop-down list, select the source schema to use with this port.</span></span>    |
   |       <span data-ttu-id="f0c97-150">**マップ**</span><span class="sxs-lookup"><span data-stu-id="f0c97-150">**Map**</span></span>       | <span data-ttu-id="f0c97-151">ドロップダウン リストから、このポートに関連付けるマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-151">From the drop-down list, select the map you want to associate with this port.</span></span> |
   | <span data-ttu-id="f0c97-152">**送信先ドキュメント**</span><span class="sxs-lookup"><span data-stu-id="f0c97-152">**Target Document**</span></span> | <span data-ttu-id="f0c97-153">ドロップダウン リストから、このポートで使用する送信先スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-153">From the drop-down list, select the destination schema to use with this port.</span></span> |


8. <span data-ttu-id="f0c97-154">受信ポートを構成したら、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f0c97-154">When finished configuring the receive port, click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f0c97-155">参照</span><span class="sxs-lookup"><span data-stu-id="f0c97-155">See Also</span></span>  
 [<span data-ttu-id="f0c97-156">受信ポートの管理</span><span class="sxs-lookup"><span data-stu-id="f0c97-156">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)