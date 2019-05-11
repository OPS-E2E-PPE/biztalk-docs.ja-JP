---
title: リンクの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, links
- BizTalk Mapper, links
ms.assetid: e8596c50-62e9-40a7-ad61-29cbdb4f4fc9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 441ae9536dec11f8eead5544e95b7ba7f7814852
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353646"
---
# <a name="creating-links"></a><span data-ttu-id="4a491-102">リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a491-102">Creating Links</span></span>
<span data-ttu-id="4a491-103">BizTalk マッパーでは、リンクの作成に関連するいくつかの要素を自動化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4a491-103">BizTalk Mapper helps you automate some elements involved in link creation.</span></span> <span data-ttu-id="4a491-104">簡易リンク作成は、単純なデータ型に似ています。</span><span class="sxs-lookup"><span data-stu-id="4a491-104">Simple link creation is similar to simple data types.</span></span> <span data-ttu-id="4a491-105">プログラミング言語の構造の割り当てに似ているリンクの作成のより高度な形式はあります。</span><span class="sxs-lookup"><span data-stu-id="4a491-105">There are more sophisticated forms of link creation that are more like structure assignment in a programming language.</span></span> <span data-ttu-id="4a491-106">たとえば、入力インスタンス メッセージから対応する出力インスタンス メッセージに移動するデータの複数の項目を指定する 1 つのリンクの作成です。</span><span class="sxs-lookup"><span data-stu-id="4a491-106">An example is a single link creation that specifies how multiple items of data are to be moved from input instance messages to corresponding output instance messages.</span></span>  
  
 <span data-ttu-id="4a491-107">次のメソッドを使用してリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a491-107">You create links using the following methods:</span></span>  
  
-   <span data-ttu-id="4a491-108">**簡易リンク作成します。**</span><span class="sxs-lookup"><span data-stu-id="4a491-108">**Simple link creation.**</span></span> <span data-ttu-id="4a491-109">単純なリンクを作成するには、ドラッグしてリンクを生成します。</span><span class="sxs-lookup"><span data-stu-id="4a491-109">In simple link creation, you produce a link by dragging.</span></span> <span data-ttu-id="4a491-110">送信先スキーマ内のフィールドに、送信元スキーマ内のフィールドをドラッグするが作成され、要素または属性の出力インスタンス メッセージにし、メッセージの要素または属性の値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="4a491-110">Dragging a field in the source schema to a field in the destination schema causes the creation of an element or attribute in an output instance message and inserts the value of the element or attribute in the message.</span></span> <span data-ttu-id="4a491-111">このようなリンクは間で直接行われたことができます**レコード**と**フィールド**、送信元と送信先スキーマ内のノード間のリンク パスで 1 つまたは複数の functoid を含めることができますか**レコード**と**フィールド**元と送信先スキーマ内のノード。</span><span class="sxs-lookup"><span data-stu-id="4a491-111">Such links can be made directly between **Record** and **Field** nodes in the source and destination schema, or they can include one or more functoids in a link path between **Record** and **Field** nodes in the source and destination schemas.</span></span>  
  
