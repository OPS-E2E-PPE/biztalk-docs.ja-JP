---
title: BAM ソリューションの実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18a5bc04-1b0a-4242-b599-760e696f5c06
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9abc0c5cc39a624746eff42397efd9b88a826196
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332391"
---
# <a name="implementing-bam-solutions"></a><span data-ttu-id="630a0-102">BAM ソリューションの実装</span><span class="sxs-lookup"><span data-stu-id="630a0-102">Implementing BAM Solutions</span></span>
<span data-ttu-id="630a0-103">このセクションでは、必要なデータをキャプチャする方法、BAM にデータを送信する方法、ビジネス要件の変化に合わせて BAM に送信するデータを変更する方法など、BAM ソリューションを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="630a0-103">This section describes ways to implement your BAM solution, including capturing data of interest, sending data to BAM, and modifying the data you send to BAM as a result of changing business requirements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="630a0-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="630a0-104">In This Section</span></span>  
  
-   [<span data-ttu-id="630a0-105">BAM イベント ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="630a0-105">Installing the BAM-Eventing Software</span></span>](../core/installing-the-bam-eventing-software.md)  
  
-   [<span data-ttu-id="630a0-106">追跡プロファイル エディター</span><span class="sxs-lookup"><span data-stu-id="630a0-106">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)  
  
-   [<span data-ttu-id="630a0-107">イベント ストリームを使用した BAM アクティビティを実装します。</span><span class="sxs-lookup"><span data-stu-id="630a0-107">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)  
  
-   [<span data-ttu-id="630a0-108">BAM インターセプターについて</span><span class="sxs-lookup"><span data-stu-id="630a0-108">What Is the BAM Interceptor?</span></span>](../core/what-is-the-bam-interceptor.md)  
  
-   [<span data-ttu-id="630a0-109">カスタム分析タスクを作成する方法</span><span class="sxs-lookup"><span data-stu-id="630a0-109">How to Create a Custom Analysis Task</span></span>](../core/how-to-create-a-custom-analysis-task.md)  
  
-   [<span data-ttu-id="630a0-110">BAM イベントを公開する際のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="630a0-110">Performance Considerations for BAM Event Publishing</span></span>](../core/performance-considerations-for-bam-event-publishing.md)  
  
-   [<span data-ttu-id="630a0-111">BAM コードの管理に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="630a0-111">Considerations for BAM Code Maintenance</span></span>](../core/considerations-for-bam-code-maintenance.md)  
  
-   [<span data-ttu-id="630a0-112">BAM API を使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="630a0-112">Considerations for Working with BAM APIs</span></span>](../core/considerations-for-working-with-bam-apis.md)  
  
-   [<span data-ttu-id="630a0-113">参照を使用して BAM データを強化する方法</span><span class="sxs-lookup"><span data-stu-id="630a0-113">How to Enrich BAM Data Using Lookups</span></span>](../core/how-to-enrich-bam-data-using-lookups.md)  
  
-   [<span data-ttu-id="630a0-114">ローカライズされた BAM XML ファイルの展開</span><span class="sxs-lookup"><span data-stu-id="630a0-114">Deploying Localized BAM XML Files</span></span>](../core/deploying-localized-bam-xml-files.md)  
  
-   [<span data-ttu-id="630a0-115">BAM WCF インターセプターと WF インターセプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="630a0-115">Using the BAM WCF and WF Interceptors</span></span>](../core/using-the-bam-wcf-and-wf-interceptors.md)