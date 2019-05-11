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
# <a name="bam-interceptors-in-a-high-availability-environment"></a>高可用性環境における BAM インターセプタ
このトピックでは、SQL Server のフェールオーバー中に BAM WF インターセプタと高可用性環境で BAM WCF インターセプタのフェールオーバー プロセスを説明します。  
  
## <a name="bam-wf-interceptor"></a>BAM WF インターセプタ  
 高可用性環境で使用する場合、SQL Server のフェールオーバー中に SQL Server 接続の問題がある場合、BAM WF インターセプターは、インターセプター構成ファイルの取得を再試行します。 ただし、プロセスが SQL Server のフェールオーバーの場合、BAM プライマリ インポート データベースにデータを書き込むときに、インターセプターは再試行しません。 これは、インターセプターは、の動作に依存しているため、 **WorkflowCommitBatchService**クラス、BAM プライマリ インポート データベースにデータを書き込むときにします。  
  
 次の例では、 **DefaultWorkflowCommitWorkBatchService** enableRetries のランタイム サービスとして追加されます、App.config ファイルのスニペットで示すように、バッチを再試行するように ="true"。  
  
```  
<add type="System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  enableRetries="True"/>  
```  
  
 ただし、アンビエント トランザクションが存在する場合と、 **CommitWorkBatch**メソッドが呼び出されると、すぐに、SQL Server の接続が利用できない場合、ワークフロー インスタンスが終了します。  
  
 動作の詳細については、 **WorkflowCommitBatchService**クラスの高可用性環境で、"の概要をホストしている Windows Workflow foundation"、「Reliability and High Availability」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068)します。  
  
## <a name="bam-wcf-interceptor"></a>BAM WCF インターセプタ  
 高可用性環境で BAM WCF インターセプタは、インターセプタ構成ファイルの取得を再試行しない SQL Server のフェールオーバー中に SQL Server 接続の問題がある場合。 そのため、エラーの補正または信頼性の高いメッセージを再送信メッセージングを使用する WCF コードをカスタマイズする必要があります。  
  
## <a name="see-also"></a>参照  
 [BAM WF インターセプター](../core/bam-wf-interceptor.md)