---
title: プロパティを編集する方法、受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], properties
- managing [receive locations], editing
- receive locations, properties
- receive locations, editing
- editing, receive locations
- editing, properties
ms.assetid: 2b622050-a875-4896-bed6-65ca39a26dd3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bace802ee40c98cd6ffee956c967d01fcdb7994
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985931"
---
# <a name="how-to-edit-the-properties-of-a-receive-location"></a><span data-ttu-id="0c0ab-102">受信場所のプロパティを編集する方法</span><span class="sxs-lookup"><span data-stu-id="0c0ab-102">How to Edit the Properties of a Receive Location</span></span>
<span data-ttu-id="0c0ab-103">このトピックでは、BizTalk Server 管理コンソールを使用して既存の受信場所のプロパティを編集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-103">This topic describes how to use the BizTalk Server Administration console to edit properties of an existing receive location.</span></span> <span data-ttu-id="0c0ab-104">受信場所の作成方法の詳細については、[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-104">For instructions on creating a receive location, see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0c0ab-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="0c0ab-105">Prerequisites</span></span>  
 <span data-ttu-id="0c0ab-106">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="0c0ab-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-edit-the-properties-of-a-receive-location"></a><span data-ttu-id="0c0ab-108">受信場所のプロパティを編集するには</span><span class="sxs-lookup"><span data-stu-id="0c0ab-108">To edit the properties of a receive location</span></span>  
  
1. <span data-ttu-id="0c0ab-109">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="0c0ab-110">コンソール ツリーで、BizTalk グループと受信場所のプロパティを編集し、をクリックし、BizTalk アプリケーション展開**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-110">In the console tree, expand the BizTalk group and the BizTalk application for which you want to edit the properties of a receive location and then click **Receive Locations**.</span></span>  
  
3. <span data-ttu-id="0c0ab-111">右側のウィンドウで、受信場所を右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-111">In the right pane, right-click the receive location, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="0c0ab-112">**受信場所のプロパティ**ウィンドウは、次のプロパティの 1 つ以上を編集し、クリックして**OK**:</span><span class="sxs-lookup"><span data-stu-id="0c0ab-112">In the **Receive Location Properties** window, edit one or more of the following properties, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="0c0ab-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c0ab-113">Use this</span></span>|<span data-ttu-id="0c0ab-114">目的</span><span class="sxs-lookup"><span data-stu-id="0c0ab-114">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="0c0ab-115">**名前**</span><span class="sxs-lookup"><span data-stu-id="0c0ab-115">**Name**</span></span>|<span data-ttu-id="0c0ab-116">受信場所の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-116">Type the name of the receive location.</span></span>|  
   |<span data-ttu-id="0c0ab-117">**型**</span><span class="sxs-lookup"><span data-stu-id="0c0ab-117">**Type**</span></span>|<span data-ttu-id="0c0ab-118">ドロップダウン リストから、トランスポートの種類またはトランスポート プロトコルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-118">From the drop-down list, select the transport type, or transport protocol.</span></span> <span data-ttu-id="0c0ab-119">トランスポートの種類を変更する場合、次に説明するように、トランスポートのプロパティを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-119">If you change the transport type, you must configure transport properties, as described next.</span></span>|  
   |<span data-ttu-id="0c0ab-120">**構成**</span><span class="sxs-lookup"><span data-stu-id="0c0ab-120">**Configure**</span></span>|<span data-ttu-id="0c0ab-121">トランスポートの種類を選択してクリックして**構成**を表示する、**トランスポートのプロパティ** ダイアログ ボックスし、受信場所のアダプター プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-121">After you select the transport type, click **Configure** to display the **Transport Properties** dialog box and configure adapter properties for the receive location.</span></span> <span data-ttu-id="0c0ab-122">手順については、次のようにクリックします。**ヘルプ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-122">For instructions, click **Help** in the dialog box.</span></span> <span data-ttu-id="0c0ab-123">アダプターの種類ごとの構成の詳細については、該当するトピックを参照してください。[を使用してアダプター](../core/using-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-123">For details on configuring each type of adapter, see the appropriate topic under [Using Adapters](../core/using-adapters.md).</span></span>|  
   |<span data-ttu-id="0c0ab-124">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="0c0ab-124">**Receive handler**</span></span>|<span data-ttu-id="0c0ab-125">ドロップダウン リストから、受信場所が動作する BizTalk Server ホストのインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-125">From the drop-down list, select the instance of the BizTalk Server host on which the receive location will run.</span></span> <span data-ttu-id="0c0ab-126">受信ハンドラーは、このホストで実行される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-126">The receive handler must be running on this host.</span></span>|  
   |<span data-ttu-id="0c0ab-127">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="0c0ab-127">**Receive pipeline**</span></span>|<span data-ttu-id="0c0ab-128">ドロップダウン リストから、この受信場所でのメッセージの受信に使用する受信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-128">From the drop-down list, select the receive pipeline to use to receive messages at this receive location.</span></span>|  
   |<span data-ttu-id="0c0ab-129">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="0c0ab-129">**Send pipeline**</span></span>|<span data-ttu-id="0c0ab-130">ドロップダウン リストから、この受信場所からの応答の送信に使用する送信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-130">From the drop-down list, select the send pipeline to use to send responses from this receive location.</span></span> <span data-ttu-id="0c0ab-131">この一覧は、受信場所が要求 - 応答の受信ポートに関連付けられている場合にのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-131">This list is available only for a receive location associated with a request-response receive port.</span></span>|  
   |<span data-ttu-id="0c0ab-132">**プライマリの場所を確認します。**</span><span class="sxs-lookup"><span data-stu-id="0c0ab-132">**Make this the primary location**</span></span>|<span data-ttu-id="0c0ab-133">1 つの受信ポートに対して複数の受信場所があり、この受信ポートで取引先など別のエンティティから自分の組織宛てのメッセージを受け取るときにこの受信場所を使用する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-133">Select this check box if you have more than one receive location for a receive port and you want this receive location to represent the receive port when the port needs to be passed to another entity, such as a business partner, that needs to send messages to your organization.</span></span> <span data-ttu-id="0c0ab-134">最初に作成した受信場所は、自動的にプライマリ受信場所として選択されます。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-134">The first receive location created is automatically selected as the primary receive location.</span></span> <span data-ttu-id="0c0ab-135">別の受信場所をプライマリとして指定しない限り、このプロパティは選択された状態で使用不可となります。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-135">This property remains selected and unavailable until you designate a different receive location as the primary.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="0c0ab-136">受信場所を変更した場合は、変更した受信場所に対応する分離ホストのワーカー プロセスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0c0ab-136">In case you change or modify Receive location, restart the Isolated Host Worker Processes corresponding to the modified receive location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0ab-137">参照</span><span class="sxs-lookup"><span data-stu-id="0c0ab-137">See Also</span></span>  
 [<span data-ttu-id="0c0ab-138">受信場所の管理</span><span class="sxs-lookup"><span data-stu-id="0c0ab-138">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)