---
title: 関連するアクティビティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], related activities
- Query Builder [BAM portal], related activities
- queries [BAM], related activities
- Query Builder [BAM portal], viewing details
- queries [BAM], viewing details
ms.assetid: 141b7943-d244-4810-aa88-12aa4a2b7658
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 547a8f80dbb84e12a89c96a5b85ec6a5cc6421ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013867"
---
# <a name="related-activities"></a><span data-ttu-id="ca666-102">関連アクティビティ</span><span class="sxs-lookup"><span data-stu-id="ca666-102">Related Activities</span></span>
<span data-ttu-id="ca666-103">[関連アクティビティ] 領域には、クエリの基礎となるアクティビティに関連するアクティビティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca666-103">The Related Activities area contains a list of activities that are related to the activity on which the query is based.</span></span> <span data-ttu-id="ca666-104">たとえば、1 回の発注で指示された品物を複数回に分けて出荷することが可能である場合、単一の発注アクティビティに対する関連アクティビティは、複数の出荷アクティビティになります。</span><span class="sxs-lookup"><span data-stu-id="ca666-104">An example of a related activity for a Purchase Order activity would be multiple Shipment activities, since items on a single purchase order can be delivered in multiple shipments.</span></span>  
  
## <a name="creating-related-activities"></a><span data-ttu-id="ca666-105">関連アクティビティの作成</span><span class="sxs-lookup"><span data-stu-id="ca666-105">Creating related activities</span></span>  
 <span data-ttu-id="ca666-106">2 つの方法のいずれかでは、関連アクティビティの一覧が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ca666-106">The list of related activities is generated in one of two ways:</span></span>  
  
- <span data-ttu-id="ca666-107">2 つのアクティビティを定義し、その両方を含んだ単一のビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca666-107">You define two activities and then create a single view that includes both of them.</span></span> <span data-ttu-id="ca666-108">開発者が 2 つのアクティビティの間にキー、フィールド、および値のリレーションシップを実装することで、この 2 つを結ぶ関連付けの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="ca666-108">Your developer makes a correlation connection between the two by implementing the key, field, and value relationships between the activities.</span></span>  
  
- <span data-ttu-id="ca666-109">2 つのアクティビティを定義します。</span><span class="sxs-lookup"><span data-stu-id="ca666-109">You define two activities.</span></span> <span data-ttu-id="ca666-110">開発者が AddRelationship() を呼び出し、2 つのアクティビティの間にキー、フィールド、および値のリレーションシップを定義することで、カスタム アプリケーションに関連付けの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="ca666-110">Your developer makes a correlation connection in your custom application by calling AddRelationship() and defining the key, field, and value relationships between the activities.</span></span>  
  
  <span data-ttu-id="ca666-111">内の行を追加で次の方法のいずれかのアクティビティのリレーションシップを定義する、 \<activityname\>_Relationships テーブル。</span><span class="sxs-lookup"><span data-stu-id="ca666-111">Defining the activity relationships in either of these ways adds a row in the \<activityname\>_Relationships table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca666-112">リレーションを定義する最初の方法のみ、関連アクティビティの相互にライブ リンクが設定されます。</span><span class="sxs-lookup"><span data-stu-id="ca666-112">Only the first method of defining relationships results in the related activities having live links to each other.</span></span> <span data-ttu-id="ca666-113">2 番目の方法では、2 つのアクティビティにわたるビューが定義されないので、ポータルでは両者のリレーションシップについて認識できません。</span><span class="sxs-lookup"><span data-stu-id="ca666-113">The second method does not define a spanning view and therefore the portal cannot know about the relationship between the two activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca666-114">参照</span><span class="sxs-lookup"><span data-stu-id="ca666-114">See Also</span></span>  
 [<span data-ttu-id="ca666-115">アクティビティの検索の結果を表示する方法</span><span class="sxs-lookup"><span data-stu-id="ca666-115">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)