---
title: "リンクを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, links
- BizTalk Mapper, links
ms.assetid: e8596c50-62e9-40a7-ad61-29cbdb4f4fc9
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87570b82dc63a02c629e0fc024c2e44d57df1401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-links"></a><span data-ttu-id="44507-102">リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="44507-102">Creating Links</span></span>
<span data-ttu-id="44507-103">BizTalk マッパーを使用すると、リンク作成に関連する一部の要素を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="44507-103">BizTalk Mapper helps you automate some elements involved in link creation.</span></span> <span data-ttu-id="44507-104">簡易リンク作成は、単純なデータ型に似ています。</span><span class="sxs-lookup"><span data-stu-id="44507-104">Simple link creation is similar to simple data types.</span></span> <span data-ttu-id="44507-105">プログラミング言語の構造の割り当てに似ている高度な形式のリンク作成もあります。</span><span class="sxs-lookup"><span data-stu-id="44507-105">There are more sophisticated forms of link creation that are more like structure assignment in a programming language.</span></span> <span data-ttu-id="44507-106">たとえば、入力インスタンス メッセージから対応する出力インスタンス メッセージに複数の項目のデータを移動する方法を指定するリンク作成などがあります。</span><span class="sxs-lookup"><span data-stu-id="44507-106">An example is a single link creation that specifies how multiple items of data are to be moved from input instance messages to corresponding output instance messages.</span></span>  
  
 <span data-ttu-id="44507-107">次の方法で、リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="44507-107">You create links using the following methods:</span></span>  
  
-   <span data-ttu-id="44507-108">**簡易リンク作成します。**</span><span class="sxs-lookup"><span data-stu-id="44507-108">**Simple link creation.**</span></span> <span data-ttu-id="44507-109">簡易リンクを作成するには、ドラッグ操作でリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="44507-109">In simple link creation, you produce a link by dragging.</span></span> <span data-ttu-id="44507-110">送信元スキーマのフィールドを送信先スキーマのフィールドにドラッグすると、出力インスタンス メッセージの要素または属性が作成され、要素または属性の値がメッセージに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="44507-110">Dragging a field in the source schema to a field in the destination schema causes the creation of an element or attribute in an output instance message and inserts the value of the element or attribute in the message.</span></span> <span data-ttu-id="44507-111">このようなリンクにできる間で直接**レコード**と**フィールド**、送信元と送信先スキーマのノード間のリンク パスに 1 つまたは複数の functoid を含めることができます、または**レコード**と**フィールド**送信元と送信先スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="44507-111">Such links can be made directly between **Record** and **Field** nodes in the source and destination schema, or they can include one or more functoids in a link path between **Record** and **Field** nodes in the source and destination schemas.</span></span>  
  
