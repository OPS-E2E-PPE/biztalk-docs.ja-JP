---
title: MQSeries アダプターの送信を構成し、ハンドラーを受信する方法 |Microsoft Docs
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
ms.openlocfilehash: 88c97b109146dadd1a5cc90710f00c9c8f6620f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988899"
---
# <a name="how-to-configure-mqseries-adapter-send-and-receive-handlers"></a><span data-ttu-id="bf3c6-102">MQSeries アダプターを構成する方法は、送信し、受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="bf3c6-102">How to Configure MQSeries Adapter Send and Receive Handlers</span></span>
<span data-ttu-id="bf3c6-103">MQSeries アダプターの送信ハンドラーと受信ハンドラーの一部のプロパティは、BizTalk Server 管理コンソールを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-103">You can configure some properties for the send and receive handlers for the MQSeries adapter through the BizTalk Server Administration console.</span></span> <span data-ttu-id="bf3c6-104">プロセスが記載[MQSeries アダプター受信場所の構成、送信ポートを](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)大部分の送信ハンドラのプロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-104">The process described in [How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) establishes the values for the majority of send handler properties.</span></span>  

## <a name="to-configure-the-send-and-receive-handlers"></a><span data-ttu-id="bf3c6-105">送信ハンドラーと受信ハンドラーを構成するには</span><span class="sxs-lookup"><span data-stu-id="bf3c6-105">To configure the send and receive handlers</span></span>  
 <span data-ttu-id="bf3c6-106">MSQeries アダプターの送信ハンドラーと受信ハンドラーを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-106">Follow these steps to configure send and receive handlers for the MSQeries adapter:</span></span>  

1. <span data-ttu-id="bf3c6-107">クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-107">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="bf3c6-108">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**をクリックして展開**プラットフォームの設定**を順にクリックします。展開**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-108">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, click to expand **Platform Settings**, and then click to expand **Adapters**.</span></span>  

3. <span data-ttu-id="bf3c6-109">展開したアダプターの一覧で選択**MQSeries**します。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-109">In the expanded adapter list, select **MQSeries**.</span></span> <span data-ttu-id="bf3c6-110">右ペインには、MQSeries アダプターにバインドされている送信ハンドラーと受信ハンドラーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-110">The list of send and receive handlers that are bound to the MQSeries adapter appear in the right pane.</span></span>  

4. <span data-ttu-id="bf3c6-111">右ペインで、送信ハンドラーまたは受信ハンドラーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-111">In the right pane, double-click a send or receive handler in the right pane.</span></span>  

5. <span data-ttu-id="bf3c6-112">**アダプター ハンドラーのプロパティ**ダイアログ ボックスで、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-112">In the **Adapter Handler Properties** dialog box, click **Properties**.</span></span>  

6. <span data-ttu-id="bf3c6-113">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-113">In the **MQSeries Transport Properties** dialog box, do the following:</span></span>  


   |           <span data-ttu-id="bf3c6-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bf3c6-114">Use this</span></span>            |                                    <span data-ttu-id="bf3c6-115">目的</span><span class="sxs-lookup"><span data-stu-id="bf3c6-115">To do this</span></span>                                    |
   |-------------------------------|----------------------------------------------------------------------------------|
   | <span data-ttu-id="bf3c6-116">**バッチ内の最大メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="bf3c6-116">**Maximum Messages in Batch**</span></span> | <span data-ttu-id="bf3c6-117">バッチ内に含めるメッセージの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-117">Set the maximum number of messages in a batch.</span></span> <span data-ttu-id="bf3c6-118">送信ハンドラーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-118">Applies only to the send handler.</span></span> |
   |          <span data-ttu-id="bf3c6-119">**[サーバー]**</span><span class="sxs-lookup"><span data-stu-id="bf3c6-119">**Server**</span></span>           |      <span data-ttu-id="bf3c6-120">MQSeries Server for Windows が実行されているコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-120">The name of the computer that is running MQSeries Server for Windows.</span></span>       |


7. <span data-ttu-id="bf3c6-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-121">Click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="bf3c6-122">受信場所のプロパティと送信ポートのプロパティは、受信ハンドラーの値と送信ハンドラーの値をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-122">The Receive Location and Send Port properties override the Receive Handler and Send Handler values.</span></span> <span data-ttu-id="bf3c6-123">受信場所のプロパティまたは送信ポートのプロパティに値が設定されていない場合、アダプターでは、それぞれ受信ハンドラーの値と送信ハンドラーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-123">If there is no value for the Receive Location or Send Port properties, the adapter uses the Receive Handler and Send Handler values respectively.</span></span>  

8. <span data-ttu-id="bf3c6-124">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf3c6-124">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="bf3c6-125">参照</span><span class="sxs-lookup"><span data-stu-id="bf3c6-125">See Also</span></span>  
 <span data-ttu-id="bf3c6-126">[アダプター受信場所と送信ポートを MQSeries を構成する方法](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="bf3c6-126">[How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md) </span></span>  
 [<span data-ttu-id="bf3c6-127">MQSeries アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="bf3c6-127">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)