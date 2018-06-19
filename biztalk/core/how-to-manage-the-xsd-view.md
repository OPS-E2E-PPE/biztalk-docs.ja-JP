---
title: XSD ビューを管理する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 945f3fc4d8eac3b09279ea774209a9f43a0f6bd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254434"
---
# <a name="how-to-manage-the-xsd-view"></a><span data-ttu-id="d0ea0-102">XSD ビューの管理方法</span><span class="sxs-lookup"><span data-stu-id="d0ea0-102">How to Manage the XSD View</span></span>
<span data-ttu-id="d0ea0-103">XSD ビューの管理タスクは、3 つのカテゴリに分類できます。 そのサイズを変更する、その背景色とフォントの変更、および更新特性の変更。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-103">Management tasks with respect to the XSD view can be divided into three categories: changing its size, changing its background color and font, and changing its refresh characteristics.</span></span>  
  
 <span data-ttu-id="d0ea0-104">特に更新特性の変更はスキーマの規模が大きい場合に有用です。スキーマの規模が大きいと、自動更新に時間かかる場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-104">The latter category, concerning refresh characteristics, is most useful when working with large schemas, for which using automatic refresh might cause undesirable delays.</span></span> <span data-ttu-id="d0ea0-105">このような場合は、自動 (連続) 更新を無効にし、必要に応じて手動で XSD ビューを更新できます。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-105">In such cases, you can disable automatic (continuous) refresh, and instead refresh the XSD view manually as needed.</span></span>  
  
 <span data-ttu-id="d0ea0-106">このトピックでは、これらの作業手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-106">This topic provides step-by-step instructions for these tasks.</span></span>  
  
### <a name="to-make-the-xsd-view-taller-or-shorter"></a><span data-ttu-id="d0ea0-107">XSD ビューのサイズを垂直方向に変更するには</span><span class="sxs-lookup"><span data-stu-id="d0ea0-107">To make the XSD view taller or shorter</span></span>  
  
1.  <span data-ttu-id="d0ea0-108">XSD ビューとスキーマ ツリー ビューが並んで表示されている Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウで、マウス ポインターをウィンドウの下枠に移動すると、カーソルのアイコンが、ウィンドウのサイズを垂直方向に変更する標準的なアイコンに変わります。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-108">Move the mouse pointer to the bottom edge of the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] main editing window, which displays the XSD view side-by-side with the schema tree view, until the cursor changes to the standard window vertical resizing icon.</span></span>  
  
2.  <span data-ttu-id="d0ea0-109">マウスの左ボタンをクリックし、ボタンを押しながらウィンドウの下枠を上または下にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-109">Click and hold the left mouse button and drag the window edge either up or down.</span></span>  
  
     <span data-ttu-id="d0ea0-110">メイン編集ウィンドウ全体を垂直方向にサイズ変更することにより、XSD ビューを垂直方向にサイズ変更できます。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-110">You have vertically resized the XSD view by vertically resizing the entire main editing window.</span></span>  
  
### <a name="to-make-the-xsd-view-wider-or-more-narrow"></a><span data-ttu-id="d0ea0-111">XSD ビューのサイズを水平方向に変更するには</span><span class="sxs-lookup"><span data-stu-id="d0ea0-111">To make the XSD view wider or more narrow</span></span>  
  
1.  <span data-ttu-id="d0ea0-112">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウで、マウス ポインターをペイン分割バー (XSD ビューとスキーマ ツリー ビューを区切る線) に移動すると、カーソルのアイコンが、ウィンドウのサイズを水平方向に変更する標準的なアイコンに変わります。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-112">Move the mouse pointer to the pane divider in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] main editing window, which divides the XSD view from the schema tree view, until the cursor changes to the standard window horizontal resizing icon.</span></span>  
  
2.  <span data-ttu-id="d0ea0-113">マウスの左ボタンをクリックし、ボタンを押しながらペインの端を左 (広くする) または右 (狭くする) にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-113">Click and hold the left mouse button and drag the pane edge either left (wider) or right (narrower).</span></span>  
  
     <span data-ttu-id="d0ea0-114">メイン編集ウィンドウ内でスキーマ ツリー ビューと XSD ビューが占める割合を水平方向に変更することにより、XSD ビューを水平方向にサイズ変更できます。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-114">You have horizontally resized the XSD view by changing the amount of the main editing window dedicated to the XSD view, relative to the schema tree view.</span></span>  
  
     <span data-ttu-id="d0ea0-115">また、メイン編集ウィンドウ全体を水平方向にサイズ変更することによって、XSD ビューの幅を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-115">You can also make the XSD view wider or narrower by horizontally resizing the entire main editing window.</span></span>  
  
