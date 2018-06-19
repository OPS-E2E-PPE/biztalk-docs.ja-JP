---
title: マイルス トーン グループを定義する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, milestone groups
- business activities, milestone groups
- BAM View Wizard, milestone groups
- creating, milestone groups
ms.assetid: 8b04d0ef-d676-476e-a292-16c4f1bf89c8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0122637fa92a360a5fda5093679fc5c1484e59a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249354"
---
# <a name="how-to-define-milestone-groups"></a><span data-ttu-id="2f5ef-102">マイルストーン グループを定義する方法</span><span class="sxs-lookup"><span data-stu-id="2f5ef-102">How to Define Milestone Groups</span></span>
<span data-ttu-id="2f5ef-103">マイルストーン グループを使用すると、関連するマイルストーンをまとめることができます。たとえば、注文書の有効期限を定義する開始マイルストーンと終了マイルストーンをまとめて、マイルストーン グループとして定義できます。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-103">Use a milestone group to put related milestones together, for example the beginning and end milestones that define how long a Purchase Order is valid.</span></span> <span data-ttu-id="2f5ef-104">マイルストーン グループは単一のマイルストーンとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-104">You can then use the milestone group as a single milestone.</span></span>  
  
 <span data-ttu-id="2f5ef-105">BAM ビュー ウィザードでは、新しいマイルストーン グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-105">Use the BAM View wizard to create new milestone groups.</span></span> <span data-ttu-id="2f5ef-106">マイルストーンまたはマイルストーン グループを作成する前に、BAM アクティビティ ウィザードを使用して、ビジネス アクティビティ、項目、およびビジネス アクティビティ ビューを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-106">Before you can create milestones or milestone groups, use the BAM Activity wizard to create business activities, items, and business activity views.</span></span> <span data-ttu-id="2f5ef-107">詳細については、ウィザードを使用して、次を参照してください。[ビジネス アクティビティの定義および Excel でビュー](../core/defining-business-activities-and-views-in-excel.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-107">For more information about using the wizard, see [Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md).</span></span>  
  
 <span data-ttu-id="2f5ef-108">ビジネス アクティビティと項目は、BAM ビュー ウィザードではなく、BAM アクティビティ ウィザードで作成します。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-108">Business activities and items are created through BAM Acitivity wizard, rather than BAM View wizard.</span></span>  
  
### <a name="to-define-milestone-groups"></a><span data-ttu-id="2f5ef-109">マイルストーン グループを定義するには</span><span class="sxs-lookup"><span data-stu-id="2f5ef-109">To define milestone groups</span></span>  
  
1.  <span data-ttu-id="2f5ef-110">BAM ビュー ウィザードで、をクリックして **[次へ]** 、2 番目に表示されるまで**BAM ビューの編集: 表示項目**ページ。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-110">In the BAM View wizard, click **Next** until you see the second **Edit BAM View: View Items** page.</span></span> <span data-ttu-id="2f5ef-111">をクリックして**新しいグループ**です。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-111">Click **New Group**.</span></span>  
  
2.  <span data-ttu-id="2f5ef-112">ビジネス マイルストーン エイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-112">Type a Business milestone alias.</span></span>  
  
3.  <span data-ttu-id="2f5ef-113">[エイリアス] ボックスの下ウィンドウで、グループに追加し、をクリックするマイルス トーンをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-113">In the window below the alias box, click the milestones you want to include in the group, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f5ef-114">クリックする場合はすべてのグループで、マイルス トーン アクティビティ、**すべてのマイルス トーンを選択して**です。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-114">If you want all of your milestone activities in the group, click **Select all milestones**.</span></span>  
  
4.  <span data-ttu-id="2f5ef-115">エイリアス、期間、およびグループの追加が完了したら、をクリックして**次**ダイアログ ボックスの集計ページに進みます。</span><span class="sxs-lookup"><span data-stu-id="2f5ef-115">When you finish adding aliases, durations, and groups, click **Next** to continue to the aggregation page of the dialog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f5ef-116">参照</span><span class="sxs-lookup"><span data-stu-id="2f5ef-116">See Also</span></span>  
 <span data-ttu-id="2f5ef-117">[Excel でビジネス アクティビティとビューを定義します。](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="2f5ef-117">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 <span data-ttu-id="2f5ef-118">[ピボット テーブルを使用する方法](../core/how-to-use-the-pivottable.md) </span><span class="sxs-lookup"><span data-stu-id="2f5ef-118">[How to Use the PivotTable](../core/how-to-use-the-pivottable.md) </span></span>  
 [<span data-ttu-id="2f5ef-119">リアルタイム集計の定義</span><span class="sxs-lookup"><span data-stu-id="2f5ef-119">Defining Real-Time Aggregations</span></span>](../core/defining-real-time-aggregations.md)