---
title: "選択アイテムの種類 ダイアログ ボックスを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Select Artifact Type dialog box
- artifacts, Select Artifact Type dialog box
- Orchestration Designer, items
ms.assetid: f0f767f1-4130-4ff0-a898-a089343ee71f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3027971059d99a921bd743ff28aca1617c5d628d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-select-artifact-type-dialog-box"></a><span data-ttu-id="77c0f-102">選択アイテムの種類 ダイアログ ボックスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="77c0f-102">How to Use the Select Artifact Type Dialog Box</span></span>
<span data-ttu-id="77c0f-103">*項目*オーケストレーション デザイナーでオーケストレーションの要素を構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="77c0f-103">An *item* is used to configure elements of an orchestration in Orchestration Designer.</span></span> <span data-ttu-id="77c0f-104">項目の例としては、スキーマ、マップ、パイプライン、ポートの種類、マルチパート メッセージの種類などが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="77c0f-104">Examples of items are schemas, maps, pipelines, port types, and multi-part message types.</span></span> <span data-ttu-id="77c0f-105">ポート図形、変換図形、メッセージなど、オーケストレーションとその構成部分を開発する場合、現在のオーケストレーションではなく、BizTalk Server アセンブリにコンパイルされた現在のプロジェクトまたは他のプロジェクトに含まれる項目を参照する必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="77c0f-105">When you develop an orchestration and its constituent parts such as port shapes, transform shapes, and messages, you may need to refer to items that do not reside in the current orchestration, but are in the current project or another project that has been compiled into a BizTalk Server assembly.</span></span> <span data-ttu-id="77c0f-106">使用する、**成果物の種類の選択** ダイアログ ボックスを探して、オーケストレーション内の要素を構成するときに項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="77c0f-106">You use the **Select Artifact Type** dialog box to locate and then specify items when configuring an element within an orchestration.</span></span>  
  
 <span data-ttu-id="77c0f-107">**成果物の種類の選択**オーケストレーション デザイナーでさまざまな場所からダイアログ ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="77c0f-107">The **Select Artifact Type** dialog box is available from many locations in Orchestration Designer.</span></span> <span data-ttu-id="77c0f-108">選択できる\<参照されたアセンブリから選択 > 構成オプションを表示するドロップダウン リストです。 このテキストをクリックすると開きます、**成果物の種類の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="77c0f-108">You can select \<Select from referenced assembly> in a drop-down list that displays configuration options; clicking this text opens the **Select Artifact Type** dialog box.</span></span>  
  
 <span data-ttu-id="77c0f-109">項目を選択する前に、構成する要素を事前に選択しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="77c0f-109">Before you can select an item, you must first select the element you want to configure.</span></span>  
  
 <span data-ttu-id="77c0f-110">使用することができます、**成果物の種類の選択**次の特定の目的 ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="77c0f-110">You can use the **Select Artifact Type** dialog box for the following specific purposes:</span></span>  
  
|<span data-ttu-id="77c0f-111">操作</span><span class="sxs-lookup"><span data-stu-id="77c0f-111">Action</span></span>|<span data-ttu-id="77c0f-112">用途</span><span class="sxs-lookup"><span data-stu-id="77c0f-112">Purpose</span></span>|  
|------------|-------------|  
|<span data-ttu-id="77c0f-113">パイプラインの選択</span><span class="sxs-lookup"><span data-stu-id="77c0f-113">Select a pipeline</span></span>|<span data-ttu-id="77c0f-114">直接 (初期) バインド用のポートを構成する際に、パイプライン プロパティのパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c0f-114">Select a pipeline for the pipeline property when configuring a port for direct (early) binding.</span></span>|  
|<span data-ttu-id="77c0f-115">マップの選択</span><span class="sxs-lookup"><span data-stu-id="77c0f-115">Select a map</span></span>|<span data-ttu-id="77c0f-116">使用するマップを選択して、**変換**図形です。</span><span class="sxs-lookup"><span data-stu-id="77c0f-116">Select a map to use with a **Transform** shape.</span></span>|  
|<span data-ttu-id="77c0f-117">スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c0f-117">Select a schema</span></span>|<span data-ttu-id="77c0f-118">マルチパート メッセージの種類を作成する場合に、プロジェクトでスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c0f-118">Select schemas in the project when creating multi-part message types.</span></span>|  
|<span data-ttu-id="77c0f-119">ポートの種類の選択</span><span class="sxs-lookup"><span data-stu-id="77c0f-119">Select a port type</span></span>|<span data-ttu-id="77c0f-120">ポートを作成する際に、既存のポートの種類を参照します。</span><span class="sxs-lookup"><span data-stu-id="77c0f-120">Refer to existing port types when creating a port.</span></span>|  
|<span data-ttu-id="77c0f-121">マルチパート メッセージの種類の選択</span><span class="sxs-lookup"><span data-stu-id="77c0f-121">Select a multi-part message type</span></span>|<span data-ttu-id="77c0f-122">メッセージを作成する際に、既存のマルチパートの種類を参照します。</span><span class="sxs-lookup"><span data-stu-id="77c0f-122">Refer to existing multipart types when creating messages.</span></span>|  
|<span data-ttu-id="77c0f-123">.NET の種類の選択</span><span class="sxs-lookup"><span data-stu-id="77c0f-123">Select a .NET type</span></span>|<span data-ttu-id="77c0f-124">変数またはメッセージを作成する際に、既存の .NET の種類を参照します。</span><span class="sxs-lookup"><span data-stu-id="77c0f-124">Refer to existing .NET types when creating variables or messages.</span></span>|  
  
 <span data-ttu-id="77c0f-125">**参照ペイン**</span><span class="sxs-lookup"><span data-stu-id="77c0f-125">**Reference pane**</span></span>  
  
 <span data-ttu-id="77c0f-126">参照ペイン、**成果物の種類の選択** ダイアログ ボックスでは、使用可能なその他のアセンブリと、現在のプロジェクトでの参照が表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c0f-126">The reference pane of the **Select Artifact Type** dialog box displays references in the current project and in other available assemblies.</span></span> <span data-ttu-id="77c0f-127">このペインで参照を選択するには、目的の参照をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77c0f-127">To select a reference in this pane, click it.</span></span> <span data-ttu-id="77c0f-128">このウィンドウでコンテナーを展開 (など、**アセンブリ**コンテナー)、その横にあるプラス記号 (+) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77c0f-128">To expand a container in this pane (such as the **Assemblies** container), click the plus sign (+) beside it.</span></span>  
  
 <span data-ttu-id="77c0f-129">**[アイテム] ペイン**</span><span class="sxs-lookup"><span data-stu-id="77c0f-129">**Item pane**</span></span>  
  
 <span data-ttu-id="77c0f-130">項目 ウィンドウ、**成果物の種類の選択** ダイアログ ボックスには、参照ペインで現在選択されている参照に含まれる項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c0f-130">The item pane of the **Select Artifact Type** dialog box displays the items contained in the reference currently selected in the reference pane.</span></span> <span data-ttu-id="77c0f-131">[アイテム] ペインが 2 つの列、**項目**と**修飾名**の現在のリファレンス内の項目に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c0f-131">The item pane has two columns, **Item** and **Qualified Name**, which display information about the items in the current reference.</span></span>  
  
