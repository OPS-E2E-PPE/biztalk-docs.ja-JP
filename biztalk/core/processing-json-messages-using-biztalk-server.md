---
title: BizTalk Server を使用して JSON メッセージの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6db1421-9478-477c-8645-09eefba06246
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7336b515d196fadc6e8e6cc4fe0bcf500b883189
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396982"
---
# <a name="processing-json-messages-using-biztalk-server"></a><span data-ttu-id="01c94-102">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="01c94-102">Processing JSON messages using BizTalk Server</span></span>
> [!NOTE]
>  <span data-ttu-id="01c94-103">このチュートリアルは、BizTalk Server にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="01c94-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="01c94-104">このチュートリアルを使用して JSON メッセージを処理する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="01c94-104">This tutorial demonstrates how to process JSON messages using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="01c94-105">チュートリアルでは、BizTalk Server で今すぐ使用できるカスタム パイプライン コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="01c94-105">The tutorial uses custom pipeline components, now available with BizTalk Server.</span></span> <span data-ttu-id="01c94-106">これらのパイプライン コンポーネントでは、JSON メッセージを XML に変換 (にメッセージを受信中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションとメッセージを送信するときにメッセージを XML から JSON に変換します。</span><span class="sxs-lookup"><span data-stu-id="01c94-106">These pipeline components convert the JSON message to XML (while receiving the message into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration, and converts the message from XML to JSON while sending the message out.</span></span>  
  
## <a name="what-does-this-tutorial-do"></a><span data-ttu-id="01c94-107">このチュートリアルの目的が何か。</span><span class="sxs-lookup"><span data-stu-id="01c94-107">What does this tutorial do?</span></span>  
 <span data-ttu-id="01c94-108">JSON の処理を示すためには、作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定の順序で、次を行うこと。</span><span class="sxs-lookup"><span data-stu-id="01c94-108">To demonstrate JSON processing, we create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that does the following, in the given order:</span></span>  
  
1. <span data-ttu-id="01c94-109">JSON 注文書を受信し、受信パイプラインで XML メッセージに JSON メッセージを変換する JSON デコーダー コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="01c94-109">Receives a JSON purchase order and in the receive pipeline, uses a JSON decoder component to transform the JSON message to XML message.</span></span>  
  
2. <span data-ttu-id="01c94-110">マップを使用して XML 請求書には、XML 注文書を変換します。</span><span class="sxs-lookup"><span data-stu-id="01c94-110">Transforms the XML purchase order into an XML invoice using a map.</span></span>  
  
3. <span data-ttu-id="01c94-111">送信パイプラインでに JSON 請求書の XML を変換する JSON エンコーダーを使用して請求書し、送信されます。</span><span class="sxs-lookup"><span data-stu-id="01c94-111">In the send pipeline, uses a JSON encoder to transform the XML invoice into a JSON invoice and sends it out.</span></span>  
  
   <span data-ttu-id="01c94-112">![BizTalk Server で JSON メッセージの処理](../core/media/btsjson-flow.png "BTSJSON_Flow")</span><span class="sxs-lookup"><span data-stu-id="01c94-112">![Processing JSON messages in BizTalk Server](../core/media/btsjson-flow.png "BTSJSON_Flow")</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="01c94-113">このチュートリアルを使用する方法は?</span><span class="sxs-lookup"><span data-stu-id="01c94-113">How to use this tutorial?</span></span>  
 <span data-ttu-id="01c94-114">このチュートリアルは、サンプルに構築されています (**BTSJSON**) からダウンロードできますが、 [MSDN コード ギャラリー](http://go.microsoft.com/fwlink/?LinkId=403197)します。</span><span class="sxs-lookup"><span data-stu-id="01c94-114">This tutorial is built around a sample (**BTSJSON**) that can be downloaded from the [MSDN Code Gallery](http://go.microsoft.com/fwlink/?LinkId=403197).</span></span> <span data-ttu-id="01c94-115">サンプルを使用して、サンプルの構築方法を理解するには、このチュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01c94-115">You could use the sample and go through this tutorial to understand how the sample was built.</span></span> <span data-ttu-id="01c94-116">または、独自のソリューション地上-アップを作成するこのチュートリアルを使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01c94-116">Or, you could use this tutorial to create your own solution ground-up.</span></span> <span data-ttu-id="01c94-117">このソリューションの構築方法を理解できるようにこのチュートリアルの 2 番目のアプローチが対象です。</span><span class="sxs-lookup"><span data-stu-id="01c94-117">This tutorial is targeted towards the second approach so that you understand how this solution was built.</span></span> <span data-ttu-id="01c94-118">また、可能な限り、チュートリアルはサンプルを使用して一貫性のある使用してアーティファクト (スキーマ、変換など) に同じ名前として、サンプルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="01c94-118">Also, as much as possible, the tutorial is consistent with the sample and uses the same names for artifacts (for example, schemas, transforms) as used in the sample.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01c94-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="01c94-119">In This Section</span></span>  
  
-   [<span data-ttu-id="01c94-120">JSON メッセージの XSD スキーマの生成</span><span class="sxs-lookup"><span data-stu-id="01c94-120">Generate an XSD schema for JSON message</span></span>](../core/generate-an-xsd-schema-for-json-message.md)  
  
-   [<span data-ttu-id="01c94-121">JSON メッセージ処理用のカスタム パイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="01c94-121">Create custom pipelines to process JSON messages</span></span>](../core/create-custom-pipelines-to-process-json-messages.md)  
  
-   [<span data-ttu-id="01c94-122">BizTalk Server のオーケストレーションの作成</span><span class="sxs-lookup"><span data-stu-id="01c94-122">Create a BizTalk Server orchestration</span></span>](../core/create-a-biztalk-server-orchestration.md)  
  
-   [<span data-ttu-id="01c94-123">アプリの配置およびテスト</span><span class="sxs-lookup"><span data-stu-id="01c94-123">Deploy and test the application</span></span>](../core/deploy-and-test-the-application.md)  
  
## <a name="see-also"></a><span data-ttu-id="01c94-124">参照</span><span class="sxs-lookup"><span data-stu-id="01c94-124">See Also</span></span>  
 [<span data-ttu-id="01c94-125">BizTalk Server チュートリアル</span><span class="sxs-lookup"><span data-stu-id="01c94-125">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)