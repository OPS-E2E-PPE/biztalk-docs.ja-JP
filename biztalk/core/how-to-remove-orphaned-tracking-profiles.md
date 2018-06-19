---
title: 孤立した追跡プロファイルを削除する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 33ddea8751a017db21306c06cdcca5929de641ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255402"
---
# <a name="how-to-remove-orphaned-tracking-profiles"></a><span data-ttu-id="d27df-102">孤立した追跡プロファイルを削除する方法</span><span class="sxs-lookup"><span data-stu-id="d27df-102">How to Remove Orphaned Tracking Profiles</span></span>
<span data-ttu-id="d27df-103">追跡プロファイルはアクティビティに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="d27df-103">Tracking profiles are associated with an activity.</span></span> <span data-ttu-id="d27df-104">アクティビティが展開解除された場合、これに関連する追跡プロファイルは孤立します。つまり、アクティビティとの関連付けが失われます。</span><span class="sxs-lookup"><span data-stu-id="d27df-104">If an activity is undeployed, the associated tracking profiles can become orphaned, which means they are no longer associated with an activity.</span></span> <span data-ttu-id="d27df-105">次の手順に従うと、追跡プロファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d27df-105">You can use the following procedure to remove the tracking profile.</span></span>  
  
### <a name="to-remove-an-orphaned-tracking-profile"></a><span data-ttu-id="d27df-106">孤立した追跡プロファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="d27df-106">To remove an orphaned tracking profile</span></span>  
  
1.  <span data-ttu-id="d27df-107">BAM 定義を再展開します。</span><span class="sxs-lookup"><span data-stu-id="d27df-107">Redeploy the BAM definition.</span></span> <span data-ttu-id="d27df-108">BAM 定義の展開方法の詳細については、次を参照してください。 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)です。</span><span class="sxs-lookup"><span data-stu-id="d27df-108">For information about deploying BAM definitions, see [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
2.  <span data-ttu-id="d27df-109">追跡プロファイル エディター (TPE) を使用して追跡プロファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="d27df-109">Use the Tracking Profile Editor (TPE) to remove the tracking profile.</span></span> <span data-ttu-id="d27df-110">追跡プロファイルの削除については、次を参照してください。[を適用し、追跡プロファイルを削除する方法](../core/how-to-apply-and-remove-a-tracking-profile.md)です。</span><span class="sxs-lookup"><span data-stu-id="d27df-110">For information about removing tracking profiles, see [How to Apply and Remove a Tracking Profile](../core/how-to-apply-and-remove-a-tracking-profile.md).</span></span>  
  
3.  <span data-ttu-id="d27df-111">BAM 定義の展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="d27df-111">Undeploy the BAM definition.</span></span> <span data-ttu-id="d27df-112">BAM 定義を削除する方法の詳細については、次を参照してください。 [BAM 定義を削除する方法](../core/how-to-remove-bam-definitions.md)です。</span><span class="sxs-lookup"><span data-stu-id="d27df-112">For information about removing BAM definitions, see [How to Remove BAM Definitions](../core/how-to-remove-bam-definitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d27df-113">参照</span><span class="sxs-lookup"><span data-stu-id="d27df-113">See Also</span></span>  
 <span data-ttu-id="d27df-114">[追跡プロファイル エディター](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="d27df-114">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="d27df-115">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="d27df-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)