---
title: 値のマッピングをマップに Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc70067a-67a1-4a0e-95e5-b0cb327d2cee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b06dbef26572dfc6634e70d12b632f361440df6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387326"
---
# <a name="how-to-add-value-mapping-functoids-to-a-map"></a><span data-ttu-id="364af-102">値のマッピングをマップに Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="364af-102">How to Add Value Mapping Functoids to a Map</span></span>
<span data-ttu-id="364af-103">**値のマッピング**functoid は、最初のパラメーターが true の場合に 2 番目のパラメーターの値を返します。</span><span class="sxs-lookup"><span data-stu-id="364af-103">The **Value Mapping** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="364af-104">Functoid の一般的な用途は、フィールドの属性をレコードの属性に変更するのにです。</span><span class="sxs-lookup"><span data-stu-id="364af-104">A common use of the functoid is to change the attributes of a field into the attributes of a record.</span></span>  
  
 <span data-ttu-id="364af-105">概念情報については、**値のマッピング**functoid を参照してください[値のマッピング Functoid](../core/value-mapping-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="364af-105">For conceptual information about the **Value Mapping** functoid, see [Value Mapping Functoid](../core/value-mapping-functoid.md).</span></span>  
  
### <a name="to-add-the-value-mapping-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="364af-106">値のマッピング functoid をマップに追加し、構成するには</span><span class="sxs-lookup"><span data-stu-id="364af-106">To add the Value Mapping functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="364af-107">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。</span><span class="sxs-lookup"><span data-stu-id="364af-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="364af-108">選択したカテゴリでの高度な functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="364af-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="364af-109">ドラッグ、**値のマッピング**functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) ツールボックスからグリッド ページの適切な場所にします。</span><span class="sxs-lookup"><span data-stu-id="364af-109">Drag the **Value Mapping** functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="364af-110">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="364af-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="364af-111">別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="364af-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="364af-112">複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="364af-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="364af-113">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="364af-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="364af-114">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="364af-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="364af-115">最初の入力パラメーターを設定する、**値のマッピング**functoid をドラッグして、入力リンクを作成、**値のマッピング**functoid、送信元スキーマのレコードまたはフィールド ノードまたは別の functoid左は、Boolean データ型を持つし、"true"または"false"の入力値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="364af-115">To establish the first input parameter for the **Value Mapping** functoid, create an input link by dragging the **Value Mapping** functoid to a record or field node in the source schema, or to another functoid to its left, that has a Boolean data type and that will produce an input value of "true" or "false".</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="364af-116">ドラッグすることも、方向が逆にするブール値のソースをドラッグ、**値のマッピング**functoid。</span><span class="sxs-lookup"><span data-stu-id="364af-116">You can also drag in the opposite direction, dragging the source of the Boolean value to the **Value Mapping** functoid.</span></span>  
  
4. <span data-ttu-id="364af-117">2 番目の入力パラメーターを設定する、**値のマッピング**functoid をドラッグして、入力リンクを作成、**値のマッピング**レコードまたはフィールド ノードは、送信元スキーマ、またはレコードをドラッグして functoidまたはフィールド ノードに送信元スキーマ、**値のマッピング**functoid。</span><span class="sxs-lookup"><span data-stu-id="364af-117">To establish the second input parameter for the **Value Mapping** functoid, create an input link by dragging the **Value Mapping** functoid to a record or field node in the source schema, or by dragging a record or field node in the source schema to the **Value Mapping** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="364af-118">2 番目の入力パラメーターを**値のマッピング**の左側に、functoid は別の functoid の出力から指定もできます。</span><span class="sxs-lookup"><span data-stu-id="364af-118">The second input parameter to the **Value Mapping** functoid can also be from the output of another functoid to its left.</span></span> <span data-ttu-id="364af-119">関連する functoid のいずれかをその他の関連する functoid にドラッグしてこのような入力ソースを表すリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="364af-119">Create the links that represent such sources of input by dragging one of the relevant functoids to the other relevant functoid.</span></span>  
  
5. <span data-ttu-id="364af-120">出力パラメーターを使用する、**値のマッピング**functoid をドラッグして、出力リンクを作成、**値のマッピング**functoid、レコードまたはフィールドに、送信先スキーマ レコード フィールドをドラッグするかを変換先スキーマ、**値のマッピング**functoid。</span><span class="sxs-lookup"><span data-stu-id="364af-120">To use the output parameter from the **Value Mapping** functoid, create an output link by dragging the **Value Mapping** functoid to a record or field in the destination schema, or by dragging a record field in the destination schema to the **Value Mapping** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="364af-121">他の functoid の出力と同様、**値のマッピング**functoid が別の functoid への入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="364af-121">As with other functoids, the output of the **Value Mapping** functoid can serve as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="364af-122">参照</span><span class="sxs-lookup"><span data-stu-id="364af-122">See Also</span></span>  
 [<span data-ttu-id="364af-123">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="364af-123">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)