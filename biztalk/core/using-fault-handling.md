---
title: "エラー処理の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc793386-d2ec-4e02-9283-3237f65c9e01
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00547917da65253123cb2067715a09633547eb4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-fault-handling"></a>エラー処理の使用
中に[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]しない限り、エラー、例外メッセージの処理はクライアントに返されません、 **FaultException** (または subtype) がスローされますまたは**FaultContract**は実装されています。 したがって、このようなシナリオでは、エラー メッセージ自体からデータを追跡することしかできません。 コールバックの実装で例外が自動的に両方のエラー メッセージとして返さ**ServerFault**と**ClientFault**ポイントを追跡します。 ただし、どのような場合でも、一般的なメッセージを示す汎用エラーが戻されます。 WCF エラー コントラクトの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=83132](http://go.microsoft.com/fwlink/?LinkId=83132)です。  
  
 エラー追跡ポイントを使用して、定数とコンテキスト プロパティを追跡することもできます。  
  
 使用してエラー例外の詳細が返される場合、 **IncludeExceptionDetailInFaults**属性を XPath から実際の例外メッセージを抽出します。  
  
 エラー処理がで定義されているエラー追跡ポイントによって提供される[GetServiceContractCallPoint](../core/getservicecontractcallpoint.md):  
  
-   ServiceFault  
  
-   ClientFault  
  
-   CallbackFault  
  
 エラー追跡ポイントを使用する場合、トランザクションベースのシナリオで行われた操作であっても、エラー データは必ず保持されます。 トランザクション整合性は、エラーではないすべての追跡データ上で維持されます。エラーへの応答として、エラーではないすべての追跡データはロールバックされます。  
  
> [!NOTE]
>  これらの追跡ポイントの応答パスに適用され、ServiceReply、ClientReply、および CallbackReply サービス コントラクト呼び出しポイントによって提供されるにのみ適用[GetServiceContractCallPoint](../core/getservicecontractcallpoint.md)です。  
  
## <a name="fault-configuration-sample"></a>エラー構成サンプル  
 次の例は、例外メッセージの追跡、 **ServiceFault**サービスがスローした場合、 **FaultException**で、 **AuthorizationServiceFault**イベントです。それ以外の場合の操作によって返されるブール式を追跡、 **AuthorizationServiceReply**イベント。 いずれか、 **AuthorizationServiceReply** OnEvent または**AuthorizationServiceFault** OnEvent が永続化します。  
  
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
 [BAM データを受信する WCF アダプタの構成](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)