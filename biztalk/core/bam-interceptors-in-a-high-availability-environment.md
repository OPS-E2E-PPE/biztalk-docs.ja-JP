---
title: 高可用性環境における BAM インターセプタ |Microsoft ドキュメント
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
ms.openlocfilehash: 79a697eb2a1a27ceeec1538ad8d46127413e7ed1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230738"
---
# <a name="bam-interceptors-in-a-high-availability-environment"></a><span data-ttu-id="e105f-102">高可用性環境における BAM インターセプタ</span><span class="sxs-lookup"><span data-stu-id="e105f-102">BAM Interceptors in a High Availability Environment</span></span>
<span data-ttu-id="e105f-103">このトピックでは、高可用性環境における SQL Server のフェールオーバー時の BAM WF インターセプタと BAM WCF インターセプタのフェールオーバー プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e105f-103">This topic describes the failover processes for the BAM WF interceptor and the BAM WCF interceptor in a high availability environment during a SQL Server failover.</span></span>  
  
## <a name="bam-wf-interceptor"></a><span data-ttu-id="e105f-104">BAM WF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="e105f-104">BAM WF Interceptor</span></span>  
 <span data-ttu-id="e105f-105">BAM WF インターセプタは、高可用性環境での稼働中での SQL Server のフェールオーバー時に SQL Server との接続で問題が発生すると、インターセプタ構成ファイルの取得を再試行します。</span><span class="sxs-lookup"><span data-stu-id="e105f-105">When operating in a high availability environment, the BAM WF interceptor will retry retrieval of the interceptor configuration file when there is a SQL Server connection problem during a SQL Server failover.</span></span> <span data-ttu-id="e105f-106">しかし、SQL Server のフェールオーバー時に BAM プライマリ インポート データベースにデータの書き込みを行っている場合、BAM WF インターセプタはこの操作を再試行しません。</span><span class="sxs-lookup"><span data-stu-id="e105f-106">However, the interceptor will not retry when writing data to the BAM Primary Import database when a SQL Server failover is in process.</span></span> <span data-ttu-id="e105f-107">これは、インターセプターは、の動作に依存しているため、 **WorkflowCommitBatchService**クラスのデータを BAM プライマリ インポート データベースに書き込むとき。</span><span class="sxs-lookup"><span data-stu-id="e105f-107">This is because the interceptor relies on the behavior of the **WorkflowCommitBatchService** class when writing data to the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="e105f-108">次の例では、 **DefaultWorkflowCommitWorkBatchService** enableRetries ランタイム サービスとして追加は、App.config ファイルのスニペットで示すように、バッチを再試行するように ="true"。</span><span class="sxs-lookup"><span data-stu-id="e105f-108">In the following example, **DefaultWorkflowCommitWorkBatchService** is added as a run-time service with enableRetries="true" so that it retries the batch as shown in a snippet from an App.config file:</span></span>  
  
```  
<add type="System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  enableRetries="True"/>  
```  
  
 <span data-ttu-id="e105f-109">ただし、アンビエント トランザクションが存在する場合と、 **CommitWorkBatch**メソッドが呼び出されると、ワークフロー インスタンスが SQL Server 接続が利用可能なされません直ちに終了します。</span><span class="sxs-lookup"><span data-stu-id="e105f-109">However, if there are existing ambient transactions when the **CommitWorkBatch** method is called, the workflow instance is terminated immediately when a SQL Server connection is not available.</span></span>  
  
 <span data-ttu-id="e105f-110">動作の詳細については、 **WorkflowCommitBatchService**クラスの高可用性環境で、"の概要をホストしている Windows Workflow Foundation"で「Reliability and High Availability」を参照してください[http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068)です。</span><span class="sxs-lookup"><span data-stu-id="e105f-110">For more information about the behavior of the **WorkflowCommitBatchService** class in a high availability environment, see the "Reliability and High Availability" section in "Introduction to Hosting Windows Workflow Foundation" at [http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068).</span></span>  
  
## <a name="bam-wcf-interceptor"></a><span data-ttu-id="e105f-111">BAM WCF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="e105f-111">BAM WCF Interceptor</span></span>  
 <span data-ttu-id="e105f-112">BAM WCF インターセプタは、高可用性環境での SQL Server のフェールオーバー時に SQL Server との接続で問題が発生すると、インターセプタ構成ファイルの取得を再試行しません。</span><span class="sxs-lookup"><span data-stu-id="e105f-112">In a high availability environment, the BAM WCF interceptor does not retry retrieval of the interceptor configuration file when there is a SQL Server connection problem during a SQL Server failover.</span></span> <span data-ttu-id="e105f-113">このため、WCF コードをカスタマイズして障害発生時に対応できるようにするか、信頼できるメッセージング機能を使用してメッセージを再送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e105f-113">You should therefore customize the WCF code to compensate for failure or use reliable messaging to resubmit messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e105f-114">参照</span><span class="sxs-lookup"><span data-stu-id="e105f-114">See Also</span></span>  
 [<span data-ttu-id="e105f-115">BAM WF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="e105f-115">BAM WF Interceptor</span></span>](../core/bam-wf-interceptor.md)