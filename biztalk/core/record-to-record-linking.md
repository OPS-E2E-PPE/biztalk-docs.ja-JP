---
title: レコードのリンク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a3fa4d7-5689-4f55-af1b-369defa37037
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91108b194a186488867ff083c0129570b5fd9477
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398033"
---
# <a name="record-to-record-linking"></a><span data-ttu-id="3363a-102">レコードへのリンク</span><span class="sxs-lookup"><span data-stu-id="3363a-102">Record-to-Record Linking</span></span>

## <a name="overview"></a><span data-ttu-id="3363a-103">概要</span><span class="sxs-lookup"><span data-stu-id="3363a-103">Overview</span></span>
<span data-ttu-id="3363a-104">Microsoft で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]同時に元と送信先スキーマの類似する部分の間での複数のリンクを作成する BizTalk マッパーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3363a-104">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use BizTalk Mapper to create multiple links between similar portions of the source and destination schemas at the same time.</span></span> <span data-ttu-id="3363a-105">BizTalk Server の以前のバージョンで個別に、このようなリンクを作成する必要がある。 1 つずつです。</span><span class="sxs-lookup"><span data-stu-id="3363a-105">In previous versions of BizTalk Server, you had to create such links individually, one at a time.</span></span> <span data-ttu-id="3363a-106">レコードへのリンクを次のように、リンクされている送信元と送信先スキーマのレコードの構造体の類似性に基づいて別の適切な各シナリオの 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="3363a-106">There are two distinct types of record-to-record linking, each appropriate to different scenarios based on the degree of similarity of the structures of the source and destination schema records being linked, as follows:</span></span>  
  
-   <span data-ttu-id="3363a-107">**構造リンクします。**</span><span class="sxs-lookup"><span data-stu-id="3363a-107">**Structure linking.**</span></span> <span data-ttu-id="3363a-108">構造リンクを使用レコードの構造は、元と送信先スキーマでリンクされている場合は、同じまたは非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="3363a-108">Use structure linking when the structure of the records being linked in your source and destination schemas are the same or very similar.</span></span>  
  
-   <span data-ttu-id="3363a-109">**名前の一致リンク。**</span><span class="sxs-lookup"><span data-stu-id="3363a-109">**Name-matching linking.**</span></span> <span data-ttu-id="3363a-110">送信元と送信先スキーマでリンクするレコードの構造がまだと同様と一致するレコードとフィールド名が構造的な例外の数が、構造リンクと比べるとよりも名前の一致リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="3363a-110">Use name-matching linking when the structure of the records being linked in your source and destination schemas are still similar, and with matching record and field names, but with more structural exceptions than are workable with structure linking.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3363a-111">レコードのリンク値コピーのリンクを使用して構成されている場合に、のみに適用されます、**ソース リンク**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3363a-111">Record-to-record linking applies to value-copy linking only, as configured using the **Source Links** property.</span></span>  
  
