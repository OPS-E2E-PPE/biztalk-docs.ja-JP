---
title: "作成する方法には、TIBCO Enterprise Message Service 受信ポートを |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, creating
- creating receive ports
ms.assetid: ca623c81-3dd3-4824-a586-28055d01fe9f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a85fad9dc0936baa0c3f584581d5483a30fedf6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-receive-ports-in-tibco-enterprise-message-service"></a><span data-ttu-id="1cf4d-102">TIBCO Enterprise Message Service での受信ポートの作成方法</span><span class="sxs-lookup"><span data-stu-id="1cf4d-102">How to Create Receive Ports in TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="1cf4d-103">受信ポートを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-103">Follow these steps to create a receive port.</span></span>  
  
### <a name="to-create-a-receive-port"></a><span data-ttu-id="1cf4d-104">受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="1cf4d-104">To create a receive port</span></span>  
  
1.  <span data-ttu-id="1cf4d-105">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="1cf4d-106">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-106">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="1cf4d-107">**受信ポートのプロパティ** ウィンドウで、**全般** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-107">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="1cf4d-108">**名前**フィールドに「`ReceiveFromTIBCOEMS`です。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-108">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="1cf4d-109">**認証**グループ ボックスで、認証の使用時のメッセージの処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-109">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="1cf4d-110">選択、**失敗したメッセージの有効化のルーティングを**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-110">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="1cf4d-111">**受信場所** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-111">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="1cf4d-112">**[新規作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-112">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="1cf4d-113">**受信場所**ウィンドウで、**全般** ページで、入力、**名前**受信場所のです。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-113">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="1cf4d-114">**型**ドロップダウン一覧で、トランスポートの種類を選択してから、**受信ハンドラー**ドロップダウン一覧で、トランスポート アドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-114">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="1cf4d-115">**受信パイプライン**ドロップダウン リストで、受信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-115">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="1cf4d-116">**スケジュール**] ページで、[、**開始日**と**終了日**ドキュメントの受信を制限します。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-116">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="1cf4d-117">選択、**有効にするサービス時間帯**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-117">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="1cf4d-118">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="1cf4d-119">**受信マップ**ページで、選択したポートでドキュメントを変換するための受信マップを選択します。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-119">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="1cf4d-120">**追跡** ページで、必要なメッセージ本文の追跡と追跡メッセージのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-120">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="1cf4d-121">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cf4d-121">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cf4d-122">参照</span><span class="sxs-lookup"><span data-stu-id="1cf4d-122">See Also</span></span>  
 [<span data-ttu-id="1cf4d-123">TIBCO Enterprise Message Service トランスポート プロパティの設定、受信ポート</span><span class="sxs-lookup"><span data-stu-id="1cf4d-123">Setting TIBCO Enterprise Message Service Transport Properties for the Receive Port</span></span>](../core/set-tibco-enterprise-message-service-transport-properties-for-the-receive-port.md)