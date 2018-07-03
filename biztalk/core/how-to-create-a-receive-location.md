---
title: 作成する方法、受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.createreceivelocation
helpviewer_keywords:
- receive locations, creating
- managing [receive locations], creating
- creating, receive locations
ms.assetid: ec0202cf-0e69-4ae2-aba6-8cd2c3c77e82
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e13968abd25f0f7bf85743122688e44a8f2bb25f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003723"
---
# <a name="how-to-create-a-receive-location"></a><span data-ttu-id="f3657-102">受信場所を作成する方法</span><span class="sxs-lookup"><span data-stu-id="f3657-102">How to Create a Receive Location</span></span>
<span data-ttu-id="f3657-103">このトピックでは、BizTalk Server 管理コンソールを使用して、新しい受信場所を作成し、その受信場所が属する受信ポートを指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3657-103">This topic describes how to use the BizTalk Server Administration console to create a new receive location and specify the receive port to which it belongs.</span></span> <span data-ttu-id="f3657-104">受信場所は、受信メッセージを受信するアドレスと、そのアドレスで受信したメッセージを処理するメッセージング パイプラインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f3657-104">A receive location is an address where inbound messages arrive as well as the messaging pipeline that processes messages received at that address.</span></span>  
  
 <span data-ttu-id="f3657-105">受信場所を作成するには、作成する受信場所と同じ種類の受信ポートがこのアプリケーションに既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3657-105">Before you can create a receive location, a receive port must already exist in this application that of the same type as the receive location you want to create.</span></span> <span data-ttu-id="f3657-106">受信ポートを作成する方法の詳細については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="f3657-106">For instructions on creating a receive port, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span>  
  
 <span data-ttu-id="f3657-107">作成できる受信場所の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f3657-107">You can create the following types of receive locations:</span></span>  
  
-   <span data-ttu-id="f3657-108">一方向 — メッセージを渡すだけで、応答を同期的に待機することの不要なアプリケーションに使用します。</span><span class="sxs-lookup"><span data-stu-id="f3657-108">One-way — used for applications that drop off a message and do not wait synchronously for a reply</span></span>  
  
-   <span data-ttu-id="f3657-109">要求 - 応答 — メッセージに対する応答が必要なアプリケーションに使用します。</span><span class="sxs-lookup"><span data-stu-id="f3657-109">Request-response — used with applications that require a response to a message</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3657-110">アプリケーション開発者が開発プロセス中に受信場所を作成するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f3657-110">The application developer can create a receive location during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f3657-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="f3657-111">Prerequisites</span></span>  
 <span data-ttu-id="f3657-112">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3657-112">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f3657-113">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="f3657-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span> <span data-ttu-id="f3657-114">さらに、SSO データベースに対する適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f3657-114">In addition, you need to have appropriate permissions on the SSO database.</span></span>  
  
### <a name="to-create-a-receive-location"></a><span data-ttu-id="f3657-115">受信場所を作成するには</span><span class="sxs-lookup"><span data-stu-id="f3657-115">To create a receive location</span></span>  
  
1. <span data-ttu-id="f3657-116">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f3657-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f3657-117">コンソール ツリーで、BizTalk グループを展開し、受信場所を作成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="f3657-117">In the console tree, expand the BizTalk group and the BizTalk application for which you want to create a receive location.</span></span>  
  
3. <span data-ttu-id="f3657-118">右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**または**要求応答の受信場所**に基づいたの種類を作成する場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="f3657-118">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location** or **Request Response Receive Location**, according to the type of receive location to create.</span></span>  
  
