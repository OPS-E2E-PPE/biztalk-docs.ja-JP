---
title: インターセプター OnEvent 要素 |Microsoft Docs
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
ms.openlocfilehash: 1c849da92941690b7987cd2aff2f1d10714142b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381941"
---
# <a name="interceptor-onevent-element"></a>インターセプタ OnEvent 要素
**OnEvent**要素が外側の BAM アクティビティにマップされている実際のイベントについて説明します。  
  
## <a name="format"></a>形式  
 `OnEvent`要素には、イベント フィルタ、関連付け ID を指定する子要素が含まれていて、必要に応じて、データの参照を更新するには、どのデータと継続トークンです。  
  
### <a name="attributes"></a>属性  
  
|属性名|説明|  
|--------------------|-----------------|  
|名前|このイベントのユーザー定義名。|  
|ソース|イベントの名前に表示されるソース、 **EventSource**要素。|  
|IsBegin|イベントが新しい BAM アクティビティの先頭であるかどうかを示すブール値 (`true`) かどうか (`false`)。|  
|IsEnd|イベントが BAM アクティビティの末尾かどうかを示すブール値 (`true`) かどうか (`false`)。|  
  
### <a name="child-elements"></a>子要素  
  
|実行状態|説明|  
|----------------------|-----------------|  
|Assert|特定の条件にイベントを制限する方法を提供します。|  
|CorrelationID|相関 ID (アクティビティ インスタンス ID) を指定します。|  
|ContinuationToken|継続トークン、将来のイベントと同じアクティビティになることによって使用される関連付け ID を指定します。|  
|更新|イベントから抽出し、BAM アクティビティをインポートするデータを指定します。|  
|リファレンス|BAM アクティビティにリレーションシップを追加します。|  
  
## <a name="remarks"></a>コメント  
  
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
  
 この例で、一般的なは**OnEvent** WCF サービスのブロック。  
  
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
  
-   [[フィルター]](../core/filter.md)  
  
-   [CorrelationID](../core/correlationid.md)  
  
-   [ContinuationToken](../core/continuationtoken.md)  
  
-   [リファレンス](../core/reference.md)  
  
-   [Update](../core/update2.md)  
  
## <a name="see-also"></a>参照  
 [インターセプター構成ファイルの構造](../core/structure-of-an-interceptor-configuration-file.md)