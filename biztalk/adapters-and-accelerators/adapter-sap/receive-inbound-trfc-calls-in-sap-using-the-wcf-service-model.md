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
# <a name="receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="a47f1-102">WCF サービス モデルを使用して SAP で受信 tRFC 呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="a47f1-102">Receive Inbound tRFC Calls in SAP using the WCF Service Model</span></span>
<span data-ttu-id="a47f1-103">使用することができます、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP から受信 tRFC 呼び出しを受信するトランザクションの RFC (tRFC) サーバーとして。</span><span class="sxs-lookup"><span data-stu-id="a47f1-103">You can use the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as a transactional RFC (tRFC) server to receive inbound tRFC calls from SAP.</span></span> <span data-ttu-id="a47f1-104">受信 Trfc、用、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作業 (LUW) の同じ SAP の論理ユニットに複数の Trfc をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a47f1-104">For inbound tRFCs, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports multiple tRFCs in the same SAP logical unit of work (LUW).</span></span>  
  
 <span data-ttu-id="a47f1-105">このトピックのセクションでは、WCF サービス モデルで tRFC サーバーとして、アダプターを使用する方法についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="a47f1-105">The sections in this topic provide information about how to use the adapter as a tRFC server in the WCF service model.</span></span>  
  
 <span data-ttu-id="a47f1-106">使用に関する詳細についてを見つけることができます、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC サーバーで、次のトピックとして。</span><span class="sxs-lookup"><span data-stu-id="a47f1-106">You can find more information about using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as a tRFC server in the following topics:</span></span>  
  
- <span data-ttu-id="a47f1-107">Trfc のサポートの概要については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="a47f1-107">For an overview of support for tRFCs on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span> <span data-ttu-id="a47f1-108">このトピックでは、続行する前にお読みください。</span><span class="sxs-lookup"><span data-stu-id="a47f1-108">You should read this topic before continuing.</span></span>  
  
- <span data-ttu-id="a47f1-109">TRFC サーバー操作のメッセージ スキーマの詳細については、[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47f1-109">For more information about the message schemas for tRFC server operations, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
## <a name="the-wcf-service-contract-for-a-trfc"></a><span data-ttu-id="a47f1-110">TRFC の WCF サービス コントラクト</span><span class="sxs-lookup"><span data-stu-id="a47f1-110">The WCF Service Contract for a tRFC</span></span>  
 <span data-ttu-id="a47f1-111">使用する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または SAP システムから受信する Trfc の WCF サービス コントラクトを生成する ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)。</span><span class="sxs-lookup"><span data-stu-id="a47f1-111">You use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF service contract for the tRFCs that you want to receive from the SAP system.</span></span> <span data-ttu-id="a47f1-112">契約の受信の tRFC は受信 RFC 用に生成するときと同様に生成された点が異なります。</span><span class="sxs-lookup"><span data-stu-id="a47f1-112">The contract generated for an inbound tRFC is similar to that generated for an inbound RFC except that:</span></span>  
  
- <span data-ttu-id="a47f1-113">tRFC 操作は、TRFC ノードの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a47f1-113">tRFC operations are surfaced under the TRFC node.</span></span>  
  
- <span data-ttu-id="a47f1-114">受信 Trfc に対して生成された WCF サービス コントラクト (インターフェイス) は、"Trfc"という名前です。</span><span class="sxs-lookup"><span data-stu-id="a47f1-114">The WCF service contract (interface) generated for incoming tRFCs is named "Trfc".</span></span> <span data-ttu-id="a47f1-115">サービス ホストにサービス エンドポイントを追加すると、このインターフェイスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a47f1-115">You must specify this interface when you add the service endpoint to the service host.</span></span> <span data-ttu-id="a47f1-116">これも、WCF サービスを実装する必要があるインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="a47f1-116">This is also the interface that your WCF service must implement.</span></span>  
  
  ```  
  public interface Trfc {  
  
      // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Trfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
      [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD/response")]  
      Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
  }  
  ```  
  
