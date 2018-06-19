---
title: 受信ハンドラーを MQSeries アダプターの送信を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, MQSeries adapters
- configuring [MQSeries adapters], receive handlers
- MQSeries adapters, send handlers
- MQSeries adapters, receive handlers
- send handlers, MQSeries adapters
- configuring [MQSeries adapters], send handlers
ms.assetid: e1cfc415-50d2-440b-9301-ad69da28ad3e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a1e933f62adaf4e17fae5334e65f50610fb6f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248234"
---
# <a name="how-to-configure-mqseries-adapter-send-and-receive-handlers"></a><span data-ttu-id="a45ac-102">MQSeries アダプターを構成する方法は、送信し、受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="a45ac-102">How to Configure MQSeries Adapter Send and Receive Handlers</span></span>
<span data-ttu-id="a45ac-103">MQSeries アダプターの送信ハンドラーと受信ハンドラーの一部のプロパティは、BizTalk Server 管理コンソールを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="a45ac-103">You can configure some properties for the send and receive handlers for the MQSeries adapter through the BizTalk Server Administration console.</span></span> <span data-ttu-id="a45ac-104">処理に示す[方法を構成する MQSeries アダプターの受信場所と送信ポートを](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)ほとんど送信ハンドラのプロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a45ac-104">The process described in [How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) establishes the values for the majority of send handler properties.</span></span>  
  
## <a name="to-configure-the-send-and-receive-handlers"></a><span data-ttu-id="a45ac-105">送信ハンドラーと受信ハンドラーを構成するには</span><span class="sxs-lookup"><span data-stu-id="a45ac-105">To configure the send and receive handlers</span></span>  
 <span data-ttu-id="a45ac-106">MSQeries アダプターの送信ハンドラーと受信ハンドラーを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a45ac-106">Follow these steps to configure send and receive handlers for the MSQeries adapter:</span></span>  
  
1.  <span data-ttu-id="a45ac-107">をクリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="a45ac-107">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a45ac-108">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**をクリックして展開**プラットフォームの設定**をクリックして展開**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="a45ac-108">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, click to expand **Platform Settings**, and then click to expand **Adapters**.</span></span>  
  
3.  <span data-ttu-id="a45ac-109">展開したアダプターの一覧で選択**MQSeries**です。</span><span class="sxs-lookup"><span data-stu-id="a45ac-109">In the expanded adapter list, select **MQSeries**.</span></span> <span data-ttu-id="a45ac-110">右ペインには、MQSeries アダプターにバインドされている送信ハンドラーと受信ハンドラーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a45ac-110">The list of send and receive handlers that are bound to the MQSeries adapter appear in the right pane.</span></span>  
  
4.  <span data-ttu-id="a45ac-111">右ペインで、送信ハンドラーまたは受信ハンドラーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a45ac-111">In the right pane, double-click a send or receive handler in the right pane.</span></span>  
  
5.  <span data-ttu-id="a45ac-112">**アダプター ハンドラーのプロパティ**ダイアログ ボックスで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="a45ac-112">In the **Adapter Handler Properties** dialog box, click **Properties**.</span></span>  
  
6.  <span data-ttu-id="a45ac-113">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="a45ac-113">In the **MQSeries Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a45ac-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a45ac-114">Use this</span></span>|<span data-ttu-id="a45ac-115">目的</span><span class="sxs-lookup"><span data-stu-id="a45ac-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a45ac-116">**バッチ内の最大メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="a45ac-116">**Maximum Messages in Batch**</span></span>|<span data-ttu-id="a45ac-117">バッチ内に含めるメッセージの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="a45ac-117">Set the maximum number of messages in a batch.</span></span> <span data-ttu-id="a45ac-118">送信ハンドラーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a45ac-118">Applies only to the send handler.</span></span>|  
    |<span data-ttu-id="a45ac-119">**[サーバー]**</span><span class="sxs-lookup"><span data-stu-id="a45ac-119">**Server**</span></span>|<span data-ttu-id="a45ac-120">MQSeries Server for Windows が実行されているコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a45ac-120">The name of the computer that is running MQSeries Server for Windows.</span></span>|  
  
7.  <span data-ttu-id="a45ac-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a45ac-121">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a45ac-122">受信場所のプロパティと送信ポートのプロパティは、受信ハンドラーの値と送信ハンドラーの値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="a45ac-122">The Receive Location and Send Port properties override the Receive Handler and Send Handler values.</span></span> <span data-ttu-id="a45ac-123">受信場所のプロパティまたは送信ポートのプロパティに値が設定されていない場合、アダプターでは、それぞれ受信ハンドラーの値と送信ハンドラーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a45ac-123">If there is no value for the Receive Location or Send Port properties, the adapter uses the Receive Handler and Send Handler values respectively.</span></span>  
  
8.  <span data-ttu-id="a45ac-124">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a45ac-124">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a45ac-125">参照</span><span class="sxs-lookup"><span data-stu-id="a45ac-125">See Also</span></span>  
 <span data-ttu-id="a45ac-126">[アダプター受信場所と送信ポートを MQSeries を構成する方法](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a45ac-126">[How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) </span></span>  
 [<span data-ttu-id="a45ac-127">MQSeries アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="a45ac-127">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)