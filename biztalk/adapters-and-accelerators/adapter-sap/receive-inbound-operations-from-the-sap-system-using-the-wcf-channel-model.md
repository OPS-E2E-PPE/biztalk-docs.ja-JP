---
title: WCF チャネル モデルを使用して、SAP システムからの受信操作の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming inbound flat-file IDOCs
- WCF channel model, receiving inbound operations from the SAP system
- WCF channel model, raising an exception
ms.assetid: d71d0537-fda4-44ab-85dc-6e27aad23caf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7c0c819372cf23842eb5311df8636e55e28c72a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969683"
---
# <a name="receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して、SAP システムからの受信操作を受信します。
RFC サーバーとして動作し、SAP システム (IDOC を送信、RFC を呼び出すなど) によって呼び出された操作の受信、経由での SAP プログラム ID からのメッセージをリッスンできるチャネル リスナーを作成する必要があります、 **System.ServiceModel.Channels.IReplyChannel**チャネル形状です。  
  
 チャネル リスナー (**System.ServiceModel.Channels.IChannelListener**) は、特定の WCF エンドポイントからメッセージを受信するために使用する WCF 通信オブジェクトです。 チャネル リスナーは、サービスによって、クライアント (SAP システム) によって呼び出されたメッセージを受信できるチャネルを作成するためのファクトリとして機能します。 チャネル リスナーを作成する、 **Microsoft.Adapters.SAP.SAPBinding**オブジェクトを呼び出すことによって、 **BuildChannelListener**メソッド。 SAP 接続元の受信操作はこのメソッドを受信する SAP プログラム ID を指定する URI を指定します。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポート、 **IReplyChannel**チャネル形状です。 **IReplyChannel**チャネルが受信要求-応答メッセージ交換パターンをサポートします。 つまり、外部プログラムが、チャネルとプログラム経由で要求メッセージを送信するパターンは、応答を返します。  
  
 受信操作を使用する方法の概要については、 **IReplyChannel** WCF では、次を参照してください。[サービス チャネル レベルのプログラミング](https://msdn.microsoft.com/library/ms789029.aspx)します。
  
 このセクションでは、SAP システムからの操作の受信に固有の次のトピックについて説明します。  
  
-   チャネル リスナーを使用して特定の操作に対してフィルター処理する方法。  
  
-   SAP システムで例外を発生させる方法。  
  
-   SAP アダプターからのフラット ファイル Idoc の受信をストリーミングします。  
  
-   SAP システムから操作を受信する方法。  
  
## <a name="how-do-i-filter-operations-using-the-channel-listener"></a>チャネル リスナーを使用して操作をフィルター処理する方法  
  
### <a name="using-an-inboundactioncollection-to-filter-operations"></a>InboundActionCollection を使用して操作をフィルター処理するには  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供、 **Microsoft.ServiceModel.Channels.InboundActionCollection**チャネル リスナーによって受信され、アプリケーション コードに渡されるされる操作をフィルター処理するためのクラス。 特定の操作をフィルターするには、リスナー エンドポイント URI を使用してこのクラスのインスタンスを作成します。 コレクションに対象の操作ごとに (要求) メッセージのアクションを追加します。 最後に、受信アクションのコレクションを追加、 **System.ServiceModel.Channels.BindingParameterCollection**オブジェクトし、チャネル リスナーを作成する呼び出しにこのバインディング パラメーターのコレクションを渡します。  
  
 場合は、SAP システムでは、受信アクションのコレクションではない操作を呼び出します。  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムを次のメッセージで例外の例外を呼び出し元に返します。"受信 RFC 呼び出し [RFC_NAME] を Rfc サーバーが処理されない"。 このメッセージの [RFC_NAME] は、RFC (たとえば、IDOC_INBOUND_ASYNCHRONOUS) の名前です。  
  
- アダプターがスローされます、 **Microsoft.ServiceModel.Channels.Common.AdapterException**受信した操作を示すメッセージを使用します。 この例外を使用する方法の例は、このトピックの最後の例を参照してください。  
  
  次のコード例を使用する方法を示しています、 **InboundActionCollection** Z_RFC_MKD_DIV、1 つの RFC をフィルター処理するチャネル リスナーを作成します。  
  
```  
// The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
// and credentials.  
Uri listeneraddress =  
    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
// Create a binding and set AcceptCredentialsInUri to true  
SAPBinding binding = new SAPBinding();  
binding.AcceptCredentialsInUri = true;  
  
// Create an InboundActionCollection and add the message actions to listen for,  
// only the actions added to the InboundActionCollection are received on the channel.  
// In this case a single action is specified: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
  
// Create a BindingParameterCollection and add the InboundActionCollection  
BindingParameterCollection bpcol = new BindingParameterCollection();  
bpcol.Add(actions);  
  
// Create the channel listener by specifying the binding parameter collection (to filter for the Z_RFC_MKD_DIV action)  
listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
```  
  
### <a name="manually-filtering-operations"></a>手動でフィルター処理  
 チャネル リスナーを受信アクションのコレクションを指定しない場合、SAP システムによって呼び出されるすべての操作はコードに渡すされます。 手動で、受信要求のメッセージのアクションを確認してこのような操作をフィルター処理することができます。  
  
 そのコンテンツに基づいて操作をフィルター処理するシナリオもあります。 例での Idoc を受信している場合。  
  
- 文字列の形式 (、 **ReceiveIDocFormat**プロパティのバインドは**文字列**) すべて; ReceiveIdoc 操作を使用して Idoc を受信します。  
  
- Rfc 形式 (、 **ReceiveIDocFormat**プロパティのバインドは**Rfc**) すべて; IDOC_INBOUND_ASYNCHRONOUS RFC または INBOUND_IDOC_PROCESS RFC を使用して Idoc を受信します。  
  
  実装するこのシナリオでは、IDOC の種類) など、コード内の特定の IDOC パラメーターに基づくフィルター処理します。  
  
  操作を手動でフィルター処理する場合にエラーを返すことができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]処理しない操作。 これにより、SAP システムの呼び出し元に例外の例外が発生します。 SAP で例外が発生しない場合は、空の応答を返すこともできます。  
  
  次のコードでは、Z_RFC_MKD_DIV 操作を手動でフィルター処理する方法を示します。  
  