-   <span data-ttu-id="4a491-112">**構造リンクを示します。**</span><span class="sxs-lookup"><span data-stu-id="4a491-112">**Structure links.**</span></span> <span data-ttu-id="4a491-113">構造リンクを作成するでの間で同時に複数の簡易リンクを生成する**レコード**と**フィールド**同じ相対構造を持つ元と送信先スキーマ内のノード。</span><span class="sxs-lookup"><span data-stu-id="4a491-113">In creating structure links, you produce multiple simple links at the same time between **Record** and **Field** nodes in the source and destination schemas that have the same relative structure.</span></span> <span data-ttu-id="4a491-114">構造リンクを使用するには、は、2 つのスキーマの関連する部分の構造は同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a491-114">To use structure linking, the structure of the relevant parts of the two schemas must be the same.</span></span> <span data-ttu-id="4a491-115">構造リンクを構成する方法の詳細については、次を参照してください。[レコードを自動的にリンクする方法](../core/how-to-link-records-automatically.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a491-115">For more information about configuring structure links, see [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
-   <span data-ttu-id="4a491-116">**名前の一致リンク。**</span><span class="sxs-lookup"><span data-stu-id="4a491-116">**Name-matching links.**</span></span> <span data-ttu-id="4a491-117">間で同時に複数の簡易リンクを作成するときに、このメソッドを使用すると、**レコード**と**フィールド**元と送信先スキーマのノードの名前に基づく、 **レコード**と**フィールド**ノード。</span><span class="sxs-lookup"><span data-stu-id="4a491-117">When you use this method, you create multiple simple links at the same time between **Record** and **Field** nodes in the source and destination schemas based on the names of the **Records** and **Field** nodes.</span></span> <span data-ttu-id="4a491-118">名前の一致リンクを使用する元と送信先スキーマの構造があります非常に似ていますが、まったく同じです。</span><span class="sxs-lookup"><span data-stu-id="4a491-118">To use name-matching linking, the structure of the source and destination schemas must be very similar, but not exactly the same.</span></span> <span data-ttu-id="4a491-119">名前の一致リンクを構成する方法の詳細については、次を参照してください。[レコードを自動的にリンクする方法](../core/how-to-link-records-automatically.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a491-119">For more information about configuring name-matching links, see [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4a491-120">表示することも[既存のリンクを管理する方法](../core/how-to-manage-existing-links.md)既存のリンクを変更する方法についてはします。</span><span class="sxs-lookup"><span data-stu-id="4a491-120">You can also see [How to Manage Existing Links](../core/how-to-manage-existing-links.md) for information about how to change/modify the existing links.</span></span>  
  
## <a name="preserving-whitespace-in-a-link"></a><span data-ttu-id="4a491-121">リンクの空白の保持</span><span class="sxs-lookup"><span data-stu-id="4a491-121">Preserving Whitespace in a Link</span></span>  
 <span data-ttu-id="4a491-122">ターゲット要素または functoid をマップするときに、ソース要素から空白を保持する場合は、カスタム スクリプトを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a491-122">If you want to preserve whitespace from a source element when mapping to a target element or functoid, you will need to write a custom script.</span></span>  
  
 <span data-ttu-id="4a491-123">マッパーでまたはをランタイム システムでは、空白は保持されません。</span><span class="sxs-lookup"><span data-stu-id="4a491-123">Whitespace is not preserved either in the Mapper or in the runtime system.</span></span> <span data-ttu-id="4a491-124">マッパーとランタイム システムの両方は、サイズの大きいメッセージの変換を処理し、移動、XPath データ モデルを使用する XmlReader 依存 BTSXslTransform.Transform を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a491-124">Both the Mapper and the runtime system use BTSXslTransform.Transform which handles large-message transformations and relies on XmlReader to navigate using the XPath data model.</span></span>  
  
 <span data-ttu-id="4a491-125">空白を保持するために必要な数の空白を返すカスタム スクリプトを記述できます。</span><span class="sxs-lookup"><span data-stu-id="4a491-125">To preserve whitespace, you can write a custom script that returns the required amount of whitespace.</span></span> <span data-ttu-id="4a491-126">たとえば、次のコードでは、常に 5 文字の空白を含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="4a491-126">For example, the code below always returns a string containing 5 whitespace characters:</span></span>  
  
```  
public string Whitespace(string param1)  
{  
  return "     ";  
}  
```  
  
 <span data-ttu-id="4a491-127">ソース要素にリンクしたこのスクリプトとターゲット要素の入力、出力としてマップを実行すると、出力要素は、5 文字の空白が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4a491-127">If you link a source element to the input of this script and a target element as the output, when the map is executed, the output element will contain 5 whitespace characters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a491-128">使用して出力を表示する場合[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]要素は空として表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a491-128">If you view the output using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], the element will appear empty.</span></span> <span data-ttu-id="4a491-129">これは、XML ビューアーは空として空白を含む要素を処理するためです。</span><span class="sxs-lookup"><span data-stu-id="4a491-129">This is because the XML viewer treats elements containing whitespace only as empty.</span></span> <span data-ttu-id="4a491-130">空白を確認するには、XML ビューを右クリックして**ソースの表示**します。</span><span class="sxs-lookup"><span data-stu-id="4a491-130">To see the whitespace, right-click the XML view and select **View Source**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a491-131">参照</span><span class="sxs-lookup"><span data-stu-id="4a491-131">See Also</span></span>  
 [<span data-ttu-id="4a491-132">リンクのプロパティを編集する方法</span><span class="sxs-lookup"><span data-stu-id="4a491-132">How to Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)