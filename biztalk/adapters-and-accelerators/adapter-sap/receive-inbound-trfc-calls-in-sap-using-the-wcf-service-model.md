---
title: WCF サービス モデルを使用して SAP で受信 tRFC 呼び出しを受け取る |Microsoft Docs
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
ms.openlocfilehash: cd54bdfd3a772912b4d2687ab1ce9e715e7fbab9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013331"
---
# <a name="receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SAP で受信 tRFC 呼び出しを受信します。
使用することができます、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP から受信 tRFC 呼び出しを受信するトランザクションの RFC (tRFC) サーバーとして。 受信 Trfc、用、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作業 (LUW) の同じ SAP の論理ユニットに複数の Trfc をサポートしています。  
  
 このトピックのセクションでは、WCF サービス モデルで tRFC サーバーとして、アダプターを使用する方法についてを説明します。  
  
 使用に関する詳細についてを見つけることができます、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC サーバーで、次のトピックとして。  
  
- Trfc のサポートの概要については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)します。 このトピックでは、続行する前にお読みください。  
  
- TRFC サーバー操作のメッセージ スキーマの詳細については、[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)を参照してください。  
  
## <a name="the-wcf-service-contract-for-a-trfc"></a>TRFC の WCF サービス コントラクト  
 使用する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または SAP システムから受信する Trfc の WCF サービス コントラクトを生成する ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)。 契約の受信の tRFC は受信 RFC 用に生成するときと同様に生成された点が異なります。  
  
- tRFC 操作は、TRFC ノードの下に表示されます。  
  
- 受信 Trfc に対して生成された WCF サービス コントラクト (インターフェイス) は、"Trfc"という名前です。 サービス ホストにサービス エンドポイントを追加すると、このインターフェイスを指定する必要があります。 これも、WCF サービスを実装する必要があるインターフェイスです。  
  
  ```  
  public interface Trfc {  
  
      // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Trfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
      [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD/response")]  
      Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
  }  
  ```  
  
- TRFC 操作の要求メッセージ コントラクトでは、GUID パラメーターがあります。 これは、tRFC の SAP TID にマップされる GUID です。 TRFC サーバーの操作では、アダプターは、コミット、ロールバック、および、この GUID を明示的に使用する理由がないため、SAP システムによって TID を確認するためのすべての呼び出しを管理します。 ただしから SAP TID を取得して使用することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呼び出して**SapAdapterUtilities.ConvertGuidToTid**します。 これは、SAP システムの問題を解決するために役立ちます。  
  
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
  
## <a name="how-do-i-enable-the-adapter-to-act-as-a-trfc-server"></a>TRFC サーバーとして、アダプター操作を行うことをする方法  
 TRFC サーバーとして機能するアダプターを有効に設定する必要があります、 **TidDatabaseConnectionString** TID データベースの接続文字列プロパティにバインドします。 これは、サービス ホストを開く前に行う必要があります。 これは、アダプターが各 tRFC の SAP トランザクション ID (TID) を格納するデータベースです。 このバインドのプロパティの詳細については、[mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。  
  
## <a name="how-do-i-enlist-in-the-transaction-for-inbound-trfcs"></a>受信 Trfc のトランザクションに参加させる方法をでしょうか。  
 SAP 論理単位の作業 (LUW) は、複数の Trfc を含めることができます。 SAP システムで、LUW は一意のトランザクション ID (TID) によって識別されます。 アダプターでは、アダプターの tRFC の呼び出しを呼び出すときに、SAP システムを使用している Tid ごとコミット トランザクションを作成します。 SAP システムは、アダプターの tRFC を呼び出すときにアダプターは、サービスに SAP TID に関連付けられているトランザクションをフローします。 このトランザクションをアンビエント トランザクションとしては、操作メソッドの内部にアクセスできます。 このアンビエント トランザクションへの参加、によって、操作で実行されるアクションは、SAP LUW に参加できます。  
  
 操作メソッドのアンビエント トランザクションに参加して、次の操作をする必要があります。  
  
1. 操作メソッドに注釈を付け、 **TransactionScopeRequired**のプロパティ、 **OperationBehavior**属性。 これにより、WCF から、操作内でのアンビエント トランザクションへのアクセスをすることが。  
  
2. トランザクション スコープを作成するかの操作メソッドの注釈を付けることによって、 **TransactionAutoComplete**のプロパティ、 **OperationBehavior**属性または明示的を使用して、 **TransactionScope**操作メソッドの内部。  
  
   次の例では、2 つの操作を実装するサービスを示します。 両方の操作メソッドの注釈が付けられて、 **TransactionScopeRequired**アンビエント トランザクションにアクセスするプロパティ。  
  
-   **Z_TRFC_EXAMPLE1**を使用して、トランザクションに明示的に参加する**TransactionScope**オブジェクト。  
  
-   **Z_TRFC_EXAMPLE2**で注釈が、 **TransactionAutoComplete**プロパティは、トランザクションに参加するには  
  
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
[WCF サービス モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)