---
title: XSD ビューを管理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3245ebf0-6128-47b4-8e88-ea06ececbc15
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aa052fffcb50854b43cd8b1df169c026e4c0320
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384608"
---
# <a name="how-to-manage-the-xsd-view"></a><span data-ttu-id="8248d-102">XSD ビューを管理する方法</span><span class="sxs-lookup"><span data-stu-id="8248d-102">How to Manage the XSD View</span></span>
<span data-ttu-id="8248d-103">に関しては、XSD ビューの管理タスクは、3 種類に分けることができます。 そのサイズを変更する、その背景色とフォントの変更、および更新特性を変更します。</span><span class="sxs-lookup"><span data-stu-id="8248d-103">Management tasks with respect to the XSD view can be divided into three categories: changing its size, changing its background color and font, and changing its refresh characteristics.</span></span>  
  
 <span data-ttu-id="8248d-104">更新特性の変更、後者に分類が最も役に立つ更新が望ましくない遅延を引き起こす可能性がありますの自動の大規模なスキーマを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="8248d-104">The latter category, concerning refresh characteristics, is most useful when working with large schemas, for which using automatic refresh might cause undesirable delays.</span></span> <span data-ttu-id="8248d-105">このような場合、自動 (連続) 更新を無効にし、代わりに、必要に応じて手動で XSD ビューを更新できます。</span><span class="sxs-lookup"><span data-stu-id="8248d-105">In such cases, you can disable automatic (continuous) refresh, and instead refresh the XSD view manually as needed.</span></span>  
  
 <span data-ttu-id="8248d-106">このトピックでは、これらのタスクの詳細な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="8248d-106">This topic provides step-by-step instructions for these tasks.</span></span>  
  
### <a name="to-make-the-xsd-view-taller-or-shorter"></a><span data-ttu-id="8248d-107">XSD ビューのサイズを垂直方向に変更するには</span><span class="sxs-lookup"><span data-stu-id="8248d-107">To make the XSD view taller or shorter</span></span>  
  
1. <span data-ttu-id="8248d-108">Microsoft の下端にマウス ポインターを移動[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]メイン編集ウィンドウが標準的なウィンドウの垂直方向サイズ変更アイコンにカーソルが変更されるまで、XSD ビューのサイドとスキーマ ツリー ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8248d-108">Move the mouse pointer to the bottom edge of the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] main editing window, which displays the XSD view side-by-side with the schema tree view, until the cursor changes to the standard window vertical resizing icon.</span></span>  
  
2. <span data-ttu-id="8248d-109">クリックし、マウスの左ボタンを押したままおよび上または下のウィンドウの端をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8248d-109">Click and hold the left mouse button and drag the window edge either up or down.</span></span>  
  
    <span data-ttu-id="8248d-110">メイン編集ウィンドウ全体を垂直方向にサイズ変更によって、XSD ビューのサイズを変更できますが垂直方向に。</span><span class="sxs-lookup"><span data-stu-id="8248d-110">You have vertically resized the XSD view by vertically resizing the entire main editing window.</span></span>  
  
### <a name="to-make-the-xsd-view-wider-or-more-narrow"></a><span data-ttu-id="8248d-111">XSD ビューの水平方向にサイズ変更するには</span><span class="sxs-lookup"><span data-stu-id="8248d-111">To make the XSD view wider or more narrow</span></span>  
  
1. <span data-ttu-id="8248d-112">ペインの区切り線にマウス ポインターを移動、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]メイン編集ウィンドウで、カーソルは、標準のウィンドウ アイコンのサイズを水平方向に変更されるまでに、スキーマ ツリー ビューから、XSD ビューを分割します。</span><span class="sxs-lookup"><span data-stu-id="8248d-112">Move the mouse pointer to the pane divider in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] main editing window, which divides the XSD view from the schema tree view, until the cursor changes to the standard window horizontal resizing icon.</span></span>  
  
2. <span data-ttu-id="8248d-113">クリックして、マウスの左 (狭くする) ボタンと左 (広くする) か、右ペインの端をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8248d-113">Click and hold the left mouse button and drag the pane edge either left (wider) or right (narrower).</span></span>  
  
    <span data-ttu-id="8248d-114">XSD ビューがスキーマ ツリー ビューを基準に、メイン編集ウィンドウの量を変更することで、XSD ビューのサイズを変更してが水平方向にします。</span><span class="sxs-lookup"><span data-stu-id="8248d-114">You have horizontally resized the XSD view by changing the amount of the main editing window dedicated to the XSD view, relative to the schema tree view.</span></span>  
  
    <span data-ttu-id="8248d-115">メイン編集ウィンドウ全体を水平方向にサイズ変更によって、XSD ビューの幅を広げたり狭めたりを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8248d-115">You can also make the XSD view wider or narrower by horizontally resizing the entire main editing window.</span></span>  
  
