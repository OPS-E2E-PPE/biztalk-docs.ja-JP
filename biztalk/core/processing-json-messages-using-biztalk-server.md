---
title: "BizTalk Server を使用して JSON メッセージの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6db1421-9478-477c-8645-09eefba06246
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ea474e3717ec69dfe04261ba144a46350223856
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="processing-json-messages-using-biztalk-server"></a><span data-ttu-id="4f69a-102">BizTalk Server を使用した JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="4f69a-102">Processing JSON messages using BizTalk Server</span></span>
> [!NOTE]
>  <span data-ttu-id="4f69a-103">このチュートリアルは、[!INCLUDE[prague](../includes/prague-md.md)] のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="4f69a-103">This tutorial applies to [!INCLUDE[prague](../includes/prague-md.md)] only.</span></span>  
  
 <span data-ttu-id="4f69a-104">このチュートリアルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して JSON メッセージを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4f69a-104">This tutorial demonstrates how to process JSON messages using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4f69a-105">チュートリアルでは、[!INCLUDE[prague](../includes/prague-md.md)] から入手可能なカスタム パイプライン コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f69a-105">The tutorial uses custom pipeline components, now available with [!INCLUDE[prague](../includes/prague-md.md)].</span></span> <span data-ttu-id="4f69a-106">これらのパイプライン コンポーネントでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションでメッセージを受信して JSON メッセージを XML に変換し、メッセージの送信時にメッセージを XML から JSON に変換します。</span><span class="sxs-lookup"><span data-stu-id="4f69a-106">These pipeline components convert the JSON message to XML (while receiving the message into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration, and converts the message from XML to JSON while sending the message out.</span></span>  
  
## <a name="what-does-this-tutorial-do"></a><span data-ttu-id="4f69a-107">このチュートリアルの目的</span><span class="sxs-lookup"><span data-stu-id="4f69a-107">What does this tutorial do?</span></span>  
 <span data-ttu-id="4f69a-108">次の内容を次の順序で実行する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を作成して、JSON の処理方法を示します:</span><span class="sxs-lookup"><span data-stu-id="4f69a-108">To demonstrate JSON processing, we create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that does the following, in the given order:</span></span>  
  
1.  <span data-ttu-id="4f69a-109">JSON 注文書を受信して、受信パイプラインで JSON デコーダー コンポーネントを使用して JSON メッセージを XML メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="4f69a-109">Receives a JSON purchase order and in the receive pipeline, uses a JSON decoder component to transform the JSON message to XML message.</span></span>  
  
2.  <span data-ttu-id="4f69a-110">マップを使用して XML 注文書を XML 請求書に変換します。</span><span class="sxs-lookup"><span data-stu-id="4f69a-110">Transforms the XML purchase order into an XML invoice using a map.</span></span>  
  
3.  <span data-ttu-id="4f69a-111">送信パイプラインで、JSON エンコーダーを使用して XML 請求書を JSON 請求書に変換して送信します。</span><span class="sxs-lookup"><span data-stu-id="4f69a-111">In the send pipeline, uses a JSON encoder to transform the XML invoice into a JSON invoice and sends it out.</span></span>  
  
 <span data-ttu-id="4f69a-112">![BizTalk Server での JSON メッセージの処理](../core/media/btsjson-flow.png "BTSJSON_Flow")</span><span class="sxs-lookup"><span data-stu-id="4f69a-112">![Processing JSON messages in BizTalk Server](../core/media/btsjson-flow.png "BTSJSON_Flow")</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="4f69a-113">このチュートリアルの使用方法</span><span class="sxs-lookup"><span data-stu-id="4f69a-113">How to use this tutorial?</span></span>  
 <span data-ttu-id="4f69a-114">このチュートリアルが構築されています。 サンプル (**BTSJSON**) からダウンロードすることができます、 [MSDN コード ギャラリー](http://go.microsoft.com/fwlink/?LinkId=403197)です。</span><span class="sxs-lookup"><span data-stu-id="4f69a-114">This tutorial is built around a sample (**BTSJSON**) that can be downloaded from the [MSDN Code Gallery](http://go.microsoft.com/fwlink/?LinkId=403197).</span></span> <span data-ttu-id="4f69a-115">サンプルを使用してチュートリアルを進めることで、サンプルが構築された方法を理解しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="4f69a-115">You could use the sample and go through this tutorial to understand how the sample was built.</span></span> <span data-ttu-id="4f69a-116">または、このチュートリアルで独自のソリューションを作り上げることもできます。</span><span class="sxs-lookup"><span data-stu-id="4f69a-116">Or, you could use this tutorial to create your own solution ground-up.</span></span> <span data-ttu-id="4f69a-117">このチュートリアルは、このソリューションがどのように構築されたかを理解できるよう、2 つ目のアプローチに向けて作成されています。</span><span class="sxs-lookup"><span data-stu-id="4f69a-117">This tutorial is targeted towards the second approach so that you understand how this solution was built.</span></span> <span data-ttu-id="4f69a-118">また、このチュートリアルでは、可能な限りサンプルに合わせて、サンプルで使用されているのと同じアイテム名 (スキーマ、変換など) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="4f69a-118">Also, as much as possible, the tutorial is consistent with the sample and uses the same names for artifacts (for example, schemas, transforms) as used in the sample.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f69a-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4f69a-119">In This Section</span></span>  
  
-   [<span data-ttu-id="4f69a-120">JSON メッセージの XSD スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="4f69a-120">Generate an XSD schema for JSON message</span></span>](../core/generate-an-xsd-schema-for-json-message.md)  
  
-   [<span data-ttu-id="4f69a-121">JSON メッセージを処理するカスタム パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f69a-121">Create custom pipelines to process JSON messages</span></span>](../core/create-custom-pipelines-to-process-json-messages.md)  
  
-   [<span data-ttu-id="4f69a-122">BizTalk Server オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f69a-122">Create a BizTalk Server orchestration</span></span>](../core/create-a-biztalk-server-orchestration.md)  
  
-   [<span data-ttu-id="4f69a-123">展開し、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="4f69a-123">Deploy and test the application</span></span>](../core/deploy-and-test-the-application.md)  
  
## <a name="see-also"></a><span data-ttu-id="4f69a-124">参照</span><span class="sxs-lookup"><span data-stu-id="4f69a-124">See Also</span></span>  
 [<span data-ttu-id="4f69a-125">BizTalk Server チュートリアル</span><span class="sxs-lookup"><span data-stu-id="4f69a-125">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)