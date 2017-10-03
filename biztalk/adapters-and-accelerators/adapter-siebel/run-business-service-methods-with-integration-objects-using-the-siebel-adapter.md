---
title: "Siebel アダプターを使用して統合オブジェクトでのビジネス サービス メソッドを呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- integration objects
- how to, invoke business service methods with integration objects
- business service methods, invoking with integration objects
ms.assetid: ac0fa80a-3451-436e-8a1a-b6b5e93081e7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a9edb9a169d35a3f4709a8896ef3adfe404e775
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-business-service-methods-with-integration-objects-using-the-siebel-adapter"></a><span data-ttu-id="50c6f-102">Siebel アダプターを使用して統合オブジェクトでのビジネス サービス メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="50c6f-102">Invoke Business Service Methods with Integration Objects using the Siebel adapter</span></span>
<span data-ttu-id="50c6f-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアント統合オブジェクトを使用するビジネス サービス メソッドを呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="50c6f-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enables adapter clients to invoke business service methods that work with integration objects.</span></span> <span data-ttu-id="50c6f-104">これらのビジネス サービス通常 IN、OUT も IN OUT パラメーター「階層」データの型を送信または統合オブジェクト データを受信します。</span><span class="sxs-lookup"><span data-stu-id="50c6f-104">These business services typically have IN, OUT, or IN OUT parameters of "hierarchy" data type to send or receive integration object data.</span></span>  
  
 <span data-ttu-id="50c6f-105">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]文字列としてのこれらの階層型を公開します。</span><span class="sxs-lookup"><span data-stu-id="50c6f-105">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes these hierarchical types as strings.</span></span> <span data-ttu-id="50c6f-106">これらの文字列値は、本質的には、XML の CDATA セクション内のカプセル化された XML 文字列です。</span><span class="sxs-lookup"><span data-stu-id="50c6f-106">These string values are essentially an XML string encapsulated in an XML CDATA section.</span></span> <span data-ttu-id="50c6f-107">XML 文字列は、アダプターのクライアントが送信または受信をしようとして、統合オブジェクトの XML スキーマとの互換性。</span><span class="sxs-lookup"><span data-stu-id="50c6f-107">The XML string is compatible with the XML schema of the integration object the adapter client is trying to send or receive.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="50c6f-108">このトピックの内容に基づくサンプル</span><span class="sxs-lookup"><span data-stu-id="50c6f-108">Sample Based On This Topic</span></span>  
 <span data-ttu-id="50c6f-109">サンプルは、SiebelAdapterIntegrationObjects、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="50c6f-109">A sample, SiebelAdapterIntegrationObjects, based on this topic is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="50c6f-110">詳細については、次を参照してください。 [Siebel アダプターのサンプル](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="50c6f-110">For more information, see [Samples for the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).</span></span>
  
## <a name="creating-an-orchestration-to-invoke-business-service-methods-with-integration-objects"></a><span data-ttu-id="50c6f-111">統合オブジェクトとのビジネス サービス メソッドを呼び出すオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="50c6f-111">Creating an Orchestration to Invoke Business Service Methods with Integration Objects</span></span>  
 <span data-ttu-id="50c6f-112">統合オブジェクトのパラメーターを受け取るビジネス サービス メソッドを呼び出すオーケストレーションを作成するに似ていますが、他のビジネス サービスを呼び出すオーケストレーション」の説明に従って[呼び出すビジネス サービス メソッドを使用して BizTalk Server とSiebel アダプター](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="50c6f-112">Creating an orchestration to invoke a business service method that takes integration object parameters is similar to the orchestration to invoke any other business service, as described in [Invoke Business Service Methods Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span></span>  
  
 <span data-ttu-id="50c6f-113">違いは、オーケストレーションを削除する要求メッセージ。</span><span class="sxs-lookup"><span data-stu-id="50c6f-113">The difference lies in the request message that you drop for the orchestration.</span></span> <span data-ttu-id="50c6f-114">この違いは、次の理由によりです。</span><span class="sxs-lookup"><span data-stu-id="50c6f-114">This difference is because of the following:</span></span>  
  
-   <span data-ttu-id="50c6f-115">さまざまなビジネス サービスを起動するためには、要求メッセージのスキーマが異なります。</span><span class="sxs-lookup"><span data-stu-id="50c6f-115">The schema for the request message is different because you invoke a different business service.</span></span>  
  
-   <span data-ttu-id="50c6f-116">要求メッセージには、統合オブジェクト用の XML 文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="50c6f-116">The request message contains the XML string for the integration object.</span></span> <span data-ttu-id="50c6f-117">この XML は、CDATA セクション内にカプセル化されます。</span><span class="sxs-lookup"><span data-stu-id="50c6f-117">This XML is encapsulated in a CDATA section.</span></span> <span data-ttu-id="50c6f-118">最初の統合オブジェクトのスキーマを生成し、スキーマに準拠する XML を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c6f-118">You must first generate the schema for the integration object and then create an XML that conforms to the schema.</span></span> <span data-ttu-id="50c6f-119">この XML は、アダプターに送信された要求メッセージの CDATA セクション内で渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c6f-119">This XML must be passed within the CDATA section of the request message sent to the adapter.</span></span>  
  
 <span data-ttu-id="50c6f-120">統合オブジェクト スキーマに準拠し、要求メッセージに表示する XML を生成した後は、他の任意のオーケストレーションの場合と同じようにファイルの場所で要求メッセージを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c6f-120">After you have generated the XML that conforms to the integration object schema and included it in the request message, you must drop the request message at a FILE location, just like you do for any other orchestration.</span></span> <span data-ttu-id="50c6f-121">その他のファイルの場所で応答メッセージを探します。</span><span class="sxs-lookup"><span data-stu-id="50c6f-121">Look for the response message in the other FILE location.</span></span>  
  
## <a name="request-and-response-messages-for-invoking-business-service-with-integration-objects"></a><span data-ttu-id="50c6f-122">要求および応答メッセージの統合オブジェクトとのビジネス サービスを呼び出す</span><span class="sxs-lookup"><span data-stu-id="50c6f-122">Request and Response Messages for Invoking Business Service with Integration Objects</span></span>  
 <span data-ttu-id="50c6f-123">前述のように、統合オブジェクトのパラメーターを受け取るビジネス サービスを呼び出すための唯一の違いは、アダプターに送信される要求メッセージです。</span><span class="sxs-lookup"><span data-stu-id="50c6f-123">As mentioned before, the only difference for invoking a business service that takes integration object parameters is the request message sent to the adapter.</span></span> <span data-ttu-id="50c6f-124">このセクションでは、要求メッセージを作成するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="50c6f-124">This section provides instructions on the steps you must perform to create the request message.</span></span>  
  
 <span data-ttu-id="50c6f-125">理解を深めるには、例として、Siebel ビジネス サービス 'EAI Siebel アダプター' を行います。</span><span class="sxs-lookup"><span data-stu-id="50c6f-125">For better understanding, take a Siebel business service 'EAI Siebel Adapter' as an example.</span></span> <span data-ttu-id="50c6f-126">'EAI Siebel アダプター' ビジネス サービスは、Siebel の統合オブジェクト ' サンプル アカウントで動作します。</span><span class="sxs-lookup"><span data-stu-id="50c6f-126">The 'EAI Siebel Adapter' business service operates on a Siebel integration object, 'Sample Account'.</span></span> <span data-ttu-id="50c6f-127">'EAI Siebel アダプター' ビジネス サービスによって公開されるメソッドを呼び出すための要求メッセージを作成する次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c6f-127">You must perform the following tasks to create the request message to invoke a method exposed by the 'EAI Siebel Adapter' business service:</span></span>  
  
-   <span data-ttu-id="50c6f-128">**EAI Siebel アダプターのビジネス サービスのスキーマを生成**です。</span><span class="sxs-lookup"><span data-stu-id="50c6f-128">**Generate the schema for the EAI Siebel Adapter business service**.</span></span> <span data-ttu-id="50c6f-129">使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="50c6f-129">You must use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate the schema.</span></span> <span data-ttu-id="50c6f-130">スキーマを生成したスキーマに準拠した XML を生成します。</span><span class="sxs-lookup"><span data-stu-id="50c6f-130">Once you generate the schema, generate the XML that conforms to the schema.</span></span>  
  
-   <span data-ttu-id="50c6f-131">**統合オブジェクトのスキーマを生成**です。</span><span class="sxs-lookup"><span data-stu-id="50c6f-131">**Generate the schema for the integration object**.</span></span> <span data-ttu-id="50c6f-132">Siebel Tools を使用すると、統合オブジェクトのスキーマを生成できます。</span><span class="sxs-lookup"><span data-stu-id="50c6f-132">Use Siebel Tools to generate schema for an integration object.</span></span> <span data-ttu-id="50c6f-133">Siebel Tools インターフェイスから統合オブジェクト、たとえば、サンプル アカウントを選択し、をクリックして**スキーマの生成**です。</span><span class="sxs-lookup"><span data-stu-id="50c6f-133">From the Siebel Tools interface, select the integration object, for example, Sample Account, and click **Generate Schema**.</span></span> <span data-ttu-id="50c6f-134">スキーマを生成するときに確認します。</span><span class="sxs-lookup"><span data-stu-id="50c6f-134">While generating the schema, make sure:</span></span>  
  
    -   <span data-ttu-id="50c6f-135">**ビジネス サービスを一覧から選択**ドロップダウンが「EAI XML XSD ジェネレーター」の値。</span><span class="sxs-lookup"><span data-stu-id="50c6f-135">The **Select a Business Service from the list** drop-down has the value "EAI XML XSD Generator".</span></span>  
  
    -   <span data-ttu-id="50c6f-136">**封筒の種類を一覧から選択**ドロップダウン値「Siebel メッセージ エンベロープ」を持つファイルです。</span><span class="sxs-lookup"><span data-stu-id="50c6f-136">The **Select an envelope type from the list** drop-down has the value "Siebel Message Envelope".</span></span>  
  
     <span data-ttu-id="50c6f-137">詳細については、Siebel のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50c6f-137">For more information, see the Siebel documentation.</span></span>  
  
-   <span data-ttu-id="50c6f-138">**統合オブジェクトのスキーマに準拠した XML メッセージを作成する**です。</span><span class="sxs-lookup"><span data-stu-id="50c6f-138">**Create an XML message that conforms to schema of the integration object**.</span></span> <span data-ttu-id="50c6f-139">' サンプル アカウント統合オブジェクトに対して生成されたサンプルの XML メッセージは、ようになります。</span><span class="sxs-lookup"><span data-stu-id="50c6f-139">A sample XML message generated for the 'Sample Account' integration object looks like:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="UTF-16"?>  
    <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
      <ListOfSampleAccount>  
        <Account>  
          <CurrencyCode>USD</CurrencyCode>  
          <Location>Redmond</Location>  
          <Name>IntegrationObjectTest</Name>  
        </Account>  
      </ListOfSampleAccount>  
    </SiebelMessage>  
    ```  
  
-   <span data-ttu-id="50c6f-140">**この XML メッセージをビジネス サービス メソッドの要求メッセージで CDATA 要素の値として渡す**です。</span><span class="sxs-lookup"><span data-stu-id="50c6f-140">**Pass this XML message as the value for the CDATA element in the request message for the business service method**.</span></span> <span data-ttu-id="50c6f-141">CDATA 要素内で上記の XML メッセージを含む要求メッセージのサンプルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="50c6f-141">A sample request message that contains the preceding XML message within a CDATA element looks like the following.</span></span> <span data-ttu-id="50c6f-142">この要求の例では、' EAI Siebel アダプター ' ビジネス サービスの挿入メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="50c6f-142">This sample request is to invoke the Insert method for the 'EAI Siebel Adapter' business service.</span></span>  
  
    ```  
    <Insert xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter/Operation">  
      <InsertRequestRecord />   
      <InsertInOutRecord>  
        <SiebelMessage xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">  
          <![CDATA[ \<?xml version="1.0" encoding="UTF-16"?>  
            <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
              <ListOfSampleAccount>  
                <Account>  
                  <CurrencyCode>USD</CurrencyCode>  
                  <Location>Redmond</Location>  
                  <Name>IntegrationObjectTest</Name>  
                </Account>  
              </ListOfSampleAccount>  
            </SiebelMessage>  
          ]]>   
         </SiebelMessage>  
      </InsertInOutRecord>  
    </Insert>  
    ```  
  
     <span data-ttu-id="50c6f-143">上記の要求メッセージの Siebel からの応答には、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="50c6f-143">The response from Siebel for the above request message resembles the following:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <InsertResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter/Operation">  
      <InsertResult>  
        <ErrorCode xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">0x0</ErrorCode>   
        <ErrorContextIntComp xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <ErrorContextSearchSpec xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <ErrorSymbol xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <OMErrorCode xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <OMErrorSymbol xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <PrimaryRowId xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">1-6SPSJ</PrimaryRowId>   
      </InsertResult>  
      <InsertInOutRecord>  
        <SiebelMessage xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">  
          <![CDATA[ \<?xml version="1.0" encoding="UTF-16"?>  
            <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
              <ListOfSampleAccount>  
                <Account>  
                  <CurrencyCode>USD</CurrencyCode>  
                  <Location>Redmond</Location>  
                  <Name>IntegrationObjectTest</Name>  
                </Account>  
              </ListOfSampleAccount>  
            </SiebelMessage>  
          ]]>   
         </SiebelMessage>  
      </InsertInOutRecord>  
    </InsertResponse>  
    ```  
  
 <span data-ttu-id="50c6f-144">BizTalk の機能を使用して、アダプターのクライアントも実行できます (Siebel Tools から取得されます。) の統合オブジェクトのスキーマに対して統合オブジェクト IN と OUT パラメーターの追加の検証</span><span class="sxs-lookup"><span data-stu-id="50c6f-144">Using BizTalk features, adapter clients can also perform additional validation of the integration object IN and OUT parameter against the integration object schema (obtained from Siebel Tools.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c6f-145">参照</span><span class="sxs-lookup"><span data-stu-id="50c6f-145">See Also</span></span>  
<span data-ttu-id="50c6f-146">[Siebel アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)  </span><span class="sxs-lookup"><span data-stu-id="50c6f-146">[Develop BizTalk Applications using the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)  </span></span>  
[<span data-ttu-id="50c6f-147">Siebel アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="50c6f-147">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)