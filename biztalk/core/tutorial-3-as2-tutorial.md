---
title: チュートリアル 3:AS2 チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 018829a9-e670-4b87-bac5-7f7b1332d90e
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0fb5f48a8e85c318b85322557ac940e36ecd142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401710"
---
# <a name="tutorial-3-as2-tutorial"></a><span data-ttu-id="bdc4e-102">チュートリアル 3:AS2 チュートリアル</span><span class="sxs-lookup"><span data-stu-id="bdc4e-102">Tutorial 3: AS2 Tutorial</span></span>
<span data-ttu-id="bdc4e-103">このチュートリアルでは、受信し、HTTP トランスポートを介して EDIINT/AS2 でエンコードされたメッセージを送信するソリューションを設定します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-103">In this tutorial, you set up a solution that receives and sends EDIINT/AS2-encoded messages over an HTTP transport.</span></span>  
  
 <span data-ttu-id="bdc4e-104">**チュートリアル ソリューションのしくみ**</span><span class="sxs-lookup"><span data-stu-id="bdc4e-104">**How the Tutorial Solution Works**</span></span>  
  
 <span data-ttu-id="bdc4e-105">このソリューションは次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-105">The solution will do the following:</span></span>  
  
- <span data-ttu-id="bdc4e-106">パートナー (Fabrikam) から AS2 メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-106">Receive an AS2 message from a partner (Fabrikam)</span></span>  
  
- <span data-ttu-id="bdc4e-107">パートナーに非同期的に MDN 応答を返す</span><span class="sxs-lookup"><span data-stu-id="bdc4e-107">Return an MDN response asynchronously to the partner</span></span>  
  
- <span data-ttu-id="bdc4e-108">AS2 メッセージの EDI ペイロードを処理します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-108">Process the EDI payload of the AS2 message</span></span>  
  
- <span data-ttu-id="bdc4e-109">AS2 経由でパートナー (Fabrikam) に 997 受信確認を返す</span><span class="sxs-lookup"><span data-stu-id="bdc4e-109">Return a 997 acknowledgment to the partner (Fabrikam) over AS2</span></span>  
  
- <span data-ttu-id="bdc4e-110">ホーム組織 (Contoso) のバックエンド アプリケーションに EDI メッセージのペイロードを含む XML ファイルをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-110">Route an XML file containing the payload of the EDI message to a backend application of the home organization (Contoso).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="bdc4e-111">このソリューションは、AS2 メッセージのセキュリティを確保するのに署名または暗号化を使用できません。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-111">This solution does not use signing or encryption to help ensure the security of AS2 messages.</span></span>  
  
  <span data-ttu-id="bdc4e-112">**チュートリアル コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="bdc4e-112">**Tutorial Components**</span></span>  
  
  <span data-ttu-id="bdc4e-113">このソリューションは、次のものを使用します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-113">This solution will use the following:</span></span>  
  
- <span data-ttu-id="bdc4e-114">BTS Http Receive ISAPI フィルタ、送信側から AS2 または EDI メッセージを受信する **(/Contoso/BTSHTTPReceive.dll**)。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-114">A BTS Http Receive ISAPI Filter to receive the AS2/EDI message from the sender **(/Contoso/BTSHTTPReceive.dll**).</span></span>  
  
