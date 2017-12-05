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
ms.openlocfilehash: 132c269d347f67cbad3038bcbbb8e62d29112b6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-business-service-methods-with-integration-objects-using-the-siebel-adapter"></a>Siebel アダプターを使用して統合オブジェクトでのビジネス サービス メソッドを呼び出す
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアント統合オブジェクトを使用するビジネス サービス メソッドを呼び出すことができるようにします。 これらのビジネス サービス通常 IN、OUT も IN OUT パラメーター「階層」データの型を送信または統合オブジェクト データを受信します。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]文字列としてのこれらの階層型を公開します。 これらの文字列値は、本質的には、XML の CDATA セクション内のカプセル化された XML 文字列です。 XML 文字列は、アダプターのクライアントが送信または受信をしようとして、統合オブジェクトの XML スキーマとの互換性。  
  
## <a name="sample-based-on-this-topic"></a>このトピックの内容に基づくサンプル  
 サンプルは、SiebelAdapterIntegrationObjects、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [Siebel アダプターのサンプル](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)です。
  
## <a name="creating-an-orchestration-to-invoke-business-service-methods-with-integration-objects"></a>統合オブジェクトとのビジネス サービス メソッドを呼び出すオーケストレーションを作成します。  
 統合オブジェクトのパラメーターを受け取るビジネス サービス メソッドを呼び出すオーケストレーションを作成するに似ていますが、他のビジネス サービスを呼び出すオーケストレーション」の説明に従って[呼び出すビジネス サービス メソッドを使用して BizTalk Server とSiebel アダプター](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)です。  
  
 違いは、オーケストレーションを削除する要求メッセージ。 この違いは、次の理由によりです。  
  
-   さまざまなビジネス サービスを起動するためには、要求メッセージのスキーマが異なります。  
  
-   要求メッセージには、統合オブジェクト用の XML 文字列が含まれています。 この XML は、CDATA セクション内にカプセル化されます。 最初の統合オブジェクトのスキーマを生成し、スキーマに準拠する XML を作成する必要があります。 この XML は、アダプターに送信された要求メッセージの CDATA セクション内で渡す必要があります。  
  
 統合オブジェクト スキーマに準拠し、要求メッセージに表示する XML を生成した後は、他の任意のオーケストレーションの場合と同じようにファイルの場所で要求メッセージを削除する必要があります。 その他のファイルの場所で応答メッセージを探します。  
  
## <a name="request-and-response-messages-for-invoking-business-service-with-integration-objects"></a>要求および応答メッセージの統合オブジェクトとのビジネス サービスを呼び出す  
 前述のように、統合オブジェクトのパラメーターを受け取るビジネス サービスを呼び出すための唯一の違いは、アダプターに送信される要求メッセージです。 このセクションでは、要求メッセージを作成するための手順について説明します。  
  
 理解を深めるには、例として、Siebel ビジネス サービス 'EAI Siebel アダプター' を行います。 'EAI Siebel アダプター' ビジネス サービスは、Siebel の統合オブジェクト ' サンプル アカウントで動作します。 'EAI Siebel アダプター' ビジネス サービスによって公開されるメソッドを呼び出すための要求メッセージを作成する次のタスクを実行する必要があります。  
  
-   **EAI Siebel アダプターのビジネス サービスのスキーマを生成**です。 使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 スキーマを生成したスキーマに準拠した XML を生成します。  
  
-   **統合オブジェクトのスキーマを生成**です。 Siebel Tools を使用すると、統合オブジェクトのスキーマを生成できます。 Siebel Tools インターフェイスから統合オブジェクト、たとえば、サンプル アカウントを選択し、をクリックして**スキーマの生成**です。 スキーマを生成するときに確認します。  
  
    -   **ビジネス サービスを一覧から選択**ドロップダウンが「EAI XML XSD ジェネレーター」の値。  
  
    -   **封筒の種類を一覧から選択**ドロップダウン値「Siebel メッセージ エンベロープ」を持つファイルです。  
  
     詳細については、Siebel のドキュメントを参照してください。  
  
-   **統合オブジェクトのスキーマに準拠した XML メッセージを作成する**です。 ' サンプル アカウント統合オブジェクトに対して生成されたサンプルの XML メッセージは、ようになります。  
  
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
  
-   **この XML メッセージをビジネス サービス メソッドの要求メッセージで CDATA 要素の値として渡す**です。 CDATA 要素内で上記の XML メッセージを含む要求メッセージのサンプルは、次のようになります。 この要求の例では、' EAI Siebel アダプター ' ビジネス サービスの挿入メソッドを呼び出します。  
  
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
  
     上記の要求メッセージの Siebel からの応答には、次のようになります。  
  
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
  
 BizTalk の機能を使用して、アダプターのクライアントも実行できます (Siebel Tools から取得されます。) の統合オブジェクトのスキーマに対して統合オブジェクト IN と OUT パラメーターの追加の検証  
  
## <a name="see-also"></a>参照  
[Siebel アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)    
[Siebel アプリケーションの開発](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)