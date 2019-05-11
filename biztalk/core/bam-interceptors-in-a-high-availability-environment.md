---
title: 高可用性環境における BAM インターセプタ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 555c8200-949f-4c7d-8041-5ba4b6cbaed5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb2784fe37e115e4ad409b67cf052c2a16d7116b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528789"
---
# <a name="bam-interceptors-in-a-high-availability-environment"></a><span data-ttu-id="2390d-102">高可用性環境における BAM インターセプタ</span><span class="sxs-lookup"><span data-stu-id="2390d-102">BAM Interceptors in a High Availability Environment</span></span>
<span data-ttu-id="2390d-103">このトピックでは、SQL Server のフェールオーバー中に BAM WF インターセプタと高可用性環境で BAM WCF インターセプタのフェールオーバー プロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="2390d-103">This topic describes the failover processes for the BAM WF interceptor and the BAM WCF interceptor in a high availability environment during a SQL Server failover.</span></span>  
  
## <a name="bam-wf-interceptor"></a><span data-ttu-id="2390d-104">BAM WF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="2390d-104">BAM WF Interceptor</span></span>  
 <span data-ttu-id="2390d-105">高可用性環境で使用する場合、SQL Server のフェールオーバー中に SQL Server 接続の問題がある場合、BAM WF インターセプターは、インターセプター構成ファイルの取得を再試行します。</span><span class="sxs-lookup"><span data-stu-id="2390d-105">When operating in a high availability environment, the BAM WF interceptor will retry retrieval of the interceptor configuration file when there is a SQL Server connection problem during a SQL Server failover.</span></span> <span data-ttu-id="2390d-106">ただし、プロセスが SQL Server のフェールオーバーの場合、BAM プライマリ インポート データベースにデータを書き込むときに、インターセプターは再試行しません。</span><span class="sxs-lookup"><span data-stu-id="2390d-106">However, the interceptor will not retry when writing data to the BAM Primary Import database when a SQL Server failover is in process.</span></span> <span data-ttu-id="2390d-107">これは、インターセプターは、の動作に依存しているため、 **WorkflowCommitBatchService**クラス、BAM プライマリ インポート データベースにデータを書き込むときにします。</span><span class="sxs-lookup"><span data-stu-id="2390d-107">This is because the interceptor relies on the behavior of the **WorkflowCommitBatchService** class when writing data to the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="2390d-108">次の例では、 **DefaultWorkflowCommitWorkBatchService** enableRetries のランタイム サービスとして追加されます、App.config ファイルのスニペットで示すように、バッチを再試行するように ="true"。</span><span class="sxs-lookup"><span data-stu-id="2390d-108">In the following example, **DefaultWorkflowCommitWorkBatchService** is added as a run-time service with enableRetries="true" so that it retries the batch as shown in a snippet from an App.config file:</span></span>  
  
```  
<add type="System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  enableRetries="True"/>  
```  
  
 <span data-ttu-id="2390d-109">ただし、アンビエント トランザクションが存在する場合と、 **CommitWorkBatch**メソッドが呼び出されると、すぐに、SQL Server の接続が利用できない場合、ワークフロー インスタンスが終了します。</span><span class="sxs-lookup"><span data-stu-id="2390d-109">However, if there are existing ambient transactions when the **CommitWorkBatch** method is called, the workflow instance is terminated immediately when a SQL Server connection is not available.</span></span>  
  
 <span data-ttu-id="2390d-110">動作の詳細については、 **WorkflowCommitBatchService**クラスの高可用性環境で、"の概要をホストしている Windows Workflow foundation"、「Reliability and High Availability」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068)します。</span><span class="sxs-lookup"><span data-stu-id="2390d-110">For more information about the behavior of the **WorkflowCommitBatchService** class in a high availability environment, see the "Reliability and High Availability" section in "Introduction to Hosting Windows Workflow Foundation" at [http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068).</span></span>  
  
## <a name="bam-wcf-interceptor"></a><span data-ttu-id="2390d-111">BAM WCF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="2390d-111">BAM WCF Interceptor</span></span>  
 <span data-ttu-id="2390d-112">高可用性環境で BAM WCF インターセプタは、インターセプタ構成ファイルの取得を再試行しない SQL Server のフェールオーバー中に SQL Server 接続の問題がある場合。</span><span class="sxs-lookup"><span data-stu-id="2390d-112">In a high availability environment, the BAM WCF interceptor does not retry retrieval of the interceptor configuration file when there is a SQL Server connection problem during a SQL Server failover.</span></span> <span data-ttu-id="2390d-113">そのため、エラーの補正または信頼性の高いメッセージを再送信メッセージングを使用する WCF コードをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2390d-113">You should therefore customize the WCF code to compensate for failure or use reliable messaging to resubmit messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2390d-114">参照</span><span class="sxs-lookup"><span data-stu-id="2390d-114">See Also</span></span>  
 [<span data-ttu-id="2390d-115">BAM WF インターセプター</span><span class="sxs-lookup"><span data-stu-id="2390d-115">BAM WF Interceptor</span></span>](../core/bam-wf-interceptor.md)