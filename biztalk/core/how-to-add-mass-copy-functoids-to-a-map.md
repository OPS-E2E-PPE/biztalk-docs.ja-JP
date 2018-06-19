---
title: マップに一括コピー Functoid を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cff63fc-8f34-4bd0-8501-a8401bde6349
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cee6f2c53bbd3b3dbabe55f0160309532d0ebf3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247570"
---
# <a name="how-to-add-mass-copy-functoids-to-a-map"></a><span data-ttu-id="6fca1-102">マップに一括コピー Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="6fca1-102">How to Add Mass Copy Functoids to a Map</span></span>
<span data-ttu-id="6fca1-103">**一括コピー** functoid を含むスキーマを使用して、マップを有効に**任意**と**anyAttribute**要素。</span><span class="sxs-lookup"><span data-stu-id="6fca1-103">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="6fca1-104">これらの要素は基本的に、XML スキーマ定義言語で提供されているワイルドカードであり、不明な構造や属性のセットに一致します。</span><span class="sxs-lookup"><span data-stu-id="6fca1-104">These elements are, in essence, wildcards provided in the XML Schema definition language to match unknown structures or sets of attributes.</span></span>  
  
 <span data-ttu-id="6fca1-105">概要については、**一括コピー** functoid を参照してください[一括コピー Functoid](../core/mass-copy-functoid.md)です。</span><span class="sxs-lookup"><span data-stu-id="6fca1-105">For conceptual information about the **Mass Copy** functoid, see [Mass Copy Functoid](../core/mass-copy-functoid.md).</span></span>  
  
### <a name="to-add-the-mass-copy-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="6fca1-106">マップに一括コピー Functoid を追加して構成するには</span><span class="sxs-lookup"><span data-stu-id="6fca1-106">To add the Mass Copy functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="6fca1-107">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。</span><span class="sxs-lookup"><span data-stu-id="6fca1-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="6fca1-108">選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fca1-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="6fca1-109">ドラッグ、**一括コピー** functoid (![](../core/media/advmasscopy.gif "advmasscopy")) をグリッド ページの適切な場所にツールボックスからです。</span><span class="sxs-lookup"><span data-stu-id="6fca1-109">Drag the **Mass Copy** functoid (![](../core/media/advmasscopy.gif "advmasscopy")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6fca1-110">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6fca1-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="6fca1-111">別のグリッド ページに functoid を配置する場合は、その他のグリッド ページを最初に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fca1-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6fca1-112">複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fca1-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="6fca1-113">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="6fca1-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="6fca1-114">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="6fca1-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="6fca1-115">入力パラメーターを設定する、**一括コピー** functoid、送信元スキーマからレコードをドラッグして、入力リンクを作成、**一括コピー** functoid をドラッグするか、**一括コピー** functoid、送信元スキーマ内のレコードを送信します。</span><span class="sxs-lookup"><span data-stu-id="6fca1-115">To establish the input parameter for the **Mass Copy** functoid, create an input link by dragging a record from the source schema to the **Mass Copy** functoid, or dragging the **Mass Copy** functoid to a record in the source schema.</span></span>  
  
4.  <span data-ttu-id="6fca1-116">出力パラメーターを使用する、**一括コピー** functoid をドラッグして、出力リンクを作成、**一括コピー** functoid を送信先スキーマのレコードをドラッグするか、送信先スキーマのレコードを**一括コピー** functoid です。</span><span class="sxs-lookup"><span data-stu-id="6fca1-116">To use the output parameter from the **Mass Copy** functoid, create an output link by dragging the **Mass Copy** functoid to a record in the destination schema, or by dragging a record in the destination schema to the **Mass Copy** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6fca1-117">他の functoid とは異なりの出力を使用することはできません、**一括コピー** functoid を別の functoid の入力として。</span><span class="sxs-lookup"><span data-stu-id="6fca1-117">Unlike other functoids, you cannot use the output of the **Mass Copy** functoid as input to another functoid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fca1-118">挿入して構成することができます、**一括コピー**直接リンクすると 2 つの functoid を記録します。</span><span class="sxs-lookup"><span data-stu-id="6fca1-118">You can insert and configure the **Mass Copy** functoid by linking two records directly.</span></span> <span data-ttu-id="6fca1-119">詳細については、リンクするには、一括コピー functoid を使用する」セクションを参照してください[レコードを自動的にリンクする方法](../core/how-to-link-records-automatically.md)です。</span><span class="sxs-lookup"><span data-stu-id="6fca1-119">For more information, see the section “To link using a mass copy functoid” in [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fca1-120">参照</span><span class="sxs-lookup"><span data-stu-id="6fca1-120">See Also</span></span>  
 [<span data-ttu-id="6fca1-121">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="6fca1-121">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)