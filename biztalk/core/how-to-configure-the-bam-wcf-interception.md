---
title: BAM WCF インターセプションを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d85aa130-3219-4df1-8974-a44a51a15002
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90577a73abc0291635bf4b7d9bad34a11d1f806
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249210"
---
# <a name="how-to-configure-the-bam-wcf-interception"></a>BAM WCF インターセプションを構成する方法
BAM を WCF インターセプション用に構成するには、イベント ソースに対する正しいアセンブリ マニフェストにアクセスするようにインターセプター構成ファイルを変更する必要があります。  
  
 正しく書式設定された指定する必要があります、イベントを構成する際、 [XPath](../core/xpath.md)アクションの式。  
  
 適切な形式を作成することができます[XPath](../core/xpath.md)メッセージが含まれるサンプル WCF ログを生成するために WCF トレースとアプリケーションの実行を有効にすると、インターセプタ構成で使用する式。 使用することができます、 **Microsoft Service Trace Viewer** (SvcTraceViewer.exe) をログを表示して、メッセージを展開します。 このビューアは、WCF SDK に付属しています。 必要な[XPath](../core/xpath.md)式は、メッセージ ベースの形式し、インターセプター構成に適用します。  
  
 BAM WCF インターセプションを構成するときには、machine.config ファイルで使用されている動作拡張機能が、受信場所のカスタム動作構成で使用されている拡張機能に一致することが不可欠です。 machine.config ファイルで構成されている受信場所の拡張子の名前を変更すると、動作が読み込みに失敗します。 また、受信場所の構成 UI が失敗します。  
  
 クラスタ化されたシナリオでは、カスタム動作は一度だけ構成されるため、クラスタ内のコンピュータ上のすべての machine.config ファイルで同じファイル名拡張子を指定する必要があります。  
  
### <a name="to-set-the-manifest"></a>マニフェストを設定するには  
  
1.  インターセプション構成内の EventSource のマニフェストに、「Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid, Microsoft.BizTalk.Adapter.Wcf.Runtime, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35」を設定します。  
  
    > [!NOTE]
    >  使用するサービスと受信ポートの種類に基づいてインターフェイスが変更されます。 次の表に従って、使用するポートの種類を反映するようにマニフェスト行を変更します。  
  
    |ポートの種類|新しく使用する機能|  
    |---------------|---------|  
    |双方向ポート|ITwoWayAsync|  
    |本質的に 2 つの双方向のバインドを持つ一方向のポート (たとえば HTTP)。|ITwoWayAsyncVoid|  
    |トランザクションを使用する、本質的に 2 つの双方向のバインドを持つ一方向のポート。|ITwoWayAsyncVoidTxn|  
    |一方向のバインド (たとえば MSMQ)。|IOneWayAsync|  
    |トランザクションを使用する一方向のバインド。|IOneWayAsyncTxn|  
  
    > [!IMPORTANT]
    >  使用する代わりに、フィルターで、 [GetOperationName](../core/getoperationname.md)操作、次の例で強調表示されている XPath 操作を使用します。 汎用の契約では、すべてのメッセージが汎用の操作に到着し、そこでメッセージ自身 (Action 属性) に基づいて個別の操作にルーティングされます。  
  
2.  この時点では操作名は常に同じです。 WCF アダプタ (汎用の契約を使用) の場合、メソッド BizTalkSubmit が使用されます。 GetOperationName の代わりに Action ノードに対する XPath を使用して操作名を取得できます。 その後、操作名に対してフィルタを適用できます。  
  
## <a name="sample-interceptor-configurations"></a>インターセプタ構成のサンプル  
 このサンプルは、WCF アダプタの ServiceRequest と ServiceReply の使用方法を示します。 強調表示されたセクションで、 [XPath](../core/xpath.md)フィルターを使用せずに操作を適用するアクションの式が使用される[GetOperationName](../core/getoperationname.md)です。 応答に対してフィルタを適用することもできますが、ITwoWayAsync の場合だけです。 その他すべてのインターフェイスは、何も返さないか void を返します。  
  
### <a name="servicerequest"></a>ServiceRequest  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="WCFServiceRequest" Source="WCFService">  
      <ic:Filter>  
        <ic:Expression>  
          <wcf:Operation Name="GetServiceContractCallPoint"/>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>ServiceRequest</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
          <wcf:Operation Name ="XPath">  
            <wcf:Argument>//s:Header/a:Action</wcf:Argument>  
          </wcf:Operation>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>Operation1</ic:Argument>  
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
  
      <ic:Update DataItemName ="Activity Date" Type ="DATETIME">  
        <ic:Expression>  
          <wcf:Operation Name ="GetContextProperty">  
            <wcf:Argument>EventTime</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
      <ic:Update DataItemName ="Source" Type ="NVARCHAR">  
        <ic:Expression>  
          <ic:Operation Name="Constant">  
            <ic:Argument>WcfAdapter_ServiceRequest</ic:Argument>  
          </ic:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
    </ic:OnEvent>  
```  
  
### <a name="servicereply"></a>ServiceReply  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="WCFServiceReply" Source="WCFService">  
      <ic:Filter>  
        <ic:Expression>  
          <wcf:Operation Name="GetServiceContractCallPoint"/>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>ServiceReply</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
        </ic:Expression>  
      </ic:Filter>  
  
      <ic:CorrelationID>  
        <ic:Expression>  
          <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
        </ic:Expression>  
      </ic:CorrelationID>  
  
      <ic:Update DataItemName ="Activity Date" Type ="DATETIME">  
        <ic:Expression>  
          <wcf:Operation Name ="GetContextProperty">  
            <wcf:Argument>EventTime</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
      <ic:Update DataItemName ="Name" Type ="NVARCHAR">  
        <ic:Expression>  
          <ic:Operation Name="Constant">  
            <ic:Argument>WcfAdapter_ServiceReply</ic:Argument>  
          </ic:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
    </ic:OnEvent>  
```  
  
## <a name="see-also"></a>参照  
 [BAM データを受信する WCF アダプタの構成](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)