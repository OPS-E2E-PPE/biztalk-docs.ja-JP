---
title: BizTalk Server チュートリアル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, getting started
- getting started, tutorials
ms.assetid: 58019f98-e91a-4705-b689-c269174d6bae
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f13a5d74d0957a208600653823e7604680296f4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232074"
---
# <a name="biztalk-server-tutorials"></a><span data-ttu-id="3a78e-102">BizTalk Server チュートリアル</span><span class="sxs-lookup"><span data-stu-id="3a78e-102">BizTalk Server Tutorials</span></span>
<span data-ttu-id="3a78e-103">使用する方法を説明するチュートリアル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3a78e-103">Tutorials to learn how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>

<span data-ttu-id="3a78e-104">BizTalk Server チュートリアルでは簡単なシナリオを用意しています。初めて BizTalk Server を使用する場合でも、さまざまな BizTalk ツールの使用方法を習得しながら、コンパイルされたテスト可能な統合ソリューションを作成する方法を学習できます。</span><span class="sxs-lookup"><span data-stu-id="3a78e-104">The BizTalk Server tutorials contain simple scenarios to give new users an experience of using a variety of BizTalk tools while creating compiled, testable integration solutions.</span></span> <span data-ttu-id="3a78e-105">高度なユーザー、または BizTalk ソリューションの設計は、ユーザーは、次を参照してください。[ビジネス ソリューションのシナリオ](../core/scenarios-for-business-solutions.md)です。</span><span class="sxs-lookup"><span data-stu-id="3a78e-105">For more advanced users, or users who are designing BizTalk solutions, see [Scenarios for Business Solutions](../core/scenarios-for-business-solutions.md).</span></span>  
  
## <a name="enterprise-application-integration"></a><span data-ttu-id="3a78e-106">エンタープライズ アプリケーション統合</span><span class="sxs-lookup"><span data-stu-id="3a78e-106">Enterprise Application Integration</span></span>
  
[<span data-ttu-id="3a78e-107">チュートリアル: エンタープライズ アプリケーション統合</span><span class="sxs-lookup"><span data-stu-id="3a78e-107">Tutorial: Enterprise Application Integration</span></span>](../core/tutorial-1-enterprise-application-integration.md) 

<span data-ttu-id="3a78e-108">倉庫から在庫補充要求メッセージを受信し、要求メッセージを評価する BizTalk ソリューションを実装します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-108">Implement a BizTalk solution that receives inventory replenishment request messages from a warehouse, and evaluates the request messages.</span></span> <span data-ttu-id="3a78e-109">ソリューションは、要求を拒否する場合は、倉庫に拒否メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-109">If the solution denies a request, then it sends a decline message to the warehouse.</span></span> <span data-ttu-id="3a78e-110">ソリューションでは、要求を承認する場合は、エンタープライズ リソース プランニング (ERP) システムにメッセージが転送されます。</span><span class="sxs-lookup"><span data-stu-id="3a78e-110">If the solution approves a request, then it forwards the message to an Enterprise Resource Planning (ERP) system.</span></span>  