- <span data-ttu-id="a47f1-117">TRFC 操作の要求メッセージ コントラクトでは、GUID パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="a47f1-117">The request message contract for TRFC operations has a GUID parameter.</span></span> <span data-ttu-id="a47f1-118">これは、tRFC の SAP TID にマップされる GUID です。</span><span class="sxs-lookup"><span data-stu-id="a47f1-118">This is the GUID that maps to the SAP TID for the tRFC.</span></span> <span data-ttu-id="a47f1-119">TRFC サーバーの操作では、アダプターは、コミット、ロールバック、および、この GUID を明示的に使用する理由がないため、SAP システムによって TID を確認するためのすべての呼び出しを管理します。</span><span class="sxs-lookup"><span data-stu-id="a47f1-119">In tRFC server operations, the adapter manages all calls to commit, rollback, and confirm the TID by the SAP system so there is no reason for you to explicitly use this GUID.</span></span> <span data-ttu-id="a47f1-120">ただしから SAP TID を取得して使用することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呼び出して**SapAdapterUtilities.ConvertGuidToTid**します。</span><span class="sxs-lookup"><span data-stu-id="a47f1-120">However, you can use it to retrieve the SAP TID from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by calling **SapAdapterUtilities.ConvertGuidToTid**.</span></span> <span data-ttu-id="a47f1-121">これは、SAP システムの問題を解決するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a47f1-121">This can be useful to help you troubleshoot issues on the SAP system.</span></span>  
  
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
  
## <a name="how-do-i-enable-the-adapter-to-act-as-a-trfc-server"></a><span data-ttu-id="a47f1-122">TRFC サーバーとして、アダプター操作を行うことをする方法</span><span class="sxs-lookup"><span data-stu-id="a47f1-122">How do I Enable the Adapter to Act as a tRFC Server?</span></span>  
 <span data-ttu-id="a47f1-123">TRFC サーバーとして機能するアダプターを有効に設定する必要があります、 **TidDatabaseConnectionString** TID データベースの接続文字列プロパティにバインドします。</span><span class="sxs-lookup"><span data-stu-id="a47f1-123">To enable the adapter to act as a tRFC server, you must set the **TidDatabaseConnectionString** binding property to the connection string for the TID database.</span></span> <span data-ttu-id="a47f1-124">これは、サービス ホストを開く前に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a47f1-124">You should do this before you open the service host.</span></span> <span data-ttu-id="a47f1-125">これは、アダプターが各 tRFC の SAP トランザクション ID (TID) を格納するデータベースです。</span><span class="sxs-lookup"><span data-stu-id="a47f1-125">This is the database in which the adapter stores the SAP transaction ID (TID) for each tRFC.</span></span> <span data-ttu-id="a47f1-126">このバインドのプロパティの詳細については、[mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47f1-126">For more information about this binding property, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