```  
// Get the message from the channel  
RequestContext rc = channel.ReceiveRequest();  
Message reqMessage = rc.RequestMessage;  
  
// Filter based on the message action.  
if (reqMessage.Headers.Action == "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV")  
{  
  
    // Process message and return response.  
    ...  
  
}  
else  
{  
    // If this isn't the correct message return an empty response or a fault message.  
    // This example returns an empty response.  
    rc.Reply(Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response"));  
}  
```  
  
## <a name="how-do-i-raise-an-exception-on-the-sap-system"></a>SAP システムで例外を発生させる方法  
 SAP システムの呼び出し元にエラーを示すには、SOAP エラーで要求メッセージに返信することができます。 SOAP エラーに戻ったら、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプターは、SAP システムで、呼び出し元に例外例外を返します。 例外メッセージは、SOAP エラーの要素から作成されます。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次の優先順位に従って SAP 例外のメッセージを作成します。  
  
1.  SOAP エラーに詳細オブジェクトが含まれている場合は、アダプターを文字列の詳細をシリアル化し、例外メッセージは、この文字列に設定されます。  
  
2.  SOAP エラーに理由が含まれている場合、例外メッセージは、その値に設定されます。  
  
3.  それ以外の場合、アダプターがシリアル化、 **MessageFault**文字列および例外メッセージをオブジェクト自体がこの文字列に設定します。  
  
> [!NOTE]
>  アダプターでは、SAP システムで発生する例外で返された例外メッセージを作成するのにエラー メッセージのみが使用します。そのため、これらのエンティティに設定した値は、責任は完全にです。  
  
 WCF の提供、 **System.ServiceModel.Channels.MessageFault**の SOAP エラー、メモリ内表現をカプセル化するクラス。 Static のいずれかを使用するオーバー ロードされた**MessageFault.CreateFault**元となることができますし、エラー メッセージを作成するを呼び出して、適切な新しい SOAP エラーを作成するメソッドを**Message.CreateMessage**オーバー ロードします。 WCF は、のオーバー ロードも用意されています。 **CreateMessage**を使用せず、エラー メッセージを作成する、 **MessageFault**オブジェクト。  
  
 使用する、 **System.ServiceModel.Channels.RequestContext.Reply**をアダプターにフォールト メッセージを返すメソッド。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージのアクションを任意の値に設定できるように、エラー メッセージのメッセージのアクションは無視されます。  
  
 次の例にエラー メッセージを返す方法を示しています、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 この例では、チャネル リスナーとチャネルを作成する手順を省略します。  
  
