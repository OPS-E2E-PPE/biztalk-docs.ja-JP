---
title: インターセプタ OnEvent 要素 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d684ac8e-61bc-410b-97a2-6fd3549e0d97
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6fb70b2536dbf5db5b0abc03bc194de154b4317
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257610"
---
# <a name="interceptor-onevent-element"></a>インターセプタ OnEvent 要素
**OnEvent**要素が外側の BAM アクティビティにマップされている実際のイベントについて説明します。  
  
## <a name="format"></a>Format  
 `OnEvent` 要素には、イベント フィルタ、関連付け ID を指定する子要素が含まれています。オプションで、更新するデータ、参照データ、継続トークンを指定する子要素が含まれていることもあります。  
  
### <a name="attributes"></a>属性  
  
|属性名|Description|  
|--------------------|-----------------|  
|名前|このイベントのユーザー定義の名前です。|  
|ソース|イベントの名前に表示されるソース、 **EventSource**要素。|  
|IsBegin|イベントが新しい BAM アクティビティを開始するか (`true`)、開始しないか (`false`) を示すブール値です。|  
|IsEnd|イベントが BAM アクティビティを終了するか (`true`)、終了しないか (`false`) を示すブール値です。|  
  
### <a name="child-elements"></a>子要素  
  
|実行状態|Description|  
|----------------------|-----------------|  
|[フィルター]|イベントを特定の条件に限定する方法を提供します。|  
|CorrelationID|関連付け ID (アクティビティ インスタンス ID) を指定します。|  
|ContinuationToken|継続トークンを指定します。これは、将来のイベントにおいて、同じアクティビティ インスタンスに使用される関連付け ID です。|  
|Update|イベントから抽出して BAM アクティビティにインポートするデータを指定します。|  
|リファレンス|BAM アクティビティにリレーションシップを追加します。|  
  
## <a name="remarks"></a>解説  
  
## <a name="example"></a>例  
 次の例は、一般的な**OnEvent** WF のブロック。  
  
```  
<ic:OnEvent Name="BeginAct" IsBegin="true" Source="ResWF">  
  <ic:Filter>  
    <ic:Expression>  
      <wf:Operation Name="GetActivityName"/>  
      <ic:Operation Name="Constant">  
        <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name="Equals"/>  
      <wf:Operation Name="GetActivityEvent"/>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Closed</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name="Equals"/>  
      <ic:Operation Name="And"/>  
    </ic:Expression>  
  </ic:Filter>  
  <ic:CorrelationID>  
    <ic:Expression>  
      <wf:Operation Name="GetContextProperty">  
        <wf:Argument>InstanceId</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:CorrelationID>  
  <ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
    <ic:Expression>  
      <wf:Operation Name="GetContextProperty">  
        <wf:Argument>EventTime</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  <ic:Update DataItemName="FoodItem" Type="NVARCHAR">  
    <ic:Expression>  
      <wf:Operation Name="GetWorkflowProperty">  
        <wf:Argument>foodItem</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:Update>  
</ic:OnEvent>  
```  
  
 この例は、一般的な**OnEvent** WCF サービスをブロックします。  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="AuthorizationRequestService" Source="ESCreditCardService">  
  <ic:Filter>  
    <ic:Expression>  
      <wcf:Operation Name="GetServiceContractCallPoint"/>  
      <ic:Operation Name ="Constant">  
        <ic:Argument>ServiceRequest</ic:Argument>  
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
      <ic:Operation Name="Constant">  
        <ic:Argument>ServiceRequest</ic:Argument>  
      </ic:Operation>  
    </ic:Expression>  
  </ic:CorrelationID>  
  <ic:Update DataItemName="Name" Type="NVARCHAR">  
    <ic:Expression>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:creditCard/creditcard:FirstName</wcf:Argument>  
      </wcf:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:creditCard/creditcard:LastName</wcf:Argument>  
      </wcf:Operation>  
      <ic:Operation Name ="Concatenate"/>  
    </ic:Expression>  
  </ic:Update>  
</ic:OnEvent>  
```  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Assert](../core/filter.md)  
  
-   [関連付け Id](../core/correlationid.md)  
  
-   [ContinuationToken](../core/continuationtoken.md)  
  
-   [リファレンス](../core/reference.md)  
  
-   [Update](../core/update2.md)  
  
## <a name="see-also"></a>参照  
 [インターセプタ構成ファイルの構造](../core/structure-of-an-interceptor-configuration-file.md)