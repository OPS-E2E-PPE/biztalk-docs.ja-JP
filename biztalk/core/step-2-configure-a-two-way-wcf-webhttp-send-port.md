---
title: '手順 2: 双方向 Wcf-webhttp 送信ポートの構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bcab296-7921-4df4-abcc-eea78cc827e8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f355275f9480cfa13f3a15bcc6522fbe7ec83b8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278890"
---
# <a name="step-2-configure-a-two-way-wcf-webhttp-send-port"></a><span data-ttu-id="4f9d7-102">手順 2: 双方向 Wcf-webhttp 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-102">Step 2: Configure a Two-way WCF-WebHttp Send Port</span></span>
<span data-ttu-id="4f9d7-103">この手順で構成する、双方向**Wcf-webhttp**米国航空会社のスケジュールで遅延を取得するための REST リソース URL を起動するポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-103">In this step you configure a two-way **WCF-WebHttp** send port to invoke the REST resource URL to retrieve delays in the US air carriers’ schedules.</span></span>  
  
### <a name="to-configure-wcf-webhttp-send-port"></a><span data-ttu-id="4f9d7-104">WCF-WebHttp 送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="4f9d7-104">To configure WCF-WebHttp send port</span></span>  
  
1.  <span data-ttu-id="4f9d7-105">BizTalk Server 管理コンソールから下にある、 **BizTalk アプリケーション 1**  ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリック**静的送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-105">From BizTalk Server Administration Console, under the **BizTalk Application 1** node, right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
2.  <span data-ttu-id="4f9d7-106">**[全般]** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-106">On the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="4f9d7-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f9d7-107">Use this</span></span>|<span data-ttu-id="4f9d7-108">目的</span><span class="sxs-lookup"><span data-stu-id="4f9d7-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4f9d7-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="4f9d7-109">**Name**</span></span>|<span data-ttu-id="4f9d7-110">型**SendPortRESTAzureMarketPlace**です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-110">Type **SendPortRESTAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="4f9d7-111">**型**</span><span class="sxs-lookup"><span data-stu-id="4f9d7-111">**Type**</span></span>|<span data-ttu-id="4f9d7-112">選択**Wcf-webhttp**です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-112">Select **WCF-WebHttp**.</span></span>|  
    |<span data-ttu-id="4f9d7-113">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="4f9d7-113">**Send handler**</span></span>|<span data-ttu-id="4f9d7-114">**[BizTalkServerApplication]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-114">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="4f9d7-115">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="4f9d7-115">**Send pipeline**</span></span>|<span data-ttu-id="4f9d7-116">選択**PassThruTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-116">Select **PassThruTransmit**.</span></span>|  
    |<span data-ttu-id="4f9d7-117">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="4f9d7-117">**Receive pipeline**</span></span>|<span data-ttu-id="4f9d7-118">選択**PassThruReceive**です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-118">Select **PassThruReceive**.</span></span>|  
  
     <span data-ttu-id="4f9d7-119">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-119">Click **Configure**.</span></span>  
  
