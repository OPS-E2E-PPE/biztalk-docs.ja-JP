---
title: "高可用性環境における BAM インターセプタ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 555c8200-949f-4c7d-8041-5ba4b6cbaed5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79a697eb2a1a27ceeec1538ad8d46127413e7ed1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-interceptors-in-a-high-availability-environment"></a>高可用性環境における BAM インターセプタ
このトピックでは、高可用性環境における SQL Server のフェールオーバー時の BAM WF インターセプタと BAM WCF インターセプタのフェールオーバー プロセスについて説明します。  
  
## <a name="bam-wf-interceptor"></a>BAM WF インターセプタ  
 BAM WF インターセプタは、高可用性環境での稼働中での SQL Server のフェールオーバー時に SQL Server との接続で問題が発生すると、インターセプタ構成ファイルの取得を再試行します。 しかし、SQL Server のフェールオーバー時に BAM プライマリ インポート データベースにデータの書き込みを行っている場合、BAM WF インターセプタはこの操作を再試行しません。 これは、インターセプターは、の動作に依存しているため、 **WorkflowCommitBatchService**クラスのデータを BAM プライマリ インポート データベースに書き込むとき。  
  
 次の例では、 **DefaultWorkflowCommitWorkBatchService** enableRetries ランタイム サービスとして追加は、App.config ファイルのスニペットで示すように、バッチを再試行するように ="true"。  
  
```  
<add type="System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  enableRetries="True"/>  
```  
  
 ただし、アンビエント トランザクションが存在する場合と、 **CommitWorkBatch**メソッドが呼び出されると、ワークフロー インスタンスが SQL Server 接続が利用可能なされません直ちに終了します。  
  
 動作の詳細については、 **WorkflowCommitBatchService**クラスの高可用性環境で、"の概要をホストしている Windows Workflow Foundation"で「Reliability and High Availability」を参照してください[http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068)です。  
  
## <a name="bam-wcf-interceptor"></a>BAM WCF インターセプタ  
 BAM WCF インターセプタは、高可用性環境での SQL Server のフェールオーバー時に SQL Server との接続で問題が発生すると、インターセプタ構成ファイルの取得を再試行しません。 このため、WCF コードをカスタマイズして障害発生時に対応できるようにするか、信頼できるメッセージング機能を使用してメッセージを再送信する必要があります。  
  
## <a name="see-also"></a>参照  
 [BAM WF インターセプタ](../core/bam-wf-interceptor.md)