---
title: '[成果物の種類] ダイアログ ボックスを使用する方法 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Select Artifact Type dialog box
- artifacts, Select Artifact Type dialog box
- Orchestration Designer, items
ms.assetid: f0f767f1-4130-4ff0-a898-a089343ee71f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 362f1ffe21023aaddb5b492548914d35348fa5e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333220"
---
# <a name="how-to-use-the-select-artifact-type-dialog-box"></a><span data-ttu-id="082dc-102">[成果物の種類] ダイアログ ボックスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="082dc-102">How to Use the Select Artifact Type Dialog Box</span></span>
<span data-ttu-id="082dc-103">*項目*オーケストレーション デザイナーでオーケストレーションの要素を構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="082dc-103">An *item* is used to configure elements of an orchestration in Orchestration Designer.</span></span> <span data-ttu-id="082dc-104">項目には、スキーマ、マップ、パイプライン、ポートの種類、およびマルチパート メッセージの種類があります。</span><span class="sxs-lookup"><span data-stu-id="082dc-104">Examples of items are schemas, maps, pipelines, port types, and multi-part message types.</span></span> <span data-ttu-id="082dc-105">オーケストレーションおよびポート図形、変換図形、およびメッセージなどの構成要素を開発するとき、現在のオーケストレーションに存在していないが、現在のプロジェクトまたはにコンパイルされている別のプロジェクトでは項目を参照する必要があります。BizTalk Server アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="082dc-105">When you develop an orchestration and its constituent parts such as port shapes, transform shapes, and messages, you may need to refer to items that do not reside in the current orchestration, but are in the current project or another project that has been compiled into a BizTalk Server assembly.</span></span> <span data-ttu-id="082dc-106">使用する、**成果物の種類の選択** ダイアログ ボックスを探して、オーケストレーション内の要素を構成するときに項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="082dc-106">You use the **Select Artifact Type** dialog box to locate and then specify items when configuring an element within an orchestration.</span></span>  
  
 <span data-ttu-id="082dc-107">**成果物の種類の選択** ダイアログ ボックスはオーケストレーション デザイナーでのさまざまな場所から利用できます。</span><span class="sxs-lookup"><span data-stu-id="082dc-107">The **Select Artifact Type** dialog box is available from many locations in Orchestration Designer.</span></span> <span data-ttu-id="082dc-108">選択することができます\<参照されたアセンブリから選択\>構成オプションを表示するドロップダウン リストでは、このテキストをクリックすると、**成果物の種類の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="082dc-108">You can select \<Select from referenced assembly\> in a drop-down list that displays configuration options; clicking this text opens the **Select Artifact Type** dialog box.</span></span>  
  
 <span data-ttu-id="082dc-109">項目を選択する前に、まずを構成する要素を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="082dc-109">Before you can select an item, you must first select the element you want to configure.</span></span>  
  
 <span data-ttu-id="082dc-110">使用することができます、**成果物の種類の選択**次の目的でのダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="082dc-110">You can use the **Select Artifact Type** dialog box for the following specific purposes:</span></span>  
  
|<span data-ttu-id="082dc-111">操作</span><span class="sxs-lookup"><span data-stu-id="082dc-111">Action</span></span>|<span data-ttu-id="082dc-112">目的</span><span class="sxs-lookup"><span data-stu-id="082dc-112">Purpose</span></span>|  
|------------|-------------|  
|<span data-ttu-id="082dc-113">パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="082dc-113">Select a pipeline</span></span>|<span data-ttu-id="082dc-114">直接 (初期) バインド用のポートを構成するときに、パイプライン プロパティ用のパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="082dc-114">Select a pipeline for the pipeline property when configuring a port for direct (early) binding.</span></span>|  
|<span data-ttu-id="082dc-115">マップを選択します。</span><span class="sxs-lookup"><span data-stu-id="082dc-115">Select a map</span></span>|<span data-ttu-id="082dc-116">使用するマップを選択して、**変換**図形。</span><span class="sxs-lookup"><span data-stu-id="082dc-116">Select a map to use with a **Transform** shape.</span></span>|  
|<span data-ttu-id="082dc-117">スキーマを選択します</span><span class="sxs-lookup"><span data-stu-id="082dc-117">Select a schema</span></span>|<span data-ttu-id="082dc-118">マルチパート メッセージの種類を作成するときに、プロジェクトでスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="082dc-118">Select schemas in the project when creating multi-part message types.</span></span>|  
|<span data-ttu-id="082dc-119">ポートの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="082dc-119">Select a port type</span></span>|<span data-ttu-id="082dc-120">ポートを作成するときに、既存のポートの種類を参照してください。</span><span class="sxs-lookup"><span data-stu-id="082dc-120">Refer to existing port types when creating a port.</span></span>|  
|<span data-ttu-id="082dc-121">マルチパート メッセージの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="082dc-121">Select a multi-part message type</span></span>|<span data-ttu-id="082dc-122">メッセージを作成するときに、既存のマルチパートの種類を参照してください。</span><span class="sxs-lookup"><span data-stu-id="082dc-122">Refer to existing multipart types when creating messages.</span></span>|  
|<span data-ttu-id="082dc-123">.NET 型を選択します。</span><span class="sxs-lookup"><span data-stu-id="082dc-123">Select a .NET type</span></span>|<span data-ttu-id="082dc-124">変数またはメッセージを作成するときに、既存の .NET 型を参照してください。</span><span class="sxs-lookup"><span data-stu-id="082dc-124">Refer to existing .NET types when creating variables or messages.</span></span>|  
  
 <span data-ttu-id="082dc-125">**参照ペイン**</span><span class="sxs-lookup"><span data-stu-id="082dc-125">**Reference pane**</span></span>  
  
 <span data-ttu-id="082dc-126">参照ペイン、**成果物の種類の選択** ダイアログ ボックスは、現在のプロジェクトとその他の使用可能なアセンブリ参照を表示します。</span><span class="sxs-lookup"><span data-stu-id="082dc-126">The reference pane of the **Select Artifact Type** dialog box displays references in the current project and in other available assemblies.</span></span> <span data-ttu-id="082dc-127">このウィンドウでの参照を選択するにはをクリックします。</span><span class="sxs-lookup"><span data-stu-id="082dc-127">To select a reference in this pane, click it.</span></span> <span data-ttu-id="082dc-128">このウィンドウでコンテナーを展開 (など、**アセンブリ**コンテナー)、横にあるプラス記号 (+) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="082dc-128">To expand a container in this pane (such as the **Assemblies** container), click the plus sign (+) beside it.</span></span>  
  
 <span data-ttu-id="082dc-129">**[アイテム] ペイン**</span><span class="sxs-lookup"><span data-stu-id="082dc-129">**Item pane**</span></span>  
  
 <span data-ttu-id="082dc-130">項目 ウィンドウ、**成果物の種類の選択**ダイアログ ボックスで、参照ペインで現在選択されている参照に含まれる項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="082dc-130">The item pane of the **Select Artifact Type** dialog box displays the items contained in the reference currently selected in the reference pane.</span></span> <span data-ttu-id="082dc-131">項目 ウィンドウが 2 つの列**項目**と**修飾名**、現在の参照で、項目に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="082dc-131">The item pane has two columns, **Item** and **Qualified Name**, which display information about the items in the current reference.</span></span>  
  
