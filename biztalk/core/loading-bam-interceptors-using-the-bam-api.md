---
title: BAM API を使用して BAM インターセプタの読み込み |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d77ea5fb-a796-48f1-8c77-173e995c5252
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1236d674a643224d2aaf5ca2cb5be2be15c2f2bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331147"
---
# <a name="loading-bam-interceptors-using-the-bam-api"></a>BAM API を使用した BAM インターセプタの読み込み
このトピックでは、構成ファイルではなく、コードを使用した WF インターセプタおよび WCF インターセプタの読み込みについて説明します。  
  
## <a name="loading-the-wf-interceptor-from-code"></a>コードからの WF インターセプタの読み込み  
 実行時にコードから WF インターセプタを読み込むには、WorkflowRuntime の新しいインスタンスを作成し、BamTrackingService の新しいインスタンスを使用して AddService メソッドを呼び出します。 この処理について、次に例示します。  
  
```csharp  
string connectionString = "Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport";  
int PollingIntervalSec = 300;  
  
WorkflowRuntime workflowRuntime = new WorkflowRuntime();  
workflowRuntime.AddService(new BamTrackingService(connectionString, interceptorConfigurationPollingInterval));  
```  
  
## <a name="loading-the-wcf-interceptor-from-code"></a>コードからの WCF インターセプタの読み込み  
 WCF インターセプタを読み込むには、サービスを開いて実装にアクセスできる派生クラスを作成する必要があります。 この処理について、次に例示します。  
  
```csharp  
// Your project must have a reference to Microsoft.BizTalk.BAM.Interceptors.dll.  
// Create a derived class accessible to the implementation that opens the service.  
internal class MyBamBehaviorExtension : BamBehaviorExtension  
{  
    internal MyBamBehaviorExtension(string connectionString, int pollingInterval)  
        : base()  
    {  
        this.ConnectionString = connectionString;  
        this.PollingIntervalSec = pollingInterval.ToString();  
    }  
  
    internal IEndpointBehavior Create()  
    {  
        return (IEndpointBehavior) this.CreateBehavior();  
    }  
}  
  
// Add the endpoint behavior just before the service is opened.   
// In this example the connection string and polling intervals are being read from appSettings in App.config.  
MyBamBehaviorExtension bamBehaviorExtension = new MyBamBehaviorExtension(ConfigurationManager.AppSettings["ConnectionString"], int.Parse(ConfigurationManager.AppSettings["PollingIntervalSec"]));  
IEndpointBehavior bamBehavior = bamBehaviorExtension.Create();  
foreach (System.ServiceModel.Description.ServiceEndpoint endpoint in myServiceHost.Description.Endpoints)  
{  
    if (endpoint.Behaviors.Find<MyBamBehaviorExtension>() == null)  
        endpoint.Behaviors.Add(bamBehavior);  
}  
```  
  
## <a name="see-also"></a>参照  
 [BAM WCF インターセプターと WF インターセプターを使用します。](../core/using-the-bam-wcf-and-wf-interceptors.md)