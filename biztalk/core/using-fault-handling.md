---
title: エラー処理の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc793386-d2ec-4e02-9283-3237f65c9e01
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90cb589894b9bb2166cf701866575092da53540e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015123"
---
# <a name="using-fault-handling"></a><span data-ttu-id="a45c0-102">エラー処理の使用</span><span class="sxs-lookup"><span data-stu-id="a45c0-102">Using Fault Handling</span></span>
<span data-ttu-id="a45c0-103">中に[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]しない限り、エラーの例外メッセージの処理は、クライアントに返されません、 **FaultException** (または subtype) がスローされますまたは**FaultContract**実装されます。</span><span class="sxs-lookup"><span data-stu-id="a45c0-103">During [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] fault handling an exception message is not returned to the client unless a **FaultException** (or a subtype) is thrown or a **FaultContract** is implemented.</span></span> <span data-ttu-id="a45c0-104">したがって、このようなシナリオでは、エラー メッセージ自体からデータを追跡することしかできません。</span><span class="sxs-lookup"><span data-stu-id="a45c0-104">So you can only track data from the fault message itself in these scenarios.</span></span> <span data-ttu-id="a45c0-105">コールバック実装では、例外が自動的に両方は、エラー メッセージとして返されます**ServerFault**と**ClientFault**ポイントを追跡します。</span><span class="sxs-lookup"><span data-stu-id="a45c0-105">An exception in callback implementations automatically comes back as a fault message for both **ServerFault** and **ClientFault** track points.</span></span> <span data-ttu-id="a45c0-106">ただし、どのような場合でも、一般的なメッセージを示す汎用エラーが戻されます。</span><span class="sxs-lookup"><span data-stu-id="a45c0-106">However, it will always return a generic fault with a generic message.</span></span> <span data-ttu-id="a45c0-107">WCF エラー コントラクトの詳細については、[ http://go.microsoft.com/fwlink/?LinkId=83132](http://go.microsoft.com/fwlink/?LinkId=83132)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a45c0-107">For more information about WCF fault contracts, see [http://go.microsoft.com/fwlink/?LinkId=83132](http://go.microsoft.com/fwlink/?LinkId=83132).</span></span>  
  
 <span data-ttu-id="a45c0-108">エラー追跡ポイントを使用して、定数とコンテキスト プロパティを追跡することもできます。</span><span class="sxs-lookup"><span data-stu-id="a45c0-108">You can also track constants and context properties through the fault track points.</span></span>  
  
 <span data-ttu-id="a45c0-109">使用してエラー例外の詳細が返される場合、 **IncludeExceptionDetailInFaults**属性を XPath から実際の例外メッセージを抽出します。</span><span class="sxs-lookup"><span data-stu-id="a45c0-109">If exception details are returned in faults using the **IncludeExceptionDetailInFaults** attribute, you extract the actual exception message through the XPath.</span></span>  
  
 <span data-ttu-id="a45c0-110">エラー処理がで定義されているエラー追跡ポイントによって提供される[GetServiceContractCallPoint](../core/getservicecontractcallpoint.md):</span><span class="sxs-lookup"><span data-stu-id="a45c0-110">Fault handling is provided by the fault track points defined in [GetServiceContractCallPoint](../core/getservicecontractcallpoint.md):</span></span>  
  
- <span data-ttu-id="a45c0-111">ServiceFault</span><span class="sxs-lookup"><span data-stu-id="a45c0-111">ServiceFault</span></span>  
  
- <span data-ttu-id="a45c0-112">ClientFault</span><span class="sxs-lookup"><span data-stu-id="a45c0-112">ClientFault</span></span>  
  
- <span data-ttu-id="a45c0-113">CallbackFault</span><span class="sxs-lookup"><span data-stu-id="a45c0-113">CallbackFault</span></span>  
  
  <span data-ttu-id="a45c0-114">エラー追跡ポイントを使用する場合、トランザクションベースのシナリオで行われた操作であっても、エラー データは必ず保持されます。</span><span class="sxs-lookup"><span data-stu-id="a45c0-114">When using these fault track points, fault data is always persisted, even when operating in a transaction-based scenario.</span></span> <span data-ttu-id="a45c0-115">トランザクション整合性は、エラーではないすべての追跡データ上で維持されます。エラーへの応答として、エラーではないすべての追跡データはロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="a45c0-115">Transactional integrity is maintained on all non-fault tracked data and non-fault tracked data is rolled back as a response to the fault.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a45c0-116">これらの追跡ポイントの応答パスに適用され、ServiceReply、ClientReply、および CallbackReply サービス コントラクト呼び出しポイントによって提供されるだけに適用[GetServiceContractCallPoint](../core/getservicecontractcallpoint.md)します。</span><span class="sxs-lookup"><span data-stu-id="a45c0-116">These track points are applied to the reply path and apply only to the ServiceReply, ClientReply and CallbackReply service contract call points provided by [GetServiceContractCallPoint](../core/getservicecontractcallpoint.md).</span></span>  
  
## <a name="fault-configuration-sample"></a><span data-ttu-id="a45c0-117">エラー構成サンプル</span><span class="sxs-lookup"><span data-stu-id="a45c0-117">Fault Configuration Sample</span></span>  
 <span data-ttu-id="a45c0-118">次のサンプルに例外メッセージを追跡する**ServiceFault**サービスがスローした場合、 **FaultException**で、 **AuthorizationServiceFault**イベント。それ以外の場合で、操作によって返されるブール式を追跡、 **AuthorizationServiceReply**イベント。</span><span class="sxs-lookup"><span data-stu-id="a45c0-118">The following sample demonstrates tracking the exception message on a **ServiceFault** when the service throws a **FaultException** in the **AuthorizationServiceFault** event; otherwise it tracks the Boolean expression returned by the operation in the **AuthorizationServiceReply** event.</span></span> <span data-ttu-id="a45c0-119">いずれか、 **AuthorizationServiceReply** OnEvent または**AuthorizationServiceFault** OnEvent が永続化します。</span><span class="sxs-lookup"><span data-stu-id="a45c0-119">Either the **AuthorizationServiceReply** OnEvent or the **AuthorizationServiceFault** OnEvent is persisted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a45c0-120">このサンプルを実装すると、ServiceReply 追跡ポイントと ServiceFault 追跡ポイントが相互に排他的であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="a45c0-120">The implementation of this sample demonstrates the mutual exclusivity of the ServiceReply and ServiceFault trackpoints.</span></span>  
  
```  
<ic:OnEvent IsBegin ="true" IsEnd="false" Name="AuthorizationServiceReply" Source="ESCreditCardService">  
  
  <ic:Filter>  
    <ic:Expression>  
      <wcf:Operation Name="GetServiceContractCallPoint"/>  
      <ic:Operation Name ="Constant">  
        <ic:Argument>ServiceReply</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals"/>  
      <wcf:Operation Name="GetOperationName" />  
      <ic:Operation Name="Constant">  
        <ic:Argument>AuthorizeWithDataContract</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals" />  
      <ic:Operation Name ="And" />  
    </ic:Expression>  
  </ic:Filter>  
  
  <ic:CorrelationID>  
    <ic:Expression>  
      <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
    </ic:Expression>  
  </ic:CorrelationID>  
  
  <ic:Update DataItemName="Status" Type="NVARCHAR">  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Success</ic:Argument>  
      </ic:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
  <ic:Update DataItemName="Result" Type="NVARCHAR">  
    <ic:Expression>  
      <wcf:Operation Name ="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:AuthorizeWithDataContractResult</wcf:Argument>  
      </wcf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
  <ic:Update DataItemName ="Service Call Date" Type ="DATETIME">  
    <ic:Expression>  
      <wcf:Operation Name ="GetContextProperty">  
        <wcf:Argument>EventTime</wcf:Argument>  
      </wcf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
</ic:OnEvent>  
  
<ic:OnEvent IsBegin ="true" IsEnd="false" Name="AuthorizationServiceFault" Source="ESCreditCardService">  
  
  <ic:Filter>  
    <ic:Expression>  
      <wcf:Operation Name="GetServiceContractCallPoint"/>  
      <ic:Operation Name ="Constant">  
        <ic:Argument>ServiceFault</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals"/>  
      <wcf:Operation Name="GetOperationName" />  
      <ic:Operation Name="Constant">  
        <ic:Argument>AuthorizeWithDataContract</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals" />  
      <ic:Operation Name ="And" />  
    </ic:Expression>  
  </ic:Filter>  
  
  <ic:CorrelationID>  
    <ic:Expression>  
      <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
    </ic:Expression>  
  </ic:CorrelationID>  
  
  <ic:Update DataItemName="Status" Type="NVARCHAR">  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Fault</ic:Argument>  
      </ic:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
      <ic:Update DataItemName="Source" Type="NVARCHAR">  
        <ic:Expression>  
          <wcf:Operation Name ="XPath">  
            <wcf:Argument>//s:Body/Fault/Reason/Text</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
  <ic:Update DataItemName ="Service Call Date" Type ="DATETIME">  
    <ic:Expression>  
      <wcf:Operation Name ="GetContextProperty">  
        <wcf:Argument>EventTime</wcf:Argument>  
      </wcf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  
</ic:OnEvent>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a45c0-121">参照</span><span class="sxs-lookup"><span data-stu-id="a45c0-121">See Also</span></span>  
 [<span data-ttu-id="a45c0-122">BAM データを受信するための WCF アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="a45c0-122">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)