## <a name="record-to-record-linking-structure-links"></a><span data-ttu-id="3363a-112">--レコードをリンクします。構造リンク</span><span class="sxs-lookup"><span data-stu-id="3363a-112">Record-to-Record Linking: Structure Links</span></span>  
 <span data-ttu-id="3363a-113">構造と、元と送信先スキーマでリンクするレコードの構造が同じかほぼ同じようにリンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="3363a-113">Use structure linking when the structure of the records that you want to link in your source and destination schemas is the same or almost exactly the same.</span></span>  
  
 <span data-ttu-id="3363a-114">スキーマの構造は、同じでは正確にある場合は、各スキーマのルート ノードでのみ 1 つのリンクを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3363a-114">If the structure of your schemas is exactly the same, you need only add one link at the root node of each schema.</span></span> <span data-ttu-id="3363a-115">ショートカット メニューで、リンクの目的のモードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3363a-115">In the shortcut menu, select the desired mode of linking.</span></span>  
  
 <span data-ttu-id="3363a-116">スキーマ内の特定のレコードの構造は、同じでは正確にある場合は、各スキーマの該当するレコード間リンクを 1 つのみ追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3363a-116">If the structure of particular records in your schemas is exactly the same, you need only add one link between those records in each schema.</span></span> <span data-ttu-id="3363a-117">ショートカット メニューで、リンクの目的のモードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3363a-117">In the shortcut menu, select the desired mode of linking.</span></span>  
  
 <span data-ttu-id="3363a-118">構造リンクを使用してリンクまたは名前の一致リンクを参照してください - レコードを構成する方法については[レコードを自動的にリンク](../core/how-to-link-records-automatically.md)します。</span><span class="sxs-lookup"><span data-stu-id="3363a-118">For information about how to configure record-to-record linking as using either structure linking or name-matching linking, see [Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3363a-119">構造リンクは、既定のレコードのリンクの種類です。</span><span class="sxs-lookup"><span data-stu-id="3363a-119">Structure links are the default type of record-to-record linking.</span></span>  
  
## <a name="record-to-record-linking-name-matching-links"></a><span data-ttu-id="3363a-120">--レコードをリンクします。名前の一致リンク</span><span class="sxs-lookup"><span data-stu-id="3363a-120">Record-to-Record Linking: Name-Matching Links</span></span>  
 <span data-ttu-id="3363a-121">リンクを使用して名前の一致、元と送信先スキーマでリンクするレコードの構造が非常に似ていますが、まったく同じです。</span><span class="sxs-lookup"><span data-stu-id="3363a-121">Use name-matching links when the structure of the records that you want to link in your source and destination schemas is very similar, but not exactly the same.</span></span> <span data-ttu-id="3363a-122">たとえば、元または送信先スキーマには、下位レコードまたはその他のスキーマによりもリンクされているノード内のフィールドの詳細があります。</span><span class="sxs-lookup"><span data-stu-id="3363a-122">For example, the source or destination schema might have more subordinate records or fields within the nodes to be linked than in the other schema.</span></span>  
  
 <span data-ttu-id="3363a-123">該当する場合、スキーマ全体をなど、構造がほとんど一致する元と送信先スキーマの部分の間で名前の一致リンクを作成するには、サブ階層親ノードの送信元アドレスと別の終了のリンクを作成します。サブ階層親ノードです。</span><span class="sxs-lookup"><span data-stu-id="3363a-123">To create a name-matching link between portions of your source and destination schemas that have nearly matching structures, including the entire schemas where applicable, create a link originating from a sub-hierarchy parent node and ending on another sub-hierarchy parent node.</span></span> <span data-ttu-id="3363a-124">ショートカット メニューで、目的のモードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3363a-124">In the shortcut menu, select the desired mode.</span></span> <span data-ttu-id="3363a-125">ノードをリンクした後のすべての下位のレコードと同じ構造をいて、同じ名前が元と送信先スキーマ内のフィールドへのリンクが自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="3363a-125">After you link the nodes, links are automatically created for all of the subordinate records and fields in the source and destination schemas that are named the same and have the same substructure.</span></span>  
  
 <span data-ttu-id="3363a-126">構造リンクを使用してリンクまたは名前の一致リンクを参照してください - レコードを構成する方法については[レコードを自動的にリンク](../core/how-to-link-records-automatically.md)します。</span><span class="sxs-lookup"><span data-stu-id="3363a-126">For information about how to configure record-to-record linking as using either structure linking or name-matching linking, see [Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3363a-127">参照</span><span class="sxs-lookup"><span data-stu-id="3363a-127">See Also</span></span>  
 <span data-ttu-id="3363a-128">[レコードを自動的にリンクします。](../core/how-to-link-records-automatically.md) </span><span class="sxs-lookup"><span data-stu-id="3363a-128">[Link Records Automatically](../core/how-to-link-records-automatically.md) </span></span>  
 [<span data-ttu-id="3363a-129">リンクのプロパティの編集</span><span class="sxs-lookup"><span data-stu-id="3363a-129">Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)