4. <span data-ttu-id="f3657-119">受信ポートの選択] では、この受信場所が含まれてし、[受信ポートをクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="f3657-119">In the Select a Receive Port window, click the receive port that will contain this receive location, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="f3657-120">**受信場所のプロパティ**ウィンドウで、次の操作をクリックして**OK**:</span><span class="sxs-lookup"><span data-stu-id="f3657-120">In the **Receive Location Properties** window, do the following, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="f3657-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f3657-121">Use this</span></span>|<span data-ttu-id="f3657-122">目的</span><span class="sxs-lookup"><span data-stu-id="f3657-122">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="f3657-123">**名前**</span><span class="sxs-lookup"><span data-stu-id="f3657-123">**Name**</span></span>|<span data-ttu-id="f3657-124">受信場所の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f3657-124">Type the name of the receive location.</span></span>|  
   |<span data-ttu-id="f3657-125">**型**</span><span class="sxs-lookup"><span data-stu-id="f3657-125">**Type**</span></span>|<span data-ttu-id="f3657-126">ドロップダウン リストから、トランスポートの種類またはトランスポート プロトコルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f3657-126">From the drop-down list, select the transport type, or transport protocol.</span></span> <span data-ttu-id="f3657-127">トランスポートの種類を変更する場合、次に説明するように、トランスポートのプロパティを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3657-127">If you change the transport type, you must configure transport properties, as described next.</span></span>|  
   |<span data-ttu-id="f3657-128">**構成**</span><span class="sxs-lookup"><span data-stu-id="f3657-128">**Configure**</span></span>|<span data-ttu-id="f3657-129">トランスポートの種類を選択してクリックして**構成**を表示する、**トランスポートのプロパティ** ダイアログ ボックスし、受信場所のアダプター プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="f3657-129">After you select the transport type, click **Configure** to display the **Transport Properties** dialog box and configure adapter properties for the receive location.</span></span> <span data-ttu-id="f3657-130">手順については、次のようにクリックします。**ヘルプ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="f3657-130">For instructions, click **Help** in the dialog box.</span></span> <span data-ttu-id="f3657-131">アダプターの種類ごとの構成の詳細については、該当するトピックを参照してください。[を使用してアダプター](../core/using-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="f3657-131">For details on configuring each type of adapter, see the appropriate topic under [Using Adapters](../core/using-adapters.md).</span></span>|  
   |<span data-ttu-id="f3657-132">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="f3657-132">**Receive handler**</span></span>|<span data-ttu-id="f3657-133">ドロップダウン リストから、受信場所が動作する BizTalk Server ホストのインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f3657-133">From the drop-down list, select the instance of the BizTalk Server host on which the receive location will run.</span></span> <span data-ttu-id="f3657-134">受信ハンドラーは、このホストで実行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3657-134">The receive handler must be running on this host.</span></span>|  
   |<span data-ttu-id="f3657-135">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="f3657-135">**Receive pipeline**</span></span>|<span data-ttu-id="f3657-136">ドロップダウン リストから、この受信場所でのメッセージの受信に使用する受信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="f3657-136">From the drop-down list, select the receive pipeline to use to receive messages at this receive location.</span></span>|  
   |<span data-ttu-id="f3657-137">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="f3657-137">**Send pipeline**</span></span>|<span data-ttu-id="f3657-138">ドロップダウン リストから、この受信場所からの応答の送信に使用する送信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="f3657-138">From the drop-down list, select the send pipeline to use to send responses from this receive location.</span></span> <span data-ttu-id="f3657-139">この一覧は、受信場所が要求 - 応答の受信ポートに関連付けられている場合にのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="f3657-139">This list is available only for a receive location associated with a request-response receive port.</span></span>|  
   |<span data-ttu-id="f3657-140">**プライマリの場所を確認します。**</span><span class="sxs-lookup"><span data-stu-id="f3657-140">**Make this the primary location**</span></span>|<span data-ttu-id="f3657-141">1 つの受信ポートに対して複数の受信場所があり、この受信ポートで取引先など別のエンティティから自分の組織宛てのメッセージを受け取るときにこの受信場所を使用する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f3657-141">Select this check box if you have more than one receive location for a receive port and you want this receive location to represent the receive port when the port needs to be passed to another entity, such as a business partner, that needs to send messages to your organization.</span></span> <span data-ttu-id="f3657-142">最初に作成した受信場所は、自動的にプライマリ受信場所として選択されます。</span><span class="sxs-lookup"><span data-stu-id="f3657-142">The first receive location created is automatically selected as the primary receive location.</span></span> <span data-ttu-id="f3657-143">別の受信場所をプライマリとして指定しない限り、このプロパティは選択された状態で使用不可となります。</span><span class="sxs-lookup"><span data-stu-id="f3657-143">This property remains selected and unavailable until you designate a different receive location as the primary.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3657-144">参照</span><span class="sxs-lookup"><span data-stu-id="f3657-144">See Also</span></span>  
 [<span data-ttu-id="f3657-145">受信場所の管理</span><span class="sxs-lookup"><span data-stu-id="f3657-145">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)