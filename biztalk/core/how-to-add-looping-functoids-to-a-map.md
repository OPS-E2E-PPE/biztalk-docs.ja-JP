---
title: "マップにループ Functoid を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b24051b7-3e79-4a49-8249-a057c048ddae
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa380b4a92de685ad8dc19c27a98f6578d12dc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-looping-functoids-to-a-map"></a><span data-ttu-id="48be9-102">マップにループ Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="48be9-102">How to Add Looping Functoids to a Map</span></span>

## <a name="overview"></a><span data-ttu-id="48be9-103">概要</span><span class="sxs-lookup"><span data-stu-id="48be9-103">Overview</span></span>
<span data-ttu-id="48be9-104">**ループ**functoid が複数のレコードまたは送信元スキーマ内のフィールドを送信先スキーマの 1 つのレコードに結合します。</span><span class="sxs-lookup"><span data-stu-id="48be9-104">The **Looping** functoid combines multiple records or fields in the source schema into a single record in the destination schema.</span></span>  
  
 <span data-ttu-id="48be9-105">概要については、**ループ**functoid を参照してください[ループ Functoid の](../core/looping-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="48be9-105">For conceptual information about the **Looping** functoid, see [Looping Functoid](../core/looping-functoid.md).</span></span>  
  
 <span data-ttu-id="48be9-106">特定の状況では、一部の functoid が正常に動作しないと共にマップで使用している場合、**ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="48be9-106">Under certain conditions, some functoids might not behave as expected when they are used in a map with a **Looping** functoid.</span></span> <span data-ttu-id="48be9-107">次の条件下では、期待どおりの結果が生成されません。</span><span class="sxs-lookup"><span data-stu-id="48be9-107">If such a functoid meets the following conditions, it does not produce the expected results:</span></span>  
  
-   <span data-ttu-id="48be9-108">Functoid に複数の入力リンクが存在する。</span><span class="sxs-lookup"><span data-stu-id="48be9-108">The functoid has more than one input link.</span></span>  
  
-   <span data-ttu-id="48be9-109">2 つまたは複数の functoid の入力リンクは、入力レコードの子フィールドにリンクされて、**ループ**functoid は、子フィールドが兄弟ではないです。</span><span class="sxs-lookup"><span data-stu-id="48be9-109">Two or more of the functoid input links are linked to child fields of the input records to the **Looping** functoid, where the child fields are not siblings.</span></span>  
  
-   <span data-ttu-id="48be9-110">Functoid の出力レコードの子フィールドにリンクされている出力リンクを持つ、**ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="48be9-110">The functoid has an output link that is linked to a child field of the output record of the **Looping** functoid.</span></span>  
  
## <a name="add-the-looping-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="48be9-111">マップにループ functoid を追加し、構成</span><span class="sxs-lookup"><span data-stu-id="48be9-111">Add the Looping functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="48be9-112">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。</span><span class="sxs-lookup"><span data-stu-id="48be9-112">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="48be9-113">選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48be9-113">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="48be9-114">ドラッグ、**ループ**ツールボックスから functoid をグリッド ページの適切な場所をします。</span><span class="sxs-lookup"><span data-stu-id="48be9-114">Drag the **Looping** functoid from the Toolbox to the appropriate location on a grid page.</span></span>  
  
     ![](../core/media/bts-tls-looping.gif "bts_tls_looping")  
<span data-ttu-id="48be9-115">ループ functoid</span><span class="sxs-lookup"><span data-stu-id="48be9-115">Looping functoid</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48be9-116">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="48be9-116">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="48be9-117">別のグリッド ページに functoid を配置する場合は、その他のグリッド ページを最初に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48be9-117">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
    > 
    >  <span data-ttu-id="48be9-118">複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48be9-118">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="48be9-119">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="48be9-119">Functoids are executed from left to right.</span></span> <span data-ttu-id="48be9-120">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="48be9-120">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="48be9-121">入力パラメーターを確立するために、**ループ**functoid、レコードをドラッグして、入力リンクを作成またはフィールドを送信元スキーマから、**ループ**functoid をドラッグするか、**ループ** functoid、レコードまたは送信元スキーマのフィールドをします。</span><span class="sxs-lookup"><span data-stu-id="48be9-121">To establish the input parameters for the **Looping** functoid, create an input link by dragging a record or field from the source schema to the **Looping** functoid, or dragging the **Looping** functoid to a record or field in the source schema.</span></span> <span data-ttu-id="48be9-122">すべての関連する入力レコードまたはフィールドを含める手順を繰り返して、**ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="48be9-122">Repeat as required to include all of the relevant input records or fields to the **Looping** functoid.</span></span>  
  
4.  <span data-ttu-id="48be9-123">出力パラメーターを使用する、**ループ**functoid をドラッグして、出力リンクを作成、**ループ**functoid、レコードまたはフィールド、送信先スキーマのレコードまたはフィールドをドラッグするかを変換先スキーマ、**ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="48be9-123">To use the output parameter from the **Looping** functoid, create an output link by dragging the **Looping** functoid to a record or field in the destination schema, or by dragging a record or field in the destination schema to the **Looping** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48be9-124">多くの他の functoid の出力とは異なり、**ループ**functoid は送信先スキーマの要素にのみリンクできます。</span><span class="sxs-lookup"><span data-stu-id="48be9-124">Unlike many other functoids, the output of the **Looping** functoid can only be linked to an element of the destination schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48be9-125">参照</span><span class="sxs-lookup"><span data-stu-id="48be9-125">See Also</span></span>  
-  [<span data-ttu-id="48be9-126">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="48be9-126">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)   
-  <span data-ttu-id="48be9-127">**ループ Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="48be9-127">**Looping Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>