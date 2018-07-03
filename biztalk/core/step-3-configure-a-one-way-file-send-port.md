---
title: '手順 3: 一方向 FILE 送信ポートの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c52c6b6b-6f9c-48f2-8732-450fe3a15eae
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67cc96dfccc7256681887290ef37261c4c7fecb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987923"
---
# <a name="step-3-configure-a-one-way-file-send-port"></a><span data-ttu-id="217c2-102">手順 3: 一方向 FILE 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="217c2-102">Step 3: Configure a One-way FILE Send Port</span></span>
<span data-ttu-id="217c2-103">このステップでは、REST インターフェイスから受信した応答メッセージを使用し、そのメッセージをファイルの場所にコピーする一方向の FILE 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="217c2-103">In this step you configure a one-way FILE send port that consumes the response message received from the REST interface and copies it to a file location.</span></span>  

### <a name="to-configure-a-file-send-port"></a><span data-ttu-id="217c2-104">FILE 送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="217c2-104">To configure a FILE send port</span></span>  

1. <span data-ttu-id="217c2-105">BizTalk Server 管理コンソールから下、 **BizTalk アプリケーション 1**ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="217c2-105">From BizTalk Server Administration Console, under the **BizTalk Application 1** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="217c2-106">[全般] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="217c2-106">On the General tab, do the following:</span></span>  

   |<span data-ttu-id="217c2-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="217c2-107">Use this</span></span>|<span data-ttu-id="217c2-108">目的</span><span class="sxs-lookup"><span data-stu-id="217c2-108">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="217c2-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="217c2-109">**Name**</span></span>|<span data-ttu-id="217c2-110">型**SendPortOutAzureMarketPlaceData**します。</span><span class="sxs-lookup"><span data-stu-id="217c2-110">Type **SendPortOutAzureMarketPlaceData**.</span></span>|  
   |<span data-ttu-id="217c2-111">**型**</span><span class="sxs-lookup"><span data-stu-id="217c2-111">**Type**</span></span>|<span data-ttu-id="217c2-112">選択**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="217c2-112">Select **FILE**.</span></span>|  
   |<span data-ttu-id="217c2-113">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="217c2-113">**Send handler**</span></span>|<span data-ttu-id="217c2-114">**[BizTalkServerApplication]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="217c2-114">Select **BizTalkServerApplication**.</span></span>|  
   |<span data-ttu-id="217c2-115">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="217c2-115">**Send pipeline**</span></span>|<span data-ttu-id="217c2-116">選択**PassThruTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="217c2-116">Select **PassThruTransmit**.</span></span>|  

    <span data-ttu-id="217c2-117">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="217c2-117">Click **Configure**.</span></span>  

3. <span data-ttu-id="217c2-118">[FILE トランスポートのプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="217c2-118">From File Transport Properties, do the following:</span></span>  


   |      <span data-ttu-id="217c2-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="217c2-119">Use this</span></span>      |                                                              <span data-ttu-id="217c2-120">目的</span><span class="sxs-lookup"><span data-stu-id="217c2-120">To do this</span></span>                                                               |
   |--------------------|---------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="217c2-121">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="217c2-121">**Receive folder**</span></span> | <span data-ttu-id="217c2-122">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が応答メッセージをコピーする場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="217c2-122">Type a location where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copies the response message.</span></span> |
   |   <span data-ttu-id="217c2-123">**[ファイル名]**</span><span class="sxs-lookup"><span data-stu-id="217c2-123">**File name**</span></span>    |                                                       <span data-ttu-id="217c2-124">保持 `%MessageID%.xml`</span><span class="sxs-lookup"><span data-stu-id="217c2-124">Retain `%MessageID%.xml`</span></span>                                                        |


4. <span data-ttu-id="217c2-125">**フィルター**タブで、指定に書き込まれるすべてのメッセージを処理するフィルターを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で作成した受信ポートでメッセージ ボックス データベース[手順 2: 双方向 Wcf-webhttp 送信ポート構成](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md).</span><span class="sxs-lookup"><span data-stu-id="217c2-125">On the **Filters** tab, specify the filter to consume all messages that are written to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Message Box database by the receive port you created in [Step 2: Configure a Two-way WCF-WebHttp Send Port](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md).</span></span>  


   |              |                                       |
   |--------------|---------------------------------------|
   | <span data-ttu-id="217c2-126">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="217c2-126">**Property**</span></span> |         <span data-ttu-id="217c2-127">設定**BTS します。SPName**</span><span class="sxs-lookup"><span data-stu-id="217c2-127">Set to **BTS.SPName**</span></span>         |
   | <span data-ttu-id="217c2-128">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="217c2-128">**Operator**</span></span> |             <span data-ttu-id="217c2-129">を設定します。 **==**</span><span class="sxs-lookup"><span data-stu-id="217c2-129">Set to **==**</span></span>             |
   |  <span data-ttu-id="217c2-130">**[値]**</span><span class="sxs-lookup"><span data-stu-id="217c2-130">**Value**</span></span>   | <span data-ttu-id="217c2-131">を設定します。 `SendPortRESTAzureMarketPlace`</span><span class="sxs-lookup"><span data-stu-id="217c2-131">Set to `SendPortRESTAzureMarketPlace`</span></span> |


5. <span data-ttu-id="217c2-132">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="217c2-132">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="217c2-133">参照</span><span class="sxs-lookup"><span data-stu-id="217c2-133">See Also</span></span>  
 [<span data-ttu-id="217c2-134">チュートリアル 5: BizTalk Server を使用して REST インターフェイスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="217c2-134">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)