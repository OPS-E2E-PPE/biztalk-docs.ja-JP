---
title: "BAM ソリューションを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18a5bc04-1b0a-4242-b599-760e696f5c06
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a167f2991250c446bedcb6bb235739f5414454e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-bam-solutions"></a><span data-ttu-id="1568c-102">BAM ソリューションの実装</span><span class="sxs-lookup"><span data-stu-id="1568c-102">Implementing BAM Solutions</span></span>
<span data-ttu-id="1568c-103">このセクションでは、必要なデータをキャプチャする方法、BAM にデータを送信する方法、ビジネス要件の変化に合わせて BAM に送信するデータを変更する方法など、BAM ソリューションを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1568c-103">This section describes ways to implement your BAM solution, including capturing data of interest, sending data to BAM, and modifying the data you send to BAM as a result of changing business requirements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1568c-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1568c-104">In This Section</span></span>  
  
-   [<span data-ttu-id="1568c-105">BAM イベント ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1568c-105">Installing the BAM-Eventing Software</span></span>](../core/installing-the-bam-eventing-software.md)  
  
-   [<span data-ttu-id="1568c-106">追跡プロファイル エディター</span><span class="sxs-lookup"><span data-stu-id="1568c-106">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)  
  
-   [<span data-ttu-id="1568c-107">BAM アクティビティのイベント ストリームの実装</span><span class="sxs-lookup"><span data-stu-id="1568c-107">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)  
  
-   [<span data-ttu-id="1568c-108">BAM インターセプタとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="1568c-108">What Is the BAM Interceptor?</span></span>](../core/what-is-the-bam-interceptor.md)  
  
-   [<span data-ttu-id="1568c-109">カスタム分析タスクを作成する方法</span><span class="sxs-lookup"><span data-stu-id="1568c-109">How to Create a Custom Analysis Task</span></span>](../core/how-to-create-a-custom-analysis-task.md)  
  
-   [<span data-ttu-id="1568c-110">BAM イベントの発行のためのパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1568c-110">Performance Considerations for BAM Event Publishing</span></span>](../core/performance-considerations-for-bam-event-publishing.md)  
  
-   [<span data-ttu-id="1568c-111">BAM コードの保守に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1568c-111">Considerations for BAM Code Maintenance</span></span>](../core/considerations-for-bam-code-maintenance.md)  
  
-   [<span data-ttu-id="1568c-112">BAM Api を操作するための考慮事項</span><span class="sxs-lookup"><span data-stu-id="1568c-112">Considerations for Working with BAM APIs</span></span>](../core/considerations-for-working-with-bam-apis.md)  
  
-   [<span data-ttu-id="1568c-113">参照を使用して BAM データを強化する方法</span><span class="sxs-lookup"><span data-stu-id="1568c-113">How to Enrich BAM Data Using Lookups</span></span>](../core/how-to-enrich-bam-data-using-lookups.md)  
  
-   [<span data-ttu-id="1568c-114">ローカライズされた BAM XML ファイルの配置</span><span class="sxs-lookup"><span data-stu-id="1568c-114">Deploying Localized BAM XML Files</span></span>](../core/deploying-localized-bam-xml-files.md)  
  
-   [<span data-ttu-id="1568c-115">BAM WCF インターセプタと WF インターセプタを使用します。</span><span class="sxs-lookup"><span data-stu-id="1568c-115">Using the BAM WCF and WF Interceptors</span></span>](../core/using-the-bam-wcf-and-wf-interceptors.md)