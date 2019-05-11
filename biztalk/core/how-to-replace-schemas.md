---
title: スキーマを置換する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 104e60d3-1303-4e56-b13a-c10ab14ba383
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d71c2c4231d3de506e3efc472281cac31f2b4b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334931"
---
# <a name="how-to-replace-schemas"></a><span data-ttu-id="60167-102">スキーマを置換する方法</span><span class="sxs-lookup"><span data-stu-id="60167-102">How to Replace Schemas</span></span>
<span data-ttu-id="60167-103">更新されたスキーマを取引先から受信したとき、既存のマップ内の元または変換先スキーマの置換する場合があります。</span><span class="sxs-lookup"><span data-stu-id="60167-103">There may be times when you want to replace either the source or destination schema in an existing map, such as when you receive an updated schema from a trading partner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60167-104">BizTalk マッパーは、保持されているスキーマと置換スキーマの間の既存のリンクを維持しようとします。</span><span class="sxs-lookup"><span data-stu-id="60167-104">The BizTalk Mapper attempts to maintain all existing links between the retained schema and the replaced schema.</span></span>  
  
## <a name="replace-a-source-or-destination-schema"></a><span data-ttu-id="60167-105">送信元または送信先スキーマを置換します。</span><span class="sxs-lookup"><span data-stu-id="60167-105">Replace a source or destination schema</span></span>  
  
1. <span data-ttu-id="60167-106">移行元または送信先のスキーマ ツリー ビューを右クリックし、**スキーマの置換**します。</span><span class="sxs-lookup"><span data-stu-id="60167-106">Right-click either the source or destination schema tree view, and then select **Replace Schema**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="60167-107">または、CTRL + M, CTRL + S、キーボードからを押してもできます。</span><span class="sxs-lookup"><span data-stu-id="60167-107">Alternatively, you can also press CTRL+M, CTRL+S from the keyboard.</span></span> <span data-ttu-id="60167-108">マッパーのキーボード ショートカットの完全な一覧を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)します。</span><span class="sxs-lookup"><span data-stu-id="60167-108">For a complete list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
2. <span data-ttu-id="60167-109">**BizTalk 型の選択**] ダイアログ ボックスで、展開、**スキーマ**ツリーで、ノードは、適切なスキーマを選択し、[ **OK**します。</span><span class="sxs-lookup"><span data-stu-id="60167-109">In the **BizTalk Type Picker** dialog box, expand the **Schemas** node in the tree, select the appropriate schema, and then select **OK**.</span></span>  
  
    <span data-ttu-id="60167-110">![スキーマ選択](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")</span><span class="sxs-lookup"><span data-stu-id="60167-110">![Select the Schema](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")</span></span>  

   > [!TIP]
   > <span data-ttu-id="60167-111">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** スキーマの完全名を表示する型の選択 ウィンドウのサイズを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="60167-111">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize the Type Picker window to see the full name of your schema.</span></span>
      
    <span data-ttu-id="60167-112">場合のみ、置換スキーマに単一のルートが存在するか、使用して置換スキーマのルート ノードが設定された、**ルート参照**のプロパティ、**スキーマ**ノード、置換スキーマが開きます関連するウィンドウで、手順 3. を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="60167-112">If only a single root exists in the replacement schema, or a root node has been established for the replacement schema using the **Root Reference** property of the **Schema** node, the replacement schema opens in the relevant pane, and you will not need to perform step 3.</span></span>  
  
3. <span data-ttu-id="60167-113">複数のルート ノードが、送信先スキーマ内に存在し、使用して変換先スキーマのルート ノードが設定されていない場合、**ルート参照**のプロパティ、**スキーマ**ノードで、**ルートノードの\<*ソース/ターゲット*\>スキーマ**ダイアログ ボックスで、適切なルート ノードを選択し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="60167-113">If multiple root nodes exist in the destination schema, and no root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, in the **Root Node for \<*Source/Target*\> Schema** dialog box, select the appropriate root node, and then select **OK**.</span></span>  
  
    <span data-ttu-id="60167-114">置換スキーマが、関連するウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="60167-114">The replacement schema opens in the relevant pane.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="60167-115">ときにスキーマを置換するには、関連するレコードまたはフィールドが見つからない場合のリンク可能性があります発生失われます。</span><span class="sxs-lookup"><span data-stu-id="60167-115">While replacing schema, if relevant records/fields are not found, some links may get lost.</span></span> <span data-ttu-id="60167-116">選択した場合にのみ、スキーマが置き換えられます**はい**上、**確認** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="60167-116">The schema is replaced only when you select **Yes** on the **Confirmation**  dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60167-117">参照</span><span class="sxs-lookup"><span data-stu-id="60167-117">See Also</span></span>  
 [<span data-ttu-id="60167-118">プロジェクト内のマップの管理</span><span class="sxs-lookup"><span data-stu-id="60167-118">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)