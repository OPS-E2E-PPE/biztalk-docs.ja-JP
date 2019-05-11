---
title: Siebel アダプターを使用して統合オブジェクトでのビジネス サービス メソッドの呼び出し |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- integration objects
- how to, invoke business service methods with integration objects
- business service methods, invoking with integration objects
ms.assetid: ac0fa80a-3451-436e-8a1a-b6b5e93081e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9eaed223b88ad3be039ebb6a77a5f63c2094c4c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371139"
---
# <a name="invoke-business-service-methods-with-integration-objects-using-the-siebel-adapter"></a><span data-ttu-id="54228-102">Siebel アダプターを使用して統合オブジェクトでのビジネス サービス メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="54228-102">Invoke Business Service Methods with Integration Objects using the Siebel adapter</span></span>
<span data-ttu-id="54228-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアント統合オブジェクトと連携するビジネス サービス メソッドの呼び出しに使用できます。</span><span class="sxs-lookup"><span data-stu-id="54228-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enables adapter clients to invoke business service methods that work with integration objects.</span></span> <span data-ttu-id="54228-104">これらのビジネス サービスでは、OUT、IN、通常があるか、IN OUT パラメーターの「階層」のデータが送信または統合オブジェクト データを受信する入力します。</span><span class="sxs-lookup"><span data-stu-id="54228-104">These business services typically have IN, OUT, or IN OUT parameters of "hierarchy" data type to send or receive integration object data.</span></span>  
  
 <span data-ttu-id="54228-105">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]文字列としてのこれらの階層型を公開します。</span><span class="sxs-lookup"><span data-stu-id="54228-105">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes these hierarchical types as strings.</span></span> <span data-ttu-id="54228-106">これらの文字列値は、基本的に XML の CDATA セクション内にカプセル化された XML 文字列です。</span><span class="sxs-lookup"><span data-stu-id="54228-106">These string values are essentially an XML string encapsulated in an XML CDATA section.</span></span> <span data-ttu-id="54228-107">XML 文字列は、アダプターのクライアントが送信または受信しようとした統合オブジェクトの XML スキーマと互換性が。</span><span class="sxs-lookup"><span data-stu-id="54228-107">The XML string is compatible with the XML schema of the integration object the adapter client is trying to send or receive.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="54228-108">このトピックに基づくサンプル</span><span class="sxs-lookup"><span data-stu-id="54228-108">Sample Based On This Topic</span></span>  
 <span data-ttu-id="54228-109">サンプル SiebelAdapterIntegrationObjects、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="54228-109">A sample, SiebelAdapterIntegrationObjects, based on this topic is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="54228-110">詳細については、次を参照してください。[の Siebel アダプターのサンプル](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="54228-110">For more information, see [Samples for the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).</span></span>
  
## <a name="creating-an-orchestration-to-invoke-business-service-methods-with-integration-objects"></a><span data-ttu-id="54228-111">統合オブジェクトでのビジネス サービス メソッドを呼び出すオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="54228-111">Creating an Orchestration to Invoke Business Service Methods with Integration Objects</span></span>  
 <span data-ttu-id="54228-112">」の説明に従って統合オブジェクトのパラメーターを受け取るビジネス サービス メソッドを呼び出すオーケストレーションの作成は他のビジネス サービスを呼び出すオーケストレーションに似ています[呼び出すビジネス サービス メソッドを使用して BizTalk Server とSiebel アダプター](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="54228-112">Creating an orchestration to invoke a business service method that takes integration object parameters is similar to the orchestration to invoke any other business service, as described in [Invoke Business Service Methods Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span></span>  
  
 <span data-ttu-id="54228-113">違いは、オーケストレーションを削除する要求メッセージです。</span><span class="sxs-lookup"><span data-stu-id="54228-113">The difference lies in the request message that you drop for the orchestration.</span></span> <span data-ttu-id="54228-114">この違いは、次の理由によりです。</span><span class="sxs-lookup"><span data-stu-id="54228-114">This difference is because of the following:</span></span>  
  
- <span data-ttu-id="54228-115">さまざまなビジネス サービスを呼び出すためには、要求メッセージのスキーマが異なります。</span><span class="sxs-lookup"><span data-stu-id="54228-115">The schema for the request message is different because you invoke a different business service.</span></span>  
  
- <span data-ttu-id="54228-116">要求メッセージには、統合オブジェクト用の XML 文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="54228-116">The request message contains the XML string for the integration object.</span></span> <span data-ttu-id="54228-117">この XML は、CDATA セクション内にカプセル化されます。</span><span class="sxs-lookup"><span data-stu-id="54228-117">This XML is encapsulated in a CDATA section.</span></span> <span data-ttu-id="54228-118">まず統合オブジェクトのスキーマを生成して、スキーマに準拠した XML を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54228-118">You must first generate the schema for the integration object and then create an XML that conforms to the schema.</span></span> <span data-ttu-id="54228-119">この XML は、アダプターに送信される要求メッセージの CDATA セクション内で渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="54228-119">This XML must be passed within the CDATA section of the request message sent to the adapter.</span></span>  
  
  <span data-ttu-id="54228-120">統合オブジェクトのスキーマに準拠しているし、要求メッセージに含めている XML を生成した後は、ファイルの場所、他の任意のオーケストレーションの場合と同様に、要求メッセージを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54228-120">After you have generated the XML that conforms to the integration object schema and included it in the request message, you must drop the request message at a FILE location, just like you do for any other orchestration.</span></span> <span data-ttu-id="54228-121">その他のファイルの場所で応答メッセージを探します。</span><span class="sxs-lookup"><span data-stu-id="54228-121">Look for the response message in the other FILE location.</span></span>  
  
## <a name="request-and-response-messages-for-invoking-business-service-with-integration-objects"></a><span data-ttu-id="54228-122">要求と応答メッセージの統合オブジェクトでのビジネス サービスを呼び出す</span><span class="sxs-lookup"><span data-stu-id="54228-122">Request and Response Messages for Invoking Business Service with Integration Objects</span></span>  
 <span data-ttu-id="54228-123">前述のように、統合オブジェクトのパラメーターを受け取るビジネス サービスを呼び出すための唯一の違いは、アダプターに送信される要求メッセージです。</span><span class="sxs-lookup"><span data-stu-id="54228-123">As mentioned before, the only difference for invoking a business service that takes integration object parameters is the request message sent to the adapter.</span></span> <span data-ttu-id="54228-124">このセクションでは、要求メッセージを作成する必要がありますを実行する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="54228-124">This section provides instructions on the steps you must perform to create the request message.</span></span>  
  
 <span data-ttu-id="54228-125">理解を深めるには、例として、Siebel ビジネス サービス 'EAI Siebel アダプター' を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="54228-125">For better understanding, take a Siebel business service 'EAI Siebel Adapter' as an example.</span></span> <span data-ttu-id="54228-126">'EAI Siebel アダプター' ビジネス サービスは、Siebel の統合オブジェクト ' サンプル アカウントに対して動作します。</span><span class="sxs-lookup"><span data-stu-id="54228-126">The 'EAI Siebel Adapter' business service operates on a Siebel integration object, 'Sample Account'.</span></span> <span data-ttu-id="54228-127">'EAI Siebel アダプター' のビジネス サービスによって公開されるメソッドを呼び出す要求メッセージを作成するには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54228-127">You must perform the following tasks to create the request message to invoke a method exposed by the 'EAI Siebel Adapter' business service:</span></span>  
  
- <span data-ttu-id="54228-128">**Siebel アダプターの EAI ビジネス サービスのスキーマを生成**します。</span><span class="sxs-lookup"><span data-stu-id="54228-128">**Generate the schema for the EAI Siebel Adapter business service**.</span></span> <span data-ttu-id="54228-129">使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="54228-129">You must use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate the schema.</span></span> <span data-ttu-id="54228-130">スキーマを生成したスキーマに準拠した XML を生成します。</span><span class="sxs-lookup"><span data-stu-id="54228-130">Once you generate the schema, generate the XML that conforms to the schema.</span></span>  
  
- <span data-ttu-id="54228-131">**統合オブジェクトのスキーマを生成**します。</span><span class="sxs-lookup"><span data-stu-id="54228-131">**Generate the schema for the integration object**.</span></span> <span data-ttu-id="54228-132">Siebel Tools を使用すると、統合オブジェクトのスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="54228-132">Use Siebel Tools to generate schema for an integration object.</span></span> <span data-ttu-id="54228-133">Siebel Tools インターフェイスから統合オブジェクトなどのサンプルのアカウントを選択し、をクリックして**スキーマの生成**します。</span><span class="sxs-lookup"><span data-stu-id="54228-133">From the Siebel Tools interface, select the integration object, for example, Sample Account, and click **Generate Schema**.</span></span> <span data-ttu-id="54228-134">スキーマを生成するときにことを確認します。</span><span class="sxs-lookup"><span data-stu-id="54228-134">While generating the schema, make sure:</span></span>  
  
  - <span data-ttu-id="54228-135">**ビジネス サービスを一覧から選択**ドロップダウンは、「EAI XML XSD のジェネレーター」の値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="54228-135">The **Select a Business Service from the list** drop-down has the value "EAI XML XSD Generator".</span></span>  
  
  - <span data-ttu-id="54228-136">**封筒の種類を一覧から選択**ドロップダウンは、「Siebel メッセージ エンベロープ」の値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="54228-136">The **Select an envelope type from the list** drop-down has the value "Siebel Message Envelope".</span></span>  
  
    <span data-ttu-id="54228-137">詳細については、Siebel のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54228-137">For more information, see the Siebel documentation.</span></span>  
  
- <span data-ttu-id="54228-138">**統合オブジェクトのスキーマに準拠した XML メッセージを作成する**します。</span><span class="sxs-lookup"><span data-stu-id="54228-138">**Create an XML message that conforms to schema of the integration object**.</span></span> <span data-ttu-id="54228-139">' サンプル アカウントの統合オブジェクトに対して生成されたサンプル XML メッセージは、ようになります。</span><span class="sxs-lookup"><span data-stu-id="54228-139">A sample XML message generated for the 'Sample Account' integration object looks like:</span></span>  
  
  ```  
  <?xml version="1.0" encoding="UTF-16"?>  
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
  
- <span data-ttu-id="54228-140">**この XML メッセージをビジネス サービス メソッドの要求メッセージ内で CDATA 要素の値として渡す**します。</span><span class="sxs-lookup"><span data-stu-id="54228-140">**Pass this XML message as the value for the CDATA element in the request message for the business service method**.</span></span> <span data-ttu-id="54228-141">CDATA 要素内で上記の XML メッセージを含む要求メッセージのサンプルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="54228-141">A sample request message that contains the preceding XML message within a CDATA element looks like the following.</span></span> <span data-ttu-id="54228-142">この要求の例では、' EAI Siebel アダプター ' ビジネス サービスの Insert メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="54228-142">This sample request is to invoke the Insert method for the 'EAI Siebel Adapter' business service.</span></span>  
  
  ```  
  <Insert xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter/Operation">  
    <InsertRequestRecord />   
    <InsertInOutRecord>  
      <SiebelMessage xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">  
        <![CDATA[ <?xml version="1.0" encoding="UTF-16"?>  
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
  
   <span data-ttu-id="54228-143">上記の要求メッセージの Siebel からの応答には、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="54228-143">The response from Siebel for the above request message resembles the following:</span></span>  
  
  ```  
  <?xml version="1.0" encoding="utf-8" ?>   
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
        <![CDATA[ <?xml version="1.0" encoding="UTF-16"?>  
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
  
  <span data-ttu-id="54228-144">BizTalk の機能を使用して、アダプター クライアントも実行できます (Siebel Tools から取得した)。 統合オブジェクト スキーマに対して統合オブジェクト IN および OUT パラメーターの追加の検証</span><span class="sxs-lookup"><span data-stu-id="54228-144">Using BizTalk features, adapter clients can also perform additional validation of the integration object IN and OUT parameter against the integration object schema (obtained from Siebel Tools.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54228-145">参照</span><span class="sxs-lookup"><span data-stu-id="54228-145">See Also</span></span>  
<span data-ttu-id="54228-146">[Siebel アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)  </span><span class="sxs-lookup"><span data-stu-id="54228-146">[Develop BizTalk Applications using the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)  </span></span>  
[<span data-ttu-id="54228-147">Siebel アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="54228-147">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)