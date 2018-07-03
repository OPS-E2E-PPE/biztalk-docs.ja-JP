---
title: マップに繰り返し Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1eaea929-e352-447d-b119-bd69b6b24e6c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed2dfe33feb7d5e0e6f43be61742bfbbddfc98c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997195"
---
# <a name="how-to-add-iteration-functoids-to-a-map"></a><span data-ttu-id="77427-102">マップに繰り返し Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="77427-102">How to Add Iteration Functoids to a Map</span></span>
<span data-ttu-id="77427-103">**イテレーション**functoid の出力、ループの現在のレコードのインデックスが構造体の最初のレコードでは、2、2 つ目のレコードを 1 から始まる具合です。</span><span class="sxs-lookup"><span data-stu-id="77427-103">The **Iteration** functoid outputs the index of the current record in a looping structure, beginning at 1 for the first record, 2 for the second record, and so on.</span></span>  
  
 <span data-ttu-id="77427-104">概念情報については、**イテレーション**functoid を参照してください[繰り返し Functoid](../core/iteration-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="77427-104">For conceptual information about the **Iteration** functoid, see [Iteration Functoid](../core/iteration-functoid.md).</span></span>  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="77427-105">マップにインデックス Functoid を追加して構成するには</span><span class="sxs-lookup"><span data-stu-id="77427-105">To add the Index functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="77427-106">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。</span><span class="sxs-lookup"><span data-stu-id="77427-106">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="77427-107">選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="77427-107">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="77427-108">ドラッグ、**インデックス**functoid (![](../core/media/bts-tls-iteration.gif "bts_tls_iteration")) ツールボックスからグリッド ページの適切な場所にします。</span><span class="sxs-lookup"><span data-stu-id="77427-108">Drag the **Index** functoid (![](../core/media/bts-tls-iteration.gif "bts_tls_iteration")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="77427-109">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="77427-109">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="77427-110">別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77427-110">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="77427-111">複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77427-111">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="77427-112">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="77427-112">Functoids are executed from left to right.</span></span> <span data-ttu-id="77427-113">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="77427-113">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="77427-114">ループ レコード入力パラメーターを設定する、**イテレーション**functoid、送信元スキーマからループ レコードをドラッグして、入力リンクを作成、**イテレーション**functoid、をドラッグするか**イテレーション**functoid、送信元スキーマのループ レコードを送信します。</span><span class="sxs-lookup"><span data-stu-id="77427-114">To establish the looping record input parameter for the **Iteration** functoid, create an input link by dragging a looping record from the source schema to the **Iteration** functoid, or by dragging the **Iteration** functoid to a looping record in the source schema.</span></span>  
  
4. <span data-ttu-id="77427-115">出力パラメーターを使用する、**イテレーション**functoid をドラッグして、出力リンクを作成、**イテレーション**または変換先スキーマのフィールドをドラッグして、送信先スキーマのフィールドを functoid**イテレーション**functoid。</span><span class="sxs-lookup"><span data-stu-id="77427-115">To use the output parameter from the **Iteration** functoid, create an output link by dragging the **Iteration** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Iteration** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="77427-116">出力のデータ型に一致するように、送信先スキーマ内の関連するフィールドのデータ型が数値または数値に変換できるをある必要があります、**イテレーション**functoid。</span><span class="sxs-lookup"><span data-stu-id="77427-116">The data type of the relevant field in the destination schema must be numeric or convertible to numeric so that it matches the output data type of the **Iteration** functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77427-117">参照</span><span class="sxs-lookup"><span data-stu-id="77427-117">See Also</span></span>  
 [<span data-ttu-id="77427-118">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="77427-118">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)