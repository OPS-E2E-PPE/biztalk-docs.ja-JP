---
title: "BAM 定義を管理する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions]
- definitions [BAM], managing
- definition files [BAM], managing
- managing [BAM], definitions
- managing [BAM definitions], about managing BAM definitions
ms.assetid: 7aba0e40-b8d3-4afc-9e4c-92392f1f6269
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93cf3d280d0e615442a4141b7fa41f6ee3566490
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-bam-definitions"></a><span data-ttu-id="a6c06-102">BAM 定義の管理</span><span class="sxs-lookup"><span data-stu-id="a6c06-102">Managing BAM Definitions</span></span>
<span data-ttu-id="a6c06-103">BAM 定義は、BAM インフラストラクチャの一部であり、</span><span class="sxs-lookup"><span data-stu-id="a6c06-103">A BAM definition is part of the BAM infrastructure.</span></span> <span data-ttu-id="a6c06-104">追跡および集計するデータの定義、および追跡データに関するビジネス エンド ユーザー向けビューの定義を設定します。</span><span class="sxs-lookup"><span data-stu-id="a6c06-104">It defines the data to track and aggregate, as well as the business end user's view on the tracking data.</span></span> <span data-ttu-id="a6c06-105">このセクションのトピックでは、アクティビティ、ビュー、アイテム、警告など、BAM 定義の要素を管理するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6c06-105">The topics in this section give procedures for managing the elements of BAM definitions, which include activities, views, artifacts, and alerts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6c06-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a6c06-106">In This Section</span></span>  
  
-   [<span data-ttu-id="a6c06-107">BAM 定義ファイルを管理するユーザー権利が必要</span><span class="sxs-lookup"><span data-stu-id="a6c06-107">Required User Rights for Managing BAM Definition Files</span></span>](../core/required-user-rights-for-managing-bam-definition-files.md)  
  
-   [<span data-ttu-id="a6c06-108">BAM 定義を展開する方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-108">How to Deploy BAM Definitions</span></span>](../core/how-to-deploy-bam-definitions.md)  
  
-   [<span data-ttu-id="a6c06-109">BAM 定義を削除する方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-109">How to Remove BAM Definitions</span></span>](../core/how-to-remove-bam-activities.md)  
  
-   [<span data-ttu-id="a6c06-110">BAM インフラストラクチャに対する変更を一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-110">How to List Changes to the BAM Infrastructure</span></span>](../core/how-to-list-changes-to-the-bam-infrastructure.md)  
  
-   [<span data-ttu-id="a6c06-111">BAM アクティビティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-111">How to List BAM Activities</span></span>](../core/how-to-list-bam-activities.md)  
  
-   [<span data-ttu-id="a6c06-112">BAM アクティビティを削除する方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-112">How to Remove BAM Activities</span></span>](../core/how-to-remove-bam-activities.md)  
  
-   [<span data-ttu-id="a6c06-113">BAM ビューを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-113">How to List BAM Views</span></span>](../core/how-to-list-bam-views.md)  
  
-   [<span data-ttu-id="a6c06-114">BAM ビューを削除する方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-114">How to Remove BAM Views</span></span>](../core/how-to-remove-bam-views.md)  
  
-   [<span data-ttu-id="a6c06-115">アラートを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-115">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md)  
  
-   [<span data-ttu-id="a6c06-116">アラートを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-116">How to Disable Alerts</span></span>](../core/how-to-disable-alerts.md)  
  
-   [<span data-ttu-id="a6c06-117">BAM 警告を削除する方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-117">How to Remove BAM Alerts</span></span>](../core/how-to-remove-bam-alerts.md)  
  
-   [<span data-ttu-id="a6c06-118">BAM アイテムを更新する方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-118">How to Update BAM Artifacts</span></span>](../core/how-to-update-bam-artifacts.md)  
  
-   [<span data-ttu-id="a6c06-119">展開済みのアイテムを削除する方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-119">How to Remove Deployed Artifacts</span></span>](../core/how-to-remove-deployed-artifacts.md)  
  
-   [<span data-ttu-id="a6c06-120">BAM 警告の構成</span><span class="sxs-lookup"><span data-stu-id="a6c06-120">Configuring BAM Alerts</span></span>](../core/configuring-bam-alerts.md)  
  
-   [<span data-ttu-id="a6c06-121">BAM 警告の実行を管理します。</span><span class="sxs-lookup"><span data-stu-id="a6c06-121">Managing BAM Alert Execution</span></span>](../core/managing-bam-alert-execution.md)  
  
-   [<span data-ttu-id="a6c06-122">変更の頻度をどのアラートを評価する方法</span><span class="sxs-lookup"><span data-stu-id="a6c06-122">How to Change the Frequency With Which Alerts Are Evaluated</span></span>](../core/how-to-change-the-frequency-with-which-alerts-are-evaluated.md)