```  
RequestContext rc = channel.ReceiveRequest();  
…  
// Start processing the inbound message  
…  
// If an error is encountered return a fault to the SAP system  
// This example uses CreateMessage overload to create a fault message.  
// The overload takes a SOAP version, fault code, reason, and message action  
// The SAP adapter ignores the message action for a fault so you can set it to any value you want.   
Message faultMessage = Message.CreateMessage(MessageVersion.Default, new FaultCode("SAP Example Fault"), "Testing SAP Faults", rc.RequestMessage.Headers.Action + "/fault");  
  
rc.Reply(faultMessage);  
```  
  
## <a name="streaming-inbound-flat-file-idocs-from-the-sap-adapter"></a>受信フラット ファイル Idoc を SAP アダプターからストリーミング  
 (String) Idoc 受信 ReceiveIdoc 操作でアダプターからのフラット ファイルが表示されます。 IDOC データは、この操作で 1 つのノードの下の文字列として表されます。 このため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ノード値の要求メッセージのストリーミングをサポートしています。 ノード値のストリーミングを実行するのには、呼び出すことによって ReceiveIdoc 操作の要求メッセージを使用する必要があります、 **Message.WriteBodyContents**メソッドを**System.Xml.XmlDictionaryWriter**ですIDOC データをストリーミングすることができます。 これを行う方法については、次を参照してください。 [WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc のストリーミング](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)します。  
  
## <a name="how-do-i-receive-operations-from-a-sap-system-using-an-ireplychannel"></a>IReplyChannel を使用して SAP システムから操作を受信する方法  
 WCF チャネル モデルを使用して、SAP システムから操作を受信するには、次の手順を実行します。  
  
#### <a name="to-receive-operations-from-the-sap-system-using-an-ireplychannel"></a>操作を IReplyChannel を使用して、SAP システムから受信するには  
  
1.  インスタンスを作成**SAPBinding**を受信する操作に必要なバインドのプロパティを設定します。 設定する必要がありますには、少なくとも、 **AcceptCredentialsInUri**プロパティを true にバインドします。 TRFC サーバーとして機能しを設定する必要があります、 **TidDatabaseConnectionString**プロパティをバインドします。 バインド プロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
    ```  
    SAPBinding binding = new SAPBinding();  
    binding.AcceptCredentialsInUri = true;  
    ```  
  
2.  作成、 **BindingParameterCollection**を追加し、 **InboundActionCollection**を受信する操作のアクションを格納しています。 アダプターでは、その他のすべての操作の SAP システムに例外を返します。 このステップは省略可能です。 詳細については、次を参照してください。 [WCF チャネル モデルを使用して、SAP システムからの受信操作の受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)します。  
  
    ```  
    InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
    actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
    BindingParameterCollection bpcol = new BindingParameterCollection();  
    bpcol.Add(actions);  
    ```  
  
3.  呼び出してチャネル リスナーを作成して**BuildChannelListener < IReplyChannel\>** メソッドを**SAPBinding**を開きます。 このメソッドにパラメーターの 1 つとして、SAP 接続 URI を指定します。 接続 URI は、SAP システムの RFC 転送先のパラメーターを含める必要があります。 SAP 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。 作成した場合、 **BindingParameterCollection**手順 3 で指定することもこのチャネル リスナーを作成するときにします。  
  
    ```  
    Uri listeneraddress =  
        new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
    IChannelListener<IReplyChannel> listener = binding.BuildChannelListener<IReplyChannel>(connectionUri, bpcol);  
    listener.Open();  
    ```  
  