## <a name="how-do-i-enlist-in-the-transaction-for-inbound-trfcs"></a><span data-ttu-id="a47f1-127">受信 Trfc のトランザクションに参加させる方法をでしょうか。</span><span class="sxs-lookup"><span data-stu-id="a47f1-127">How do I Enlist in the Transaction for Inbound tRFCs?</span></span>  
 <span data-ttu-id="a47f1-128">SAP 論理単位の作業 (LUW) は、複数の Trfc を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a47f1-128">An SAP Logical Unit of Work (LUW) can contain multiple tRFCs.</span></span> <span data-ttu-id="a47f1-129">SAP システムで、LUW は一意のトランザクション ID (TID) によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="a47f1-129">On the SAP system a LUW is identified by a unique Transaction ID (TID).</span></span> <span data-ttu-id="a47f1-130">アダプターでは、アダプターの tRFC の呼び出しを呼び出すときに、SAP システムを使用している Tid ごとコミット トランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="a47f1-130">The adapter creates a committable transaction for each of the TIDs that the SAP system uses when it invokes tRFC calls on the adapter.</span></span> <span data-ttu-id="a47f1-131">SAP システムは、アダプターの tRFC を呼び出すときにアダプターは、サービスに SAP TID に関連付けられているトランザクションをフローします。</span><span class="sxs-lookup"><span data-stu-id="a47f1-131">When the SAP system invokes a tRFC on the adapter; the adapter flows the transaction associated with the SAP TID to your service.</span></span> <span data-ttu-id="a47f1-132">このトランザクションをアンビエント トランザクションとしては、操作メソッドの内部にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a47f1-132">You can access this transaction as the ambient transaction from inside your operation method.</span></span> <span data-ttu-id="a47f1-133">このアンビエント トランザクションへの参加、によって、操作で実行されるアクションは、SAP LUW に参加できます。</span><span class="sxs-lookup"><span data-stu-id="a47f1-133">By enlisting in this ambient transaction, the actions performed in the operation can participate in the SAP LUW.</span></span>  
  
 <span data-ttu-id="a47f1-134">操作メソッドのアンビエント トランザクションに参加して、次の操作をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a47f1-134">To enlist in the ambient transaction in an operation method, you must:</span></span>  
  
1. <span data-ttu-id="a47f1-135">操作メソッドに注釈を付け、 **TransactionScopeRequired**のプロパティ、 **OperationBehavior**属性。</span><span class="sxs-lookup"><span data-stu-id="a47f1-135">Annotate the operation method with the **TransactionScopeRequired** property of the **OperationBehavior** attribute.</span></span> <span data-ttu-id="a47f1-136">これにより、WCF から、操作内でのアンビエント トランザクションへのアクセスをすることが。</span><span class="sxs-lookup"><span data-stu-id="a47f1-136">This tells WCF that you want access to the ambient transaction from inside the operation.</span></span>  
  
2. <span data-ttu-id="a47f1-137">トランザクション スコープを作成するかの操作メソッドの注釈を付けることによって、 **TransactionAutoComplete**のプロパティ、 **OperationBehavior**属性または明示的を使用して、 **TransactionScope**操作メソッドの内部。</span><span class="sxs-lookup"><span data-stu-id="a47f1-137">Create a transaction scope either by annotating the operation method with the **TransactionAutoComplete** property of the **OperationBehavior** attribute or by explicitly using a **TransactionScope** inside the operation method.</span></span>  
  
   <span data-ttu-id="a47f1-138">次の例では、2 つの操作を実装するサービスを示します。</span><span class="sxs-lookup"><span data-stu-id="a47f1-138">The following example shows a service that implements two operations.</span></span> <span data-ttu-id="a47f1-139">両方の操作メソッドの注釈が付けられて、 **TransactionScopeRequired**アンビエント トランザクションにアクセスするプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a47f1-139">Both operation methods are annotated with the **TransactionScopeRequired** property to access the ambient transaction.</span></span>  
  
-   <span data-ttu-id="a47f1-140">**Z_TRFC_EXAMPLE1**を使用して、トランザクションに明示的に参加する**TransactionScope**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a47f1-140">**Z_TRFC_EXAMPLE1** explicitly enlists in the transaction by using a **TransactionScope** object.</span></span>  
  
-   <span data-ttu-id="a47f1-141">**Z_TRFC_EXAMPLE2**で注釈が、 **TransactionAutoComplete**プロパティは、トランザクションに参加するには</span><span class="sxs-lookup"><span data-stu-id="a47f1-141">**Z_TRFC_EXAMPLE2** is annotated with the **TransactionAutoComplete** property to enlist in the transaction</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a47f1-142">参照</span><span class="sxs-lookup"><span data-stu-id="a47f1-142">See Also</span></span>  
[<span data-ttu-id="a47f1-143">WCF サービス モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="a47f1-143">Develop applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)