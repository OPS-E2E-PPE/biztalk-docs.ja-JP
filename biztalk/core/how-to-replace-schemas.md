---
title: スキーマを置換する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 104e60d3-1303-4e56-b13a-c10ab14ba383
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df444b8169d75408fe6e412135029ae2b051a6d2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-replace-schemas"></a><span data-ttu-id="49bc0-102">スキーマを置換する方法</span><span class="sxs-lookup"><span data-stu-id="49bc0-102">How to Replace Schemas</span></span>
<span data-ttu-id="49bc0-103">更新されたスキーマを取引先から受け取った場合など、既存のマップ内にある送信元や送信先スキーマの置換が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="49bc0-103">There may be times when you want to replace either the source or destination schema in an existing map, such as when you receive an updated schema from a trading partner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49bc0-104">BizTalk マッパーでは、保持されるスキーマと置換されるスキーマの間の既存のリンクが維持されます。</span><span class="sxs-lookup"><span data-stu-id="49bc0-104">The BizTalk Mapper attempts to maintain all existing links between the retained schema and the replaced schema.</span></span>  
  
## <a name="replace-a-source-or-destination-schema"></a><span data-ttu-id="49bc0-105">送信元または送信先スキーマを置換します。</span><span class="sxs-lookup"><span data-stu-id="49bc0-105">Replace a source or destination schema</span></span>  
  
1.  <span data-ttu-id="49bc0-106">移行元または送信先のスキーマ ツリー ビューを右クリックし、 **スキーマの置換**します。</span><span class="sxs-lookup"><span data-stu-id="49bc0-106">Right-click either the source or destination schema tree view, and then select **Replace Schema**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49bc0-107">または、キーボードで Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら S キーを押します。</span><span class="sxs-lookup"><span data-stu-id="49bc0-107">Alternatively, you can also press CTRL+M, CTRL+S from the keyboard.</span></span> <span data-ttu-id="49bc0-108">マッパーのキーボード ショートカットの一覧については、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="49bc0-108">For a complete list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
2.  <span data-ttu-id="49bc0-109">**BizTalk 型の選択** ] ダイアログ ボックスで、展開、 **スキーマ** 、ツリー内のノードが、適切なスキーマを選択し、[ **OK**します。</span><span class="sxs-lookup"><span data-stu-id="49bc0-109">In the **BizTalk Type Picker** dialog box, expand the **Schemas** node in the tree, select the appropriate schema, and then select **OK**.</span></span>  
  
     <span data-ttu-id="49bc0-110">![スキーマを選択](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")</span><span class="sxs-lookup"><span data-stu-id="49bc0-110">![Select the Schema](../core/media/biztalk-typepicker.gif "BizTalk_TypePicker")</span></span>  

    > [!TIP] 
    > <span data-ttu-id="49bc0-111">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**スキーマの完全な名前を表示する型の選択 ウィンドウのサイズを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="49bc0-111">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize the Type Picker window to see the full name of your schema.</span></span>
      
     <span data-ttu-id="49bc0-112">置換スキーマに単一のルートが存在するか、置換を使用してスキーマのルート ノードが設定された場合のみ、 **ルート参照** のプロパティ、 **スキーマ** ノード、該当するペインに置換スキーマが開きますおよび手順 3. を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="49bc0-112">If only a single root exists in the replacement schema, or a root node has been established for the replacement schema using the **Root Reference** property of the **Schema** node, the replacement schema opens in the relevant pane, and you will not need to perform step 3.</span></span>  
  
3.  <span data-ttu-id="49bc0-113">複数のルート ノードが、送信先スキーマ内に存在し、変換先を使用してスキーマのルート ノードが設定されていない場合、**ルート参照**のプロパティ、**スキーマ**ノードで、**ルートノードを\<*ソース/ターゲット*\>スキーマ**ダイアログ ボックスで、適切なルート ノードを選択し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="49bc0-113">If multiple root nodes exist in the destination schema, and no root node has been established for the destination schema using the **Root Reference** property of the **Schema** node, in the **Root Node for \<*Source/Target*\> Schema** dialog box, select the appropriate root node, and then select **OK**.</span></span>  
  
     <span data-ttu-id="49bc0-114">該当するペインに置換スキーマが開きます。</span><span class="sxs-lookup"><span data-stu-id="49bc0-114">The replacement schema opens in the relevant pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49bc0-115">スキーマを置換する際、関連するレコードまたはフィールドが見つかった場合は、一部のリンクが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="49bc0-115">While replacing schema, if relevant records/fields are not found, some links may get lost.</span></span> <span data-ttu-id="49bc0-116">選択した場合にのみ、スキーマが置き換えられます **はい** で、 **確認**   ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="49bc0-116">The schema is replaced only when you select **Yes** on the **Confirmation**  dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49bc0-117">参照</span><span class="sxs-lookup"><span data-stu-id="49bc0-117">See Also</span></span>  
 [<span data-ttu-id="49bc0-118">プロジェクト内のマップの管理</span><span class="sxs-lookup"><span data-stu-id="49bc0-118">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)