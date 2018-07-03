---
title: ヒントとツールヒントを表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5621bd0a-7028-43fc-b6e8-74a528129285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 833fedbcb731971bb305c759b6f87a5a575f58e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995939"
---
# <a name="how-to-view-infotip-and-tooltip"></a><span data-ttu-id="607fd-102">ヒントを表示する方法</span><span class="sxs-lookup"><span data-stu-id="607fd-102">How to View Infotip and Tooltip</span></span>
<span data-ttu-id="607fd-103">カーソルをマップ項目の上に移動しポイントすると、その項目についての役に立つ情報が画面ヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-103">When you move the cursor over a map item without clicking it, a screen tip appears with useful information about that item.</span></span>  
  
 <span data-ttu-id="607fd-104">BizTalk マッパーでは、ヒントとツールヒントという 2 種類の画面ヒントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-104">The BizTalk Mapper uses two types of screen tips – infotip and tooltip.</span></span>  
  
- <span data-ttu-id="607fd-105">**ヒント**functoid またはリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-105">**Infotips** are displayed for functoids or links.</span></span> <span data-ttu-id="607fd-106">Functoid またはリンクに対してラベルまたはコメントを構成すると、それらはグリッド ページのヒントとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-106">When you configure labels or comments for functoids or links, you see them as infotip on the grid page.</span></span> <span data-ttu-id="607fd-107">表示を超えたときにも、プロパティのテキスト値、**プロパティ グリッド**ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-107">Also, when the text value for properties exceeds the display of the **Properties Grid**, the infotip is displayed.</span></span>  
  
- <span data-ttu-id="607fd-108">**ツールヒント**グリッド ビューで現在の配置から部分的または完全に非表示をこれらのスキーマ ノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-108">**Tooltips** are displayed for those schema nodes that are hidden partially/completely from the current alignment in the grid view.</span></span>  
  
  <span data-ttu-id="607fd-109">リンク ラベルの場合は、最初の 256 文字だけが保持されて、ツールヒントには完全なラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-109">For link labels, only the first 256 characters are retained, and the tooltip displays the complete label.</span></span> <span data-ttu-id="607fd-110">Functoid の場合は、ラベルは最大 256 文字を含むことができ、コメントは 1024 文字に制限されています。</span><span class="sxs-lookup"><span data-stu-id="607fd-110">For functoids, the label can contain a maximum of 256 characters and comments have a limit of 1024 characters.</span></span> <span data-ttu-id="607fd-111">コメントのテキストは、最初の 256 文字だけが表示されるように切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="607fd-111">Text of comment gets truncated accordingly to display only first 256 characters of comment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="607fd-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="607fd-112">Prerequisites</span></span>  
 <span data-ttu-id="607fd-113">ツールヒントを表示するには、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="607fd-113">To view the tooltips, ensure BizTalk Mapper is running.</span></span>  
  
## <a name="to-view-the-infotip"></a><span data-ttu-id="607fd-114">ヒントを表示するには</span><span class="sxs-lookup"><span data-stu-id="607fd-114">To view the infotip</span></span>  
 <span data-ttu-id="607fd-115">マウスを Functoid に移動すると、Functoid の名前、Functoid のラベル、Functoid のコメント、および入力パラメーター (ある場合) についての情報がヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-115">When you move the mouse on a functoid, the infotip displays information about the functoid name, the functoid label, the functoid comment, and the input parameters (if existing).</span></span> <span data-ttu-id="607fd-116">**Scripting** functoid、ヒントには、最初の数行のコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-116">For a **Scripting** functoid, the infotip displays the first few lines of code.</span></span>  
  
 <span data-ttu-id="607fd-117">リンクのヒントには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-117">The infotip to a link displays the following information:</span></span>  
  
- <span data-ttu-id="607fd-118">リンク ラベル (設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="607fd-118">Link label, if set.</span></span>  
  
- <span data-ttu-id="607fd-119">**: 元接続**します。</span><span class="sxs-lookup"><span data-stu-id="607fd-119">**From: source connection**.</span></span> <span data-ttu-id="607fd-120">送信元接続がスキーマ要素の場合は、要素名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-120">If the source connection is a schema element, it shows the element name.</span></span> <span data-ttu-id="607fd-121">送信元接続が Functoid の場合は、Functoid 名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-121">If the source connection is a functoid, it shows the functoid name.</span></span>  
  
- <span data-ttu-id="607fd-122">**: 送信先接続**します。</span><span class="sxs-lookup"><span data-stu-id="607fd-122">**To: destination connection**.</span></span> <span data-ttu-id="607fd-123">送信先接続がスキーマ要素の場合は、要素名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-123">If the destination connection is a schema element, it shows the element name.</span></span> <span data-ttu-id="607fd-124">送信先接続が Functoid の場合は、Functoid 名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-124">If the destination connection is a functoid, it shows the functoid name.</span></span>  
  
  <span data-ttu-id="607fd-125">場合のフィールド、**プロパティ グリッド**フィールドにマウスを移動するテキストが、表示を超えています。</span><span class="sxs-lookup"><span data-stu-id="607fd-125">If the fields in the **Properties Grid** have text that exceeds the display, move the mouse on the field.</span></span> <span data-ttu-id="607fd-126">ヒントにテキスト全体が表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-126">The infotip will show the full text.</span></span>  
  
  <span data-ttu-id="607fd-127">次の図は、functoid へのヒントを示しています。 リンク、および**プロパティ グリッド**します。</span><span class="sxs-lookup"><span data-stu-id="607fd-127">The following figure illustrates infotips to a functoid, link, and the **Properties Grid**.</span></span>  
  
  <span data-ttu-id="607fd-128">![Functoid、リンク、およびラベルのヒント](../core/media/viewing-infotips.gif "Viewing_infotips")</span><span class="sxs-lookup"><span data-stu-id="607fd-128">![Infotips for functoid, link, and label](../core/media/viewing-infotips.gif "Viewing_infotips")</span></span>  
  
## <a name="to-view-the-tooltip"></a><span data-ttu-id="607fd-129">ツールヒントを表示するには</span><span class="sxs-lookup"><span data-stu-id="607fd-129">To view the tooltip</span></span>  
 <span data-ttu-id="607fd-130">送信元スキーマまたは送信先スキーマが大きい場合、マップが縦に広がり、スキーマ ノードが部分的に表示されなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="607fd-130">When your source and/or destination schemas are big, your map can span vertically; hence the schema nodes may be partially visible.</span></span> <span data-ttu-id="607fd-131">そのような場合は、送信元ノードの上にマウスを移動するとツールヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="607fd-131">In such a scenario, you can see tooltips when you move the mouse on those source nodes.</span></span>  
  
 <span data-ttu-id="607fd-132">次の図では、部分的に表示されていない送信先スキーマ ノードのツールヒントを示します。</span><span class="sxs-lookup"><span data-stu-id="607fd-132">The following figure shows a tooltip to a partially hidden target schema node.</span></span>  
  
 <span data-ttu-id="607fd-133">![スキーマ ノードのヒント](../core/media/viewing-tooltips.gif "Viewing_tooltips")</span><span class="sxs-lookup"><span data-stu-id="607fd-133">![Tooltip to a schema node](../core/media/viewing-tooltips.gif "Viewing_tooltips")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="607fd-134">参照</span><span class="sxs-lookup"><span data-stu-id="607fd-134">See Also</span></span>  
 [<span data-ttu-id="607fd-135">BizTalk マッパーの使用</span><span class="sxs-lookup"><span data-stu-id="607fd-135">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)