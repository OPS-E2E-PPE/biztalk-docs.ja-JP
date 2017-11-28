---
title: "レコードのリンク |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a3fa4d7-5689-4f55-af1b-369defa37037
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac6abc3d27ad3ee2f135e3ff5c8c1749fcae5f4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="record-to-record-linking"></a><span data-ttu-id="147a9-102">レコード間のリンク</span><span class="sxs-lookup"><span data-stu-id="147a9-102">Record-to-Record Linking</span></span>

## <a name="overview"></a><span data-ttu-id="147a9-103">概要</span><span class="sxs-lookup"><span data-stu-id="147a9-103">Overview</span></span>
<span data-ttu-id="147a9-104">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BizTalk マッパーを使用すると、送信元スキーマや送信先スキーマの類似する部分間に複数のリンクを同時に作成できます。</span><span class="sxs-lookup"><span data-stu-id="147a9-104">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use BizTalk Mapper to create multiple links between similar portions of the source and destination schemas at the same time.</span></span> <span data-ttu-id="147a9-105">BizTalk Server の以前のバージョンでは、個別に (一度に 1 つ) このようなリンクを作成する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="147a9-105">In previous versions of BizTalk Server, you had to create such links individually, one at a time.</span></span> <span data-ttu-id="147a9-106">レコード間のリンクには、2 つの異なる種類があります。次のように、リンクする送信元 (および送信先) スキーマ レコードの構造の類似性に基づいて、さまざまなシナリオに適切に対応します。</span><span class="sxs-lookup"><span data-stu-id="147a9-106">There are two distinct types of record-to-record linking, each appropriate to different scenarios based on the degree of similarity of the structures of the source and destination schema records being linked, as follows:</span></span>  
  
-   <span data-ttu-id="147a9-107">**構造リンクします。**</span><span class="sxs-lookup"><span data-stu-id="147a9-107">**Structure linking.**</span></span> <span data-ttu-id="147a9-108">送信元スキーマおよび送信先スキーマでリンクするレコードの構造が同じか非常に似ている場合は、構造リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="147a9-108">Use structure linking when the structure of the records being linked in your source and destination schemas are the same or very similar.</span></span>  
  
-   <span data-ttu-id="147a9-109">**名前の一致リンク。**</span><span class="sxs-lookup"><span data-stu-id="147a9-109">**Name-matching linking.**</span></span> <span data-ttu-id="147a9-110">送信元スキーマおよび送信先スキーマでリンクするレコードの構造が似ており、レコード名とフィールド名が一致しているが、構造リンクを使用するときと比べると、多くの構造上の例外が発生する場合は、名前の一致リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="147a9-110">Use name-matching linking when the structure of the records being linked in your source and destination schemas are still similar, and with matching record and field names, but with more structural exceptions than are workable with structure linking.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="147a9-111">レコードのリンク値コピーのリンクのみを使用して構成に適用されます、**送信元のリンク**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="147a9-111">Record-to-record linking applies to value-copy linking only, as configured using the **Source Links** property.</span></span>  
  
