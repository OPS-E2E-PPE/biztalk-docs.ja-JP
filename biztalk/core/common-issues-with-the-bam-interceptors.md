---
title: BAM インターセプタにおける一般的な問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a32145e2-1367-4576-9103-86c9182c11a8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 787ed9f5fd2f94f719e224db471bde8c2aad9829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357103"
---
# <a name="common-issues-with-the-bam-interceptors"></a><span data-ttu-id="19c01-102">BAM インターセプタにおける一般的な問題</span><span class="sxs-lookup"><span data-stu-id="19c01-102">Common Issues with the BAM Interceptors</span></span>
<span data-ttu-id="19c01-103">このトピックでは、BAM インターセプタを使用する際に発生する可能性がある、以下の一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="19c01-103">This topic discusses the following common problems that can arise when using BAM interceptors:</span></span>  
  
-   <span data-ttu-id="19c01-104">分散トランザクションに関連した SQL 例外</span><span class="sxs-lookup"><span data-stu-id="19c01-104">SQL Exception relating to a distributed transaction</span></span>  
  
## <a name="you-receive-a-sql-exception-concerning-a-completed-distributed-transaction-or-a-transaction-descriptor"></a><span data-ttu-id="19c01-105">完了した分散トランザクションまたはトランザクション記述子に関連した SQL 例外が返される</span><span class="sxs-lookup"><span data-stu-id="19c01-105">You Receive a SQL Exception Concerning a Completed Distributed Transaction or a Transaction Descriptor</span></span>  
 <span data-ttu-id="19c01-106">BAM Windows Communication Framework (WCF) インターセプタを実行すると、次のいずれかの例外が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="19c01-106">You may see one of the following exceptions when running the BAM Windows Communication Framework (WCF) interceptor:</span></span>  
  
- <span data-ttu-id="19c01-107">分散トランザクションが完了しました。</span><span class="sxs-lookup"><span data-stu-id="19c01-107">Distributed transaction completed.</span></span> <span data-ttu-id="19c01-108">このセッションを新規トランザクションまたは NULL トランザクションのいずれかに参加させます。</span><span class="sxs-lookup"><span data-stu-id="19c01-108">Either enlist this session in a new transaction or the NULL transaction.</span></span>  
  
- <span data-ttu-id="19c01-109">新しい要求は、有効なトランザクション記述子を含んでいる必要があるため、この要求を開始できません。</span><span class="sxs-lookup"><span data-stu-id="19c01-109">New request is not allowed to start because it should come with a valid transaction descriptor.</span></span>  
  
  <span data-ttu-id="19c01-110">この問題をトラブルシューティングする方法としては、以下が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="19c01-110">Some suggestions for troubleshooting this problem are:</span></span>  
  
- <span data-ttu-id="19c01-111">BAM トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="19c01-111">Enable BAM tracing.</span></span> <span data-ttu-id="19c01-112">このトレースでは、エラーの根本原因を含むすべての関連メッセージが対象となります。</span><span class="sxs-lookup"><span data-stu-id="19c01-112">This trace will include all relevant messages including the root cause of the error.</span></span> <span data-ttu-id="19c01-113">BAM トレースの詳細については、次を参照してください。 [BAM のトレースの有効化する方法](../core/how-to-enable-tracing-in-bam.md)します。</span><span class="sxs-lookup"><span data-stu-id="19c01-113">For more information about BAM tracing, see [How to Enable Tracing in BAM](../core/how-to-enable-tracing-in-bam.md).</span></span>  
  
- <span data-ttu-id="19c01-114">この分散トランザクション コーディネータ (DTC) 例外が表示される場合は、完全に同一なシナリオをトランザクションなしで返すことを試みます。</span><span class="sxs-lookup"><span data-stu-id="19c01-114">When you see this distributed transaction coordinator (DTC) exception, try to rerun exactly the same scenario without transactions.</span></span>  
  
- <span data-ttu-id="19c01-115">SQL Server Profiler を使用して、トランザクションが中断する原因となるエラーをトレースで検索します。</span><span class="sxs-lookup"><span data-stu-id="19c01-115">Use SQL Server Profiler and look for errors in the trace that will cause the transaction to be aborted.</span></span>  
  
## <a name="you-receive-an-error-similar-to-interceptor-configuration-polling-interval-0-must-be-at-least-5-seconds-when-using-the-wcf-interceptor"></a><span data-ttu-id="19c01-116">WCF インターセプタを使用すると、「インターセプタ構成ポーリング間隔 '0' を '5' 秒以上にする必要があります」というエラーが返される</span><span class="sxs-lookup"><span data-stu-id="19c01-116">You receive an error similar to "interceptor configuration polling interval '0' must be at least '5' seconds" when using the WCF Interceptor</span></span>  
 <span data-ttu-id="19c01-117">このエラーは、アプリケーション構成ファイルでインターセプタ構成ポーリング間隔の値を明示的に指定しなかった場合、または有効な下限値である 5 秒に満たない値を指定した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="19c01-117">You may encounter this error when you do not explicitly provide an interceptor configuration polling interval value in the application configuration file, or when you provide a value but it is less than 5 seconds, the required minimum.</span></span>  
  
 <span data-ttu-id="19c01-118">この問題を解決するには、次のように PollingIntervalSec に有効な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="19c01-118">To fix the problem, provide a valid value for PollingIntervalSec as shown:</span></span>  
  
```  
<BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" PollingIntervalSec="1500" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="19c01-119">参照</span><span class="sxs-lookup"><span data-stu-id="19c01-119">See Also</span></span>  
 [<span data-ttu-id="19c01-120">BAM インターセプタのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="19c01-120">Troubleshooting BAM Interceptors</span></span>](../core/troubleshooting-bam-interceptors.md)