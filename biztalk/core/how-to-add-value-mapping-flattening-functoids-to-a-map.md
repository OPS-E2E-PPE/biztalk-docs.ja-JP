---
title: 値のマッピング (フラット化) Functoid をマップに追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00a447c3-58d0-42ab-a5c4-417ee7800a6b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b630b586e1252d0afb244deb77ab3e4c7bfaf30
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343056"
---
# <a name="how-to-add-value-mapping-flattening-functoids-to-a-map"></a><span data-ttu-id="a7bf8-102">値のマッピング (フラット化) Functoid をマップに追加する方法</span><span class="sxs-lookup"><span data-stu-id="a7bf8-102">How to Add Value Mapping (Flattening) Functoids to a Map</span></span>
<span data-ttu-id="a7bf8-103">**値のマッピング (フラット化)** functoid では、複数のレコードを 1 つのレコードに変換することによって、入力インスタンス メッセージの一部をフラット化することができます。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-103">The **Value Mapping (Flattening)** functoid enables you to flatten a portion of an input instance message by converting multiple records into a single record.</span></span> <span data-ttu-id="a7bf8-104">これは、Microsoft Commerce Server カタログを変換する場合の一般的な操作です。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-104">This is a common operation in converting Microsoft Commerce Server catalogs.</span></span>  
  
 <span data-ttu-id="a7bf8-105">概念情報については、**値のマッピング (フラット化)** functoid を参照してください[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-105">For conceptual information about the **Value Mapping (Flattening)** functoid, see [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
### <a name="to-add-the-value-mapping-flattening-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="a7bf8-106">値のマッピング (フラット化) functoid をマップに追加し、構成するには</span><span class="sxs-lookup"><span data-stu-id="a7bf8-106">To add the Value Mapping (Flattening) functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="a7bf8-107">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="a7bf8-108">選択したカテゴリでの高度な functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="a7bf8-109">ドラッグ、**値のマッピング (フラット化)** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) ツールボックスからグリッド ページの適切な場所にします。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-109">Drag the **Value Mapping (Flattening)** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7bf8-110">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="a7bf8-111">別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7bf8-112">複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="a7bf8-113">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="a7bf8-114">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="a7bf8-115">最初の入力パラメーターを設定する、**値のマッピング (フラット化)** functoid をドラッグして、入力リンクを作成、**値のマッピング (フラット化)** ソースのレコードまたはフィールド ノードを functoidスキーマ、またはブール型のデータ型を持つ別の functoid の左側に、および"true"または"false"の入力値が生成されます</span><span class="sxs-lookup"><span data-stu-id="a7bf8-115">To establish the first input parameter for the **Value Mapping (Flattening)** functoid, create an input link by dragging the **Value Mapping (Flattening)** functoid to a record or field node in the source schema, or to another functoid to its left, that has a Boolean data type and that will produce an input value of "true" or "false."</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7bf8-116">ドラッグすることも、方向が逆にするブール値のソースをドラッグ、**値のマッピング (フラット化)** functoid。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-116">You can also drag in the opposite direction, dragging the source of the Boolean value to the **Value Mapping (Flattening)** functoid.</span></span>  
  
4. <span data-ttu-id="a7bf8-117">2 番目の入力パラメーターを設定する、**値のマッピング (フラット化)** functoid をドラッグして、入力リンクを作成、**値のマッピング (フラット化)** ソースのレコードまたはフィールド ノードを functoidスキーマ、送信元スキーマのレコードまたはフィールド ノードをドラッグするか、**値のマッピング (フラット化)** functoid、または定数を挿入します。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-117">To establish the second input parameter for the **Value Mapping (Flattening)** functoid, create an input link by dragging the **Value Mapping (Flattening)** functoid to a record or field node in the source schema, or by dragging a record or field node in the source schema to the **Value Mapping (Flattening)** functoid, or insert a constant.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7bf8-118">2 番目の入力パラメーターを**値のマッピング (フラット化)** の左側に、functoid は別の functoid の出力から指定もできます。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-118">The second input parameter to the **Value Mapping (Flattening)** functoid can also be from the output of another functoid to its left.</span></span> <span data-ttu-id="a7bf8-119">リンクを作成して、表すなどのソースの関連する functoid のいずれかをその他の関連する functoid にドラッグして入力します。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-119">Create the links the represent such sources of input by dragging one of the relevant functoids to the other relevant functoid.</span></span>  
  
5. <span data-ttu-id="a7bf8-120">出力パラメーターを使用する、**値のマッピング (フラット化)** functoid をドラッグして、出力リンクを作成、**値のマッピング (フラット化)** のレコードまたはフィールドを送信先スキーマ、または functoid変換先スキーマのレコード フィールドをドラッグして、**値のマッピング (フラット化)** functoid。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-120">To use the output parameter from the **Value Mapping (Flattening)** functoid, create an output link by dragging the **Value Mapping (Flattening)** functoid to a record or field in the destination schema, or by dragging a record field in the destination schema to the **Value Mapping (Flattening)** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7bf8-121">他の functoid の出力と同様、**値のマッピング (フラット化)** functoid を別の functoid への入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7bf8-121">As with other functoids, the output of the **Value Mapping (Flattening)** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7bf8-122">参照</span><span class="sxs-lookup"><span data-stu-id="a7bf8-122">See Also</span></span>  
 [<span data-ttu-id="a7bf8-123">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="a7bf8-123">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)