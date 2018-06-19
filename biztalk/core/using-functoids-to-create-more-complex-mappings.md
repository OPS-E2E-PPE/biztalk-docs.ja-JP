---
title: Functoid を使用して、複雑なマッピングを作成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d53e3a3-5ccd-4733-8c2f-3101e41fca61
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 736b6fa99844182c59db582182056faea1d3f322
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287162"
---
# <a name="using-functoids-to-create-more-complex-mappings"></a><span data-ttu-id="c32f6-102">Functoid を使用した複雑なマッピングの作成</span><span class="sxs-lookup"><span data-stu-id="c32f6-102">Using Functoids to Create More Complex Mappings</span></span>

## <a name="overview"></a><span data-ttu-id="c32f6-103">概要</span><span class="sxs-lookup"><span data-stu-id="c32f6-103">Overview</span></span>
<span data-ttu-id="c32f6-104">Functoid は、マッピング シナリオの多くで重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="c32f6-104">Functoids play a crucial role in many mapping scenarios.</span></span> <span data-ttu-id="c32f6-105">Functoid を使用しなくても要素と属性データをコピーできますが、値自体を操作することはできません。</span><span class="sxs-lookup"><span data-stu-id="c32f6-105">Without functoids, you can copy element and attribute data, but you cannot, to any significant extent, manipulate the values themselves.</span></span> <span data-ttu-id="c32f6-106">Functoid を使用すると、ほとんどすべての変換が可能です。</span><span class="sxs-lookup"><span data-stu-id="c32f6-106">Using functoids, almost any transformation is possible.</span></span> <span data-ttu-id="c32f6-107">たとえば、Functoid を使用して、異なる場所から 2 つの値を取得し、これらの値を加算して、合計を送信先スキーマに配置できます。</span><span class="sxs-lookup"><span data-stu-id="c32f6-107">For example, with a functoid you can take two values from entirely different locations, add them together, and place the sum in the destination schema.</span></span>  
  
 <span data-ttu-id="c32f6-108">BizTalk マップを編集するとき、Functoid は [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスに表示されます。カテゴリごとにツールボックス タブが 1 つ表示されます。</span><span class="sxs-lookup"><span data-stu-id="c32f6-108">Functoids appear in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox, one toolbox tab per category, when you are editing a BizTalk map.</span></span> <span data-ttu-id="c32f6-109">ツールボックスを開き、対応するタブをクリックして Functoid のカテゴリを選択してから、Functoid をグリッド ページにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c32f6-109">After you open the Toolbox and choose a category of functoids by clicking on the corresponding tab, you drag the functoid onto a grid page.</span></span> <span data-ttu-id="c32f6-110">次に、Functoid とスキーマ ノード間、または Functoid と別の Functoid 間に入力リンクや出力リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="c32f6-110">Then you create input and output links between the functoid and either schema nodes or another functoid.</span></span> <span data-ttu-id="c32f6-111">入力リンクは入力パラメーターに対応し、Functoid の左側から入ります。出力リンクは出力パラメーターに対応し、Functoid の右側に出て行きます。</span><span class="sxs-lookup"><span data-stu-id="c32f6-111">Input links correspond to input parameters and lead to a functoid from the left; an output link corresponds to the output parameter and leaves a functoid to the right.</span></span>  
  
 <span data-ttu-id="c32f6-112">他のマップ要素と同じように、Functoid にはプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="c32f6-112">Like other map elements, functoids have properties.</span></span> <span data-ttu-id="c32f6-113">Functoid の最も重要なプロパティの 1 つは、入力パラメーターのセットです。</span><span class="sxs-lookup"><span data-stu-id="c32f6-113">One of the most important properties of a functoid is its set of input parameters.</span></span> <span data-ttu-id="c32f6-114">詳細については、次を参照してください。[マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)です。</span><span class="sxs-lookup"><span data-stu-id="c32f6-114">For more information, see [How to Add Basic Functoids to a Map](../core/how-to-add-basic-functoids-to-a-map.md).</span></span>  
  
 <span data-ttu-id="c32f6-115">このセクションでは、BizTalk マップでの Functoid の操作手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="c32f6-115">This section provides step-by-step instructions for working with functoids within BizTalk maps.</span></span> <span data-ttu-id="c32f6-116">Functoid のリファレンスについては、次を参照してください。、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c32f6-116">For reference information about functoids, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="c32f6-117">次の手順</span><span class="sxs-lookup"><span data-stu-id="c32f6-117">Next steps</span></span> 
  
-   [<span data-ttu-id="c32f6-118">Functoid のツールボックスを開く方法</span><span class="sxs-lookup"><span data-stu-id="c32f6-118">How to Open the Functoid Toolbox</span></span>](../core/how-to-open-the-functoid-toolbox.md)  
  
-   [<span data-ttu-id="c32f6-119">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="c32f6-119">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="c32f6-120">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="c32f6-120">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="c32f6-121">Functoid のプロパティおよび入力パラメーターの編集</span><span class="sxs-lookup"><span data-stu-id="c32f6-121">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)  
  
-   [<span data-ttu-id="c32f6-122">複数の Functoid を選択する方法</span><span class="sxs-lookup"><span data-stu-id="c32f6-122">How to Select Multiple Functoids</span></span>](../core/how-to-select-multiple-functoids.md)  
  
-   [<span data-ttu-id="c32f6-123">Functoid を削除する方法</span><span class="sxs-lookup"><span data-stu-id="c32f6-123">How to Delete Functoids</span></span>](../core/how-to-delete-functoids.md)  
  
-   [<span data-ttu-id="c32f6-124">コピー、切り取り、および Functoid を貼り付けする方法</span><span class="sxs-lookup"><span data-stu-id="c32f6-124">How to Copy, Cut, and Paste a Functoid</span></span>](../core/how-to-copy-cut-and-paste-a-functoid.md)