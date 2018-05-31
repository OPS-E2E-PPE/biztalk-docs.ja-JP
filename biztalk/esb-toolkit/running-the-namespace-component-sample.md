---
title: Namespace コンポーネント サンプルを実行している |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f334a8-06de-4a56-a41a-3df088bf4a72
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fc142ca70971f023e491dbdeee693a8d41c42fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295298"
---
# <a name="running-the-namespace-component-sample"></a><span data-ttu-id="d0675-102">Namespace コンポーネント サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0675-102">Running the Namespace Component Sample</span></span>
<span data-ttu-id="d0675-103">Namespace コンポーネント サンプル アプリケーションを含む 4 つの場所/送信ポートのペアを受信します。</span><span class="sxs-lookup"><span data-stu-id="d0675-103">The Namespace Component sample application contains four receive location/send port pairs.</span></span> <span data-ttu-id="d0675-104">各ペアは、テストを表します。</span><span class="sxs-lookup"><span data-stu-id="d0675-104">Each pair represents a test.</span></span> <span data-ttu-id="d0675-105">4 つのテストを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d0675-105">The following are the four tests:</span></span>  
  
-   <span data-ttu-id="d0675-106">**パススルーに追加**です。</span><span class="sxs-lookup"><span data-stu-id="d0675-106">**Add to Pass-through**.</span></span> <span data-ttu-id="d0675-107">このテストでは、XML メッセージ ドキュメントに名前空間を追加し、新しい名前空間を認識できるように、ファイルに直接メッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="d0675-107">This test adds a namespace to an XML message document and writes the message directly to a file so that you can see the new namespace.</span></span> <span data-ttu-id="d0675-108">このテストの入力ファイルでは、TEST_Add_to_PassThrough.0000.ns.xml です。</span><span class="sxs-lookup"><span data-stu-id="d0675-108">The input file for this test is TEST_Add_to_PassThrough.0000.ns.xml.</span></span> <span data-ttu-id="d0675-109">このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d0675-109">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component.</span></span>  
  
-   <span data-ttu-id="d0675-110">**削除する追加**です。</span><span class="sxs-lookup"><span data-stu-id="d0675-110">**Add to Remove**.</span></span> <span data-ttu-id="d0675-111">このテストでは、XML ドキュメントのメッセージに名前空間を追加、削除されます。</span><span class="sxs-lookup"><span data-stu-id="d0675-111">This test adds a namespace to an XML document message and then removes it.</span></span> <span data-ttu-id="d0675-112">これは、後、ファイルに直接メッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="d0675-112">It then writes the message directly to a file.</span></span> <span data-ttu-id="d0675-113">このテストの入力ファイルでは、test _ Add_to_Remove.0000.ns.xml です。</span><span class="sxs-lookup"><span data-stu-id="d0675-113">The input file for this test is TEST_ Add_to_Remove.0000.ns.xml.</span></span> <span data-ttu-id="d0675-114">このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネントおよび**NamespaceSampleSendPipeline**を含む、 **RemoveNamespace**コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d0675-114">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component and the **NamespaceSampleSendPipeline** that contains a **RemoveNamespace** component.</span></span>  
  
-   <span data-ttu-id="d0675-115">**削除するにはパススルー**です。</span><span class="sxs-lookup"><span data-stu-id="d0675-115">**Pass-through to Remove**.</span></span> <span data-ttu-id="d0675-116">このテストでは、XML ドキュメントのメッセージからすべての名前空間を削除しが確認できるように、ファイルに直接メッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="d0675-116">This test removes all namespaces from an XML document message and writes the message directly to a file so that you can confirm this.</span></span> <span data-ttu-id="d0675-117">このテストの入力ファイルでは、TEST_PassThrough_to_Remove.0000.ns.xml です。</span><span class="sxs-lookup"><span data-stu-id="d0675-117">The input file for this test is TEST_PassThrough_to_Remove.0000.ns.xml.</span></span> <span data-ttu-id="d0675-118">このテストでは、 **NamespaceSampleSendPipeline**を格納している、 **RemoveNamespace**コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d0675-118">This test uses the **NamespaceSampleSendPipeline** that contains a **RemoveNamespace** component.</span></span>  
  
-   <span data-ttu-id="d0675-119">**抽出パススルーを使用して追加**です。</span><span class="sxs-lookup"><span data-stu-id="d0675-119">**Add Via Extraction to Pass-through**.</span></span> <span data-ttu-id="d0675-120">このテストの抽出、 **OrderDetails** XML の要素と文書化メッセージの書き込み、ファイルに直接には、この要素を含む新しいメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d0675-120">This test extracts the **OrderDetails** element of an XML document message and writes a new message containing this element directly to a file.</span></span> <span data-ttu-id="d0675-121">このテストの入力ファイルでは、TEST_AddViaExtraction_to_PassThrough.0000.ns.xml です。</span><span class="sxs-lookup"><span data-stu-id="d0675-121">The input file for this test is TEST_AddViaExtraction_to_PassThrough.0000.ns.xml.</span></span> <span data-ttu-id="d0675-122">このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネントを**ExtractionNodeXPath**プロパティに設定 **/CanonicalOrder/OrderDetails** (要素を返す任意の有効な XPath がこのプロパティには十分)。</span><span class="sxs-lookup"><span data-stu-id="d0675-122">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component with the **ExtractionNodeXPath** property set to **/CanonicalOrder/OrderDetails** (any valid XPath that returns an element will suffice for this property).</span></span>  
  
 <span data-ttu-id="d0675-123">サンプル アプリケーションで基になる受信場所はテストの種類ごとに該当するファイル マスクを持ち、関連する送信ポート フィルターを受信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="d0675-123">The underlying receive locations in the sample application have file masks that are appropriate for each of the test types, and the related send ports filter on the receive port name.</span></span> <span data-ttu-id="d0675-124">そのため、テストを実行するだけにドロップする適切に名前付きのメッセージ入力フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="d0675-124">Therefore, to execute a test, you just drop the appropriately named message into the input folder.</span></span> <span data-ttu-id="d0675-125">サンプル アプリケーションのテストを実行し、現在のテストでは、適切な名前を使用して、メッセージの ID を含む出力フォルダーに、更新されたメッセージをドロップ</span><span class="sxs-lookup"><span data-stu-id="d0675-125">The sample application executes the test and drops the updated message into the output folder using a name appropriate for the current test, and including the Message ID.</span></span>  
  
 <span data-ttu-id="d0675-126">このセクションのトピックは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d0675-126">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="d0675-127">Namespace コンポーネントのテストを実行しています。</span><span class="sxs-lookup"><span data-stu-id="d0675-127">Running the Namespace Component Tests</span></span>](../esb-toolkit/running-the-namespace-component-tests.md)  
  
-   [<span data-ttu-id="d0675-128">どのように Namespace サンプルは、動作を追加</span><span class="sxs-lookup"><span data-stu-id="d0675-128">How the Add Namespace Sample Works</span></span>](../esb-toolkit/how-the-add-namespace-sample-works.md)  
  
-   [<span data-ttu-id="d0675-129">削除 Namespace サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="d0675-129">How the Remove Namespace Sample Works</span></span>](../esb-toolkit/how-the-remove-namespace-sample-works.md)