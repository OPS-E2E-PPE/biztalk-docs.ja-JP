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
# <a name="using-fault-handling"></a>エラー処理の使用
中に[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]しない限り、エラーの例外メッセージの処理は、クライアントに返されません、 **FaultException** (または subtype) がスローされますまたは**FaultContract**実装されます。 したがって、このようなシナリオでは、エラー メッセージ自体からデータを追跡することしかできません。 コールバック実装では、例外が自動的に両方は、エラー メッセージとして返されます**ServerFault**と**ClientFault**ポイントを追跡します。 ただし、どのような場合でも、一般的なメッセージを示す汎用エラーが戻されます。 WCF エラー コントラクトの詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=83132](http://go.microsoft.com/fwlink/?LinkId=83132)します。  
  
 エラー追跡ポイントを使用して、定数とコンテキスト プロパティを追跡することもできます。  
  
 使用してエラー例外の詳細が返される場合、 **IncludeExceptionDetailInFaults**属性を XPath から実際の例外メッセージを抽出します。  
  
 エラー処理がで定義されているエラー追跡ポイントによって提供される[GetServiceContractCallPoint](../core/getservicecontractcallpoint.md):  
  
- ServiceFault  
  
- ClientFault  
  
- CallbackFault  
  
  エラー追跡ポイントを使用する場合、トランザクションベースのシナリオで行われた操作であっても、エラー データは必ず保持されます。 トランザクション整合性は、エラーではないすべての追跡データ上で維持されます。エラーへの応答として、エラーではないすべての追跡データはロールバックされます。  
  
> [!NOTE]
>  これらの追跡ポイントの応答パスに適用され、ServiceReply、ClientReply、および CallbackReply サービス コントラクト呼び出しポイントによって提供されるだけに適用[GetServiceContractCallPoint](../core/getservicecontractcallpoint.md)します。  
  
## <a name="fault-configuration-sample"></a>エラー構成サンプル  
 次のサンプルに例外メッセージを追跡する**ServiceFault**サービスがスローした場合、 **FaultException**で、 **AuthorizationServiceFault**イベント。それ以外の場合で、操作によって返されるブール式を追跡、 **AuthorizationServiceReply**イベント。 いずれか、 **AuthorizationServiceReply** OnEvent または**AuthorizationServiceFault** OnEvent が永続化します。  
  
> [!NOTE]
>  このサンプルを実装すると、ServiceReply 追跡ポイントと ServiceFault 追跡ポイントが相互に排他的であることがわかります。  
  
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
  
## <a name="see-also"></a>参照  
 [BAM データを受信するための WCF アダプターの構成](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)