-   <span data-ttu-id="44507-112">**構造リンクを示します。**</span><span class="sxs-lookup"><span data-stu-id="44507-112">**Structure links.**</span></span> <span data-ttu-id="44507-113">構造リンクを作成するには、間で同時に複数の簡易リンクを生成する**レコード**と**フィールド**同じ相対構造を持つ送信元と送信先スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="44507-113">In creating structure links, you produce multiple simple links at the same time between **Record** and **Field** nodes in the source and destination schemas that have the same relative structure.</span></span> <span data-ttu-id="44507-114">構造リンクを使用するには、2 つのスキーマの関連する部分の構造が同じであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="44507-114">To use structure linking, the structure of the relevant parts of the two schemas must be the same.</span></span> <span data-ttu-id="44507-115">構造リンクを構成する方法の詳細については、次を参照してください。[レコードを自動的にリンクする方法](../core/how-to-link-records-automatically.md)です。</span><span class="sxs-lookup"><span data-stu-id="44507-115">For more information about configuring structure links, see [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
-   <span data-ttu-id="44507-116">**名前の一致リンク。**</span><span class="sxs-lookup"><span data-stu-id="44507-116">**Name-matching links.**</span></span> <span data-ttu-id="44507-117">間で同時に複数の簡易リンクを作成するときに、このメソッドを使用する**レコード**と**フィールド**の名前に基づいて、送信元と送信先スキーマのノード、**レコード**と**フィールド**ノード。</span><span class="sxs-lookup"><span data-stu-id="44507-117">When you use this method, you create multiple simple links at the same time between **Record** and **Field** nodes in the source and destination schemas based on the names of the **Records** and **Field** nodes.</span></span> <span data-ttu-id="44507-118">名前の一致リンクを使用するには、送信元スキーマおよび送信先スキーマの構造が非常に似ている (ただし、完全に同じではない) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="44507-118">To use name-matching linking, the structure of the source and destination schemas must be very similar, but not exactly the same.</span></span> <span data-ttu-id="44507-119">名前の一致リンクを構成する方法の詳細については、次を参照してください。[レコードを自動的にリンクする方法](../core/how-to-link-records-automatically.md)です。</span><span class="sxs-lookup"><span data-stu-id="44507-119">For more information about configuring name-matching links, see [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44507-120">表示することも[既存のリンクを管理する方法](../core/how-to-manage-existing-links.md)既存のリンクを変更または変更する方法についてはします。</span><span class="sxs-lookup"><span data-stu-id="44507-120">You can also see [How to Manage Existing Links](../core/how-to-manage-existing-links.md) for information about how to change/modify the existing links.</span></span>  
  
## <a name="preserving-whitespace-in-a-link"></a><span data-ttu-id="44507-121">リンクでの空白の保持</span><span class="sxs-lookup"><span data-stu-id="44507-121">Preserving Whitespace in a Link</span></span>  
 <span data-ttu-id="44507-122">ソース要素からターゲット要素または Functoid にマッピングする際に、要素内の空白を保持する場合は、カスタム スクリプトを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44507-122">If you want to preserve whitespace from a source element when mapping to a target element or functoid, you will need to write a custom script.</span></span>  
  
 <span data-ttu-id="44507-123">マッパーとランタイム システムのいずれにおいても空白は保持されません。</span><span class="sxs-lookup"><span data-stu-id="44507-123">Whitespace is not preserved either in the Mapper or in the runtime system.</span></span> <span data-ttu-id="44507-124">マッパーとランタイム システムの両方が、サイズの大きいメッセージの変換に BTSXslTransform.Transform を使用し、ナビゲーション操作に XmlReader と XPath データ モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="44507-124">Both the Mapper and the runtime system use BTSXslTransform.Transform which handles large-message transformations and relies on XmlReader to navigate using the XPath data model.</span></span>  
  
 <span data-ttu-id="44507-125">空白を保持するには、必要な数の空白を返すカスタム スクリプトを記述できます。</span><span class="sxs-lookup"><span data-stu-id="44507-125">To preserve whitespace, you can write a custom script that returns the required amount of whitespace.</span></span> <span data-ttu-id="44507-126">たとえば、次のコードでは常に 5 文字の空白を含む文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="44507-126">For example, the code below always returns a string containing 5 whitespace characters:</span></span>  
  
```  
public string Whitespace(string param1)  
{  
  return "     ";  
}  
```  
  
 <span data-ttu-id="44507-127">ソース要素をこのスクリプトの入力とし、ターゲット要素を出力としてリンクすると、マップの実行後、出力要素には 5 文字の空白が含められます。</span><span class="sxs-lookup"><span data-stu-id="44507-127">If you link a source element to the input of this script and a target element as the output, when the map is executed, the output element will contain 5 whitespace characters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44507-128">使用して、出力を表示する場合[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]要素は空として表示されます。</span><span class="sxs-lookup"><span data-stu-id="44507-128">If you view the output using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], the element will appear empty.</span></span> <span data-ttu-id="44507-129">この理由は、XML ビューアーでは空白を含む要素は空として扱われるためです。</span><span class="sxs-lookup"><span data-stu-id="44507-129">This is because the XML viewer treats elements containing whitespace only as empty.</span></span> <span data-ttu-id="44507-130">空白を確認するには、XML ビューを右クリックして**ソースの表示**です。</span><span class="sxs-lookup"><span data-stu-id="44507-130">To see the whitespace, right-click the XML view and select **View Source**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44507-131">参照</span><span class="sxs-lookup"><span data-stu-id="44507-131">See Also</span></span>  
 [<span data-ttu-id="44507-132">リンクのプロパティを編集する方法</span><span class="sxs-lookup"><span data-stu-id="44507-132">How to Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)