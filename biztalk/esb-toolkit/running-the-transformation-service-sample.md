---
title: 変換サービスのサンプルを実行している |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42064d32-5ec5-4219-a338-c5769969b958
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ac733f3164a319ed0b86e0f609de8ccd03bdbca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295234"
---
# <a name="running-the-transformation-service-sample"></a><span data-ttu-id="de2c3-102">変換サービス サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="de2c3-102">Running the Transformation Service Sample</span></span>
<span data-ttu-id="de2c3-103">好きなツール、Web サービス メソッドを実行できるユーティリティを使用して変換サービス サンプルを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="de2c3-103">You can execute the Transformation Service sample using any tool or utility that can execute Web service methods.</span></span> <span data-ttu-id="de2c3-104">たとえば、Storm から使用可能なを使用することができます[CodePlex](http://go.microsoft.com/fwlink/?LinkId=187762) ([http://go.microsoft.com/fwlink/?LinkId=187762](http://go.microsoft.com/fwlink/?LinkId=187762))、変換の Web サービスを呼び出す独自のテスト クライアントを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="de2c3-104">For example, you can use Storm, available from [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187762) ([http://go.microsoft.com/fwlink/?LinkId=187762](http://go.microsoft.com/fwlink/?LinkId=187762)), or you can create your own test client that invokes the Transformation Web service.</span></span>  
  
 <span data-ttu-id="de2c3-105">変換サービス サンプルの正しいインストールをテストする、.NET の Web サービスの Studio を使用するに変換の ASMX ベースの Web サービスの URL を入力、 **WSDL エンドポイント**テキスト ボックスに入力し、 **取得**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="de2c3-105">To use the .NET Web Service Studio to test for correct installation of the Transformation Service sample, enter the URL for the ASMX-based Transformation Web service into the **WSDL EndPoint** text box, and then click the **Get** button.</span></span> <span data-ttu-id="de2c3-106">これには、図 1 に示すように、ESB 変換 Web サービスの呼び出しに使用できるクライアントのフロント エンド インターフェイスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="de2c3-106">This generates a client front-end interface that you can use to call the ESB Transformation Web Service, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="de2c3-107">![変換サービス](../esb-toolkit/media/ch6-transformationservice.gif "Ch6 TransformationService")</span><span class="sxs-lookup"><span data-stu-id="de2c3-107">![Transformation Service](../esb-toolkit/media/ch6-transformationservice.gif "Ch6-TransformationService")</span></span>  
  
 <span data-ttu-id="de2c3-108">**図 1**</span><span class="sxs-lookup"><span data-stu-id="de2c3-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="de2c3-109">**.NET Web サービスの Studio を使用して変換サービスのサンプルをテストするには**</span><span class="sxs-lookup"><span data-stu-id="de2c3-109">**Using the .NET Web Service Studio to test the Transformation Service sample**</span></span>  
  
 <span data-ttu-id="de2c3-110">変換サービスのサンプルには、2 つの Microsoft BizTalk マップが含まれています、2 つのテスト メッセージの XML ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="de2c3-110">The Transformation Service sample contains two Microsoft BizTalk maps and two test XML message documents.</span></span> <span data-ttu-id="de2c3-111">TEST_CanonicalOrder_to_OrderConfirmation.xml および TEST_RetailOrder_to_CanonicalOrder.xml (\Source\Samples\TransformServices\Test\Data フォルダーにあります) という名前の XML メッセージでは、変換の Web サービスを実行できます。</span><span class="sxs-lookup"><span data-stu-id="de2c3-111">You can execute the Transformation Web service with the XML messages named TEST_CanonicalOrder_to_OrderConfirmation.xml and TEST_RetailOrder_to_CanonicalOrder.xml (located in the \Source\Samples\TransformServices\Test\Data folder).</span></span>  
  
 <span data-ttu-id="de2c3-112">サービスは CanonicalOrder.xsd および RetailOrder.xsd OrderConfirmation.xsd (、\Source\Samples\TransformServices\Source\ESB にありますスキーマを使用してメッセージを自動的に変換します。TransformServices.Schemas フォルダーの場合)、.NET Web サービス Studio は、結果として得られる変換されたメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="de2c3-112">The service will automatically transform the messages using the schemas CanonicalOrder.xsd and RetailOrder.xsd and OrderConfirmation.xsd (located in the \Source\Samples\TransformServices\Source\ESB.TransformServices.Schemas folder), and .NET Web Service Studio will display the resulting transformed messages.</span></span> <span data-ttu-id="de2c3-113">次の手順では、CanonicalOrder_To_OrderConfirmation マップをテストする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="de2c3-113">The following procedure shows how you can test the CanonicalOrder_To_OrderConfirmation map.</span></span>  
  
 <span data-ttu-id="de2c3-114">**GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_OrderConfirmation マップをテストするには**</span><span class="sxs-lookup"><span data-stu-id="de2c3-114">**To test the GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_OrderConfirmation map**</span></span>  
  
1.  <span data-ttu-id="de2c3-115">GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="de2c3-115">If the GlobalBank.ESB application is not running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="de2c3-116">値として、TEST_CanonicalOrder_to_OrderConfirmation.xml ファイルの次の文字列表現を入力、**メッセージ**内のパラメーター、**入力**ツリー .NET Web サービス Studio のビューです。</span><span class="sxs-lookup"><span data-stu-id="de2c3-116">Enter the following string representation of the TEST_CanonicalOrder_to_OrderConfirmation.xml file as the value of the **message** parameter in the **Input** tree view of .NET Web Service Studio.</span></span> <span data-ttu-id="de2c3-117">この文字列は、GlobalBank.ESB.TransformServices.Schemas.CanonicalOrder スキーマに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="de2c3-117">This string conforms to the GlobalBank.ESB.TransformServices.Schemas.CanonicalOrder schema:</span></span>  
  
    ```  
    <ns0:CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1"   
        Status="Status_2" xmlns:ns0=  
        "http://schemas.globalbank.esb.transformservices.com">  
        <OrderHeader><CustomerName>CustomerName_0</CustomerName>  
        <CustomerID>CustomerID_0</CustomerID><ShipToLine1>  
        ShipToLine1_0</ShipToLine1><ShipToLine2>ShipToLine2_0  
        </ShipToLine2><BillToLine1>BillToLine1_0</BillToLine1>  
        <BillToLine2>BillToLine2_0</BillToLine2><OrderTotal>OrderTotal_0  
        </OrderTotal></OrderHeader><OrderDetails><LineItem Qty="Qty_0"   
        PartNum="PartNum_1" Description="Description_2"   
        UnitPrice="UnitPrice_3" Ext="Ext_4" /></OrderDetails>  
        <B2BPartnerDetails CreditLimit="CreditLimit_0"   
        AccountBalance="AccountBalance_1"   
        LastOrderedData="LastOrderedData_2"   
        DiscountLevel="DiscountLevel_3" /></ns0:CanonicalOrder>  
    ```  
  
3.  <span data-ttu-id="de2c3-118">値として、次の文字列を入力、 **mapName**内のパラメーター、**入力**ツリー .NET Web サービス Studio のビューです。</span><span class="sxs-lookup"><span data-stu-id="de2c3-118">Enter the following string as the value of the **mapName** parameter in the **Input** tree view of .NET Web Service Studio.</span></span> <span data-ttu-id="de2c3-119">これは、メッセージに対して実行する BizTalk マップの完全な型指定された名前です。</span><span class="sxs-lookup"><span data-stu-id="de2c3-119">This is the fully typed name of the BizTalk map to execute against the message:</span></span>  
  
    ```  
    GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_  
        OrderConfirmation, GlobalBank.ESB.TransformServices.Maps,   
        Version=1.0.0.0, Culture=neutral, PublicKeyToken=<insertYourPublicKeyTokenHere>  
    ```  
  
4.  <span data-ttu-id="de2c3-120">クリックして、 **Invoke** Web サービスを実行するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="de2c3-120">Click the **Invoke** button to execute the Web service.</span></span> <span data-ttu-id="de2c3-121">**出力**テスト ボックスには、結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de2c3-121">The **Output** test box displays the results.</span></span>