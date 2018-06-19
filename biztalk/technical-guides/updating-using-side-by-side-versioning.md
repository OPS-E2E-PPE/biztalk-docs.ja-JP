---
title: サイド バイ サイドのバージョン管理を使用して更新 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9721a091-98ec-4f0b-ad1f-6ca184956e7c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe8264b76867c2f4fa3200f906e1d99975c9e0eb
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22301970"
---
# <a name="updating-using-side-by-side-versioning"></a><span data-ttu-id="e17f2-102">サイド バイ サイドのバージョン管理を使用して更新</span><span class="sxs-lookup"><span data-stu-id="e17f2-102">Updating Using Side-by-Side Versioning</span></span>
<span data-ttu-id="e17f2-103">できない場合は、ダウンタイムをスケジュールまたは終了できません非常に長時間のオーケストレーション インスタンスがある、サイド バイ サイドのバージョン管理が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e17f2-103">If you are not able to schedule downtime, or have very long-running orchestration instances that cannot be terminated, side-by-side versioning may be required.</span></span> <span data-ttu-id="e17f2-104">この種類のアップグレードでは、同じアプリケーションまたはアプリケーションのアイテムの 2 つのバージョンは、サイド バイ サイドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e17f2-104">In this type of upgrade, two versions of the same application or application artifacts run side-by-side.</span></span> <span data-ttu-id="e17f2-105">.NET ランタイム本質的には、同じ名前が、異なるバージョンのアセンブリを展開して実行、および BizTalk Server もできます。</span><span class="sxs-lookup"><span data-stu-id="e17f2-105">The .NET runtime inherently allows for same-named but differently versioned assemblies to be deployed and running, and BizTalk Server also allows it.</span></span>  
  
 <span data-ttu-id="e17f2-106">アプリケーションのサイド バイ サイドのバージョン管理は、たとえばが使用できるようにビジネス パートナーのサブセットにすべてのパートナーではなく、最初に、1 回にアプリケーションの大幅アップグレードを段階的ロールアウトする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e17f2-106">Side-by-side versioning of applications is useful when you want to roll out a major application upgrade incrementally, for example making it available to a subset of business partners initially, rather than to all partners at once.</span></span> <span data-ttu-id="e17f2-107">この方法を使用すると、新しいバージョンへの完全な切り替えの準備ができるまで、新しいバージョンをまだ使用していないユーザーに、既存のアプリケーションを実行してサービスを提供し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="e17f2-107">Using this approach allows you to continue running the existing application to service the users who are not yet using the new version until you are ready to completely cut over to the new version.</span></span>  
  
 <span data-ttu-id="e17f2-108">アセンブリ バージョンを作成する場合と異なり、アプリケーション バージョンは、バージョン番号を増やす方法では作成しません。</span><span class="sxs-lookup"><span data-stu-id="e17f2-108">You do not create application versions in the same manner that you create assembly versions, by incrementing the version number.</span></span> <span data-ttu-id="e17f2-109">代わりに、元のアプリケーションから別の名前を持つ新しいアプリケーションを作成し、アプリケーションのアイテムの新しいバージョンで作成します。</span><span class="sxs-lookup"><span data-stu-id="e17f2-109">Instead, you create a new application that has a different name from the original application, and populate it with the new versions of the application artifacts.</span></span>  
  
 <span data-ttu-id="e17f2-110">アセンブリなどの多くの種類のアイテムは、BizTalk グループ内の 1 つのアプリケーションにしか存在できません。したがって、グループ内に既に存在するアセンブリを新しいアプリケーションへ展開するには、そのバージョン番号を増やす必要があります。</span><span class="sxs-lookup"><span data-stu-id="e17f2-110">Because many types of artifacts, such as assemblies, can exist in only one application in a BizTalk group, you must increment the version number of any assemblies that already exist in the group before you can deploy them into the new application.</span></span>  
  
 <span data-ttu-id="e17f2-111">ステップ バイ ステップのアプリケーションまたはサイド バイ サイドのバージョン管理を使用してオーケストレーションを更新するために必要なタスクの一覧を表示するには、次を参照してください[チェックリスト: サイド バイ サイド、アプリケーションを使用してバージョン管理の更新](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)と[チェックリスト: 更新します。サイド バイ サイドのバージョン管理を使用してオーケストレーション](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md)です。</span><span class="sxs-lookup"><span data-stu-id="e17f2-111">For a step-by-step list of tasks required to update an application or orchestration using side-by-side versioning, see [Checklist: Updating an Application Using Side-by-Side Versioning](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md) and [Checklist: Updating an Orchestration Using Side-by-Side Versioning](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md).</span></span> <span data-ttu-id="e17f2-112">アプリケーションのサイド バイ サイド展開方法の詳細については、次を参照してください。"[既存のバージョンで実行して並行アプリケーションの新しいバージョンを展開する方法](http://go.microsoft.com/fwlink/?LinkId=155143)(http://go.microsoft.com/fwlink/?LinkId=155143)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="e17f2-112">For detailed instructions on how to have side-by-side deployment of applications, see "[How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version](http://go.microsoft.com/fwlink/?LinkId=155143) (http://go.microsoft.com/fwlink/?LinkId=155143) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e17f2-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e17f2-113">In This Section</span></span>  
  
-   [<span data-ttu-id="e17f2-114">サイドバイサイドのバージョン管理を使用したマップの更新方法</span><span class="sxs-lookup"><span data-stu-id="e17f2-114">How to Update a Map Using Side-by-Side Versioning</span></span>](../technical-guides/how-to-update-a-map-using-side-by-side-versioning.md)  
  
-   [<span data-ttu-id="e17f2-115">サイドバイサイドのバージョン管理を使用したパイプラインの更新方法</span><span class="sxs-lookup"><span data-stu-id="e17f2-115">How to Update a Pipeline Using Side-by-Side Versioning</span></span>](../technical-guides/how-to-update-a-pipeline-using-side-by-side-versioning.md)  
  
-   [<span data-ttu-id="e17f2-116">サイドバイサイドのバージョン管理を使用したスキーマの更新</span><span class="sxs-lookup"><span data-stu-id="e17f2-116">Updating a Schema Using Side-by-Side Versioning</span></span>](../technical-guides/updating-a-schema-using-side-by-side-versioning.md)