---
title: 追跡プロファイルの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, creating
- creating, tracking profiles
ms.assetid: 62598529-9763-4c73-acbe-06ce5650134a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ce1edcab724201dc03792a37b0b796625201351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238274"
---
# <a name="creating-tracking-profiles"></a><span data-ttu-id="c6a8b-102">追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6a8b-102">Creating Tracking Profiles</span></span>
<span data-ttu-id="c6a8b-103">組織の特定のビジネス プロセスに対する管理や監視機能を向上させるには、新しい追跡プロファイルを作成するか、または既存のプロファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="c6a8b-103">You create a new tracking profile or modify an existing one to better manage and monitor a specific business process for your organization.</span></span> <span data-ttu-id="c6a8b-104">追跡プロファイル エディター (TPE) を使用すると、ビジネス アナリストの要件を満たすために収集するデータを定義できます。</span><span class="sxs-lookup"><span data-stu-id="c6a8b-104">The Tracking Profile Editor (TPE) allows you to define the data to collect to meet the business analyst's requirement.</span></span> <span data-ttu-id="c6a8b-105">作成または変更するプロファイルは、ビジネスの要件に応じて簡単にも複雑にもできます。</span><span class="sxs-lookup"><span data-stu-id="c6a8b-105">The profile you create or modify can be as simple or as complex as you like depending on your business requirements.</span></span>  
  
 <span data-ttu-id="c6a8b-106">開発者の場合、BAM アクティビティ定義に基づいて新しいプロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6a8b-106">As a developer, you create a new profile based on a BAM activity definition.</span></span> <span data-ttu-id="c6a8b-107">展開されたアクティビティ定義では、その定義向けのプロファイルが既に定義されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="c6a8b-107">A deployed activity definition may already have a profile defined for it.</span></span> <span data-ttu-id="c6a8b-108">まだ定義されていない場合は、次の操作を実行して追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6a8b-108">If not, you create a tracking profile by performing these tasks:</span></span>  
  
-   <span data-ttu-id="c6a8b-109">展開サーバーおよびデータベースを選択する</span><span class="sxs-lookup"><span data-stu-id="c6a8b-109">Selecting a deployment server and database</span></span>  
  
-   <span data-ttu-id="c6a8b-110">展開された BAM アクティビティ定義を BizTalk 管理データベースから選択する</span><span class="sxs-lookup"><span data-stu-id="c6a8b-110">Selecting a deployed BAM activity definition from the BizTalk Management database</span></span>  
  
-   <span data-ttu-id="c6a8b-111">オーケストレーションから抽出するデータを定義する</span><span class="sxs-lookup"><span data-stu-id="c6a8b-111">Defining the data to be extracted from the orchestration</span></span>  
  
-   <span data-ttu-id="c6a8b-112">実際のビジネス プロセスの実装が複数のオーケストレーションにまたがる場合は、アクティビティを接続する</span><span class="sxs-lookup"><span data-stu-id="c6a8b-112">Connecting activities, if the actual implementation of your business process spans more than one orchestration</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6a8b-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c6a8b-113">In This Section</span></span>  
  
-   [<span data-ttu-id="c6a8b-114">追跡プロファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="c6a8b-114">How to Create a Tracking Profile</span></span>](../core/how-to-create-a-tracking-profile.md)  
  
-   [<span data-ttu-id="c6a8b-115">イベント ソースにマップする方法</span><span class="sxs-lookup"><span data-stu-id="c6a8b-115">How to Map Event Sources</span></span>](../core/how-to-map-event-sources.md)  
  
-   [<span data-ttu-id="c6a8b-116">項目のデータをマップする方法</span><span class="sxs-lookup"><span data-stu-id="c6a8b-116">How to Map Item Data</span></span>](../core/how-to-map-item-data.md)  
  
-   [<span data-ttu-id="c6a8b-117">Continuation を作成する方法</span><span class="sxs-lookup"><span data-stu-id="c6a8b-117">How to Create a Continuation</span></span>](../core/how-to-create-a-continuation.md)  
  
-   [<span data-ttu-id="c6a8b-118">複数のアセンブリをマップする方法</span><span class="sxs-lookup"><span data-stu-id="c6a8b-118">How to Map Multiple Assemblies</span></span>](../core/how-to-map-multiple-assemblies.md)  
  
-   [<span data-ttu-id="c6a8b-119">適用し、追跡プロファイルを削除する方法</span><span class="sxs-lookup"><span data-stu-id="c6a8b-119">How to Apply and Remove a Tracking Profile</span></span>](../core/how-to-apply-and-remove-a-tracking-profile.md)