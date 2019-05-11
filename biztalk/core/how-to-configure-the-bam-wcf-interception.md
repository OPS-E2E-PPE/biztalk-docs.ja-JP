---
title: BAM WCF インターセプションを構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 51eb7a1a5e7fc8ac6c94af3f16051d85dd8731b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341231"
---
# <a name="how-to-configure-the-bam-wcf-interception"></a>BAM WCF インターセプションを構成する方法
で BAM を WCF インターセプションを構成するには、イベント ソースに対する正しいアセンブリ マニフェストにアクセスするインターセプター構成ファイルを変更する必要があります。  
  
 正しく書式設定されたを指定する必要があります、イベントを構成するときに[XPath](../core/xpath.md)アクションの式。  
  
 適切な形式を作成する[XPath](../core/xpath.md)メッセージが含まれるサンプル WCF ログを生成するために WCF トレースとアプリケーションの実行を有効にすると、インターセプター構成に使用する式。 使用することができます、 **Microsoft Service Trace Viewer** (SvcTraceViewer.exe) をログを表示し、メッセージを抽出します。 ビューアーは、WCF SDK に含まれています。 必要な[XPath](../core/xpath.md)式は、メッセージ ベースの形式し、インターセプター構成に適用します。  
  
 BAM WCF インターセプションを構成する場合は、machine.config ファイルで使用されている動作拡張機能が、受信場所のカスタム動作構成で使用される拡張機能と一致することが重要です。 構成の拡張機能の名前を変更するメッセージが表示される場所、machine.config ファイルで読み込みに失敗します。 さらに、受信場所の構成 UI は失敗します。  
  
 クラスタ化されたシナリオでは、することが必要に 1 回だけカスタム動作が構成されているために、クラスター内のコンピューター上のすべての machine.config ファイルは、同じファイル名拡張子を指定します。  
  
### <a name="to-set-the-manifest"></a>マニフェストを設定するには  
  
1.  インターセプション構成内の EventSource のマニフェストを設定 ' Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid、, Microsoft.BizTalk.Adapter.Wcf.Runtime, バージョン =, Culture = neutral, PublicKeyToken = 31bf3856ad364e35'  
  
    > [!NOTE]
    >  使用するサービス/受信ポートの種類に基づいてインターフェイスが変更されます。 次の表に従って、使用するポートの種類を反映するようにマニフェスト行を変更します。  
  
    |ポートの種類|新しく使用する機能|  
    |---------------|---------|  
    |双方向のポート|ITwoWayAsync|  
    |バインドを持つ一方向のポートは、本質的に、2 の 2 つの方法 (HTTP など) です。|ITwoWayAsyncVoid|  
    |バインドを持つ一方向のポートは、本質的に 2 つのトランザクションで双方向です。|ITwoWayAsyncVoidTxn|  
    |1 つの方法 (たとえば、MSMQ) のバインド。|IOneWayAsync|  
    |トランザクションを使用する一方向のバインド。|IOneWayAsyncTxn|  
  
    > [!IMPORTANT]
    >  フィルターで使用する代わりに、 [GetOperationName](../core/getoperationname.md)操作では、次の例で強調表示されている XPath 操作を使用します。 汎用の契約は、すべてのメッセージはメッセージ自身 (Action 属性) に基づいて特定の操作にルーティングされますがこの時点で、汎用の操作に到着します。  
  
2.  操作名が必ず同じこの時点でします。 WCF アダプタ (汎用の契約を使用) する場合は、使用されるメソッドは、BizTalkSubmit を示します。 GetOperationName の代わりにアクション ノードの XPath を使用すると、操作名を取得します。 操作名でフィルター処理できます。  
  
## <a name="sample-interceptor-configurations"></a>インターセプタ構成のサンプル  
 このサンプルでは、WCF アダプタの ServiceRequest と ServiceReply の使用状況を示します。 強調表示されたセクションでは、 [XPath](../core/xpath.md)アクションに式を使用して、操作を使用する代わりにフィルター処理を[GetOperationName](../core/getoperationname.md)します。 同様に、応答が、ITwoWayAsync の場合だけをフィルター処理することができます。 その他のすべてのインターフェイスは、何も返しませんまたはを無効にします。  
  
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
 [BAM データを受信するための WCF アダプターの構成](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)