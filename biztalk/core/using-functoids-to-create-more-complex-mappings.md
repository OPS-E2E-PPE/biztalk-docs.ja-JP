---
title: Functoid を使用して、複雑なマッピングを作成する |Microsoft Docs
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
ms.openlocfilehash: 4e16b692f3f91aff47e978080be124220db68a89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247228"
---
# <a name="using-functoids-to-create-more-complex-mappings"></a><span data-ttu-id="8d0b9-102">Functoid を使用した複雑なマッピングの作成</span><span class="sxs-lookup"><span data-stu-id="8d0b9-102">Using Functoids to Create More Complex Mappings</span></span>

## <a name="overview"></a><span data-ttu-id="8d0b9-103">概要</span><span class="sxs-lookup"><span data-stu-id="8d0b9-103">Overview</span></span>
<span data-ttu-id="8d0b9-104">Functoid は、多くのマッピング シナリオで重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-104">Functoids play a crucial role in many mapping scenarios.</span></span> <span data-ttu-id="8d0b9-105">Functoid、せず要素と属性のデータをコピーすることができますがすることはできません、重要な程度、操作値自体。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-105">Without functoids, you can copy element and attribute data, but you cannot, to any significant extent, manipulate the values themselves.</span></span> <span data-ttu-id="8d0b9-106">Functoid を使用して、ほとんどの変換が可能です。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-106">Using functoids, almost any transformation is possible.</span></span> <span data-ttu-id="8d0b9-107">たとえば、functoid を使用することができますまったく別の場所から 2 つの値を取得、追加合計を送信先スキーマの配置。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-107">For example, with a functoid you can take two values from entirely different locations, add them together, and place the sum in the destination schema.</span></span>  
  
 <span data-ttu-id="8d0b9-108">表示されます、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス、BizTalk マップを編集している場合は、カテゴリごとに 1 つのツールボックス タブ。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-108">Functoids appear in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox, one toolbox tab per category, when you are editing a BizTalk map.</span></span> <span data-ttu-id="8d0b9-109">ツールボックスを開くし、対応するタブをクリックして functoid のカテゴリを選択すると後、は、グリッド ページに functoid をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-109">After you open the Toolbox and choose a category of functoids by clicking on the corresponding tab, you drag the functoid onto a grid page.</span></span> <span data-ttu-id="8d0b9-110">入力を作成し、functoid、スキーマ ノードまたは別の functoid とリンクを出力します。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-110">Then you create input and output links between the functoid and either schema nodes or another functoid.</span></span> <span data-ttu-id="8d0b9-111">入力リンク入力パラメーターと左から functoid に潜在顧客に対応します。出力リンクは、出力パラメーターに対応し、右側に functoid を残します。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-111">Input links correspond to input parameters and lead to a functoid from the left; an output link corresponds to the output parameter and leaves a functoid to the right.</span></span>  
  
 <span data-ttu-id="8d0b9-112">Functoid は、他のマップ要素のようなプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-112">Like other map elements, functoids have properties.</span></span> <span data-ttu-id="8d0b9-113">Functoid の最も重要なプロパティの 1 つは、入力パラメーターのセットです。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-113">One of the most important properties of a functoid is its set of input parameters.</span></span> <span data-ttu-id="8d0b9-114">詳細については、次を参照してください。[マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)します。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-114">For more information, see [How to Add Basic Functoids to a Map](../core/how-to-add-basic-functoids-to-a-map.md).</span></span>  
  
 <span data-ttu-id="8d0b9-115">このセクションには、BizTalk マップでの functoid を使用するための手順が説明します。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-115">This section provides step-by-step instructions for working with functoids within BizTalk maps.</span></span> <span data-ttu-id="8d0b9-116">Functoid のリファレンスについては、次を参照してください。、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8d0b9-116">For reference information about functoids, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="8d0b9-117">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8d0b9-117">Next steps</span></span> 
  
-   [<span data-ttu-id="8d0b9-118">Functoid のツールボックスを開く方法</span><span class="sxs-lookup"><span data-stu-id="8d0b9-118">How to Open the Functoid Toolbox</span></span>](../core/how-to-open-the-functoid-toolbox.md)  
  
-   [<span data-ttu-id="8d0b9-119">マップに基本 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="8d0b9-119">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="8d0b9-120">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="8d0b9-120">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="8d0b9-121">Functoid のプロパティおよび入力パラメーターの編集</span><span class="sxs-lookup"><span data-stu-id="8d0b9-121">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)  
  
-   [<span data-ttu-id="8d0b9-122">複数の Functoid を選択する方法</span><span class="sxs-lookup"><span data-stu-id="8d0b9-122">How to Select Multiple Functoids</span></span>](../core/how-to-select-multiple-functoids.md)  
  
-   [<span data-ttu-id="8d0b9-123">Functoid を削除する方法</span><span class="sxs-lookup"><span data-stu-id="8d0b9-123">How to Delete Functoids</span></span>](../core/how-to-delete-functoids.md)  
  
-   [<span data-ttu-id="8d0b9-124">コピー、切り取り、および貼り付けする方法</span><span class="sxs-lookup"><span data-stu-id="8d0b9-124">How to Copy, Cut, and Paste a Functoid</span></span>](../core/how-to-copy-cut-and-paste-a-functoid.md)