---
title: サイド バイ サイド バージョン管理を使用して更新しています |Microsoft Docs
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
ms.openlocfilehash: 36be63c9cef6a016ea4ad34d98a2750be86491d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974259"
---
# <a name="updating-using-side-by-side-versioning"></a><span data-ttu-id="abad5-102">サイド バイ サイド バージョン管理を使用して更新しています</span><span class="sxs-lookup"><span data-stu-id="abad5-102">Updating Using Side-by-Side Versioning</span></span>
<span data-ttu-id="abad5-103">ダウンタイム、スケジュールを設定または終了することはできません非常に長時間のオーケストレーション インスタンスがある場合は、サイド バイ サイド バージョン管理が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="abad5-103">If you are not able to schedule downtime, or have very long-running orchestration instances that cannot be terminated, side-by-side versioning may be required.</span></span> <span data-ttu-id="abad5-104">この種類のアップグレードでは、同じアプリケーションまたはアプリケーションの成果物の 2 つのバージョンは、サイド バイ サイドでを実行します。</span><span class="sxs-lookup"><span data-stu-id="abad5-104">In this type of upgrade, two versions of the same application or application artifacts run side-by-side.</span></span> <span data-ttu-id="abad5-105">.NET ランタイムで本質的に展開する同じ名前しますが、異なるバージョンのアセンブリと実行、および BizTalk Server もできます。</span><span class="sxs-lookup"><span data-stu-id="abad5-105">The .NET runtime inherently allows for same-named but differently versioned assemblies to be deployed and running, and BizTalk Server also allows it.</span></span>  
  
 <span data-ttu-id="abad5-106">アプリケーションのバージョンをサイド バイ サイドでは、たとえば利用できるようにするビジネス パートナーのサブセットにすべてのパートナーではなく、最初に 1 回、主要なアプリケーションのアップグレードのロールアウトを段階的にする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="abad5-106">Side-by-side versioning of applications is useful when you want to roll out a major application upgrade incrementally, for example making it available to a subset of business partners initially, rather than to all partners at once.</span></span> <span data-ttu-id="abad5-107">この方法を使用すると、新しいバージョンへの完全な切り替えの準備ができるまで、新しいバージョンをまだ使用していないユーザーに、既存のアプリケーションを実行してサービスを提供し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="abad5-107">Using this approach allows you to continue running the existing application to service the users who are not yet using the new version until you are ready to completely cut over to the new version.</span></span>  
  
 <span data-ttu-id="abad5-108">アセンブリ バージョンを作成する場合と異なり、アプリケーション バージョンは、バージョン番号を増やす方法では作成しません。</span><span class="sxs-lookup"><span data-stu-id="abad5-108">You do not create application versions in the same manner that you create assembly versions, by incrementing the version number.</span></span> <span data-ttu-id="abad5-109">代わりに、元のアプリケーションから別の名前を持つ新しいアプリケーションを作成し、アプリケーションのアイテムの新しいバージョンを設定します。</span><span class="sxs-lookup"><span data-stu-id="abad5-109">Instead, you create a new application that has a different name from the original application, and populate it with the new versions of the application artifacts.</span></span>  
  
 <span data-ttu-id="abad5-110">アセンブリなどの多くの種類のアイテムは、BizTalk グループ内の 1 つのアプリケーションにしか存在できません。したがって、グループ内に既に存在するアセンブリを新しいアプリケーションへ展開するには、そのバージョン番号を増やす必要があります。</span><span class="sxs-lookup"><span data-stu-id="abad5-110">Because many types of artifacts, such as assemblies, can exist in only one application in a BizTalk group, you must increment the version number of any assemblies that already exist in the group before you can deploy them into the new application.</span></span>  
  
 <span data-ttu-id="abad5-111">ステップ バイ ステップのアプリケーションまたはサイド バイ サイド バージョン管理を使用してオーケストレーションを更新するために必要なタスクの一覧を表示するには、次を参照してください[チェックリスト: サイド バイ サイドで、アプリケーションを使用してバージョン管理を更新](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)と[チェックリスト: 更新します。サイド バイ サイド バージョン管理を使用してオーケストレーション](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md)します。</span><span class="sxs-lookup"><span data-stu-id="abad5-111">For a step-by-step list of tasks required to update an application or orchestration using side-by-side versioning, see [Checklist: Updating an Application Using Side-by-Side Versioning](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md) and [Checklist: Updating an Orchestration Using Side-by-Side Versioning](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md).</span></span> <span data-ttu-id="abad5-112">アプリケーションのサイド バイ サイドで配置する方法の詳細については、次を参照してください。"[既存のバージョンで実行して並列アプリケーションの新しいバージョンをデプロイする方法](http://go.microsoft.com/fwlink/?LinkId=155143)(<http://go.microsoft.com/fwlink/?LinkId=155143>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="abad5-112">For detailed instructions on how to have side-by-side deployment of applications, see "[How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version](http://go.microsoft.com/fwlink/?LinkId=155143) (<http://go.microsoft.com/fwlink/?LinkId=155143>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="abad5-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="abad5-113">In This Section</span></span>  
  
-   [<span data-ttu-id="abad5-114">サイドバイサイドのバージョン管理を使用したマップの更新方法</span><span class="sxs-lookup"><span data-stu-id="abad5-114">How to Update a Map Using Side-by-Side Versioning</span></span>](../technical-guides/how-to-update-a-map-using-side-by-side-versioning.md)  
  
-   [<span data-ttu-id="abad5-115">サイドバイサイドのバージョン管理を使用したパイプラインの更新方法</span><span class="sxs-lookup"><span data-stu-id="abad5-115">How to Update a Pipeline Using Side-by-Side Versioning</span></span>](../technical-guides/how-to-update-a-pipeline-using-side-by-side-versioning.md)  
  
-   [<span data-ttu-id="abad5-116">サイドバイサイドのバージョン管理を使用したスキーマの更新</span><span class="sxs-lookup"><span data-stu-id="abad5-116">Updating a Schema Using Side-by-Side Versioning</span></span>](../technical-guides/updating-a-schema-using-side-by-side-versioning.md)