### <a name="to-use-the-select-artifact-type-dialog-box"></a><span data-ttu-id="082dc-132">成果物の種類の選択 ダイアログ ボックスを使用するには</span><span class="sxs-lookup"><span data-stu-id="082dc-132">To use the Select Artifact Type dialog box</span></span>  
  
1.  <span data-ttu-id="082dc-133">展開、**参照**左側のウィンドウでノード。</span><span class="sxs-lookup"><span data-stu-id="082dc-133">Expand the **References** node in the left pane.</span></span> <span data-ttu-id="082dc-134">使用可能なプロジェクトおよびアセンブリのウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="082dc-134">The pane displays available projects and assemblies.</span></span>  
  
2.  <span data-ttu-id="082dc-135">展開、**アセンブリ**ノード。</span><span class="sxs-lookup"><span data-stu-id="082dc-135">Expand the **Assemblies** node.</span></span> <span data-ttu-id="082dc-136">システムなど、1 つまたは複数のアセンブリが一覧表示されます。DLL および MICROSOFT.BIZTALK.PIPELINES.DLL します。</span><span class="sxs-lookup"><span data-stu-id="082dc-136">One or more assemblies are listed, such as SYSTEM.DLL and MICROSOFT.BIZTALK.PIPELINES.DLL.</span></span>  
  
3.  <span data-ttu-id="082dc-137">アセンブリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="082dc-137">Click an assembly.</span></span> <span data-ttu-id="082dc-138">アセンブリに項目が含まれている場合は、右側のウィンドウで表示されます。</span><span class="sxs-lookup"><span data-stu-id="082dc-138">If the assembly contains items, they are displayed in the right pane.</span></span> <span data-ttu-id="082dc-139">項目の修飾名は、右側のウィンドウの右側の列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="082dc-139">The qualified name of an item is displayed in the right column of the right pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="082dc-140">現在のプロジェクトに項目が含まれている場合は、そのアイテムを表示し、いずれかを選択してクリックできます。</span><span class="sxs-lookup"><span data-stu-id="082dc-140">If the current project contains items, you can click it to view its items and select one.</span></span>  
  
4.  <span data-ttu-id="082dc-141">項目を選択して、右側のウィンドウで、クリックし、をクリックし、 **OK**を終了する、**成果物の種類の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="082dc-141">To select an item in the right pane, click it and then click **OK** to exit the **Select Artifact Type** dialog box.</span></span> <span data-ttu-id="082dc-142">これには、選択した要素の型としてその項目が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="082dc-142">This assigns that item as the type for the selected element.</span></span> <span data-ttu-id="082dc-143">閉じるには、**成果物の種類の選択** ダイアログ ボックスを選択して、項目の割り当て をクリックしてせず**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="082dc-143">To close the **Select Artifact Type** dialog box without selecting and assigning an item, click **Cancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="082dc-144">参照</span><span class="sxs-lookup"><span data-stu-id="082dc-144">See Also</span></span>  
 <span data-ttu-id="082dc-145">[オーケストレーション図形](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="082dc-145">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="082dc-146">[オーケストレーションに図形を追加する方法](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="082dc-146">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 [<span data-ttu-id="082dc-147">オーケストレーションにパラメーターを追加する方法</span><span class="sxs-lookup"><span data-stu-id="082dc-147">How to Add Parameters to Orchestrations</span></span>](../core/how-to-add-parameters-to-orchestrations.md)