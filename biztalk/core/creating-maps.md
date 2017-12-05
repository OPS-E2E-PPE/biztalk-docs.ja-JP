---
title: "マップの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc9f8ad1-4aad-4866-8aa4-4877fdc5e5f9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00121334b076ed4c705e7b440c75c1347e4208c9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="creating-maps"></a><span data-ttu-id="519bd-102">マップの作成</span><span class="sxs-lookup"><span data-stu-id="519bd-102">Creating Maps</span></span>
<span data-ttu-id="519bd-103">BizTalk マッパーの主要なユーザー インターフェイスが内のタブに表示される、 [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。</span><span class="sxs-lookup"><span data-stu-id="519bd-103">The primary user interface for BizTalk Mapper is displayed on a tab within the [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span> <span data-ttu-id="519bd-104">この表示は、3 つのペインに分割されています。</span><span class="sxs-lookup"><span data-stu-id="519bd-104">This display is divided into three panes.</span></span> <span data-ttu-id="519bd-105">左ペインでは、送信元スキーマがツリーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="519bd-105">The left pane displays the source schema as a tree.</span></span> <span data-ttu-id="519bd-106">右ペインでは、送信先スキーマがツリーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="519bd-106">The right pane displays the destination schema as a tree.</span></span> <span data-ttu-id="519bd-107">中央のペインでは、グリッドが複数のページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="519bd-107">The middle pane displays the grid as multiple pages.</span></span> <span data-ttu-id="519bd-108">送信元スキーマのデータを送信先スキーマにどのようにマップするかを示すには、マップする対象のレコードとフィールドの間に線を引きます。</span><span class="sxs-lookup"><span data-stu-id="519bd-108">To indicate how you want to map data from the source schema to the destination schema, you draw lines between the records and fields you want to map.</span></span> <span data-ttu-id="519bd-109">これらの行が呼び出される*リンク*データのマッピングを指定する最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="519bd-109">These lines are called *links*, and they are the most basic way to specify the mapping of data.</span></span> <span data-ttu-id="519bd-110">レコードおよびフィールドのリンクの詳細については、次を参照してください。[マップでリンク](../core/links-in-maps.md)です。</span><span class="sxs-lookup"><span data-stu-id="519bd-110">For more information about linking records and fields, see [Links in Maps](../core/links-in-maps.md).</span></span>  
  
 <span data-ttu-id="519bd-111">高度なマッピング手法を実装する場合は Functoid を使用できます。</span><span class="sxs-lookup"><span data-stu-id="519bd-111">If you want to implement more advanced mapping methods, you can use functoids.</span></span> <span data-ttu-id="519bd-112">Functoid は [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックス内の BizTalk マッパー タブで使用できるツールです。</span><span class="sxs-lookup"><span data-stu-id="519bd-112">Functoids are tools available on BizTalk Mapper tabs within the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span> <span data-ttu-id="519bd-113">これを使用すると、次のような複雑な操作を実行するマップを作成できます。</span><span class="sxs-lookup"><span data-stu-id="519bd-113">They enable you to create maps to perform more complex operations, such as:</span></span>  
  
-   <span data-ttu-id="519bd-114">送信元スキーマに含まれる 2 つのフィールドの値を加算し、その結果を送信先スキーマのフィールドに入力する。</span><span class="sxs-lookup"><span data-stu-id="519bd-114">Adding the values in two fields in a source schema and putting the result in a field in the destination schema.</span></span>  
  
-   <span data-ttu-id="519bd-115">ルーピング レコードのフィールドの平均値を計算し、その結果を送信先スキーマのフィールドに入力する。</span><span class="sxs-lookup"><span data-stu-id="519bd-115">Calculating the average value of a field in a looping record and putting the result in a field in the destination schema.</span></span>  
  
-   <span data-ttu-id="519bd-116">ビジネス ニーズに応じて、インスタンス データを操作するカスタム スクリプトを記述する。</span><span class="sxs-lookup"><span data-stu-id="519bd-116">Writing a custom script to manipulate instance data as appropriate for your business needs.</span></span>  
  
 <span data-ttu-id="519bd-117">Functoid の詳細については、次を参照してください。[マップの Functoid](../core/functoids-in-maps.md)です。</span><span class="sxs-lookup"><span data-stu-id="519bd-117">For more information about functoids, see [Functoids in Maps](../core/functoids-in-maps.md).</span></span>  
  
 <span data-ttu-id="519bd-118">BizTalk マッパーは、単純な親子関係から、レコードと階層の詳細で複雑なルーピングまで、さまざまなマッピング シナリオをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="519bd-118">BizTalk Mapper can support many different mapping scenarios from simple parent-child relationships to detailed, complex looping of records and hierarchies.</span></span> <span data-ttu-id="519bd-119">マップを作成するときは、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="519bd-119">Consider the following when you create maps:</span></span>  
  
-   <span data-ttu-id="519bd-120">BizTalk マッパーは、結合および並べ替えをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="519bd-120">BizTalk Mapper does not support merge and sort.</span></span>  
  
-   <span data-ttu-id="519bd-121">送信元スキーマと送信先スキーマの構造が極端に異なる場合、1 つのマップでは変換できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="519bd-121">If the source and target schema structures are extremely different, it is possible that the transformation cannot be done in a single map.</span></span> <span data-ttu-id="519bd-122">二重に渡す必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="519bd-122">You may need a double pass.</span></span>  
  
-   <span data-ttu-id="519bd-123">**ループ**functoid には、柔軟かつ強力ですが、まだ対象ループの次のイテレーションを開始する送信元スキーマの値の変更が検出されたときに反復処理を中断することはできません。</span><span class="sxs-lookup"><span data-stu-id="519bd-123">**Looping** functoids are flexible and powerful, yet you will not be able to break up the iteration when a change in value on the source schema is detected to start the next iteration of the target loop.</span></span>  
  
-   <span data-ttu-id="519bd-124">メソッドの外部変数を宣言することができます、**スクリプト**functoid は、マップの有効期間のスコープ内の変数の中に発生します。</span><span class="sxs-lookup"><span data-stu-id="519bd-124">You can declare a variable outside the method in a **Scripting** functoid, which results in the variable being in scope for the life of the map.</span></span> <span data-ttu-id="519bd-125">したがって、使用することができます、**スクリプト**functoid 変換のスコープ領域間で値を保持するためです。</span><span class="sxs-lookup"><span data-stu-id="519bd-125">Therefore, you can use the **Scripting** functoid for holding values between scope areas of the transformation.</span></span>  
  
 <span data-ttu-id="519bd-126">処理されるすべてのデータ[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時に XML 形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="519bd-126">All data processed by [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] at run time must be in XML format.</span></span> <span data-ttu-id="519bd-127">XML でないデータは、マッピングの前に、対応する XML 形式に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="519bd-127">All non-XML data must be translated to an equivalent XML format before mapping.</span></span> <span data-ttu-id="519bd-128">同様に、マッピング プロセスが完了したときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はマッピング操作の出力を使用し、データの送信先である取引先またはアプリケーションが認識できるファイル形式を作成します。</span><span class="sxs-lookup"><span data-stu-id="519bd-128">Similarly, when the mapping process is complete, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the output of a mapping operation to create a file format that is recognized by the trading partner or application to which the data is sent.</span></span>  
  
 <span data-ttu-id="519bd-129">BizTalk マッパーにはコンパイラが含まれています。</span><span class="sxs-lookup"><span data-stu-id="519bd-129">BizTalk Mapper includes a compiler.</span></span> <span data-ttu-id="519bd-130">このツール レベル コンポーネントは、入力インスタンス メッセージを出力インスタンス メッセージに変換するために必要な XSLT (Extensible Stylesheet Language Transformations) を生成します。</span><span class="sxs-lookup"><span data-stu-id="519bd-130">This tool-level component generates the Extensible Stylesheet Language Transformations (XSLT) needed to transform or translate input instance messages to output instance messages.</span></span>  
  
 <span data-ttu-id="519bd-131">このセクションでは、BizTalk マッパーを使用して 2 つのスキーマ間のマッピングを作成する場合の、タスク固有の情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="519bd-131">This section provides task-specific information about using BizTalk Mapper to create the mapping between two schemas.</span></span> <span data-ttu-id="519bd-132">ここでは、BizTalk マッパーが既に開かれ、マップの送信元スキーマと送信先スキーマが選択されていることを前提にしています。</span><span class="sxs-lookup"><span data-stu-id="519bd-132">It assumes that you already have BizTalk Mapper open, and have chosen your source and destination schemas.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="519bd-133">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="519bd-133">In This Section</span></span>  
  
-   [<span data-ttu-id="519bd-134">プロジェクト内のマップの管理</span><span class="sxs-lookup"><span data-stu-id="519bd-134">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)  
  
-   [<span data-ttu-id="519bd-135">リンクを使用してレコードとフィールド マッピングを指定する</span><span class="sxs-lookup"><span data-stu-id="519bd-135">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)  
  
-   [<span data-ttu-id="519bd-136">Functoid を使用した複雑なマッピングの作成</span><span class="sxs-lookup"><span data-stu-id="519bd-136">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)  
  
-   [<span data-ttu-id="519bd-137">マップなしのマップを作成する方法</span><span class="sxs-lookup"><span data-stu-id="519bd-137">How to Create a Map without Maps</span></span>](../core/how-to-create-a-map-without-maps.md)  
  
-   [<span data-ttu-id="519bd-138">既定のマッパーを使用して動作を管理する\<mapsource\></span><span class="sxs-lookup"><span data-stu-id="519bd-138">Managing Default Mapper Behavior Using \<mapsource\></span></span>](../core/managing-default-mapper-behavior-using-mapsource.md)