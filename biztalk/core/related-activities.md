---
title: "関連アクティビティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities [BAM], related activities
- Query Builder [BAM portal], related activities
- queries [BAM], related activities
- Query Builder [BAM portal], viewing details
- queries [BAM], viewing details
ms.assetid: 141b7943-d244-4810-aa88-12aa4a2b7658
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f50e4de965e8f1efaa1454bb9123317ae904f7e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="related-activities"></a><span data-ttu-id="8ce32-102">関連するアクティビティ</span><span class="sxs-lookup"><span data-stu-id="8ce32-102">Related Activities</span></span>
<span data-ttu-id="8ce32-103">[関連アクティビティ] 領域には、クエリの基礎となるアクティビティに関連するアクティビティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ce32-103">The Related Activities area contains a list of activities that are related to the activity on which the query is based.</span></span> <span data-ttu-id="8ce32-104">たとえば、1 回の発注で指示された品物を複数回に分けて出荷することが可能である場合、単一の発注アクティビティに対する関連アクティビティは、複数の出荷アクティビティになります。</span><span class="sxs-lookup"><span data-stu-id="8ce32-104">An example of a related activity for a Purchase Order activity would be multiple Shipment activities, since items on a single purchase order can be delivered in multiple shipments.</span></span>  
  
## <a name="creating-related-activities"></a><span data-ttu-id="8ce32-105">関連アクティビティの作成</span><span class="sxs-lookup"><span data-stu-id="8ce32-105">Creating related activities</span></span>  
 <span data-ttu-id="8ce32-106">2 つの方法のいずれかでは、関連するアクティビティのリストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="8ce32-106">The list of related activities is generated in one of two ways:</span></span>  
  
-   <span data-ttu-id="8ce32-107">2 つのアクティビティを定義し、その両方を含んだ単一のビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ce32-107">You define two activities and then create a single view that includes both of them.</span></span> <span data-ttu-id="8ce32-108">開発者が 2 つのアクティビティの間にキー、フィールド、および値のリレーションシップを実装することで、この 2 つを結ぶ関連付けの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="8ce32-108">Your developer makes a correlation connection between the two by implementing the key, field, and value relationships between the activities.</span></span>  
  
-   <span data-ttu-id="8ce32-109">2 つのアクティビティを定義します。</span><span class="sxs-lookup"><span data-stu-id="8ce32-109">You define two activities.</span></span> <span data-ttu-id="8ce32-110">開発者が AddRelationship() を呼び出し、2 つのアクティビティの間にキー、フィールド、および値のリレーションシップを定義することで、カスタム アプリケーションに関連付けの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="8ce32-110">Your developer makes a correlation connection in your custom application by calling AddRelationship() and defining the key, field, and value relationships between the activities.</span></span>  
  
 <span data-ttu-id="8ce32-111">内の行を追加するアクティビティのリレーションシップを定義する以下の方法のいずれかで、 \<activityname\>_Relationships テーブル。</span><span class="sxs-lookup"><span data-stu-id="8ce32-111">Defining the activity relationships in either of these ways adds a row in the \<activityname\>_Relationships table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ce32-112">リレーションを定義する最初の方法のみ、関連アクティビティの相互にライブ リンクが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8ce32-112">Only the first method of defining relationships results in the related activities having live links to each other.</span></span> <span data-ttu-id="8ce32-113">2 番目の方法では、2 つのアクティビティにわたるビューが定義されないので、ポータルでは両者のリレーションシップについて認識できません。</span><span class="sxs-lookup"><span data-stu-id="8ce32-113">The second method does not define a spanning view and therefore the portal cannot know about the relationship between the two activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ce32-114">参照</span><span class="sxs-lookup"><span data-stu-id="8ce32-114">See Also</span></span>  
 [<span data-ttu-id="8ce32-115">アクティビティの検索の結果を表示する方法</span><span class="sxs-lookup"><span data-stu-id="8ce32-115">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)