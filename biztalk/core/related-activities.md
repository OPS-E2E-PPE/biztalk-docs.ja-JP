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
ms.openlocfilehash: ef8cf9e4b73b4d2eda00c022270ba4cb2db8cf6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397993"
---
# <a name="related-activities"></a><span data-ttu-id="a0053-102">関連アクティビティ</span><span class="sxs-lookup"><span data-stu-id="a0053-102">Related Activities</span></span>
<span data-ttu-id="a0053-103">関連アクティビティ 領域には、クエリの基になるアクティビティに関連するアクティビティの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0053-103">The Related Activities area contains a list of activities that are related to the activity on which the query is based.</span></span> <span data-ttu-id="a0053-104">発注アクティビティに関連するアクティビティの例には、1 つの購買発注品目を複数の出荷配信できるため、複数の出荷アクティビティになります。</span><span class="sxs-lookup"><span data-stu-id="a0053-104">An example of a related activity for a Purchase Order activity would be multiple Shipment activities, since items on a single purchase order can be delivered in multiple shipments.</span></span>  
  
## <a name="creating-related-activities"></a><span data-ttu-id="a0053-105">関連アクティビティの作成</span><span class="sxs-lookup"><span data-stu-id="a0053-105">Creating related activities</span></span>  
 <span data-ttu-id="a0053-106">2 つの方法のいずれかでは、関連アクティビティの一覧が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a0053-106">The list of related activities is generated in one of two ways:</span></span>  
  
- <span data-ttu-id="a0053-107">2 つのアクティビティを定義し、それらの両方が含まれる 1 つのビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0053-107">You define two activities and then create a single view that includes both of them.</span></span> <span data-ttu-id="a0053-108">開発者は、キー、フィールド、および、アクティビティ間の値の関係を実装することで 2 つの間の関連付けの接続が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0053-108">Your developer makes a correlation connection between the two by implementing the key, field, and value relationships between the activities.</span></span>  
  
- <span data-ttu-id="a0053-109">2 つのアクティビティを定義します。</span><span class="sxs-lookup"><span data-stu-id="a0053-109">You define two activities.</span></span> <span data-ttu-id="a0053-110">開発者は、AddRelationship() を呼び出し、キー、フィールド、およびアクティビティの間の値のリレーションシップを定義すると、カスタム アプリケーションに関連付けの接続が作成します。</span><span class="sxs-lookup"><span data-stu-id="a0053-110">Your developer makes a correlation connection in your custom application by calling AddRelationship() and defining the key, field, and value relationships between the activities.</span></span>  
  
  <span data-ttu-id="a0053-111">内の行を追加で次の方法のいずれかのアクティビティのリレーションシップを定義する、 \<activityname\>_Relationships テーブル。</span><span class="sxs-lookup"><span data-stu-id="a0053-111">Defining the activity relationships in either of these ways adds a row in the \<activityname\>_Relationships table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0053-112">リレーションシップの定義の最初のメソッドのみ相互にライブ リンクが設定関連のアクティビティになります。</span><span class="sxs-lookup"><span data-stu-id="a0053-112">Only the first method of defining relationships results in the related activities having live links to each other.</span></span> <span data-ttu-id="a0053-113">2 番目のメソッドにわたるビューを定義していないと、そのため、ポータルが 2 つのアクティビティ間の関係について知ることはできません。</span><span class="sxs-lookup"><span data-stu-id="a0053-113">The second method does not define a spanning view and therefore the portal cannot know about the relationship between the two activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0053-114">参照</span><span class="sxs-lookup"><span data-stu-id="a0053-114">See Also</span></span>  
 [<span data-ttu-id="a0053-115">アクティビティの検索の結果を表示する方法</span><span class="sxs-lookup"><span data-stu-id="a0053-115">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)