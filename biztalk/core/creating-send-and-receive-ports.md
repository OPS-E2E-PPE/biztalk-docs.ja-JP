---
title: "作成する送信ポートと受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, receive ports
- adapters [JD Edwards OneWorld adapters], receive ports
- creating, receive ports [JD Edwards OneWorld adapters]
- send ports, creating [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], send ports
- adapters [JD Edwards OneWorld adapters], transport properties
- JD Edwards OneWorld adapters, send ports
- JD Edwards OneWorld adapters, transport properties
- receive ports, creating [JD Edwards OneWorld adapters]
- creating, send ports [JD Edwards OneWorld adapters]
ms.assetid: fb4ca8b1-40d9-4beb-a791-554086f8ca98
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da4b117ca2d032ef1dc10731128acca903a51790
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="creating-send-and-receive-ports"></a><span data-ttu-id="53735-102">作成する送信ポートと受信ポート</span><span class="sxs-lookup"><span data-stu-id="53735-102">Creating Send and Receive Ports</span></span>
<span data-ttu-id="53735-103">次の手順を使用して、BizTalk Adapter for JD Edwards OneWorld 用に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信ポートおよび受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="53735-103">Use the following procedures to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports for BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="creating-a-port"></a><span data-ttu-id="53735-104">ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="53735-104">Creating a Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="53735-105">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="53735-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="53735-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="53735-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="53735-107">BizTalk Server 管理コンソールで、次のように展開します**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、を展開**アプリケーション**、の順に展開し、。送信ポートを作成するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="53735-107">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="53735-108">右クリック**送信ポート** をクリック**新規**、クリックして**静的な送信請求-応答ポート**です。</span><span class="sxs-lookup"><span data-stu-id="53735-108">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="53735-109">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="53735-109">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="53735-110">**名前**ボックスに、送信ポートの名前を入力 (たとえば、 `SSOSendToJDE OneWorld`)。</span><span class="sxs-lookup"><span data-stu-id="53735-110">In the **Name** box, type a send port name (for example, `SSOSendToJDE OneWorld`).</span></span>  
  
    -   <span data-ttu-id="53735-111">**型**ドロップダウン リストで、 **JDEdwards**です。</span><span class="sxs-lookup"><span data-stu-id="53735-111">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="53735-112">**送信ハンドラー**ドロップダウン リストで、送信ハンドラーのアドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="53735-112">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
    -   <span data-ttu-id="53735-113">**送信パイプライン** **microsoft.biztalk.defaultpipelines.xmltransmit**です。</span><span class="sxs-lookup"><span data-stu-id="53735-113">For the **Send Pipeline**, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    -   <span data-ttu-id="53735-114">**受信パイプライン** **microsoft.biztalk.defaultpiplelines.xmlreceive**です。</span><span class="sxs-lookup"><span data-stu-id="53735-114">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
5.  <span data-ttu-id="53735-115">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53735-115">Click **OK**.</span></span>  
  
## <a name="creating-a-receive-port"></a><span data-ttu-id="53735-116">作成する、受信ポート</span><span class="sxs-lookup"><span data-stu-id="53735-116">Creating a Receive Port</span></span>  
  
#### <a name="to-create-a-receive-port"></a><span data-ttu-id="53735-117">受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="53735-117">To create a receive port</span></span>  
  
1.  <span data-ttu-id="53735-118">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="53735-118">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="53735-119">BizTalk Server 管理コンソールで、次のように展開します**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、を展開**アプリケーション**、の順に展開し、。送信ポートを作成するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="53735-119">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="53735-120">右クリック**受信ポート** をクリック**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="53735-120">Right-click **Receive Ports** and click **New**, and then click **One-way Receive Port**.</span></span>  
  
     <span data-ttu-id="53735-121">**一方向受信ポートのプロパティ**画面で、**名前**フィールドに「 `ReceiveFromHttp`、クリックしてして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="53735-121">On the **One-Way Receive Port Properties** screen, in the **Name** field, type `ReceiveFromHttp`, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="53735-122">次の情報を入力、**一方向受信ポートのプロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="53735-122">Enter the following information in the **One-way Receive Port Properties** window:</span></span>  
  
    -   <span data-ttu-id="53735-123">**名前**フィールドに「`ReceiveFromHTTP`です。</span><span class="sxs-lookup"><span data-stu-id="53735-123">In the **Name** field, type `ReceiveFromHTTP`.</span></span>  
  
    -   <span data-ttu-id="53735-124">**トランスポートの種類** **HTTP**です。</span><span class="sxs-lookup"><span data-stu-id="53735-124">For the **Transport Type**, select **HTTP**.</span></span>  
  
5.  <span data-ttu-id="53735-125">[アドレス (URI)] の省略記号ボタン ([...]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53735-125">Click the ellipsis (…) button in the address (URI).</span></span>  
  
     ![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")  
  
    1.  <span data-ttu-id="53735-126">仮想ディレクトリと ISAPI 拡張 /mySSODemo/BTSHTTPReceive.dll を設定します。</span><span class="sxs-lookup"><span data-stu-id="53735-126">Set the Virtual directory plus ISAPI extension, /mySSODemo/BTSHTTPReceive.dll.</span></span>  
  
    2.  <span data-ttu-id="53735-127">選択**関連付けハンドルを返す成功**です。</span><span class="sxs-lookup"><span data-stu-id="53735-127">Select **Return correlation handle on success**.</span></span>  
  
    3.  <span data-ttu-id="53735-128">選択**を使用してシングル サインオン**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="53735-128">Select **Use Single Sign-On**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="53735-129">**受信ハンドラー**ドロップダウン リストで、 **BizTalkServerIsolatedHost**です。</span><span class="sxs-lookup"><span data-stu-id="53735-129">In the **Receive Handler** drop-down list, select **BizTalkServerIsolatedHost**.</span></span>  
  
     ![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")  
  
7.  <span data-ttu-id="53735-130">**受信パイプライン** **microsoft.biztalk.defaultpiplelines.xmlreceive**をクリックし、 **ok**です。</span><span class="sxs-lookup"><span data-stu-id="53735-130">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53735-131">参照</span><span class="sxs-lookup"><span data-stu-id="53735-131">See Also</span></span>  
 <span data-ttu-id="53735-132">[BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="53735-132">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 <span data-ttu-id="53735-133">[BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="53735-133">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="53735-134">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="53735-134">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)