---
title: BAM WF インターセプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e459084-cb72-4a75-9f5f-f1fd5fd80d17
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 898d3ebae85e3eadd44e27d7d5cb7f1ff32453b1
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530535"
---
# <a name="bam-wf-interceptor"></a><span data-ttu-id="64969-102">BAM WF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="64969-102">BAM WF Interceptor</span></span>
<span data-ttu-id="64969-103">BAM WF インターセプタは、WF アプリケーション内の追跡データを包括的にサポートします。</span><span class="sxs-lookup"><span data-stu-id="64969-103">The BAM WF interceptor provides comprehensive support for tracking data within your WF application.</span></span>  
  
 <span data-ttu-id="64969-104">BAM WF インターセプタを使用すると、次の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="64969-104">You can use the BAM WF interceptor to:</span></span>  
  
-   <span data-ttu-id="64969-105">WF アプリケーションを再コンパイルしなくても、ワークフロー アプリケーション データを BAM に透過的に配信します。</span><span class="sxs-lookup"><span data-stu-id="64969-105">Transparently deliver workflow application data to BAM without having to recompile your WF application.</span></span>  
  
-   <span data-ttu-id="64969-106">ワークフロー内の特定の操作を対象に、ワークフロー アプリケーション データを選択して BAM に配信します。</span><span class="sxs-lookup"><span data-stu-id="64969-106">Target specific activities within a workflow to selectively deliver workflow application data to BAM.</span></span>  
  
-   <span data-ttu-id="64969-107">ワークフローのトランザクション セマンティクスを使用します。</span><span class="sxs-lookup"><span data-stu-id="64969-107">Honor the transactional semantics of the workflow.</span></span> <span data-ttu-id="64969-108">所有しているトランザクションがコミットされる場合にのみ、データが BAM に配信されます。</span><span class="sxs-lookup"><span data-stu-id="64969-108">Data will be delivered to BAM only if the owning transaction commits.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="64969-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="64969-109">In This Section</span></span>  
  
-   [<span data-ttu-id="64969-110">傍受のために Workflow Foundation のアプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="64969-110">How to Configure a Workflow Foundation Application for Interception</span></span>](../core/how-to-configure-a-workflow-foundation-application-for-interception.md)  
  
-   [<span data-ttu-id="64969-111">Windows Workflow Foundation スキーマ</span><span class="sxs-lookup"><span data-stu-id="64969-111">Windows Workflow Foundation Schema</span></span>](../core/windows-workflow-foundation-schema.md)  
  
-   [<span data-ttu-id="64969-112">一般的なイベント フィルター パターン</span><span class="sxs-lookup"><span data-stu-id="64969-112">Common Event Filter Patterns</span></span>](../core/common-event-filter-patterns.md)  
  
-   [<span data-ttu-id="64969-113">Windows Workflow Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="64969-113">Operations in Windows Workflow Foundation</span></span>](../core/operations-in-windows-workflow-foundation.md)