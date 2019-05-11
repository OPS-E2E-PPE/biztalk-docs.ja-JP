---
title: 孤立した追跡プロファイルを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, orphans
- tracking profiles, activities
- tracking profiles, deleting
- activities, tracking profiles
ms.assetid: e8923dab-5d02-41a3-840b-104b20624e6c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e61365e5677b81fd48a655ba553cd44108d5a0fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384309"
---
# <a name="how-to-remove-orphaned-tracking-profiles"></a><span data-ttu-id="506b2-102">孤立した追跡プロファイルを削除する方法</span><span class="sxs-lookup"><span data-stu-id="506b2-102">How to Remove Orphaned Tracking Profiles</span></span>
<span data-ttu-id="506b2-103">追跡プロファイルは、アクティビティに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="506b2-103">Tracking profiles are associated with an activity.</span></span> <span data-ttu-id="506b2-104">アクティビティが展開解除、孤立したことを意味しなくに関連付けられているアクティビティに関連付けられた追跡プロファイルになります。</span><span class="sxs-lookup"><span data-stu-id="506b2-104">If an activity is undeployed, the associated tracking profiles can become orphaned, which means they are no longer associated with an activity.</span></span> <span data-ttu-id="506b2-105">次の手順を使用して、追跡プロファイルを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="506b2-105">You can use the following procedure to remove the tracking profile.</span></span>  
  
### <a name="to-remove-an-orphaned-tracking-profile"></a><span data-ttu-id="506b2-106">孤立した追跡プロファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="506b2-106">To remove an orphaned tracking profile</span></span>  
  
1.  <span data-ttu-id="506b2-107">BAM 定義を再デプロイします。</span><span class="sxs-lookup"><span data-stu-id="506b2-107">Redeploy the BAM definition.</span></span> <span data-ttu-id="506b2-108">BAM 定義の展開方法の詳細については、次を参照してください。 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)します。</span><span class="sxs-lookup"><span data-stu-id="506b2-108">For information about deploying BAM definitions, see [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
2.  <span data-ttu-id="506b2-109">追跡プロファイルを削除するのにには、追跡プロファイル エディター (TPE) を使用します。</span><span class="sxs-lookup"><span data-stu-id="506b2-109">Use the Tracking Profile Editor (TPE) to remove the tracking profile.</span></span> <span data-ttu-id="506b2-110">追跡プロファイルを削除する方法の詳細については、次を参照してください。[を適用し、追跡プロファイルの削除方法](../core/how-to-apply-and-remove-a-tracking-profile.md)します。</span><span class="sxs-lookup"><span data-stu-id="506b2-110">For information about removing tracking profiles, see [How to Apply and Remove a Tracking Profile](../core/how-to-apply-and-remove-a-tracking-profile.md).</span></span>  
  
3.  <span data-ttu-id="506b2-111">BAM 定義を展開解除します。</span><span class="sxs-lookup"><span data-stu-id="506b2-111">Undeploy the BAM definition.</span></span> <span data-ttu-id="506b2-112">BAM 定義を削除する方法の詳細については、次を参照してください。 [BAM 定義を削除する方法](../core/how-to-remove-bam-definitions.md)します。</span><span class="sxs-lookup"><span data-stu-id="506b2-112">For information about removing BAM definitions, see [How to Remove BAM Definitions](../core/how-to-remove-bam-definitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="506b2-113">参照</span><span class="sxs-lookup"><span data-stu-id="506b2-113">See Also</span></span>  
 <span data-ttu-id="506b2-114">[追跡プロファイル エディター](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="506b2-114">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="506b2-115">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="506b2-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)