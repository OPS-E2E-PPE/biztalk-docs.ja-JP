---
title: '手順 9: ソリューションのテスト |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df446ccc-add3-4dd3-b674-253dda385541
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89a3722d6d8e1d4b730341dfaf16d60af1686f21
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973072"
---
# <a name="step-9-test-the-solution"></a><span data-ttu-id="1c764-102">手順 9: ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="1c764-102">Step 9: Test the Solution</span></span>
<span data-ttu-id="1c764-103">このトピックでは、EDI アグリーメントが展開されている HTTP エンドポイントに X12 840 販売注文メッセージを送信することで、ハイブリッド アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="1c764-103">In this topic you test the hybrid application by sending a X12 840 sales order message to the HTTP endpoint where the EDI agreement is deployed.</span></span> <span data-ttu-id="1c764-104">販売注文メッセージのサンプルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1c764-104">The sample sales order message looks like the following:</span></span>  
  
```  
ISA*00*          *00*          *ZZ*CONTOSO        *ZZ*NORTHWIND      *991221*1226*U*00401*000000025*0*T*:~  
GS*PO*THEM*US*19991221*1226*1*X*004010~  
ST*840*0002~  
BQT*00*BQT02*20120619*001*20120719~  
PER*1A*John*EM*John@contoso.com~  
N1*001~  
N2*co~  
N3*Contoso*One Contoso Way~  
N4*Redmond*WA*98052*US~  
PO1*PO101*121*01*10*AA*A1*1~  
CTT*475~  
SE*10*0002~  
GE*1*1~  
IEA*1*000000025~  
```  
  
 <span data-ttu-id="1c764-105">このメッセージの強調表示されたセグメント (で始まる行**PO1**)、注文数量が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1c764-105">In this message, the highlighted segment (the line starting with **PO1**) contains the order quantity.</span></span> <span data-ttu-id="1c764-106">このメッセージに、注文数量が*121*です。</span><span class="sxs-lookup"><span data-stu-id="1c764-106">The order quantity in this message is *121*.</span></span> <span data-ttu-id="1c764-107">そのため、このメッセージを送信する場合に挿入してください、 **SalesOrder**テーブル。</span><span class="sxs-lookup"><span data-stu-id="1c764-107">So, if you send this message, it must be inserted into the **SalesOrder** table.</span></span> <span data-ttu-id="1c764-108">数量を 100 未満に変更してメッセージを再送信することができます。その場合は FILE 送信ポートに指定したファイルの場所に送信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c764-108">You can update the quantity to less than 100 and resend the message, it must then be sent to the file location you specified in the FILE send port.</span></span>  
  
 <span data-ttu-id="1c764-109">このメッセージを EDI アグリーメントを送信する際、 **MessageSender**するサンプルに付属のツール[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1c764-109">To send this message to the EDI agreement, you can use the **MessageSender** tool shipped with the samples for [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].</span></span> <span data-ttu-id="1c764-110">サンプルをダウンロードする[http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)です。</span><span class="sxs-lookup"><span data-stu-id="1c764-110">You can download the samples from [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057).</span></span>  
  
### <a name="to-send-a-message"></a><span data-ttu-id="1c764-111">メッセージを送信するには</span><span class="sxs-lookup"><span data-stu-id="1c764-111">To send a message</span></span>  
  
1.  <span data-ttu-id="1c764-112">検索、 **MessageSender**サンプル パッケージにプロジェクトを読み込んでビルドします。</span><span class="sxs-lookup"><span data-stu-id="1c764-112">Locate the **MessageSender** project in the sample package and build it.</span></span>  
  
2.  <span data-ttu-id="1c764-113">その結果を使用して**MessageSender**コマンドライン実行可能ファイル (プロジェクトの \bin\Debug フォルダー)、デプロイされた EDI アグリーメントにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="1c764-113">Use the resulting **MessageSender** command-line executable (under \bin\Debug folder within the project) to send messages to the deployed EDI agreement.</span></span> <span data-ttu-id="1c764-114">このツールは、次の形式のコマンド ライン パラメーターを受け付けます。</span><span class="sxs-lookup"><span data-stu-id="1c764-114">This tool accepts command-line parameter in the following format:</span></span>  
  
    ```  
    MessageSender.exe <ServiceBusNamespace> <IssuerName> <IssuerKey> <EDI agreement endpoint> <MessageFilepath> <ContentType>  
    ```  
  
     <span data-ttu-id="1c764-115">どこ</span><span class="sxs-lookup"><span data-stu-id="1c764-115">Where,</span></span>  
  
    |<span data-ttu-id="1c764-116">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="1c764-116">Parameter name</span></span>|<span data-ttu-id="1c764-117">Description</span><span class="sxs-lookup"><span data-stu-id="1c764-117">Description</span></span>|  
    |--------------------|-----------------|  
    |<span data-ttu-id="1c764-118">ServiceBusNamespace</span><span class="sxs-lookup"><span data-stu-id="1c764-118">ServiceBusNamespace</span></span>|<span data-ttu-id="1c764-119">Service Bus の名前空間</span><span class="sxs-lookup"><span data-stu-id="1c764-119">The Service Bus namespace</span></span>|  
    |<span data-ttu-id="1c764-120">IssuerName</span><span class="sxs-lookup"><span data-stu-id="1c764-120">IssuerName</span></span>|<span data-ttu-id="1c764-121">指定した名前空間の発行者名</span><span class="sxs-lookup"><span data-stu-id="1c764-121">Issuer Name for the specified namespace</span></span>|  
    |<span data-ttu-id="1c764-122">IssuerKey</span><span class="sxs-lookup"><span data-stu-id="1c764-122">IssuerKey</span></span>|<span data-ttu-id="1c764-123">指定した名前空間の発行者キー</span><span class="sxs-lookup"><span data-stu-id="1c764-123">Issuer Key for the specified namespace</span></span>|  
    |<span data-ttu-id="1c764-124">EDI agreement endpoint</span><span class="sxs-lookup"><span data-stu-id="1c764-124">EDI agreement endpoint</span></span>|<span data-ttu-id="1c764-125">EDI アグリーメントが展開されているエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="1c764-125">The endpoint where the EDI agreement is deployed.</span></span> <span data-ttu-id="1c764-126">受信の設定 タブから (とそのトランスポート ページ) は、このエンドポイントの URL を取得できますで展開した EDI アグリーメントの[ステップ 2 (Azure 用): EDI アグリーメントを作成する](../core/step-2-for-azure-create-an-edi-agreement.md)です。</span><span class="sxs-lookup"><span data-stu-id="1c764-126">You can get this endpoint URL from the Receive Settings tab (and within that, the Transport page) of the EDI agreement you deployed in [Step 2 (For Azure): Create an EDI Agreement](../core/step-2-for-azure-create-an-edi-agreement.md).</span></span>|  
    |<span data-ttu-id="1c764-127">MessageFilePath</span><span class="sxs-lookup"><span data-stu-id="1c764-127">MessageFilePath</span></span>|<span data-ttu-id="1c764-128">要求メッセージのサンプルを含むファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="1c764-128">Path to the file that contains the sample request message.</span></span>|  
    |<span data-ttu-id="1c764-129">ContentType</span><span class="sxs-lookup"><span data-stu-id="1c764-129">ContentType</span></span>|<span data-ttu-id="1c764-130">このチュートリアルでは、このパラメーターを設定**テキスト/プレーン**です。</span><span class="sxs-lookup"><span data-stu-id="1c764-130">For this tutorial, set this parameter to **text/plain**.</span></span>|  
  
     <span data-ttu-id="1c764-131">コマンド プロンプトを開き、ビルドしたソリューションに移動、 **MessageSender**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="1c764-131">Open a command prompt and navigate to the solution where you built the **MessageSender** project.</span></span> <span data-ttu-id="1c764-132">次のコマンドを実行し、注文数が 100 を超える要求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="1c764-132">Run the following command to send the request message with order quantity more than 100:</span></span>  
  
    ```  
    MessageSender.exe <service bus namespace> owner <issuer key>https://<namespace>.servicebus.appfabriclabs.com/7576ff3d-a0f3-4a46-a4f6-f5be4a50616a/DemoAgreement<path to the sample message> "text/plain"  
    ```  
  
3.  <span data-ttu-id="1c764-133">SQL Server Management Studio を開き、含まれているデータベースへの接続、 **SalesOrder**テーブル、および、新しいレコードがテーブルに挿入されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c764-133">Open SQL Server Management Studio, connect to the database that contains the **SalesOrder** table, and verify that a new record is inserted into the table.</span></span> <span data-ttu-id="1c764-134">値に注意してください、 **Qty**列である必要があります*121*です。</span><span class="sxs-lookup"><span data-stu-id="1c764-134">Notice the value in the **Qty** column; it must be *121*.</span></span>  
  
4.  <span data-ttu-id="1c764-135">使用して**MessageSender**別のメッセージがこの時間、数量の値の設定を送信するメッセージの順序付けに*99*です。</span><span class="sxs-lookup"><span data-stu-id="1c764-135">Use **MessageSender** to send another message, but this time set the value of the quantity ordered in the message to *99*.</span></span> <span data-ttu-id="1c764-136">現時点では、そのレコードは挿入されません、 **SalesOrder**テーブル。</span><span class="sxs-lookup"><span data-stu-id="1c764-136">You will notice that now, no record is inserted in the **SalesOrder** table.</span></span> <span data-ttu-id="1c764-137">代わりに、メッセージは、注文数量が 100 未満のメッセージを受信するために指定したファイルの場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="1c764-137">Instead, the message is copied to the file location you specified for receiving messages with order quantity less than 100.</span></span> <span data-ttu-id="1c764-138">受信したメッセージには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1c764-138">The received message resembles the following:</span></span>  
  
    ```  
    <ns1:SalesOrder xmlns:ns0="http://schemas.microsoft.com/BizTalk/EDI/X12/2006" xmlns:ns1="http://ECommerceSalesOrder.Inbound">  
      <CompanyCode>co</CompanyCode>  
      <PartID>1</PartID>  
      <Quantity>99</Quantity>  
      <AskPrice>10</AskPrice>  
      <RequestShipmentDate>2012-07-19</RequestShipmentDate>  
      <Address>  
        <Line1>Contoso</Line1>  
        <Line2>One Contoso Way</Line2>  
        <City>Redmond</City>  
        <State>WA</State>  
        <Country>US</Country>  
        <Zipcode>98052</Zipcode>  
      </Address>  
      <Contact>  
        <Firstname>John</Firstname>  
        <Lastname>John@contoso.com</Lastname>  
      </Contact>  
      <Comments>Order from Partnerco</Comments>  
      <DateNow>2012-06-19</DateNow>  
    </ns1:SalesOrder>  
  
    ```  
  
     <span data-ttu-id="1c764-139">値に注意してください、**数量**要素。</span><span class="sxs-lookup"><span data-stu-id="1c764-139">Notice the value in the **Quantity** element.</span></span> <span data-ttu-id="1c764-140">*99*です。</span><span class="sxs-lookup"><span data-stu-id="1c764-140">It is *99*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c764-141">参照</span><span class="sxs-lookup"><span data-stu-id="1c764-141">See Also</span></span>  
 [<span data-ttu-id="1c764-142">チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c764-142">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)