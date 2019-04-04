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
ms.openlocfilehash: 40add1c72dabfd8648d1fa33e968cb26e98c11c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996915"
---
# <a name="invoke-business-service-methods-with-integration-objects-using-the-siebel-adapter"></a>Siebel アダプターを使用して統合オブジェクトでのビジネス サービス メソッドの呼び出し
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアント統合オブジェクトと連携するビジネス サービス メソッドの呼び出しに使用できます。 これらのビジネス サービスでは、OUT、IN、通常があるか、IN OUT パラメーターの「階層」のデータが送信または統合オブジェクト データを受信する入力します。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]文字列としてのこれらの階層型を公開します。 これらの文字列値は、基本的に XML の CDATA セクション内にカプセル化された XML 文字列です。 XML 文字列は、アダプターのクライアントが送信または受信しようとした統合オブジェクトの XML スキーマと互換性が。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル SiebelAdapterIntegrationObjects、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、[の Siebel アダプターのサンプル](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)を参照してください。
  
## <a name="creating-an-orchestration-to-invoke-business-service-methods-with-integration-objects"></a>統合オブジェクトでのビジネス サービス メソッドを呼び出すオーケストレーションを作成します。  
 」の説明に従って統合オブジェクトのパラメーターを受け取るビジネス サービス メソッドを呼び出すオーケストレーションの作成は他のビジネス サービスを呼び出すオーケストレーションに似ています[呼び出すビジネス サービス メソッドを使用して BizTalk Server とSiebel アダプター](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)します。  
  
 違いは、オーケストレーションを削除する要求メッセージです。 この違いは、次の理由によりです。  
  
- さまざまなビジネス サービスを呼び出すためには、要求メッセージのスキーマが異なります。  
  
- 要求メッセージには、統合オブジェクト用の XML 文字列が含まれています。 この XML は、CDATA セクション内にカプセル化されます。 まず統合オブジェクトのスキーマを生成して、スキーマに準拠した XML を作成する必要があります。 この XML は、アダプターに送信される要求メッセージの CDATA セクション内で渡す必要があります。  
  
  統合オブジェクトのスキーマに準拠しているし、要求メッセージに含めている XML を生成した後は、ファイルの場所、他の任意のオーケストレーションの場合と同様に、要求メッセージを削除する必要があります。 その他のファイルの場所で応答メッセージを探します。  
  
## <a name="request-and-response-messages-for-invoking-business-service-with-integration-objects"></a>要求と応答メッセージの統合オブジェクトでのビジネス サービスを呼び出す  
 前述のように、統合オブジェクトのパラメーターを受け取るビジネス サービスを呼び出すための唯一の違いは、アダプターに送信される要求メッセージです。 このセクションでは、要求メッセージを作成する必要がありますを実行する手順について説明します。  
  
 理解を深めるには、例として、Siebel ビジネス サービス 'EAI Siebel アダプター' を受け取ります。 'EAI Siebel アダプター' ビジネス サービスは、Siebel の統合オブジェクト ' サンプル アカウントに対して動作します。 'EAI Siebel アダプター' のビジネス サービスによって公開されるメソッドを呼び出す要求メッセージを作成するには、次のタスクを実行する必要があります。  
  
- **Siebel アダプターの EAI ビジネス サービスのスキーマを生成**します。 使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 スキーマを生成したスキーマに準拠した XML を生成します。  
  
- **統合オブジェクトのスキーマを生成**します。 Siebel Tools を使用すると、統合オブジェクトのスキーマを生成します。 Siebel Tools インターフェイスから統合オブジェクトなどのサンプルのアカウントを選択し、をクリックして**スキーマの生成**します。 スキーマを生成するときにことを確認します。  
  
  - **ビジネス サービスを一覧から選択**ドロップダウンは、「EAI XML XSD のジェネレーター」の値を持ちます。  
  
  - **封筒の種類を一覧から選択**ドロップダウンは、「Siebel メッセージ エンベロープ」の値を持ちます。  
  
    詳細については、Siebel のドキュメントを参照してください。  
  
- **統合オブジェクトのスキーマに準拠した XML メッセージを作成する**します。 ' サンプル アカウントの統合オブジェクトに対して生成されたサンプル XML メッセージは、ようになります。  
  
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
  
- **この XML メッセージをビジネス サービス メソッドの要求メッセージ内で CDATA 要素の値として渡す**します。 CDATA 要素内で上記の XML メッセージを含む要求メッセージのサンプルは、次のようになります。 この要求の例では、' EAI Siebel アダプター ' ビジネス サービスの Insert メソッドを呼び出します。  
  
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
  
  BizTalk の機能を使用して、アダプター クライアントも実行できます (Siebel Tools から取得した)。 統合オブジェクト スキーマに対して統合オブジェクト IN および OUT パラメーターの追加の検証  
  
## <a name="see-also"></a>参照  
[Siebel アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)    
[Siebel アプリケーションの開発](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)