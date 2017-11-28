---
title: "BAM WF インターセプタ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e459084-cb72-4a75-9f5f-f1fd5fd80d17
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de770da5ee0f5d3270b0ee649b6bda61dc6d156e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-wf-interceptor"></a><span data-ttu-id="52e54-102">BAM WF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="52e54-102">BAM WF Interceptor</span></span>
<span data-ttu-id="52e54-103">BAM WF インターセプタは、WF アプリケーション内の追跡データを包括的にサポートします。</span><span class="sxs-lookup"><span data-stu-id="52e54-103">The BAM WF interceptor provides comprehensive support for tracking data within your WF application.</span></span>  
  
 <span data-ttu-id="52e54-104">BAM WF インターセプタを使用すると、次の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="52e54-104">You can use the BAM WF interceptor to:</span></span>  
  
-   <span data-ttu-id="52e54-105">WF アプリケーションを再コンパイルしなくても、ワークフロー アプリケーション データを BAM に透過的に配信します。</span><span class="sxs-lookup"><span data-stu-id="52e54-105">Transparently deliver workflow application data to BAM without having to recompile your WF application.</span></span>  
  
-   <span data-ttu-id="52e54-106">ワークフロー内の特定の操作を対象に、ワークフロー アプリケーション データを選択して BAM に配信します。</span><span class="sxs-lookup"><span data-stu-id="52e54-106">Target specific activities within a workflow to selectively deliver workflow application data to BAM.</span></span>  
  
-   <span data-ttu-id="52e54-107">ワークフローのトランザクション セマンティクスを使用します。</span><span class="sxs-lookup"><span data-stu-id="52e54-107">Honor the transactional semantics of the workflow.</span></span> <span data-ttu-id="52e54-108">所有しているトランザクションがコミットされる場合にのみ、データが BAM に配信されます。</span><span class="sxs-lookup"><span data-stu-id="52e54-108">Data will be delivered to BAM only if the owning transaction commits.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52e54-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="52e54-109">In This Section</span></span>  
  
-   [<span data-ttu-id="52e54-110">傍受のため、Workflow Foundation アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="52e54-110">How to Configure a Workflow Foundation Application for Interception</span></span>](../core/how-to-configure-a-workflow-foundation-application-for-interception.md)  
  
-   [<span data-ttu-id="52e54-111">Windows Workflow Foundation スキーマ</span><span class="sxs-lookup"><span data-stu-id="52e54-111">Windows Workflow Foundation Schema</span></span>](../core/windows-workflow-foundation-schema.md)  
  
-   [<span data-ttu-id="52e54-112">一般的なイベント フィルタ パターン</span><span class="sxs-lookup"><span data-stu-id="52e54-112">Common Event Filter Patterns</span></span>](../core/common-event-filter-patterns.md)  
  
-   [<span data-ttu-id="52e54-113">Windows Workflow Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="52e54-113">Operations in Windows Workflow Foundation</span></span>](../core/operations-in-windows-workflow-foundation.md)