3.  <span data-ttu-id="4f9d7-120">**Wcf-webhttp トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-120">From the **WCF-WebHttp Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="4f9d7-121">**全般** タブの**アドレス (URI)**、入力`https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-121">On the **General** tab, for **Address (URI)**, enter `https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`.</span></span>  
  
    2.  <span data-ttu-id="4f9d7-122">[全般] タブの**HTTP メソッドと URL マッピング**次を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-122">On the General tab, for **HTTP Method and URL Mapping**, enter the following:</span></span>  
  
        ```  
        <BtsHttpUrlMapping>  
        <Operation Method="GET" Url="/On_Time_Performance" />  
        </BtsHttpUrlMapping>  
  
        ```  
  
         <span data-ttu-id="4f9d7-123">ここでは、**取得**HTTP 動詞および**On_Time_Performance**はフライトの遅延を取得するための一意のリソース URL を構築するためにベース URI に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-123">Here, **GET** is the HTTP verb and **On_Time_Performance** is appended to the base URI to construct a unique resource URL to retrieve flight delays.</span></span>  
         
         > [!TIP] 
         > <span data-ttu-id="4f9d7-124">[URL] フィールド内で任意の特殊な XML 文字エスケープする必要が""です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-124">Within the URL field, any special XML characters must be "escaped".</span></span> <span data-ttu-id="4f9d7-125">これにより、XML の特殊文字は、処理、ポートでは保持されます。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-125">This ensures that the special XML characters are processed, and preserved by the port.</span></span> <span data-ttu-id="4f9d7-126">たとえば、`&`として特殊文字をエスケープする必要があります`&amp;`です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-126">For example, the `&` special character must be escaped as `&amp;`.</span></span> 
           >
           ><span data-ttu-id="4f9d7-127">差出人：`Url=”/Customer?{ID}& group=Location”`</span><span class="sxs-lookup"><span data-stu-id="4f9d7-127">From: `Url=”/Customer?{ID}& group=Location”`</span></span>
           >
           >
           ><span data-ttu-id="4f9d7-128">宛先：`Url=”/Customer?{ID}&amp;group=Location”`</span><span class="sxs-lookup"><span data-stu-id="4f9d7-128">To: `Url=”/Customer?{ID}&amp;group=Location”`</span></span>
  
    3.  <span data-ttu-id="4f9d7-129">**バインド** タブの**最大受信メッセージ サイズ**フィールドに、十分な大きさの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-129">On the **Bindings** tab, for the **Maximum Received Message Size** field, select a sufficiently large value.</span></span> <span data-ttu-id="4f9d7-130">通常、フライトの状況が含まれている応答メッセージはサイズがかなり大きく、指定された既定のメッセージ サイズを超える可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-130">That’s because typically the response message containing the flight status is considerably large and might exceed the default message size specified.</span></span>  
  
    4.  <span data-ttu-id="4f9d7-131">**セキュリティ** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-131">On the **Security** tab, do the following:</span></span>  
  
        1.  <span data-ttu-id="4f9d7-132">**セキュリティ モード\*\*\*\*トランスポート**です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-132">For the **Security mode**, select **Transport**.</span></span>  
  
        2.  <span data-ttu-id="4f9d7-133">**クライアント資格情報の種類のトランスポート\*\*\*\*基本**です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-133">For **Transport client credential type**, select **Basic**.</span></span>  
  
        3.  <span data-ttu-id="4f9d7-134">下にある、**ユーザー名資格情報**ボックスで、クリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-134">Under the **User name credentials** box, click **Edit**.</span></span> <span data-ttu-id="4f9d7-135">**クライアントの資格情報**ダイアログ ボックスで、**シングル サインオンに使用しない**、ユーザー名とから取得したパスワードを入力し、**マイ アカウント**した後タブログインして[Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913)です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-135">In the **Client Credentials** dialog box, select **Do no use Single-Sign On**, and enter the username and password that you retrieved from the **My Account** tab after you have logged into [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913).</span></span> <span data-ttu-id="4f9d7-136">に対して資格情報が表示されている、**顧客 ID** (ユーザー名) と**プライマリ アカウント キー** (パスワード) ラベル。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-136">The credentials are listed against the **Customer ID** (user name) and **Primary Account Key** (password) labels.</span></span>  
  
        4.  <span data-ttu-id="4f9d7-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-137">Click **OK**.</span></span>  
  
    5.  <span data-ttu-id="4f9d7-138">**メッセージ** タブの**動詞の本文を抑制**、要求メッセージからメッセージ ペイロードを除去する動詞を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-138">On the **Messages** tab, for **Suppress Body for Verbs**, specify the verb for which you want to strip the message payload from the request message.</span></span> <span data-ttu-id="4f9d7-139">このチュートリアルを指定`GET`です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-139">For this tutorial, specify this as `GET`.</span></span> <span data-ttu-id="4f9d7-140">その理由を次に示します: 米国航空会社のフライト遅延の REST エンドポイントに対する GET メソッド呼び出しには、メッセージ ペイロードは不要REST リソース URL は、情報を取得するだけで十分です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-140">Here’s why: A GET method call on the US Air Carrier flight delays REST endpoint does not require a message payload; the REST resource URL is sufficient to retrieve the information.</span></span> <span data-ttu-id="4f9d7-141">ただし、トリガーを**Wcf-webhttp** rest 呼び出しを送信ポート、いくつかのメッセージ本文を持つダミー メッセージをドロップします。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-141">However, to trigger the **WCF-WebHttp** send port that makes the REST call, you drop a dummy message that has some message body.</span></span> <span data-ttu-id="4f9d7-142">前に説明したように、REST エンドポイントはメッセージのペイロードを想定していないので、送信ポートから REST エンドポイントにダミー メッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-142">The send port must not send that dummy message to the REST endpoint because, as explained earlier, the endpoint does not expect a message payload.</span></span> <span data-ttu-id="4f9d7-143">そのため、REST エンドポイントを呼び出す前に、アダプターを切り離しますで指定した動詞についてのみ、ダミー メッセージからメッセージ ペイロード、**動詞の本文を抑制**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-143">So, before invoking the REST endpoint, the adapter strips the message payload from the dummy message only for the verbs that you specify in the **Suppress Body for Verbs** text box.</span></span>  
  
    6.  <span data-ttu-id="4f9d7-144">をクリックして**OK**送信ポートのプロパティ ダイアログ ボックスに戻るまでです。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-144">Click **OK** until you are back on the Send Port Properties dialog box.</span></span> <span data-ttu-id="4f9d7-145">左側のウィンドウからをクリックして**フィルター**で作成したポートの受信側から受信したすべてのメッセージを処理するフィルターを指定して[手順 1: ファイルの受信場所を構成する](../core/step-1-configure-a-file-receive-location.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-145">From the left pane, click **Filters**, and specify the filter to consume all messages that are received through the receive port you created in [Step 1: Configure a FILE Receive Location](../core/step-1-configure-a-file-receive-location.md).</span></span>  
  
        |||  
        |-|-|  
        |<span data-ttu-id="4f9d7-146">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4f9d7-146">**Property**</span></span>|<span data-ttu-id="4f9d7-147">設定**BTS です。ReceivePortName**</span><span class="sxs-lookup"><span data-stu-id="4f9d7-147">Set to **BTS.ReceivePortName**</span></span>|  
        |<span data-ttu-id="4f9d7-148">**演算子**</span><span class="sxs-lookup"><span data-stu-id="4f9d7-148">**Operator**</span></span>|<span data-ttu-id="4f9d7-149">を設定します。**==**</span><span class="sxs-lookup"><span data-stu-id="4f9d7-149">Set to **==**</span></span>|  
        |<span data-ttu-id="4f9d7-150">**値**</span><span class="sxs-lookup"><span data-stu-id="4f9d7-150">**Value**</span></span>|<span data-ttu-id="4f9d7-151">を設定します。`ReceivePortRestAzureMarketPlace`</span><span class="sxs-lookup"><span data-stu-id="4f9d7-151">Set to `ReceivePortRestAzureMarketPlace`</span></span>|  
  
    7.  <span data-ttu-id="4f9d7-152">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f9d7-152">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f9d7-153">参照</span><span class="sxs-lookup"><span data-stu-id="4f9d7-153">See Also</span></span>  
 [<span data-ttu-id="4f9d7-154">チュートリアル 5: BizTalk Server を使用して REST インターフェイスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="4f9d7-154">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)