## <a name="create-a-hybrid-application"></a><span data-ttu-id="3a78e-111">ハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-111">Create a Hybrid Application</span></span>
[<span data-ttu-id="3a78e-112">チュートリアル: BizTalk Server を使用してハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-112">Tutorial: Creating a Hybrid Application Using BizTalk Server</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)  

<span data-ttu-id="3a78e-113">EDI を使用してメッセージを受信するサービス バスの受信確認を生成するエンド ツー エンド アプリケーションを設定し、SQL にデータを挿入します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-113">Set up an end-to-end application that uses EDI to generate acknowledgements, Service Bus to receive messages, and then insert data into SQL.</span></span> 

## <a name="invoke-a-rest-interface"></a><span data-ttu-id="3a78e-114">REST インターフェイスを呼び出します</span><span class="sxs-lookup"><span data-stu-id="3a78e-114">Invoke a REST Interface</span></span>
[<span data-ttu-id="3a78e-115">チュートリアル: BizTalk Server を使用して REST インターフェイスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="3a78e-115">Tutorial: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)  

<span data-ttu-id="3a78e-116">REST の URL を使用し、応答メッセージを送信する Wcf-webhttp アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-116">Uses the WCF-WebHttp adapter to use a REST URL, and then send a response message.</span></span> 

## <a name="integrate-biztalk-with-salesforce"></a><span data-ttu-id="3a78e-117">Salesforce と BizTalk を統合します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-117">Integrate BizTalk with Salesforce</span></span>
[<span data-ttu-id="3a78e-118">チュートリアル: BizTalk Server の Salesforce との統合</span><span class="sxs-lookup"><span data-stu-id="3a78e-118">Tutorial: Integrating BizTalk Server with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)  

<span data-ttu-id="3a78e-119">Salesforce システムでは、営業案件を作成するたびに、Northwind には、通知を受ける他の下流システムがそのデータを取得したり、他の関連するプロセスを開始できるように、BizTalk Server などの内部設置型システムが希望しています。</span><span class="sxs-lookup"><span data-stu-id="3a78e-119">Every time a sales opportunity is created in the Salesforce system, Northwind wants its on-premise systems, such as BizTalk Server, to be notified so that other downstream systems can pick up that data and start other relevant processes.</span></span> 

## <a name="process-json-messages"></a><span data-ttu-id="3a78e-120">JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="3a78e-120">Process JSON messages</span></span>
[<span data-ttu-id="3a78e-121">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="3a78e-121">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)  

<span data-ttu-id="3a78e-122">JSON 注文書を受信する BizTalk アプリケーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-122">Set up a BizTalk application that receives a JSON purchase order.</span></span> <span data-ttu-id="3a78e-123">受信パイプラインでは、JSON デコーダー コンポーネントは、JSON メッセージを XML メッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-123">In the receive pipeline, a JSON decoder component transforms the JSON message to XML message.</span></span> <span data-ttu-id="3a78e-124">次に、マップを使用して XML 注文を XML 請求書に変換します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-124">Then, uses a map to transform the XML purchase order into an XML invoice.</span></span> <span data-ttu-id="3a78e-125">送信パイプラインは、JSON 請求書では、XML 請求書に変換する JSON エンコーダーを使用し、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-125">The send pipeline uses a JSON encoder to transform the XML invoice into a JSON invoice, and then sends the message.</span></span>

## <a name="edi-interface-developer"></a><span data-ttu-id="3a78e-126">EDI インターフェイス開発</span><span class="sxs-lookup"><span data-stu-id="3a78e-126">EDI Interface Developer</span></span>
  [<span data-ttu-id="3a78e-127">チュートリアル: EDI インターフェイス開発チュートリアル</span><span class="sxs-lookup"><span data-stu-id="3a78e-127">Tutorial: EDI Interface Developer Tutorial</span></span>](../core/tutorial-2-edi-interface-developer-tutorial.md)
  
<span data-ttu-id="3a78e-128">取引先は ANSI X12 を使用して発注書送信 4010 850 トランザクション セット (850 メッセージ)。</span><span class="sxs-lookup"><span data-stu-id="3a78e-128">A trading partner sends purchase orders using the ANSI X12 4010 850 transaction set (an 850 message).</span></span> <span data-ttu-id="3a78e-129">内部の注文システム プロセスは発注書です。</span><span class="sxs-lookup"><span data-stu-id="3a78e-129">An internal order system processes purchase orders.</span></span>

<span data-ttu-id="3a78e-130">インターフェイス開発者 850 メッセージの間のインターフェイスを設計するため、としては、取引先と、会社の内部の注文システムから表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a78e-130">As an interface developer responsible for designing the interface between the 850 message, you receive from your trading partner and your company’s internal Order System.</span></span> <span data-ttu-id="3a78e-131">取引先は、送信する 850 メッセージごとに機能確認 (997) を要求します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-131">Your trading partner requires a Functional Acknowledgement (997) for each 850 message it sends.</span></span>


## <a name="as2"></a><span data-ttu-id="3a78e-132">AS2</span><span class="sxs-lookup"><span data-stu-id="3a78e-132">AS2</span></span>  
[<span data-ttu-id="3a78e-133">チュートリアル: AS2 チュートリアル</span><span class="sxs-lookup"><span data-stu-id="3a78e-133">Tutorial: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)

<span data-ttu-id="3a78e-134">受信および HTTP トランスポートを介して EDIINT/AS2 でエンコードされたメッセージを送信するソリューションを設定します。</span><span class="sxs-lookup"><span data-stu-id="3a78e-134">Set up a solution that receives and sends EDIINT/AS2-encoded messages over an HTTP transport.</span></span>    


## <a name="do-more"></a><span data-ttu-id="3a78e-135">複数の操作を行います</span><span class="sxs-lookup"><span data-stu-id="3a78e-135">Do more</span></span>  
 <span data-ttu-id="3a78e-136">BizTalk Server の概念とアーキテクチャの詳細については、次のことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="3a78e-136">To learn more about BizTalk Server concepts and architecture, consider the following:</span></span>  
  
[<span data-ttu-id="3a78e-137">開始するには</span><span class="sxs-lookup"><span data-stu-id="3a78e-137">Get started</span></span>](../core/getting-started-with-biztalk-server.md)
  
[<span data-ttu-id="3a78e-138">計画し、BizTalk Server ソリューションの設計</span><span class="sxs-lookup"><span data-stu-id="3a78e-138">Plan and architect your BizTalk Server solution</span></span>](../core/plan-and-architect-your-biztalk-server-solution.md)