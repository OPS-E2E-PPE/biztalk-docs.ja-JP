---
title: WCF サービス モデルを使用して SAP で受信 tRFC の呼び出しを受け取る |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving inbound using the WCF service model
- WCF service model, receiving inbound tRFC calls
ms.assetid: 02dc282b-b659-466a-8bd1-f400a05f71ec
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fb2091d0701831985a1975aa33bd5ecb667b443
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217858"
---
# <a name="receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SAP で受信 tRFC の呼び出しを受信します。
使用することができます、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP から受信 tRFC の呼び出しを受信するトランザクションの RFC (tRFC) サーバーとして。 受信の tRFCs の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]同じ SAP 論理単位での作業 (LUW) 複数 tRFCs をサポートしています。  
  
 このトピックのセクションは、WCF サービス モデルで tRFC サーバーとして、アダプターを使用する方法に関する情報を提供します。  
  
 詳細についてを使用してを見つけることができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以下のトピックで tRFC サーバーとして。  
  
-   TRFCs のサポートの概要については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。 続行する前に、このトピックの内容をお読みください。  
  
-   TRFC サーバー操作のメッセージ スキーマの詳細については、次を参照してください。 [SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。  
  
## <a name="the-wcf-service-contract-for-a-trfc"></a>A tRFC の WCF サービス コントラクト  
 使用する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を SAP システムから受信する tRFCs の WCF サービス コントラクトを生成します。 受信 tRFC は受信 RFC 用に生成するときと同様に生成されるコントラクト点が異なります。  
  
-   tRFC 操作は、TRFC ノードの下に表示されます。  
  
-   着信 tRFCs に対して生成される WCF サービス コントラクト (インターフェイス) を"Trfc"と呼びます。 サービス ホストにサービス エンドポイントを追加する場合は、このインターフェイスを指定する必要があります。 これは、もインターフェイスを WCF サービスを実装する必要があります。  
  
    ```  
    public interface Trfc {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Trfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
        [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD/response")]  
        Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
    }  
    ```  
  
-   TRFC 操作の要求メッセージ コントラクトには、GUID パラメーターがあります。 これは、SAP TID、tRFC 用にマップされる GUID です。 TRFC サーバーの操作では、アダプターは、コミット、ロールバック、および、この GUID を明示的に使用する理由がないように、SAP システムによって TID を確認するためのすべての呼び出しを管理します。 ただしから SAP TID を取得する使用することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を呼び出して**SapAdapterUtilities.ConvertGuidToTid**です。 SAP システムで問題のトラブルシューティングに役立つことができます。  
  
    ```  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
    [System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADD", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Trfc/", IsWrapped=true)]  
    public partial class Z_RFC_MKD_ADDRequest {  
  
        ...  
  
        public Z_RFC_MKD_ADDRequest(string DEST, System.Nullable<int> X, System.Nullable<int> Y, System.Guid TransactionalRfcOperationIdentifier) {  
            this.DEST = DEST;  
            this.X = X;  
            this.Y = Y;  
            this.TransactionalRfcOperationIdentifier = TransactionalRfcOperationIdentifier;  
        }  
    }  
  
    ```  
  
## <a name="how-do-i-enable-the-adapter-to-act-as-a-trfc-server"></a>TRFC サーバーとして、アダプター操作を行うことが有効する方法  
 TRFC サーバーとして機能するアダプターを有効にするを設定する必要があります、 **TidDatabaseConnectionString** TID データベースへの接続文字列にプロパティを連結します。 これは、サービス ホストを開く前に行う必要があります。 これは、アダプターが各 tRFC の SAP トランザクション ID (TID) を格納するデータベースです。 このバインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
## <a name="how-do-i-enlist-in-the-transaction-for-inbound-trfcs"></a>受信 tRFCs のトランザクションに参加する方法は?  
 SAP 論理単位の作業 (LUW) は、複数の tRFCs を含めることができます。 SAP システムで、LUW は一意なトランザクション ID (TID) によって識別されます。 アダプターは、SAP システムには、アダプターで tRFC の呼び出しが起動されるが使用されている Tid の各コミットできるトランザクションを作成します。 SAP システムがアダプター; tRFC を呼び出す場合アダプターは、SAP TID をサービスに関連付けられているトランザクションをフローします。 操作メソッド内から、そのアンビエント トランザクションとは、このトランザクションにアクセスできます。 このアンビエント トランザクションに参加させることで、操作で実行されるアクションは、SAP LUW に参加できます。  
  
 操作メソッド内のアンビエント トランザクションに参加させ、する必要があります。  
  
1.  操作を使用してメソッドに注釈を付ける、 **TransactionScopeRequired**のプロパティ、 **OperationBehavior**属性。 これにより、WCF 操作の内部から、そのアンビエント トランザクションへのアクセスをすることがなります。  
  
2.  トランザクションのスコープを作成する操作を使用してメソッドに注釈を付けるか、 **TransactionAutoComplete**のプロパティ、 **OperationBehavior**属性または明示的を使用して、 **TransactionScope**操作メソッドの内部です。  
  
 次の例では、2 つの操作を実装するサービスを示します。 両方の操作方法が付けられて、 **TransactionScopeRequired**アンビエント トランザクションにアクセスするプロパティです。  
  
-   **Z_TRFC_EXAMPLE1**を使用して、トランザクションに明示的に参加する**TransactionScope**オブジェクト。  
  
-   **Z_TRFC_EXAMPLE2**注釈が付いて、 **TransactionAutoComplete**トランザクションに参加するプロパティ  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, UseSynchronizationContext = false)]  
class Z_Example_ServiceContractClass : Trfc  
{  
  
    // This operation method explicitly creates a TransactionScope to enlist in the ambient transaction  
    // You must explictly call ts.Complete to complete the transaction before you return from the operation  
    // Otherwise the transaction is aborted.  
    // You can throw an exception or return without calling ts.complete to abort the transacation  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public Z_TRFC_EXAMPLE1Response Z_TRFC_EXAMPLE1(Z_TRFC_EXAMPLE1Request request)  
    {  
        using (TransactionScope ts = new TransactionScope(TransactionScopeOption.Required))  
        {  
            // Process tRFC  
  
            ...  
  
            Z_TRFC_EXAMPLE1Response response = new Z_TRFC_EXAMPLE1Response();  
            response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
            return response;  
            //since there is no ts.Complete(), this is equivalent to a rollback.  
        }  
    }  
  
    // This operation method sets the TransactionAutoComplete property of the OperationBehavior attribute  
    // to enlist in the transaction. There is no need to explictly create a TransactionScope in the code.  
    // If the method returns with no unhandled exceptions, the transaction completes; otherwise it aborts  
    // You can throw an exception to abort the transaction.  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public Z_TRFC_EXAMPLE2Response Z_TRFC_EXAMPLE2(Z_TRFC_EXAMPLE2Request request)  
    {  
        // Process tRFC  
  
        ...  
  
        Z_TRFC_EXAMPLE2Response response = new Z_TRFC_EXAMPLE2Response();  
        response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
        return response;  
        //if there is no unhandled exception, the transaction completes when the operation returns.  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)