## <a name="record-to-record-linking-structure-links"></a><span data-ttu-id="147a9-112">構造リンクのレコードをリンクします。</span><span class="sxs-lookup"><span data-stu-id="147a9-112">Record-to-Record Linking: Structure Links</span></span>  
 <span data-ttu-id="147a9-113">リンク元とコピー先のスキーマでリンクするレコードの構造が同じか、またはほぼ同じ構造を使用します。</span><span class="sxs-lookup"><span data-stu-id="147a9-113">Use structure linking when the structure of the records that you want to link in your source and destination schemas is the same or almost exactly the same.</span></span>  
  
 <span data-ttu-id="147a9-114">スキーマの構造が完全に同じ場合は、各スキーマのルート ノードに単一のリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="147a9-114">If the structure of your schemas is exactly the same, you need only add one link at the root node of each schema.</span></span> <span data-ttu-id="147a9-115">ショートカット メニューで、リンクの目的のモードを選択します。</span><span class="sxs-lookup"><span data-stu-id="147a9-115">In the shortcut menu, select the desired mode of linking.</span></span>  
  
 <span data-ttu-id="147a9-116">スキーマの特定のレコードの構造が完全に同じ場合は、各スキーマの該当するレコード間に単一のリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="147a9-116">If the structure of particular records in your schemas is exactly the same, you need only add one link between those records in each schema.</span></span> <span data-ttu-id="147a9-117">ショートカット メニューで、リンクの目的のモードを選択します。</span><span class="sxs-lookup"><span data-stu-id="147a9-117">In the shortcut menu, select the desired mode of linking.</span></span>  
  
 <span data-ttu-id="147a9-118">構造リンクを使用してリンクまたは名前の一致リンクするを参照してレコードを構成する方法について[レコードを自動的にリンク](../core/how-to-link-records-automatically.md)です。</span><span class="sxs-lookup"><span data-stu-id="147a9-118">For information about how to configure record-to-record linking as using either structure linking or name-matching linking, see [Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="147a9-119">構造リンクは、レコード間リンクの既定の種類です。</span><span class="sxs-lookup"><span data-stu-id="147a9-119">Structure links are the default type of record-to-record linking.</span></span>  
  
## <a name="record-to-record-linking-name-matching-links"></a><span data-ttu-id="147a9-120">レコードのリンク: 名前の一致リンク</span><span class="sxs-lookup"><span data-stu-id="147a9-120">Record-to-Record Linking: Name-Matching Links</span></span>  
 <span data-ttu-id="147a9-121">送信元スキーマおよび送信先スキーマでリンクするレコードの構造が非常に似ている (完全に同じではない) 場合は、名前の一致リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="147a9-121">Use name-matching links when the structure of the records that you want to link in your source and destination schemas is very similar, but not exactly the same.</span></span> <span data-ttu-id="147a9-122">たとえば、送信元スキーマまたは送信先スキーマで、リンクするノード内にある下位のレコードとフィールドが、一方のスキーマと比べると多い場合などです。</span><span class="sxs-lookup"><span data-stu-id="147a9-122">For example, the source or destination schema might have more subordinate records or fields within the nodes to be linked than in the other schema.</span></span>  
  
 <span data-ttu-id="147a9-123">構造がほとんど一致する送信元スキーマおよび送信先スキーマの部分間 (場合によってはスキーマ全体) の名前の一致リンクを作成するには、サブ階層親ノードから始まり別のサブ階層親ノードで終わるリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="147a9-123">To create a name-matching link between portions of your source and destination schemas that have nearly matching structures, including the entire schemas where applicable, create a link originating from a sub-hierarchy parent node and ending on another sub-hierarchy parent node.</span></span> <span data-ttu-id="147a9-124">ショートカット メニューで、目的のモードを選択します。</span><span class="sxs-lookup"><span data-stu-id="147a9-124">In the shortcut menu, select the desired mode.</span></span> <span data-ttu-id="147a9-125">ノードをリンクすると、同じ名前で同じ構造を持つ送信元スキーマおよび送信先スキーマの下位のすべてのレコードとフィールドにリンクが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="147a9-125">After you link the nodes, links are automatically created for all of the subordinate records and fields in the source and destination schemas that are named the same and have the same substructure.</span></span>  
  
 <span data-ttu-id="147a9-126">構造リンクを使用してリンクまたは名前の一致リンクするを参照してレコードを構成する方法について[レコードを自動的にリンク](../core/how-to-link-records-automatically.md)です。</span><span class="sxs-lookup"><span data-stu-id="147a9-126">For information about how to configure record-to-record linking as using either structure linking or name-matching linking, see [Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="147a9-127">参照</span><span class="sxs-lookup"><span data-stu-id="147a9-127">See Also</span></span>  
 <span data-ttu-id="147a9-128">[レコードを自動的にリンクします。](../core/how-to-link-records-automatically.md) </span><span class="sxs-lookup"><span data-stu-id="147a9-128">[Link Records Automatically](../core/how-to-link-records-automatically.md) </span></span>  
 [<span data-ttu-id="147a9-129">リンクのプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="147a9-129">Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)