- <span data-ttu-id="bdc4e-115">997 受信確認および MDN を返すことによって、パートナーをシミュレートするために ASPX Web ページ (**http://localhost/Fabrikam/Default.aspx**)。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-115">An ASPX Web page to simulate the partner by returning a 997 acknowledgment and an MDN (**http://localhost/Fabrikam/Default.aspx**).</span></span>  
  
- <span data-ttu-id="bdc4e-116">使用する 864 スキーマおよびその他のスキーマをデプロイするプロジェクト ファイル (**Schemas.btproj**)。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-116">A project file that you will use to deploy an 864 schema and other schemas (**Schemas.btproj**).</span></span>  
  
- <span data-ttu-id="bdc4e-117">一方向の HTTP 受信場所で EDI ファイルを受信する (**Receive_AS2**)。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-117">A one-way HTTP receive location to receive the EDI file (**Receive_AS2**).</span></span> <span data-ttu-id="bdc4e-118">これは受信 AS2 デコーダーおよび EDI 逆アセンブラーを含む既定の AS2EdiReceive パイプラインで、場所が使用します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-118">This receive location uses the default AS2EdiReceive pipeline that contains the AS2 Decoder and EDI Disassembler.</span></span>  
  
- <span data-ttu-id="bdc4e-119">動的な HTTP 送信ポートを非同期 MDN を返す (**Send_Async_MDN**)。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-119">A dynamic HTTP send port to return an asynchronous MDN (**Send_Async_MDN**).</span></span> <span data-ttu-id="bdc4e-120">この送信ポートは、AS2 エンコーダーを含む AS2Send パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-120">This send port uses the AS2Send pipeline that contains the AS2 Encoder.</span></span>  
  
- <span data-ttu-id="bdc4e-121">静的な一方向の FILE 送信ポートをバックエンド フォルダーに XML ファイルに、EDI ペイロードをルーティングする (**Send_Payload_EdiXml**)。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-121">A static one-way FILE send port to route the EDI payload in an XML file to a back-end folder (**Send_Payload_EdiXml**).</span></span> <span data-ttu-id="bdc4e-122">この送信ポートは、PassThruTransmit 送信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-122">This send port uses the PassThruTransmit send pipeline.</span></span>  
  
- <span data-ttu-id="bdc4e-123">静的な一方向 HTTP 送信ポートを AS2 経由でパートナーに 997 受信確認を返す (**Send_Async_997**)。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-123">A static one-way HTTP send port to return a 997 acknowledgment to the partner over AS2 (**Send_Async_997**).</span></span> <span data-ttu-id="bdc4e-124">この送信ポートは、AS2 エンコーダーが含まれている EDI アセンブラーの必要がない AS2Send パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-124">This send port uses the AS2Send pipeline that includes the AS2 Encoder, but has no need for the EDI Assembler.</span></span>  
  
- <span data-ttu-id="bdc4e-125">Fabrikam 取引先から EDI ファイルを BizTalk に送信するアプリケーションの構築に使用するプロジェクト ファイル (**Sender.csproj**)。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-125">A project file that you will use to build an application to send the EDI file from the Fabrikam partner to BizTalk (**Sender.csproj**).</span></span>  
  
  <span data-ttu-id="bdc4e-126">**メッセージ フロー**</span><span class="sxs-lookup"><span data-stu-id="bdc4e-126">**Message Flow**</span></span>  
  
  <span data-ttu-id="bdc4e-127">完成したソリューションにおけるメッセージ フローは、次の図に示すようになります。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-127">The message flow in the completed solution will be as shown in the following figure:</span></span>  
  
  <span data-ttu-id="bdc4e-128">![AS2 チュートリアル メッセージ フロー](../core/media/31710c1d-4070-433e-953d-dcbfd0bb07a0.gif "31710c1d-4070-433e-953d-dcbfd0bb07a0")</span><span class="sxs-lookup"><span data-stu-id="bdc4e-128">![AS2 tutorial message flow](../core/media/31710c1d-4070-433e-953d-dcbfd0bb07a0.gif "31710c1d-4070-433e-953d-dcbfd0bb07a0")</span></span>  
  
  <span data-ttu-id="bdc4e-129">チュートリアル コンポーネントは、次のようなメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-129">The tutorial components process the message as follows:</span></span>  
  
1. <span data-ttu-id="bdc4e-130">使用する、 **sender.exe アプリケーション**パートナー Fabrikam から BizTalk Server コンピューターに、元の EDI および AS2 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-130">You use the **sender.exe application** to send the original EDI/AS2 message from the partner Fabrikam to the BizTalk Server computer.</span></span> <span data-ttu-id="bdc4e-131">Sender.exe は、Contoso 仮想ディレクトリに edi/as2 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-131">Sender.exe sends the EDI/AS2 message to the Contoso virtual directory.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bdc4e-132">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-132">The events in this list may not occur in the order shown.</span></span>  
   >   
   >  <span data-ttu-id="bdc4e-133">テスト メッセージは、\Program Files\Microsoft BizTalk Server 20xx \sdk\as2 Tutorial の X12_00401_864.edi です。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-133">The test message is X12_00401_864.edi in \Program Files\Microsoft BizTalk Server 20xx\SDK\AS2 Tutorial.</span></span>  
  
2. <span data-ttu-id="bdc4e-134">**Receive_AS2**一方向受信場所が Contoso 仮想ディレクトリからファイルを取得する、BTSHTTPReceive.dll ISAPI 拡張機能を使用して、Fabrikam から EDI メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-134">The **Receive_AS2** one-way receive location receives the EDI message from Fabrikam, using the BTSHTTPReceive.dll ISAPI extension to pick the file up from the Contoso virtual directory.</span></span> <span data-ttu-id="bdc4e-135">受信パイプラインは AS2 メッセージをデコード、EDI インターチェンジを逆アセンブル、および、メッセージ ボックスに XML メッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-135">The receive pipeline decodes the AS2 message, disassembles the EDI interchange, and then drops the message XML into the MessageBox.</span></span>  
  
3. <span data-ttu-id="bdc4e-136">受信パイプラインは、AS2 メッセージの MDN を生成し、受信パイプラインがメッセージ ボックスに MDN を削除するため、MDN は非同期に設定されて、します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-136">The receive pipeline generates an MDN for the AS2 message, and since the MDN is set up to be asynchronous, the receive pipeline drops the MDN into the MessageBox.</span></span>  
  
4. <span data-ttu-id="bdc4e-137">受信パイプラインでは、EDI インターチェンジへの応答で 997 受信確認を生成し、997 を MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-137">The receive pipeline generates a 997 acknowledgment in response to the EDI interchange, and drops the 997 into the MessageBox.</span></span>  
  
5. <span data-ttu-id="bdc4e-138">**Send_Payload_EdiXml**静的な一方向の送信ポートを取得、EDI ペイロードをメッセージ ボックスから、BTS のフィルター処理します。MessageType のコンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-138">The **Send_Payload_EdiXml** static one-way send port picks up the EDI payload from the MessageBox, filtering on the BTS.MessageType context property.</span></span>  
  
6. <span data-ttu-id="bdc4e-139">ペイロード送信ポートで表されるバックエンド Contoso アプリケーションは、EDI ペイロードを含む XML ファイル、 \\_EDIXMLToContoso フォルダー。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-139">The payload send port sends the XML file containing the EDI payload to the back-end Contoso application, represented by the \\_EDIXMLToContoso folder.</span></span> <span data-ttu-id="bdc4e-140">この送信ポートは、PassThruTransmit 送信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-140">This send port uses a PassThruTransmit send pipeline.</span></span>  
  
7. <span data-ttu-id="bdc4e-141">**Send_Async_MDN**動的送信ポート非同期 mdn はから取得し、メッセージ ボックス、EdiIntAS.IsAS2AsynchronousMdn コンテキスト プロパティに関してフィルタ処理します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-141">The **Send_Async_MDN** dynamic send port picks up the asynchronous MDN from the MessageBox, filtering on the EdiIntAS.IsAS2AsynchronousMdn context property.</span></span>  
  
8. <span data-ttu-id="bdc4e-142">MDN 送信ポートを返します。 MDN を、 \\_MDNToFabrikam フォルダー。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-142">The MDN send port returns the MDN to the \\_MDNToFabrikam folder.</span></span> <span data-ttu-id="bdc4e-143">これは、動的送信ポートであるためには、メッセージのヘッダーの Receipt-delivery-option 行にアドレスが使用されます (**http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam**) にメッセージをルーティングする、 \\_MDNToFabrikam フォルダー。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-143">Since this is a dynamic send port, it will use the address in the Receipt-Delivery-Option line in the header of the message (**http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam**) to route the message to the \\_MDNToFabrikam folder.</span></span>  
  
9. <span data-ttu-id="bdc4e-144">**Send_Async_997**送信ポートから取得し、997、メッセージ ボックス、BTS のフィルター処理します。MessageType のコンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-144">The **Send_Async_997** send port picks up the 997 from the MessageBox, filtering on the BTS.MessageType context property.</span></span>  
  
10. <span data-ttu-id="bdc4e-145">997 送信ポートの使用、EdiReceive によって生成された 997 メッセージ受信パイプラインに送信する HTTP トランスポート、 \\_ 997tofabrikam フォルダー。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-145">The 997 send port uses HTTP transport to send the 997 message generated by the EdiReceive receive pipeline to the \\_997ToFabrikam folder.</span></span> <span data-ttu-id="bdc4e-146">送信ポートの URI を使用して、Fabrikam default.aspx ページにメッセージを送信する **http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam**します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-146">The send port sends the message to the Fabrikam default.aspx page, using the URI **http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam**.</span></span> <span data-ttu-id="bdc4e-147">Default.aspx ページに 997 を送信し、 \\_ 997tofabrikam フォルダー。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-147">The default.aspx page then sends the 997 to the \\_997ToFabrikam folder.</span></span>  
  
    <span data-ttu-id="bdc4e-148">このチュートリアルには、次の知識があります。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-148">To do this tutorial, you should be knowledgeable about the following:</span></span>  
  
-   <span data-ttu-id="bdc4e-149">BizTalk Server パイプラインおよびパイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bdc4e-149">BizTalk Server pipelines and pipeline components</span></span>  
  
-   <span data-ttu-id="bdc4e-150">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="bdc4e-150">HTTP Adapter</span></span>  
  
-   <span data-ttu-id="bdc4e-151">受信ポートと受信場所</span><span class="sxs-lookup"><span data-stu-id="bdc4e-151">Receive ports and locations</span></span>  
  
-   <span data-ttu-id="bdc4e-152">送信ポート</span><span class="sxs-lookup"><span data-stu-id="bdc4e-152">Send ports</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bdc4e-153">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bdc4e-153">In This Section</span></span>  
  
-   [<span data-ttu-id="bdc4e-154">ステップ 1: AS2 チュートリアルを準備します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-154">Step 1: Prepare for the AS2 Tutorial</span></span>](../core/step-1-prepare-for-the-as2-tutorial.md)  
  
-   [<span data-ttu-id="bdc4e-155">手順 2:作成およびデプロイのサンプル X12 スキーマ</span><span class="sxs-lookup"><span data-stu-id="bdc4e-155">Step 2: Create and Deploy the Sample X12 Schema</span></span>](../core/step-2-create-and-deploy-the-sample-x12-schema.md)  
  
-   [<span data-ttu-id="bdc4e-156">ステップ 3:組織のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-156">Step 3: Configure a Party and Business Profile for Your Organization</span></span>](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)  
  
-   [<span data-ttu-id="bdc4e-157">手順 4:取引先のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-157">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md)  
  
-   [<span data-ttu-id="bdc4e-158">手順 5:取引先パートナーの Web ページを構成します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-158">Step 5: Configure the Trading Partner Web Pages</span></span>](../core/step-5-configure-the-trading-partner-web-pages.md)  
  
-   [<span data-ttu-id="bdc4e-159">手順 6:EDI AS2 を構成する受信場所</span><span class="sxs-lookup"><span data-stu-id="bdc4e-159">Step 6: Configure the EDI-AS2 Receive Location</span></span>](../core/step-6-configure-the-edi-as2-receive-location.md)  
  
-   [<span data-ttu-id="bdc4e-160">手順 7:MDN の送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-160">Step 7: Configure the MDN Send Port</span></span>](../core/step-7-configure-the-mdn-send-port.md)  
  
-   [<span data-ttu-id="bdc4e-161">手順 8:997 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-161">Step 8: Configure the 997 Send Port</span></span>](../core/step-8-configure-the-997-send-port.md)  
  
-   [<span data-ttu-id="bdc4e-162">手順 9:EDI ペイロード送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-162">Step 9: Configure the EDI Payload Send Port</span></span>](../core/step-9-configure-the-edi-payload-send-port.md)  
  
-   [<span data-ttu-id="bdc4e-163">手順 10: X12 および AS2 取引先アグリーメントを構成します。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-163">Step 10: Configure the X12 and AS2 Trading Partner Agreement</span></span>](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="bdc4e-164">手順 11: AS2 ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="bdc4e-164">Step 11: Test the AS2 Solution</span></span>](../core/step-11-test-the-as2-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="bdc4e-165">参照</span><span class="sxs-lookup"><span data-stu-id="bdc4e-165">See Also</span></span>  
 [<span data-ttu-id="bdc4e-166">BizTalk Server チュートリアル</span><span class="sxs-lookup"><span data-stu-id="bdc4e-166">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)