---
title: "手順 7: エコー アダプターの同期送信ハンドラーを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4da4d987-03c4-4817-850b-4c5ca2ba7e62
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a2e2679edafd72dc0d64510e7a8566180818f8c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter"></a>手順 7: エコー アダプターの同期送信ハンドラーを実装します。
![手順 9 の 7](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")  
  
 **所要時間:** 30 分  
  
 この手順で、同期送信アダプターの性能、エコーを実装します。 よると、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、同期の送信機能をサポートするために実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`インターフェイスです。 エコー アダプターの場合、 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdapterOutboundHandler と呼ばれる 1 つの派生クラスが自動的に生成されます。  
  
 実装する方法の理解を深めるために EchoAdapterOutboundHandler クラスを更新する次のセクションで、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`着信 WCF 要求メッセージを解析する方法、および応答の送信 WCF メッセージを生成する方法です。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を開始する前にする必要がありますが正常に完了しました[手順 6: エコー アダプターのメタデータを解決するハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)です。 基礎知識`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`も便利です。  
  
## <a name="the-ioutboundhandler-interface"></a>IOutboundHandler インターフェイス  
 `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`として定義されます。  
  
```  
public interface IOutboundHandler : IConnectionHandler, IDisposable  
{  
    Message Execute(Message message, TimeSpan timeout);  
}  
```  
  
 `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`メソッドは、ターゲット システムに対応するメソッドを呼び出すことによって、着信 WCF 要求メッセージを実行し、出力方向の WCF 応答メッセージを返します。 そのパラメーターの定義は、次の表のとおりです。  
  
|**パラメーター**|**定義**|  
|-------------------|--------------------|  
|message|受信 WCF 要求メッセージ。|  
|timeout|時間間隔が内部では、この操作を完了する必要があります。 操作がスローする必要があります、`System.TimeoutException`操作を完了する前に、指定したタイムアウト時間を超過した場合。|  
  
 場合は、アダプターは、一方向の送信 (、アダプターで期待される応答メッセージはありません) を実行する、このメソッドは null を返す必要があります。 アダプターは双方向の操作を実行している場合`Microsoft.ServiceModel.Channels.Common.OperationResult`と等しい`Microsoft.ServiceModel.Channels.Common.OperationResult.Empty%2A`、このメソッドは、空の本文で WCF 応答メッセージを返します。 それ以外の場合に値を含む本体を持つ WCF 応答メッセージを返す必要がありますが、`Microsoft.ServiceModel.Channels.Common.OperationResult`オブジェクト。 応答アクション文字列を構築するために使用`Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`です。  
  
## <a name="echo-adapter-synchronous-outbound"></a>同期アダプターをエコー送信  
 によっては、ターゲット システムの操作を実装する方法はたくさんあります、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`メソッドです。 エコー アダプターの 3 つの送信操作があるし、それらの割り当て済みのノード Id と表示名は。  
  
-   文字列 EchoStrings (文字列データを)、ノード ID エコー/EchoString、表示名を = EchoString を =  
  
-   EchoGreetings(Greeting greeting)、ノード ID を greeting エコー/EchoGreetings、表示名を = EchoGreetings を =  
  
-   CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath)、nodeID エコー/EchoCustomGreetingFromFile、表示名を = EchoGreetings を =  
  
 正しく受信 WCF 要求メッセージを解析し、出力方向の WCF 応答メッセージを生成、知識が必要で使用される SOAP メッセージ内の次の要素の[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:  
  
 受信 WCF 要求メッセージ。  
  
-   WCF メッセージのアクションを入力する操作のノード ID を =  
  
-   着信メッセージの本文 = 開始本文の要素は\<displayname\>\<パラメーター名\>{データ}\</parameter 名前\>\</displayname\>  
  
 送信 WCF 応答メッセージ。  
  
-   WCF メッセージのアクションの出力操作のノード ID = +"/応答"  
  
-   メッセージ本文を送信 = 開始本文の要素が\<displayname +"Response"\>」と入力し\<displayname +「結果」\>、続くと、 \<datatype\>データ\</datatype\>\</displayname+"結果\>\</displayname +"Response"\>  
  
 たとえば、操作**string[] EchoStrings (文字列データ)**、ノード ID = エコー/EchoStrings、および表示名が EchoStrings を =。  
  
 WCF メッセージのアクションの入力 ="エコー/EchoStrings"です。パラメーター名があるため、入力の本文は次のように、検索と`data`です。  
  
```  
<EchoStrings>  
<data>{data}  
</data>  
</EchoStrings>  
```  
  
 WCF メッセージのアクションの出力 =「エコー/EchoStrings/応答」です。出力本文次のとおり、データ型なので、**文字列**です。  
  
```  
<EchoStringsResponse>  
<EchoStringsResult>  
<string>{data}</string>  
</EchoStringsResult>  
</EchoStringsResponse>  
```  
  
 受信 WCF 要求メッセージを解析するときに行うこともできます、 `System.Xml.XmlDictionaryReader` WCF 応答メッセージを作成するときに、WCF メッセージ内のコンテンツを取得、使用することができます、`System.Xml.XmlWriter`するようにします。  
  
## <a name="implementing-the-ioutboundhandler"></a>IOutboundHandler を実装します。  
 Execute メソッドを実装する、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`です。 最初に、取得、`Microsoft.ServiceModel.Channels.Common.OperationMetadata`入力メッセージのアクションに基づいてオブジェクト。 受信 WCF メッセージを解析し、各操作に基づいて関連付けられているエコー機能を実行します。 最後に、出力方向のメッセージ本文の形式を使用して、送信 WCF 応答メッセージを作成します。  
  
#### <a name="to-implement-the-execute-method-of-the-echoadapteroutboundhandler-class"></a>EchoAdapterOutboundHandler クラスの Execute メソッドを実装するには  
  
1.  ソリューション エクスプ ローラーで、 **EchoAdapterOutboundHandler.cs**ファイル。  
  
2.  Visual Studio エディターで次の 2 つの追加のディレクティブを使用して既存のセットにディレクティブを使用します。  
  
    ```csharp  
    using System.Xml;  
    using System.IO;  
    ```  
  
3.  内部、 **Execute**メソッド、既存のロジックを次に置き換えます。  
  
    1.  このロジックでは、要求された操作を確認します。  
  
    2.  取得、 `Microsoft.ServiceModel.Channels.Common.OperationMetadata` SOAP 入力メッセージのアクションに基づいてオブジェクト。  
  
    3.  アクションの種類に基づき、WCF 要求メッセージを解析し、適切な操作が呼び出されます。  
  
    ```csharp  
    // Trace input message  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Verbose, "http://Microsoft.Adapters.Samples.Sql/TraceCode/InputWcfMessage", "Input WCF Message", this, new MessageTraceRecord(message));  
    // Timeout is not supported in this sample  
    OperationMetadata om = this.MetadataLookup.GetOperationDefinitionFromInputMessageAction(message.Headers.Action, timeout);  
    if (om == null)  
    {  
        throw new AdapterException("Invalid operation metadata for " + message.Headers.Action);  
    }  
    if (timeout.Equals(TimeSpan.Zero))  
    {  
        throw new AdapterException("time out is zero");  
    }  
  
    switch (message.Headers.Action)  
    {  
        case "Echo/EchoStrings":  
            return ExecuteEchoStrings(om as ParameterizedOperationMetadata, message, timeout);  
  
        case "Echo/EchoGreetings":  
            return ExecuteEchoGreetings(om as ParameterizedOperationMetadata, message, timeout);  
  
        case "Echo/EchoCustomGreetingFromFile":  
            return ExecuteEchoCustomGreetingFromFile(om, message, timeout);  
    }  
    return null;              
    ```  
  
4.  ここで追加、 **ExecuteEchoStrings** string[] EchoStrings (文字列データ) の操作を処理するメソッド。 このヘルパー関数を読み取り、WCF 要求メッセージ、echoInUpperCase URI 要素が設定されているかどうかはかどうかを確認 true です。場合は、大文字に変換する回数のカウント変数に示すように、入力文字列に変換します。 次に、WCF 応答メッセージの形式で生成: \<EchoStringsResponse\>\<EchoStringResult\>\<文字列\>{データ}\</string\> \</EchoStringResult\>\</EchoStringsResponse\>です。  
  
    ```csharp  
    private Message ExecuteEchoStrings(ParameterizedOperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // ** Read the WCF request  
        // ** <EchoStrings><name>{text}</name></EchoStrings>  
        XmlDictionaryReader inputReader = message.GetReaderAtBodyContents();  
        while (inputReader.Read())  
        {  
            if ((String.IsNullOrEmpty(inputReader.Prefix) && inputReader.Name.Equals("data"))  
                || inputReader.Name.Equals(inputReader.Prefix + ":" + "data")) break;  
        }  
        inputReader.Read();  
        // if the connection property "echoInUpperCase" is set to true, it echoes the data in upper case  
        bool echoInUpperCase = this.Connection.ConnectionFactory.ConnectionUri.EchoInUpperCase;  
        string inputValue = echoInUpperCase ? inputReader.Value.ToUpper() : inputReader.Value;  
        int arrayCount = this.Connection.ConnectionFactory.Adapter.Count;  
  
        // ** Generate the WCF response  
        // ** <EchoStringsResponse><EchoStringResult>{Name}</EchoStringResult></EchoStringsResponse >  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        if (om.OperationResult.IsArray)  
        {  
            for (int count = 0; count < arrayCount; count++)  
            {  
                replywriter.WriteElementString("string", "http://schemas.microsoft.com/2003/10/Serialization/Arrays", inputValue);  
            }  
        }  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
5.  追加することにより続行、 **ExecuteEchoGreetings** EchoGreetings 操作を処理するメソッド。 このヘルパー関数は、WCF 要求メッセージを読み取り、操作およびによって型を解決、`ResolveOperationMetadata`と`ResolveTypeMetadata`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`インターフェイス、およびの形式を使用して WCF 応答メッセージが生成されます: \<EchoGreetingsResponse\>\<EchoGreetingsResult\>... メッセージしています.\</EchoGreetingsResult\>\</EchoGreetingsResponse\>です。  
  
    ```csharp  
    private Message ExecuteEchoGreetings(ParameterizedOperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // NOTE this method doesn't return response in upper case based on   
        // connection property echoInUpperCase  
  
        // ** Read the WCF request  
        String inputValue = String.Empty;  
        using (XmlDictionaryReader inputReader = message.GetReaderAtBodyContents())  
        {  
  
            bool foundGreeting = inputReader.ReadToDescendant("greeting");  
            if (foundGreeting)  
            {  
                inputValue = inputReader.ReadInnerXml();  
            }  
        }  
  
        int arrayCount = this.Connection.ConnectionFactory.Adapter.Count;  
  
        // ** Generate the WCF response  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        for(int i = 0; i < arrayCount; i++ )  
        {  
            ComplexQualifiedType cqtResult = om.OperationResult.QualifiedType as ComplexQualifiedType;  
            StructuredTypeMetadata tmResult = MetadataLookup.GetTypeDefinition(cqtResult.TypeId, timeout) as StructuredTypeMetadata;  
            replywriter.WriteStartElement(tmResult.TypeName, tmResult.TypeNamespace);  
            replywriter.WriteRaw(inputValue);  
            replywriter.WriteEndElement();  
        }  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
6.  ここで追加、 **ExecuteEchoCustomGreetingFromFile** EchoCustomGreetingFromFile 操作を処理するメソッド。 指定したファイルからメッセージを読み取りこのヘルパー関数は、WCF 要求メッセージを読み取りの形式を使用して WCF 応答メッセージが生成されます: \<EchoGreetingsFromFileResponse\> \<EchoGreetingsFromFileResult\>... メッセージしています.\</EchoGreetingsFromFileResult\>\</EchoGreetingsFromFileResponse\>です。  
  
    ```csharp  
    private Message ExecuteEchoCustomGreetingFromFile(OperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // NOTE this method doesn't return response in upper case based on   
        // connection property echoInUpperCase  
  
        // ** Read the WCF request  
        Uri path;  
        using (XmlDictionaryReader inputReader = message.GetReaderAtBodyContents())  
        {  
            inputReader.MoveToContent();  
            inputReader.ReadStartElement(om.DisplayName);  
            inputReader.MoveToContent();  
            // The path contains the location of the XML file that contains the instance of Greeting object to read   
            path = new Uri(inputReader.ReadElementContentAsString());  
            inputReader.ReadEndElement();  
        }  
  
        // ** Generate the WCF response  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        // Read the XML file and set it to the reply writer here  
        FileStream stream = new FileStream(path.AbsolutePath, FileMode.Open);  
        XmlDictionaryReader xdr = XmlDictionaryReader.CreateTextReader(stream, new XmlDictionaryReaderQuotas());  
        xdr.MoveToContent();  
        string rawGreeting = xdr.ReadInnerXml();  
        replywriter.WriteRaw(rawGreeting);  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
7.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。  
  
8.  **[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。 これは、エラーなしでコンパイルする必要があります。 以外の場合は、上記のすべてのステップに従っていることを確認します。 ここで、安全に Visual Studio を終了したりに進む[手順 8: エコー アダプターの同期受信ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)です。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、エコー アダプターの同期送信メッセージング機能を実装する方法について学習しました。 実装してこれを行う、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`です。 このメソッドは、着信 WCF 要求メッセージを解析し、必要な処理を実行、出力方向の WCF 応答メッセージを生成します。  
  
 WCF を使用して、着信 WCF 要求メッセージの具体的には、`System.ServiceModel.Channels.Message.Headers.Action%2A`をさらに、受信メッセージ本文の基本的な構造を理解することにより、入力メッセージのアクションを取得します。 使用した出力方向の WCF 応答メッセージの`Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`をさらに、出力方向のメッセージ本文の基本的な構造を理解することにより、出力メッセージのアクションを取得します。 使用して解析し、WCF メッセージを作成する、`System.Xml.XmlDictionaryReader`に着信 WCF 要求メッセージを読んだり使用したり`System.Xml.XmlWriter`出力方向の WCF 応答メッセージを書き込む。  
  
## <a name="next-steps"></a>次の手順  
ビルドして、エコー アダプターを展開します。  
  
## <a name="see-also"></a>参照  
 [手順 6: エコー アダプター メタデータの解決ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)   
 [手順 8: エコー アダプターの同期受信ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)