### <a name="to-change-the-background-color-andor-font-used-by-the-xsd-view"></a><span data-ttu-id="8248d-116">背景色/XSD ビューで使用されるフォントを変更するには</span><span class="sxs-lookup"><span data-stu-id="8248d-116">To change the background color and/or font used by the XSD view</span></span>  
  
1. <span data-ttu-id="8248d-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]で、 **[ツール]** メニューの **[オプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8248d-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2. <span data-ttu-id="8248d-118">**オプション**ダイアログ ボックスで、BizTalk エディター フォルダーをクリックし、必要に応じて、展開、**スキーマの表示**プラス記号をクリックしてカテゴリ (+) アイコン。</span><span class="sxs-lookup"><span data-stu-id="8248d-118">In the **Options** dialog box, click the BizTalk Editor folder, and if necessary, expand the **Schema Display** category by clicking the plus (+) icon.</span></span>  
  
3. <span data-ttu-id="8248d-119">ドロップダウン リストのカラー ピッカーを使用して背景色/フォントを変更または**フォント**に関連付けられているダイアログ ボックス、 **XSD ビューの背景色**と**XSD ビューのフォント**プロパティは、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="8248d-119">Change the background color and/or font by using the drop-down color picker and/or **Font** dialog box associated with the **XSD View Background Color** and **XSD View Font** properties, respectively.</span></span>  
  
    <span data-ttu-id="8248d-120">アクセス、**フォント**、省略記号を使用して、ダイアログ ボックス (**.**) ボタンの右端にある、 **XSD ビューのフォント**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="8248d-120">Access the **Font** dialog box by using the ellipsis (**…**) button located at the right end of the **XSD View Font** property value box.</span></span>  
  
### <a name="to-turn-automatic-refresh-of-the-xsd-view-on-and-off"></a><span data-ttu-id="8248d-121">XSD ビューの自動更新を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="8248d-121">To turn automatic refresh of the XSD view on and off</span></span>  
  
-   <span data-ttu-id="8248d-122">BizTalk エディターでは、下、 **XSD** ] タブで [**自動更新をオフに**または**自動更新を有効**。</span><span class="sxs-lookup"><span data-stu-id="8248d-122">In BizTalk Editor, below the **XSD** tab, click **Turn off auto refresh** or **Turn on auto refresh**.</span></span>  
  
     <span data-ttu-id="8248d-123">自動更新がオフの場合は、XSD ビューが空白です。</span><span class="sxs-lookup"><span data-stu-id="8248d-123">When auto-refresh is off, the XSD view is blank.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8248d-124">既定で自動更新はオンです。</span><span class="sxs-lookup"><span data-stu-id="8248d-124">By default, auto-refresh is on.</span></span> <span data-ttu-id="8248d-125">スキーマし、自動更新機能をオフにし、スキーマを必要に応じて手動で更新することがますます重要になりますが大きく、します。</span><span class="sxs-lookup"><span data-stu-id="8248d-125">As your schemas become bigger and bigger, it becomes increasingly important for you to turn off the automatic refresh feature and refresh your schema manually as needed.</span></span>  
  
### <a name="to-manually-refresh-the-xsd-view"></a><span data-ttu-id="8248d-126">XSD ビューを手動で更新するには</span><span class="sxs-lookup"><span data-stu-id="8248d-126">To manually refresh the XSD view</span></span>  
  
-   <span data-ttu-id="8248d-127">**BizTalk**  メニューのをクリックして**XSD の更新**します。</span><span class="sxs-lookup"><span data-stu-id="8248d-127">On the **BizTalk** menu, click **Refresh XSD**.</span></span>  
  
     <span data-ttu-id="8248d-128">XSD では、スキーマ ツリーに対して行った変更を反映して更新プログラムを表示します。</span><span class="sxs-lookup"><span data-stu-id="8248d-128">The XSD view updates to reflect any changes you have made to the schema tree.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8248d-129">クリックして、XSD ビューを更新することができますも手動で**XSD の更新**かをクリックして、スキーマ ツリー内のすべてのノードに関連付けられているショートカット メニューで、**更新**以下のリンク、 **XSD** XSD ビュー タブで。</span><span class="sxs-lookup"><span data-stu-id="8248d-129">You can also manually refresh the XSD view by clicking **Refresh XSD** on the shortcut menu associated with every node in the schema tree, or by clicking the **Refresh** link below the **XSD** tab in the XSD view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8248d-130">参照</span><span class="sxs-lookup"><span data-stu-id="8248d-130">See Also</span></span>  
 [<span data-ttu-id="8248d-131">BizTalk エディターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="8248d-131">Using BizTalk Editor</span></span>](../core/using-biztalk-editor.md)