---
title: "サービスの動作を使用して、WCF LOB Adapter SDK を持つ資格情報を入力 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b203cfa-6331-4498-b656-8cd8339f8613
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cc494e55aee70a9a441eccbe056f4651448752d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-a-service-behavior-to-enter-credentials-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="db788-102">サービスの動作を使用して、WCF LOB Adapter SDK を持つ資格情報を入力</span><span class="sxs-lookup"><span data-stu-id="db788-102">Use a service behavior to enter credentials with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="db788-103">多くの場合、アダプターのコンシューマーは、対象の基幹業務システムに資格情報を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="db788-103">Many times, adapter consumers will be required to pass credentials to the target line of business system.</span></span> <span data-ttu-id="db788-104">この機能を提供するには、WCF サービスの動作を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db788-104">To provide this functionality, you will need to provide a WCF service behavior.</span></span>  
  
 <span data-ttu-id="db788-105">次のコード例では、サービスの動作を派生させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="db788-105">The following example code demonstrates how to derive a service behavior.</span></span> <span data-ttu-id="db788-106">アダプターに、アダプターのコンシューマーから取得した資格情報を委任します。</span><span class="sxs-lookup"><span data-stu-id="db788-106">It delegates the credentials obtained from the consumer of the adapter to the adapter.</span></span> <span data-ttu-id="db788-107">アダプターは、資格情報を認証するのに基幹業務プロトコルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db788-107">The adapter then must use line-of-business protocols to authenticate the credentials.</span></span> <span data-ttu-id="db788-108">資格情報が認証されると、サービスが基幹業務アプリケーションからの着信イベントのリッスンを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="db788-108">Once the credentials are authenticated, the service can start listening for incoming events from the line of business application.</span></span>  
  
```  
/// <summary>  
/// This class derives from a WCF service behavior.  It is used in the inbound scenario  
/// for the Inbound Service to pass the line-of-business credentials to the adapter using  
/// WCF ClientCredentials class.  
/// </summary>  
public class InboundClientCredentialsServiceBehavior : ClientCredentials, IServiceBehavior  
{  
    public InboundClientCredentialsServiceBehavior() { }  
  
    public InboundClientCredentialsServiceBehavior(InboundClientCredentialsServiceBehavior other)  
         : base(other)  
    {  
    }  
  
    #region IServiceBehavior Members  
  
    public void AddBindingParameters(ServiceDescription serviceDescription, System.ServiceModel.ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
    {  
        bindingParameters.Add(this);  
    }  
  
    public void ApplyDispatchBehavior(ServiceDescription serviceDescription, System.ServiceModel.ServiceHostBase serviceHostBase)  
    {  
    }  
  
    public void Validate(ServiceDescription serviceDescription, System.ServiceModel.ServiceHostBase serviceHostBase)  
    {  
    }  
  
    #endregion  
  
    protected override ClientCredentials CloneCore()  
    {  
        return new InboundClientCredentialsServiceBehavior(this);  
    }  
}  
```  
  
 <span data-ttu-id="db788-109">次のコード例では、サービスの動作を使用して、アダプターに資格情報を渡す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="db788-109">The following example code shows how to use the service behavior to pass credentials to the adapter.</span></span>  
  
```  
// Create a ServiceHost for the EchoServiceImpl type  
// and use the base address from app.config  
ServiceHost host = new ServiceHost(typeof(EchoServiceImpl));  
  
// Set service behavior to pass the line-of-business credentials.  
InboundClientCredentialsServiceBehavior credentialsBehavior = new InboundClientCredentialsServiceBehavior();  
credentialsBehavior.UserName.UserName = "username";  
credentialsBehavior.UserName.Password = "****";  
host.Description.Behaviors.Add(credentialsBehavior);  
  
// Open the ServiceHost to start listening for messages  
host.Open();  
  
Console.WriteLine("The service is ready.");  
Console.WriteLine("Press <ENTER> to terminate service.");  
Console.ReadLine();  
  
// Close the ServiceHost  
host.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="db788-110">参照</span><span class="sxs-lookup"><span data-stu-id="db788-110">See Also</span></span>  
 [<span data-ttu-id="db788-111">WCF LOB Adapter SDK を使用して、開発のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="db788-111">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)