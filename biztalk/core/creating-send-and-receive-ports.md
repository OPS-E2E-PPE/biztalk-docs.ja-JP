---
title: 送信を作成して、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 808c3d7295031832852ca40596a77a369aedb507
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353574"
---
# <a name="creating-send-and-receive-ports"></a><span data-ttu-id="214ff-102">送信を作成して、受信ポート</span><span class="sxs-lookup"><span data-stu-id="214ff-102">Creating Send and Receive Ports</span></span>
<span data-ttu-id="214ff-103">次の手順を使用して作成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信および受信ポートを BizTalk adapter for JD Edwards OneWorld します。</span><span class="sxs-lookup"><span data-stu-id="214ff-103">Use the following procedures to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports for BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="creating-a-port"></a><span data-ttu-id="214ff-104">ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="214ff-104">Creating a Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="214ff-105">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="214ff-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="214ff-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="214ff-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="214ff-107">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開し、送信ポートを作成するアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="214ff-107">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="214ff-108">右クリック**送信ポート**クリック**新規**、順にクリックします**静的な送信請求-応答ポート**します。</span><span class="sxs-lookup"><span data-stu-id="214ff-108">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="214ff-109">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="214ff-109">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="214ff-110">**名前**ボックスに、送信ポートの名前を入力 (たとえば、 `SSOSendToJDE OneWorld`)。</span><span class="sxs-lookup"><span data-stu-id="214ff-110">In the **Name** box, type a send port name (for example, `SSOSendToJDE OneWorld`).</span></span>  
  
    -   <span data-ttu-id="214ff-111">**型**ドロップダウン リストで、 **JDEdwards**します。</span><span class="sxs-lookup"><span data-stu-id="214ff-111">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="214ff-112">**送信ハンドラー**ドロップダウン リストで、送信ハンドラーのアドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="214ff-112">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
    -   <span data-ttu-id="214ff-113">**送信パイプライン**、 **[microsoft.biztalk.defaultpipelines.xmltransmit]** します。</span><span class="sxs-lookup"><span data-stu-id="214ff-113">For the **Send Pipeline**, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    -   <span data-ttu-id="214ff-114">**受信パイプライン**、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。</span><span class="sxs-lookup"><span data-stu-id="214ff-114">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
5.  <span data-ttu-id="214ff-115">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="214ff-115">Click **OK**.</span></span>  
  
## <a name="creating-a-receive-port"></a><span data-ttu-id="214ff-116">作成、受信ポート</span><span class="sxs-lookup"><span data-stu-id="214ff-116">Creating a Receive Port</span></span>  
  
#### <a name="to-create-a-receive-port"></a><span data-ttu-id="214ff-117">受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="214ff-117">To create a receive port</span></span>  
  
1.  <span data-ttu-id="214ff-118">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="214ff-118">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="214ff-119">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開し、送信ポートを作成するアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="214ff-119">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="214ff-120">右クリック**受信ポート**クリック**新規**、順にクリックします**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="214ff-120">Right-click **Receive Ports** and click **New**, and then click **One-way Receive Port**.</span></span>  
  
     <span data-ttu-id="214ff-121">**一方向受信ポートのプロパティ**画面で、**名前**フィールドに「 `ReceiveFromHttp`、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="214ff-121">On the **One-Way Receive Port Properties** screen, in the **Name** field, type `ReceiveFromHttp`, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="214ff-122">次の情報を入力、**一方向受信ポートのプロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="214ff-122">Enter the following information in the **One-way Receive Port Properties** window:</span></span>  
  
    -   <span data-ttu-id="214ff-123">**名前**フィールドに「`ReceiveFromHTTP`します。</span><span class="sxs-lookup"><span data-stu-id="214ff-123">In the **Name** field, type `ReceiveFromHTTP`.</span></span>  
  
    -   <span data-ttu-id="214ff-124">**トランスポートの種類**、 **HTTP**します。</span><span class="sxs-lookup"><span data-stu-id="214ff-124">For the **Transport Type**, select **HTTP**.</span></span>  
  
5.  <span data-ttu-id="214ff-125">アドレス (URI) で省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="214ff-125">Click the ellipsis (…) button in the address (URI).</span></span>  
  
     <span data-ttu-id="214ff-126">![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")</span><span class="sxs-lookup"><span data-stu-id="214ff-126">![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")</span></span>  
  
    1.  <span data-ttu-id="214ff-127">仮想ディレクトリと ISAPI 拡張、/mySSODemo/BTSHTTPReceive.dll を設定します。</span><span class="sxs-lookup"><span data-stu-id="214ff-127">Set the Virtual directory plus ISAPI extension, /mySSODemo/BTSHTTPReceive.dll.</span></span>  
  
    2.  <span data-ttu-id="214ff-128">選択**成功した場合の戻り値の関連付けハンドル**します。</span><span class="sxs-lookup"><span data-stu-id="214ff-128">Select **Return correlation handle on success**.</span></span>  
  
    3.  <span data-ttu-id="214ff-129">選択**使用してシングル サインオン**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="214ff-129">Select **Use Single Sign-On**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="214ff-130">**受信ハンドラー**ドロップダウン リストで、 **BizTalkServerIsolatedHost**します。</span><span class="sxs-lookup"><span data-stu-id="214ff-130">In the **Receive Handler** drop-down list, select **BizTalkServerIsolatedHost**.</span></span>  
  
     <span data-ttu-id="214ff-131">![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")</span><span class="sxs-lookup"><span data-stu-id="214ff-131">![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")</span></span>  
  
7.  <span data-ttu-id="214ff-132">**受信パイプライン**を選択します**microsoft.biztalk.defaultpiplelines.xmlreceive**、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="214ff-132">For the **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="214ff-133">参照</span><span class="sxs-lookup"><span data-stu-id="214ff-133">See Also</span></span>  
 <span data-ttu-id="214ff-134">[BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="214ff-134">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 <span data-ttu-id="214ff-135">[BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="214ff-135">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="214ff-136">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="214ff-136">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)