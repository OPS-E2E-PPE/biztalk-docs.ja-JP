---
title: Namespace コンポーネント サンプルを実行する |Microsoft Docs
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
ms.openlocfilehash: 31a7ced4587f693c13f3fd45f24057eb882f1d43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242722"
---
# <a name="running-the-namespace-component-sample"></a><span data-ttu-id="7d544-102">Namespace コンポーネント サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="7d544-102">Running the Namespace Component Sample</span></span>
<span data-ttu-id="7d544-103">Namespace コンポーネントのサンプル アプリケーションを含む 4 つの場所/送信ポートのペアを受信します。</span><span class="sxs-lookup"><span data-stu-id="7d544-103">The Namespace Component sample application contains four receive location/send port pairs.</span></span> <span data-ttu-id="7d544-104">各ペアは、テストを表します。</span><span class="sxs-lookup"><span data-stu-id="7d544-104">Each pair represents a test.</span></span> <span data-ttu-id="7d544-105">以下は、4 つのテストです。</span><span class="sxs-lookup"><span data-stu-id="7d544-105">The following are the four tests:</span></span>  

- <span data-ttu-id="7d544-106">**パススルーに追加**します。</span><span class="sxs-lookup"><span data-stu-id="7d544-106">**Add to Pass-through**.</span></span> <span data-ttu-id="7d544-107">このテストでは、XML メッセージ ドキュメントに名前空間を追加し、新しい名前空間を表示することは、ファイルに直接メッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7d544-107">This test adds a namespace to an XML message document and writes the message directly to a file so that you can see the new namespace.</span></span> <span data-ttu-id="7d544-108">このテストの入力ファイルでは、TEST_Add_to_PassThrough.0000.ns.xml です。</span><span class="sxs-lookup"><span data-stu-id="7d544-108">The input file for this test is TEST_Add_to_PassThrough.0000.ns.xml.</span></span> <span data-ttu-id="7d544-109">このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="7d544-109">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component.</span></span>  

- <span data-ttu-id="7d544-110">**削除する追加**します。</span><span class="sxs-lookup"><span data-stu-id="7d544-110">**Add to Remove**.</span></span> <span data-ttu-id="7d544-111">このテストでは、XML ドキュメントのメッセージに名前空間を追加しから削除します。</span><span class="sxs-lookup"><span data-stu-id="7d544-111">This test adds a namespace to an XML document message and then removes it.</span></span> <span data-ttu-id="7d544-112">ファイルに直接メッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7d544-112">It then writes the message directly to a file.</span></span> <span data-ttu-id="7d544-113">The input file for this test is TEST_ Add_to_Remove.0000.ns.xml.</span><span class="sxs-lookup"><span data-stu-id="7d544-113">The input file for this test is TEST_ Add_to_Remove.0000.ns.xml.</span></span> <span data-ttu-id="7d544-114">このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネントと**NamespaceSampleSendPipeline** を格納している**RemoveNamespace**コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="7d544-114">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component and the **NamespaceSampleSendPipeline** that contains a **RemoveNamespace** component.</span></span>  

- <span data-ttu-id="7d544-115">**削除するにはパススルー**します。</span><span class="sxs-lookup"><span data-stu-id="7d544-115">**Pass-through to Remove**.</span></span> <span data-ttu-id="7d544-116">このテストでは、XML ドキュメントのメッセージからすべての名前空間を削除し、これを確認できるように、ファイルに直接、メッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7d544-116">This test removes all namespaces from an XML document message and writes the message directly to a file so that you can confirm this.</span></span> <span data-ttu-id="7d544-117">このテストの入力ファイルでは、TEST_PassThrough_to_Remove.0000.ns.xml です。</span><span class="sxs-lookup"><span data-stu-id="7d544-117">The input file for this test is TEST_PassThrough_to_Remove.0000.ns.xml.</span></span> <span data-ttu-id="7d544-118">このテストでは、 **NamespaceSampleSendPipeline**を格納している、 **RemoveNamespace**コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="7d544-118">This test uses the **NamespaceSampleSendPipeline** that contains a **RemoveNamespace** component.</span></span>  

- <span data-ttu-id="7d544-119">**パススルーに抽出を使用して追加**します。</span><span class="sxs-lookup"><span data-stu-id="7d544-119">**Add Via Extraction to Pass-through**.</span></span> <span data-ttu-id="7d544-120">このテストの抽出、 **OrderDetails** XML の要素が、直接ファイルには、この要素を含む新しいメッセージをメッセージと書き込みをドキュメントします。</span><span class="sxs-lookup"><span data-stu-id="7d544-120">This test extracts the **OrderDetails** element of an XML document message and writes a new message containing this element directly to a file.</span></span> <span data-ttu-id="7d544-121">このテストの入力ファイルでは、TEST_AddViaExtraction_to_PassThrough.0000.ns.xml です。</span><span class="sxs-lookup"><span data-stu-id="7d544-121">The input file for this test is TEST_AddViaExtraction_to_PassThrough.0000.ns.xml.</span></span> <span data-ttu-id="7d544-122">このテストでは、 **NamespaceSampleReceivePipeline**を格納している、 **AddNamespace**コンポーネントを**ExtractionNodeXPath**プロパティに設定 **/CanonicalOrder/OrderDetails** (要素を返す任意の有効な XPath がこのプロパティで十分です)。</span><span class="sxs-lookup"><span data-stu-id="7d544-122">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component with the **ExtractionNodeXPath** property set to **/CanonicalOrder/OrderDetails** (any valid XPath that returns an element will suffice for this property).</span></span>  

  <span data-ttu-id="7d544-123">サンプル アプリケーションで基になる受信場所は、テストの種類ごとに該当するファイル マスクを持ち、受信ポート名での関連する送信ポート フィルター。</span><span class="sxs-lookup"><span data-stu-id="7d544-123">The underlying receive locations in the sample application have file masks that are appropriate for each of the test types, and the related send ports filter on the receive port name.</span></span> <span data-ttu-id="7d544-124">そのため、テストを実行するだけを削除する、適切に名前付きのメッセージを入力フォルダーに。</span><span class="sxs-lookup"><span data-stu-id="7d544-124">Therefore, to execute a test, you just drop the appropriately named message into the input folder.</span></span> <span data-ttu-id="7d544-125">サンプル アプリケーションはテストを実行し、現在のテストでは、適切な名前を使用して、メッセージの ID を含む、出力フォルダーに更新されたメッセージをドロップします。</span><span class="sxs-lookup"><span data-stu-id="7d544-125">The sample application executes the test and drops the updated message into the output folder using a name appropriate for the current test, and including the Message ID.</span></span>  

  <span data-ttu-id="7d544-126">このセクションでは、次のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7d544-126">This section contains the following topics:</span></span>  

- [<span data-ttu-id="7d544-127">名前空間コンポーネント テストを実行する</span><span class="sxs-lookup"><span data-stu-id="7d544-127">Running the Namespace Component Tests</span></span>](../esb-toolkit/running-the-namespace-component-tests.md)  

- [<span data-ttu-id="7d544-128">名前空間の追加サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="7d544-128">How the Add Namespace Sample Works</span></span>](../esb-toolkit/how-the-add-namespace-sample-works.md)  

- [<span data-ttu-id="7d544-129">名前空間の削除サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="7d544-129">How the Remove Namespace Sample Works</span></span>](../esb-toolkit/how-the-remove-namespace-sample-works.md)