### <a name="to-change-the-background-color-andor-font-used-by-the-xsd-view"></a><span data-ttu-id="d0ea0-116">XSD ビューで使用される背景色/フォントを変更するには</span><span class="sxs-lookup"><span data-stu-id="d0ea0-116">To change the background color and/or font used by the XSD view</span></span>  
  
1.  <span data-ttu-id="d0ea0-117">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]で、 **[ツール]** メニューの **[オプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="d0ea0-118">**オプション**ダイアログ ボックスでは、BizTalk エディター フォルダー をクリックし、必要に応じて、展開、**スキーマの表示**プラス記号をクリックしてカテゴリ (+) アイコン。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-118">In the **Options** dialog box, click the BizTalk Editor folder, and if necessary, expand the **Schema Display** category by clicking the plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="d0ea0-119">ドロップダウンのカラー ピッカーを使用して、背景色またはフォントを変更または**フォント** ダイアログ ボックスに関連付けられている、 **XSD ビューの背景色**と**XSD ビューのフォント**プロパティは、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-119">Change the background color and/or font by using the drop-down color picker and/or **Font** dialog box associated with the **XSD View Background Color** and **XSD View Font** properties, respectively.</span></span>  
  
     <span data-ttu-id="d0ea0-120">アクセス、**フォント**、省略記号ボタンを使用して、ダイアログ ボックス (**.**) ボタンの右端にある、 **XSD ビューのフォント**プロパティ値ボックスです。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-120">Access the **Font** dialog box by using the ellipsis (**…**) button located at the right end of the **XSD View Font** property value box.</span></span>  
  
### <a name="to-turn-automatic-refresh-of-the-xsd-view-on-and-off"></a><span data-ttu-id="d0ea0-121">XSD ビューの自動更新をオン/オフにするには</span><span class="sxs-lookup"><span data-stu-id="d0ea0-121">To turn automatic refresh of the XSD view on and off</span></span>  
  
-   <span data-ttu-id="d0ea0-122">BizTalk エディターでは、下、 **XSD** ] タブで、をクリックして**自動更新をオフにする**または **[自動更新を有効**です。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-122">In BizTalk Editor, below the **XSD** tab, click **Turn off auto refresh** or **Turn on auto refresh**.</span></span>  
  
     <span data-ttu-id="d0ea0-123">自動更新がオフの場合、XSD ビューには何も表示されません。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-123">When auto-refresh is off, the XSD view is blank.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d0ea0-124">既定では、自動更新はオンになっています。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-124">By default, auto-refresh is on.</span></span> <span data-ttu-id="d0ea0-125">スキーマは、その規模が大きくなるにつれて、更新に時間がかかるようになります。更新時間が長すぎる場合は、自動更新機能をオフにし、必要に応じてスキーマを手動で更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-125">As your schemas become bigger and bigger, it becomes increasingly important for you to turn off the automatic refresh feature and refresh your schema manually as needed.</span></span>  
  
### <a name="to-manually-refresh-the-xsd-view"></a><span data-ttu-id="d0ea0-126">XSD ビューを手動で更新するには</span><span class="sxs-lookup"><span data-stu-id="d0ea0-126">To manually refresh the XSD view</span></span>  
  
-   <span data-ttu-id="d0ea0-127">**BizTalk**  メニューのをクリックして**XSD の更新**です。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-127">On the **BizTalk** menu, click **Refresh XSD**.</span></span>  
  
     <span data-ttu-id="d0ea0-128">XSD ビューが更新され、スキーマ ツリーに対して行ったすべての変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-128">The XSD view updates to reflect any changes you have made to the schema tree.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0ea0-129">クリックして、XSD ビューを更新することができますも手動で**XSD の更新**スキーマ ツリーで、またはをクリックして、すべてのノードに関連付けられているショートカット メニューを開き、**更新**以下のリンク、 **XSD** XSD ビュー タブでします。</span><span class="sxs-lookup"><span data-stu-id="d0ea0-129">You can also manually refresh the XSD view by clicking **Refresh XSD** on the shortcut menu associated with every node in the schema tree, or by clicking the **Refresh** link below the **XSD** tab in the XSD view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ea0-130">参照</span><span class="sxs-lookup"><span data-stu-id="d0ea0-130">See Also</span></span>  
 [<span data-ttu-id="d0ea0-131">BizTalk エディターの使用</span><span class="sxs-lookup"><span data-stu-id="d0ea0-131">Using BizTalk Editor</span></span>](../core/using-biztalk-editor.md)