---
title: WCF チャネル モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, receiving polling-based messages
- how to, receive polling-based messages by using the WCF channel model
ms.assetid: 13f501e4-cff7-497c-a9da-fdd6382c779f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03973baf5c55d4f6b5caa3ef28ce0e11b0cd4fa1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969675"
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージを受信します。
構成することができます、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースのテーブルまたはビューのデータ変更をポーリングします。 アダプターには、このようなポーリング操作を実行するには、Oracle のテーブルまたはビューが続く省略可能の PL/SQL コード ブロックをに対して SQL クエリを定期的に実行します。 によって SQL クエリの結果が返されるし、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]受信 POLLINGSTMT 操作の設定、厳密に型指定された結果として、コードにします。 使用してデータベースを構成し、Oracle のポーリングを実行するためのメカニズムの詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)します。 続行する前に、このトピックで確認することを強くお勧めします。  
  
 構成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ポーリングと Oracle データベースのテーブルまたはビューのインスタンスにバインドのプロパティを設定して**OracleDBBinding**します。 WCF チャネル モデルで、このバインディングを使用する取得できますチャネル リスナーを作成、 **IInputChannel** POLLINGSTMT 操作をアダプターから受信するチャネル。  
  
 受信操作を使用する方法の概要については、 **IInputChannel** WCF では、次を参照してください。[サービス チャネル レベルのプログラミング](https://msdn.microsoft.com/library/ms789029.aspx)します。 
  
 このトピックのセクションでは、Oracle データベースのテーブルのポーリングを実行するために情報を提供して、WCF を使用して、ビュー モデルのチャネルします。  
  
## <a name="consuming-the-pollingstmt-request-message"></a>POLLINGSTMT 要求メッセージの使用  
 アダプターは、Oracle データベースをポーリングする、コードに POLLINGSTMT 操作を呼び出します。 つまり、アダプターが経由で受信した POLLINGSTMT 要求メッセージを送信、 **IInputChannel**チャネル形状です。 POLLINGSTMT 要求メッセージにはで指定されたクエリの結果セットが含まれています、 **PollingStatement**プロパティをバインドします。 2 つの方法のいずれかで POLLINGSTMT メッセージを使用できます。  
  
- ストリーミングするノードの値を使用してメッセージを使用して呼び出す必要があります、 **WriteBodyContents**メソッドからの応答でメッセージを渡して、 **XmlDictionaryWriter**ノード値のストリーミングを実装します。  
  
- ノードのストリーミングを使用してメッセージを呼び出すことができますを使用する**GetReaderAtBodyContents**を取得する応答メッセージで、 **XmlReader**します。  
  
  通常、ノードと値のデータ列を Oracle LOB を含む結果セットを使用するストリーミングを使用します。  
  
  POLLINGSTMT 操作のメッセージ構造の詳細については、次を参照してください。[ポーリング操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)します。  
  
  方法の詳細については[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]LOB データのストリーミング サポートを参照してください[Oracle データベース アダプターのラージ オブジェクト データ型のストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)します。  
  
  ノード値のエンド ツー エンドの LOB データのストリーミングをサポートするために、コードでは、ストリーミングの実装の詳細については、次を参照してください。[ストリーミング Oracle LOB データ型を使用してデータベース、WCF チャネル モデル](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)します。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、SCOTT を使用します。ACCOUNTACTIVITY テーブルし、SCOTT します。ACCOUNT_PKG します。PROCESS_ACTIVITY 関数。 これらの成果物を生成するスクリプトは、サンプルで提供されます。 例では、次の操作を実行します。  
  
- ポーリング ステートメントの一部として、すべてのレコードを選択する ACCOUNTACTIVITY テーブルと、コンソールに表示されます。  
  
- ポーリング後ステートメントの一部としては、この例は、ACTIVITYHISTORY テーブル ACCOUNTACTIVITY テーブルからすべてのレコードに移動する PROCESS_ACTIVITY 関数を呼び出します。  
  
- ACCOUNTACTIVITY テーブルに対する後続のアンケートでは、すべてのレコードは返されません。 ただし、ポーリング操作の一部として複数のレコードを返す例を実行する場合に、ACCOUNTACTIVITY テーブルで一部のレコードを挿入する必要があります。 サンプルで提供される more_activity_data.sql スクリプトを実行して行うことができます。  
  
  サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。  
  
## <a name="how-do-i-poll-an-oracle-database-using-an-iinputchannel"></a>IInputChannel を使用して Oracle データベースをポーリングする方法は?  
 Oracle データベースのテーブルまたは WCF チャネル モデルを使用して、データ変更メッセージを受信するビューをポーリングするには、次の手順を実行します。  
  
#### <a name="to-receive-data-changed-messages-using-an-iinputchannel"></a>IInputChannel を使用して、データ変更メッセージを受信するには  
  
1. Visual c# プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 このトピックでは、コンソール アプリケーションを作成します。  
  
2. ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleDB`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`します。  
  
3. Program.cs ファイルを開き、次の名前空間を追加します。  
  
   -   `Microsoft.Adapters.OracleDB`  
  
   -   `Microsoft.ServiceModel.Channels`  
  
   -   `System.ServiceModel`  
  
   -   `System.ServiceModel.Description`  
  
   -   `System.ServiceModel.Channels`  
  
   -   `System.Xml`  
  
   -   `System.Runtime.Serialization`  
  
   -   `System.IO`  
  
   -   `Microsoft.ServiceModel.Channels.Common`  
  
4. インスタンスを作成**OracleDBBinding**ポーリングを構成するために必要なバインドのプロパティを設定します。 設定する必要がありますには、少なくとも、 **InboundOperationType**、 **PollingStatement**、および**PollingInterval**プロパティをバインドします。 この例では、設定することも、 **PostPollStatement**プロパティをバインドします。 ポーリングを構成するためのプロパティのバインドの詳細については、次を参照してください。 [Oracle データベース アダプターのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)します。  
  
   ```  
   OracleDBBinding binding = new OracleDBBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PollingInterval = 30;  
   binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
   binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;"  
   ```  
  
5. バインディング パラメーターのコレクションを作成し、資格情報を設定します。  
  
   ```  
   ClientCredentials credentials = new ClientCredentials();  
   credentials.UserName.UserName = "SCOTT";  
   credentials.UserName.Password = "TIGER";  
  
   BindingParameterCollection bindingParams = new BindingParameterCollection();  
   bindingParams.Add(credentials);  
   ```  
  
6. チャネル リスナーを作成し、開きます。 呼び出すことによって、リスナーを作成する**BuildChannelListener < IInputChannel\>** メソッドを**OracleDBBinding**します。 POLLINGSTMT 操作のターゲット名前空間を変更するには、接続 URI の PollingId プロパティを設定します。 アダプターの接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
   ```  
   IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
   listener.Open();  
   ```  
  
7. 取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**メソッド リスナーを開きます。  
  
   ```  
   IInputChannel channel = listener.AcceptChannel();  
   channel.Open();  
   ```  
  
8. 呼び出す**受信**POLLINGSTMT の次のメッセージをアダプターから取得するチャネル。  
  
   ```  
   Message message = channel.Receive();  
   ```  
  
9. POLLINGSTMT 操作によって返される結果セットを使用します。 いずれかを使用してメッセージを処理することができます、 **XmlReader**または**XmlDictionaryWriter**します。  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
10. 要求の処理が完了したら、チャネルを閉じます。  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  POLLINGSTMT 操作の処理が完了した後、チャネルを閉じる必要があります。 チャネルを閉じない、コードの動作に影響を与える可能性があります。  
  
11. データ変更メッセージの受信が完了したら、リスナーを閉じます。  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  リスナーを閉じる、リスナーを使用して作成されるチャネルは閉じられません。 各チャネル リスナーを使用して作成を明示的に閉じる必要があります。  
  
### <a name="example"></a>例  
 次の例は、構成する方法を示します、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF を使用して操作チャネル モデルの Oracle データベースのテーブルおよびビューをポーリングして、POLLLINGSTMT を受信します。 使用して POLLINGSTMT 操作で返される結果がコンソールに書き込まれる、 **XmlReader**します。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Add this namespace for channel model  
using System.ServiceModel.Channels;  
  
using System.Xml;  
using System.Runtime.Serialization;  
using System.IO;  
  
// Include this namespace for the WCF LOB Adapter SDK and Oracle exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
namespace OraclePollingCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Uri connectionUri = new Uri("oracleDB://ADAPTER/");  
  
            IChannelListener<IInputChannel> listener = null;  
            IInputChannel channel = null;  
  
            // set timeout to receive POLLINGSTMT message  
            TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  
  
            Console.WriteLine("Sample Started");  
  
            try  
            {  
                // Create a binding: specify the InboundOperationType, PollingInterval (in seconds), the           
                // PollingStatement,and the PostPollStatement.  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PollingInterval = 30;  
                binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // Create a binding parameter collection and set the credentials  
                ClientCredentials credentials = new ClientCredentials();  
                credentials.UserName.UserName = "SCOTT";  
                credentials.UserName.Password = "TIGER";  
  
                BindingParameterCollection bindingParams = new BindingParameterCollection();  
                bindingParams.Add(credentials);  
  
                Console.WriteLine("Opening listener");  
                // get a listener  from the binding  
                listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
                listener.Open();  
  
                Console.WriteLine("Opening channel");  
                // get a channel from the listener  
                channel = listener.AcceptChannel();  
                channel.Open();  
  
                Console.WriteLine("Channel opened -- waiting for polled data");  
                Console.WriteLine("Receive request timeout is {0}", messageTimeout);  
  
                // Poll five times with the specified message timeout   
                // If a timeout occurs polling will be aborted  
                for (int i = 0; i < 5; i++)  
                {  
                    Console.WriteLine("Polling: " + i);  
                    Message message = null;  
                    XmlReader reader = null;  
                    try  
                    {  
                        //Message is received so process the results  
                        message = channel.Receive(messageTimeout);  
                    }  
                    catch (System.TimeoutException toEx)  
                    {  
                        Console.WriteLine("\nNo data for request number {0}: {1}", i + 1, toEx.Message);  
                        continue;  
                    }  
  
                    // Get the query results using an XML reader  
                    try  
                    {  
                        reader = message.GetReaderAtBodyContents();  
                    }  
                    catch (Exception ex)  
                    {  
                        Console.WriteLine("Exception :" + ex);  
                        throw;  
                    }  
  
                    // Write the TID, ACCOUNT, AMOUNT, and TRANSDATE for each record to the Console  
                    Console.WriteLine("\nPolling data received for request number {0}", i+1);  
                    Console.WriteLine("Tx ID\tACCOUNT\tAMOUNT\tTx DATE");  
  
                    while (reader.Read())  
                    {  
                        if (reader.IsStartElement())  
                        {  
                            switch (reader.Name)  
                            {  
                                case "POLLINGSTMTRECORD":  
                                    Console.Write("\n");  
                                    break;  
  
                                case "TID":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                case "ACCOUNT":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
                                case "AMOUNT":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                case "TRANSDATE":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                default:  
                                    break;  
                            }  
                        }  
                    }  
  
                    // return the cursor  
                    Console.WriteLine();  
  
                    // close the reader  
                    reader.Close();  
  
                    //            To save the polling data to a file you can REPLACE the code above with the following  
                    //  
                    //            XmlDocument doc = new XmlDocument();  
                    //            doc.Load(reader);  
                    //            using (XmlWriter writer = XmlWriter.Create("PollingOutput.xml"))  
                    //            {  
                    //                doc.WriteTo(writer);  
                    //            }  
                    message.Close();  
                }  
  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
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
                // IMPORTANT: close the channel and listener to stop polling  
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
 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)