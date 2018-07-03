---
title: マップにレコード カウント Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fbfd2a0-fac5-49f1-bcbb-873c287cd278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d5fda3565d2b7c3302b5ae3cb596bfed6781609
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980331"
---
# <a name="how-to-add-record-count-functoids-to-a-map"></a><span data-ttu-id="3d839-102">マップにレコード カウント Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="3d839-102">How to Add Record Count Functoids to a Map</span></span>
<span data-ttu-id="3d839-103">**レコード カウント**functoid では、インスタンス メッセージ内のレコードの出現回数の合計数を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="3d839-103">The **Record Count** functoid enables you to generate a count of the number of times a record occurs in an instance message.</span></span>  
  
 <span data-ttu-id="3d839-104">概念情報については、**レコード カウント**functoid を参照してください[レコード カウント Functoid](../core/record-count-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="3d839-104">For conceptual information about the **Record Count** functoid, see [Record Count Functoid](../core/record-count-functoid.md).</span></span>  
  
### <a name="to-add-the-record-count-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="3d839-105">マップにレコード カウント Functoid を追加して構成するには</span><span class="sxs-lookup"><span data-stu-id="3d839-105">To add the Record Count functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="3d839-106">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。</span><span class="sxs-lookup"><span data-stu-id="3d839-106">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="3d839-107">選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d839-107">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="3d839-108">ドラッグ、**レコード カウント**functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) ツールボックスからグリッド ページの適切な場所にします。</span><span class="sxs-lookup"><span data-stu-id="3d839-108">Drag the **Record Count** functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3d839-109">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="3d839-109">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="3d839-110">別のグリッド ページに Functoid を配置する場合は、先にそのグリッド ページを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d839-110">If you want to put the functoid onto a different grid page, you need to display the other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3d839-111">複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d839-111">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="3d839-112">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="3d839-112">Functoids are executed from left to right.</span></span> <span data-ttu-id="3d839-113">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="3d839-113">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="3d839-114">入力パラメーターを設定する、**レコード カウント**functoid、送信元スキーマからループ レコードをドラッグして、入力リンクを作成、**レコード カウント**functoid をドラッグするか、 **レコード カウント**functoid、送信元スキーマのループ レコードを送信します。</span><span class="sxs-lookup"><span data-stu-id="3d839-114">To establish the input parameter for the **Record Count** functoid, create an input link by dragging a looping record from the source schema to the **Record Count** functoid, or dragging the **Record Count** functoid to a looping record in the source schema.</span></span>  
  
4. <span data-ttu-id="3d839-115">出力パラメーターを使用する、**レコード カウント**functoid をドラッグして、出力リンクを作成、**レコード カウント**またはコピー先にフィールドをドラッグして、送信先スキーマのフィールドを functoidスキーマを**レコード カウント**functoid。</span><span class="sxs-lookup"><span data-stu-id="3d839-115">To use the output parameter from the **Record Count** functoid, create an output link by dragging the **Record Count** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Record Count** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3d839-116">他の functoid の出力と同様、**レコード カウント**functoid を別の functoid への入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d839-116">As with other functoids, the output of the **Record Count** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d839-117">参照</span><span class="sxs-lookup"><span data-stu-id="3d839-117">See Also</span></span>  
 [<span data-ttu-id="3d839-118">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="3d839-118">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)