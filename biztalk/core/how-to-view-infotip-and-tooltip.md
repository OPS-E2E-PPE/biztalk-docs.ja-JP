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
ms.openlocfilehash: 2028170edc6cd2e4414172f2be37f3c7da7ebb8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333047"
---
# <a name="how-to-view-infotip-and-tooltip"></a><span data-ttu-id="0cbd8-102">ヒントとツールヒントを表示する方法</span><span class="sxs-lookup"><span data-stu-id="0cbd8-102">How to View Infotip and Tooltip</span></span>
<span data-ttu-id="0cbd8-103">マップ アイテムの上クリックしてしなくても、カーソルを移動すると、その項目に関する有用な情報を画面ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-103">When you move the cursor over a map item without clicking it, a screen tip appears with useful information about that item.</span></span>  
  
 <span data-ttu-id="0cbd8-104">BizTalk マッパーでは、2 種類の画面ヒント-ヒントとツールヒントを使用します。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-104">The BizTalk Mapper uses two types of screen tips – infotip and tooltip.</span></span>  
  
- <span data-ttu-id="0cbd8-105">**ヒント**functoid またはリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-105">**Infotips** are displayed for functoids or links.</span></span> <span data-ttu-id="0cbd8-106">Functoid またはリンクに対してラベルまたはコメントを構成するときに、グリッド ページのヒントとして表示します。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-106">When you configure labels or comments for functoids or links, you see them as infotip on the grid page.</span></span> <span data-ttu-id="0cbd8-107">表示を超えたときにも、プロパティのテキスト値、**プロパティ グリッド**ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-107">Also, when the text value for properties exceeds the display of the **Properties Grid**, the infotip is displayed.</span></span>  
  
- <span data-ttu-id="0cbd8-108">**ツールヒント**グリッド ビューで現在の配置から部分的または完全に非表示をこれらのスキーマ ノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-108">**Tooltips** are displayed for those schema nodes that are hidden partially/completely from the current alignment in the grid view.</span></span>  
  
  <span data-ttu-id="0cbd8-109">リンク ラベルの場合は、最初の 256 文字のみが保持される場合と、ツールヒントには、完全なラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-109">For link labels, only the first 256 characters are retained, and the tooltip displays the complete label.</span></span> <span data-ttu-id="0cbd8-110">Functoid の場合、ラベルは最大 256 文字を含めることができ、コメントは 1024 文字に制限されています。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-110">For functoids, the label can contain a maximum of 256 characters and comments have a limit of 1024 characters.</span></span> <span data-ttu-id="0cbd8-111">コメントのテキストがコメントのだけ最初の 256 文字を表示するように切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-111">Text of comment gets truncated accordingly to display only first 256 characters of comment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0cbd8-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="0cbd8-112">Prerequisites</span></span>  
 <span data-ttu-id="0cbd8-113">ツールヒントを表示するには、BizTalk マッパーが実行されているを確認します。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-113">To view the tooltips, ensure BizTalk Mapper is running.</span></span>  
  
## <a name="to-view-the-infotip"></a><span data-ttu-id="0cbd8-114">ヒントを表示するには</span><span class="sxs-lookup"><span data-stu-id="0cbd8-114">To view the infotip</span></span>  
 <span data-ttu-id="0cbd8-115">Functoid にマウスを移動すると、ヒントは、(ある場合)、functoid 名、functoid のラベル、functoid のコメント、および入力パラメーターの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-115">When you move the mouse on a functoid, the infotip displays information about the functoid name, the functoid label, the functoid comment, and the input parameters (if existing).</span></span> <span data-ttu-id="0cbd8-116">**Scripting** functoid、ヒントには、最初の数行のコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-116">For a **Scripting** functoid, the infotip displays the first few lines of code.</span></span>  
  
 <span data-ttu-id="0cbd8-117">リンクをヒントには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-117">The infotip to a link displays the following information:</span></span>  
  
- <span data-ttu-id="0cbd8-118">場合、ラベルにリンクを設定します。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-118">Link label, if set.</span></span>  
  
- <span data-ttu-id="0cbd8-119">**: 元接続**します。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-119">**From: source connection**.</span></span> <span data-ttu-id="0cbd8-120">ソース接続がスキーマ要素の場合は、要素名を示します。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-120">If the source connection is a schema element, it shows the element name.</span></span> <span data-ttu-id="0cbd8-121">ソース接続が functoid、functoid 名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-121">If the source connection is a functoid, it shows the functoid name.</span></span>  
  
- <span data-ttu-id="0cbd8-122">**: 送信先接続**します。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-122">**To: destination connection**.</span></span> <span data-ttu-id="0cbd8-123">転送先接続がスキーマ要素の場合は、要素名を示します。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-123">If the destination connection is a schema element, it shows the element name.</span></span> <span data-ttu-id="0cbd8-124">転送先接続が functoid、functoid 名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-124">If the destination connection is a functoid, it shows the functoid name.</span></span>  
  
  <span data-ttu-id="0cbd8-125">場合のフィールド、**プロパティ グリッド**フィールドにマウスを移動するテキストが、表示を超えています。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-125">If the fields in the **Properties Grid** have text that exceeds the display, move the mouse on the field.</span></span> <span data-ttu-id="0cbd8-126">ヒントは、完全なテキストで表示されます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-126">The infotip will show the full text.</span></span>  
  
  <span data-ttu-id="0cbd8-127">次の図は、functoid へのヒントを示しています。 リンク、および**プロパティ グリッド**します。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-127">The following figure illustrates infotips to a functoid, link, and the **Properties Grid**.</span></span>  
  
  <span data-ttu-id="0cbd8-128">![Functoid、リンク、およびラベルのヒント](../core/media/viewing-infotips.gif "Viewing_infotips")</span><span class="sxs-lookup"><span data-stu-id="0cbd8-128">![Infotips for functoid, link, and label](../core/media/viewing-infotips.gif "Viewing_infotips")</span></span>  
  
## <a name="to-view-the-tooltip"></a><span data-ttu-id="0cbd8-129">ツールヒントを表示するには</span><span class="sxs-lookup"><span data-stu-id="0cbd8-129">To view the tooltip</span></span>  
 <span data-ttu-id="0cbd8-130">元または送信先スキーマが大きい場合、マップが垂直方向にまたがることができます。そのため、スキーマ ノードが部分的に表示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-130">When your source and/or destination schemas are big, your map can span vertically; hence the schema nodes may be partially visible.</span></span> <span data-ttu-id="0cbd8-131">このような場合は、送信元ノードの上にマウスを移動するときにツールヒントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-131">In such a scenario, you can see tooltips when you move the mouse on those source nodes.</span></span>  
  
 <span data-ttu-id="0cbd8-132">次の図は、部分的に表示されていない送信先スキーマ ノードのヒントを示します。</span><span class="sxs-lookup"><span data-stu-id="0cbd8-132">The following figure shows a tooltip to a partially hidden target schema node.</span></span>  
  
 <span data-ttu-id="0cbd8-133">![スキーマ ノードのヒント](../core/media/viewing-tooltips.gif "Viewing_tooltips")</span><span class="sxs-lookup"><span data-stu-id="0cbd8-133">![Tooltip to a schema node](../core/media/viewing-tooltips.gif "Viewing_tooltips")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cbd8-134">参照</span><span class="sxs-lookup"><span data-stu-id="0cbd8-134">See Also</span></span>  
 [<span data-ttu-id="0cbd8-135">BizTalk マッパーの使用</span><span class="sxs-lookup"><span data-stu-id="0cbd8-135">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)