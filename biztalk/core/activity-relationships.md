---
title: アクティビティ リレーションシップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], relationships
ms.assetid: da7c7205-18c6-44df-af03-3140214c84e6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3266501df57b9350e70369327fdc3142b3019d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361659"
---
# <a name="activity-relationships"></a><span data-ttu-id="70058-102">アクティビティ リレーションシップ</span><span class="sxs-lookup"><span data-stu-id="70058-102">Activity Relationships</span></span>
<span data-ttu-id="70058-103">アクティビティに関連するその他の 1 つまたは複数のアクティビティと、アクティビティのリレーションシップが存在します。</span><span class="sxs-lookup"><span data-stu-id="70058-103">An activity relationship exists when an activity relates to one or more other activities.</span></span> <span data-ttu-id="70058-104">この例には、1 つの注文書アクティビティ、または 2 つの注文書アクティビティから項目を含む 1 つの出荷アクティビティに関連する複数の出荷アクティビティが発生しました。</span><span class="sxs-lookup"><span data-stu-id="70058-104">An example of this is having multiple Shipment activities related to a single Purchase Order activity, or one Shipment activity containing items from two Purchase Order activities.</span></span>  
  
 <span data-ttu-id="70058-105">2 つのアクティビティが関連していることを示すには、両方の名前を知るし、AddRelatedActivity を呼び出すためにメモリに対応する Activityid がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="70058-105">To indicate that two activities are related, you need to know both names and have the corresponding ActivityIDs in memory in order to call AddRelatedActivity.</span></span> <span data-ttu-id="70058-106">この API は、対応するアクティビティ レコード間のリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="70058-106">This API creates the link between the corresponding activity records.</span></span>  
  
 <span data-ttu-id="70058-107">次の図では、強調表示された行のコードは、注文書アクティビティ インスタンス #123 と出荷アクティビティ #1549、1550、および 1551 との間のリレーションシップを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="70058-107">In the following figure, the highlighted lines of code show how you make a relationship between Purchase Order activity instance #123, and Shipment activities #1549, 1550, and 1551.</span></span>  
  
 <span data-ttu-id="70058-108">![](../core/media/activity-relationships-example.gif "activity_relationships_example")</span><span class="sxs-lookup"><span data-stu-id="70058-108">![](../core/media/activity-relationships-example.gif "activity_relationships_example")</span></span>  
  
 <span data-ttu-id="70058-109">ビジネス エンドユーザーが 1 つの Web ページを注文書の履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="70058-109">The business end user looks at one Web page that shows the history of a purchase order.</span></span> <span data-ttu-id="70058-110">午前 10 に示すことがあります。</span><span class="sxs-lookup"><span data-stu-id="70058-110">It may indicate that at 10 A.M.</span></span> <span data-ttu-id="70058-111">受信した、2 日後に承認が、およびページが実際のドキュメントへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="70058-111">it arrives, two days later it receives approval, and the page provides a link to the actual documents.</span></span> <span data-ttu-id="70058-112">前の図に、コードのため、ページは、対応する出荷 Web ページには、ビジネス エンドユーザーを取るハイパーリンクも提供されます。</span><span class="sxs-lookup"><span data-stu-id="70058-112">Because of the code in the previous figure, the page will also provide hyperlinks that take the business end user to the corresponding shipment Web pages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70058-113">すべての呼び出しを`AddRelatedActivity`間に行われる必要があります`BeginActivity`と`EndActivity`します。</span><span class="sxs-lookup"><span data-stu-id="70058-113">All calls to `AddRelatedActivity` should happen between `BeginActivity` and `EndActivity`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70058-114">参照</span><span class="sxs-lookup"><span data-stu-id="70058-114">See Also</span></span>  
  
 <span data-ttu-id="70058-115">[アクティビティ Continuation](../core/activity-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="70058-115">[Activity Continuation](../core/activity-continuation.md) </span></span>  
 <span data-ttu-id="70058-116">[BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="70058-116">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="70058-117">[BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md) </span><span class="sxs-lookup"><span data-stu-id="70058-117">[BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md) </span></span>  
 [<span data-ttu-id="70058-118">オーケストレーション式からの BAM API (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="70058-118">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md)