### <a name="to-use-the-select-artifact-type-dialog-box"></a><span data-ttu-id="77c0f-132">[アイテムの種類の選択] ダイアログ ボックスを使用するには</span><span class="sxs-lookup"><span data-stu-id="77c0f-132">To use the Select Artifact Type dialog box</span></span>  
  
1.  <span data-ttu-id="77c0f-133">展開して、**参照**左側のウィンドウ内のノードです。</span><span class="sxs-lookup"><span data-stu-id="77c0f-133">Expand the **References** node in the left pane.</span></span> <span data-ttu-id="77c0f-134">使用できるプロジェクトとアセンブリがペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c0f-134">The pane displays available projects and assemblies.</span></span>  
  
2.  <span data-ttu-id="77c0f-135">展開して、**アセンブリ**ノード。</span><span class="sxs-lookup"><span data-stu-id="77c0f-135">Expand the **Assemblies** node.</span></span> <span data-ttu-id="77c0f-136">SYSTEM.DLL および MICROSOFT.BIZTALK.PIPELINES.DLL など、1 つ以上のアセンブリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c0f-136">One or more assemblies are listed, such as SYSTEM.DLL and MICROSOFT.BIZTALK.PIPELINES.DLL.</span></span>  
  
3.  <span data-ttu-id="77c0f-137">いずれかのアセンブリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="77c0f-137">Click an assembly.</span></span> <span data-ttu-id="77c0f-138">そのアセンブリに項目が含まれている場合、右ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c0f-138">If the assembly contains items, they are displayed in the right pane.</span></span> <span data-ttu-id="77c0f-139">右ペインの右側の列に、項目の修飾名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="77c0f-139">The qualified name of an item is displayed in the right column of the right pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77c0f-140">現在のプロジェクトに項目が含まれている場合は、クリックして項目を表示し、選択することができます。</span><span class="sxs-lookup"><span data-stu-id="77c0f-140">If the current project contains items, you can click it to view its items and select one.</span></span>  
  
4.  <span data-ttu-id="77c0f-141">右側のウィンドウで項目を選択するにそれをクリックし、をクリックして**OK**を終了する、**成果物の種類の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="77c0f-141">To select an item in the right pane, click it and then click **OK** to exit the **Select Artifact Type** dialog box.</span></span> <span data-ttu-id="77c0f-142">この操作により、その項目が、選択されている要素の種類として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="77c0f-142">This assigns that item as the type for the selected element.</span></span> <span data-ttu-id="77c0f-143">閉じるには、**成果物の種類の選択** ダイアログ ボックスを選択して、項目の割り当て をクリックしてせず**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="77c0f-143">To close the **Select Artifact Type** dialog box without selecting and assigning an item, click **Cancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c0f-144">参照</span><span class="sxs-lookup"><span data-stu-id="77c0f-144">See Also</span></span>  
 <span data-ttu-id="77c0f-145">[オーケストレーション図形](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="77c0f-145">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="77c0f-146">[オーケストレーションに図形を追加する方法](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="77c0f-146">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 [<span data-ttu-id="77c0f-147">オーケストレーションにパラメーターを追加する方法</span><span class="sxs-lookup"><span data-stu-id="77c0f-147">How to Add Parameters to Orchestrations</span></span>](../core/how-to-add-parameters-to-orchestrations.md)