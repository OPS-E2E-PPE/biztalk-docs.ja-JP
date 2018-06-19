---
title: マップに Nil 値 Functoid を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2e193ed-fe5c-4b12-aab8-ff2d81fd45e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cc7d8b0035161b4a2126ace021072ffcd1d17e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248210"
---
# <a name="how-to-add-nil-value-functoids-to-a-map"></a><span data-ttu-id="98132-102">マップに Nil 値 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="98132-102">How to Add Nil Value Functoids to a Map</span></span>
<span data-ttu-id="98132-103">**Nil 値**functoid を移行先ノードの値を設定する**Nil**です。</span><span class="sxs-lookup"><span data-stu-id="98132-103">The **Nil Value** functoid sets the value of the destination node to **Nil**.</span></span>  
  
 <span data-ttu-id="98132-104">概要については、 **Nil 値**functoid を参照してください[Nil 値 Functoid](../core/nil-value-functoid.md)です。</span><span class="sxs-lookup"><span data-stu-id="98132-104">For conceptual information about the **Nil Value** functoid, see [Nil Value Functoid](../core/nil-value-functoid.md).</span></span>  
  
## <a name="add-the-nil-value-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="98132-105">マップに Nil 値 functoid を追加し、構成</span><span class="sxs-lookup"><span data-stu-id="98132-105">Add the Nil Value functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="98132-106">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。</span><span class="sxs-lookup"><span data-stu-id="98132-106">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span> <span data-ttu-id="98132-107">選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="98132-107">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="98132-108">ドラッグ、 **Nil 値**functoid (![Nil 値 functoid](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) をグリッド ページの適切な場所にツールボックスからです。</span><span class="sxs-lookup"><span data-stu-id="98132-108">Drag the **Nil Value** functoid (![Nil Value functoid](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="98132-109">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="98132-109">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="98132-110">別のグリッド ページに functoid を配置する場合は、その他のグリッド ページを最初に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98132-110">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
    >
    >  <span data-ttu-id="98132-111">複数の Functoid を使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98132-111">If you are constructing a map that uses more than one functoid, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="98132-112">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="98132-112">Functoids are executed from left to right.</span></span> <span data-ttu-id="98132-113">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="98132-113">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="98132-114">**Nil 値**functoid が 1 つの入力パラメーターに 0 を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="98132-114">The **Nil Value** functoid can have zero to one input parameters.</span></span> <span data-ttu-id="98132-115">この functoid の入力パラメーターがない場合は、ターゲット ノードに設定されている**Nil**です。</span><span class="sxs-lookup"><span data-stu-id="98132-115">If there is no input parameter for this functoid, the target node is set to **Nil**.</span></span> <span data-ttu-id="98132-116">入力パラメーターを設定する、 **Nil 値**functoid から他の出力をドラッグして、入力リンクを作成**論理**functoid または入力インスタンス メッセージ内の変数ブール値フィールドからです。</span><span class="sxs-lookup"><span data-stu-id="98132-116">To establish the input parameter for the **Nil Value** functoid, create an input link by dragging the output from some other **Logical** functoid or from a variable Boolean field in the input instance message.</span></span>  
  
4.  <span data-ttu-id="98132-117">出力パラメーターを使用する、 **Nil 値**functoid をドラッグして、出力リンクを作成、 **Nil 値**functoid、レコードまたは送信先スキーマのフィールドをします。</span><span class="sxs-lookup"><span data-stu-id="98132-117">To use the output parameter from the **Nil Value** functoid, create an output link by dragging the **Nil Value** functoid to a record or field in the destination schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="98132-118">その他の functoid の出力と同様、 **Nil 値**functoid を別の functoid への入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="98132-118">As with other functoids, the output of the **Nil Value** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98132-119">参照</span><span class="sxs-lookup"><span data-stu-id="98132-119">See Also</span></span>  
-  <span data-ttu-id="98132-120">**Nil 値 Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="98132-120">**Nil Value Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
-  [<span data-ttu-id="98132-121">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="98132-121">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)