4.  取得、 **IReplyChannel**チャネルを呼び出すことによって、 **AcceptChannel**メソッド リスナーを開きます。  
  
    ```  
    IReplyChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
5.  呼び出す**ReceiveRequest**で次の操作をアダプターから要求メッセージを取得するチャネル。  
  
    ```  
    RequestContext rc = channel.ReceiveRequest();  
    ```  
  
6.  アダプターによって送信された要求メッセージを消費します。 要求メッセージを取得する、 **RequestMessage**のプロパティ、 **RequestContext**します。 いずれかを使用してメッセージを処理することができます、 **XmlReader**または**XmlDictionaryWriter**します。  
  
    ```  
    XmlReader reader = (XmlReader)rc.RequestMessage.GetReaderAtBodyContents();  
    ```  
  
7.  SAP システムへの応答またはエラーを返すことによって、操作を完了します。  
  
    1.  メッセージを処理し、アダプターに応答メッセージを返すことによって、SAP システムへの応答を返します。 この例では、空のメッセージを返します。  
  
        ```  
        respMessage = Message.CreateMessage(MessageVersion.Default, rc.RequestMessage.Headers.Action + "/response");  
        rc.Reply(respMessage);  
        ```  
  
    2.  SAP システムをアダプターにフォールト メッセージを返すことによって、例外を返します。 メッセージのアクション、エラー コード、および理由は、任意の値を使用できます。  
  
        ```  
        MessageFault fault = MessageFault.CreateFault(new FaultCode("ProcFault"), "Processing Error");  
        Message respMessage = Message.CreateMessage(MessageVersion.Default, fault, String.Empty);  
        rc.Reply(respMessage);  
        ```  
  
8.  メッセージを送信した後は、要求コンテキストを閉じます。  
  
    ```  
    rc.Close();  
    ```  
  
9. 要求の処理が完了したら、チャネルを閉じます。  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  操作の処理が完了した後、チャネルを閉じる必要があります。 チャネルを閉じない、コードの動作に影響を与える可能性があります。  
  
10. SAP システムからの操作の受信が完了したら、リスナーを閉じます。  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  完了したら、リスナーを明示的に閉じる必要がありますを使用します。それ以外の場合、プログラムが適切に動作しない可能性があります。 リスナーを閉じる、リスナーを使用して作成されるチャネルは閉じられません。 各チャネル リスナーを使用して作成を明示的に閉じる必要があります。  
  
### <a name="example"></a>例  
 次の例では、RFC、SAP システムから Z_RFC_MKD_DIV を受信します。 この RFC では、2 つの数値を除算します。 この例では実装を使用して、 **InboundActionCollection** Z_RFC_MKD_DIV 操作とは、次のメッセージが受信したときにフィルターを適用します。  
  
-   除数がゼロ以外の場合は、除算の結果をコンソールに出力し、SAP システムを返します。  
  
-   除数がゼロの場合、結果の例外メッセージをコンソールに出力し、SAP システムにエラーを返します。  
  
-   SAP システムによって、他の操作を送信する場合は、コンソールにメッセージを書き込みます。 この場合、アダプター自体は、SAP システムにエラーを返します。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.Runtime.Serialization;  
using System.Xml;  
using System.IO;  
  
// Add WCF, Adapter LOB SDK, and SAP Adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Add this namespace to use Channel Model   
using System.ServiceModel.Channels;  
  
// Include this namespace for Adapter LOB SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// This sample demonstrates using the adapter as an rfc server over a channel.  
// The sample implements an RFC, Z_RFC_MKD_DIV that divides two numbers and returns the result  
// 1)  A SAPBinding instance is created and configured (AcceptCredentialsInUri is set true)  
// 2)  A binding parameter collection is created with an InboundAction collection that specifies  
//     target RFC (Z_RFC_MKD_DIV) so that only messages with this action will be received by the  
//     listener (and channel).  
// 3)  An <IReplyChannel> listener is created from the binding and binding parameter collection  
// 4)  A channel is created and opened to receive a request  
// 6)  When Z_RFC_MKD_DIV is received the two parameters are divided and the parameters and result  
//     are written to the console, then the result is returned to the adapter by using a template  
//     message.  
// 7)  If a divide by 0 occurs the exception message is written to the console and a  
//     fault is returned to the SAP system  
// 8)  If any other operation is received an error message is written to the console and the adapter  
///    returns a fault to the SAP system  
// 9)  IMPORTANT you must close the channel and listener to deregister them from the SAP Program ID.  
namespace SapRfcServerCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Variables to hold the listener and channel  
            IChannelListener<IReplyChannel> listener = null;  
            IReplyChannel channel = null;  
  
            Console.WriteLine("Sample started");  
            Console.WriteLine("Initializing and creating channel listener -- please wait");  
            try  
            {  
  
                // The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
                // and also credentials.  
                Uri listeneraddress =  
                    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
                // Create a binding -- set AcceptCredentialsInUri true  
                SAPBinding binding = new SAPBinding();  
                binding.AcceptCredentialsInUri = true;  
  
                // Create a binding parameter collection with a list of SOAP actions to listen on  
                // in this case: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
                // This ensures that only these actions are received on the channel.  
                InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
                actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
                BindingParameterCollection bpcol = new BindingParameterCollection();  
                bpcol.Add(actions);  
  
                // Pass the Uri and the binding parameter collection (to specify the Z_RFC_MKD_DIV action)  
                listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
  
                Console.WriteLine("Opening listener");  
                // Open the listener  
                listener.Open();  
  
                // Get an IReplyChannel  
                channel = listener.AcceptChannel();  
  
                Console.WriteLine("Opening channel");  
                // Open the channel  
                channel.Open();  
  
                Console.WriteLine("\nReady to receive Z_RFC_MKD_DIV RFC");  
  
                try  
                {  
                    // Get the message from the channel  
                    RequestContext rc = channel.ReceiveRequest();  
  
                    // Get the request message sent by SAP  
                    Message reqMessage = rc.RequestMessage;  
  
                    // get the message body  
                    XmlReader reader = reqMessage.GetReaderAtBodyContents();  
  
                    reader.ReadStartElement("Z_RFC_MKD_DIV");  
                    reader.ReadElementString("DEST");  
                    int x_in = int.Parse(reader.ReadElementString("X"));  
                    int y_in = int.Parse(reader.ReadElementString("Y"));  
                    reader.ReadEndElement();  
  
                    Console.WriteLine("\nRfc Received");  
                    Console.WriteLine("X =\t\t" + x_in);  
                    Console.WriteLine("Y =\t\t" + y_in);  
  
                    Message messageOut = null;  
  
                    try   
                    {  
                        int result_out = x_in/y_in;  
  
                        Console.WriteLine("RESULT =\t" + result_out.ToString());  
  
                        string out_xml = "<Z_RFC_MKD_DIVResponse xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"><RESULT>" + result_out + "</RESULT></Z_RFC_MKD_DIVResponse>";  
                        StringReader sr = new StringReader(out_xml);  
                        reader = XmlReader.Create(sr);  
  
                        // create a response message  
                        // be sure to specify the response action  
                        messageOut = Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response", reader);  
  
                    }  
                    catch (DivideByZeroException ex)  
                    {  
                        Console.WriteLine();  
                        Console.WriteLine(ex.Message + " Returning fault to SAP");  
  
                        // Create a message that contains a fault  
                        // The fault code and message action can be any value  
  
                        messageOut = Message.CreateMessage(MessageVersion.Default, new FaultCode("Fault"), ex.Message, string.Empty);  
                    }  
  
                    // Send the reply  
                    rc.Reply(messageOut);  
  
                    // Close the request context  
                    rc.Close();  
  
                }  
                catch (AdapterException aex)  
                {  
                    // Will get here if the message received was not in the InboundActionCollection  
                    Console.WriteLine();  
                    Console.WriteLine(aex.Message);  
                }  
  
                // Wait for a key to exit  
                Console.WriteLine("\nHit <RETURN> to end");  
                Console.ReadLine();  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the SAP system");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
                // IMPORTANT: close the channel and listener to stop listening on the Program ID  
                if (channel != null)  
                {  
                    if (channel.State == CommunicationState.Opened)  
                        channel.Close();  
                    else  
                        channel.Abort();  
                }  
  
                if (listener != null)  
                {  
                    if (listener.State == CommunicationState.Opened)  
                        listener.Close();  
                    else  
                        listener.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)