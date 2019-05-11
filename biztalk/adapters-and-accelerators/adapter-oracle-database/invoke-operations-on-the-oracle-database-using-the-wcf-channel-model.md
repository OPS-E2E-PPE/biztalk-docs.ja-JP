---
title: WCF チャネル モデルを使用して Oracle データベースに対する操作を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- invoking operations, using the WCF channel model
- WCF channel model, invoking operations
- invoking operations
- operations, invoking
ms.assetid: 6dd95c18-8f78-46d0-8845-b74890614c33
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95220f03bb427d2a849b23e278763d3beb0d3632
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376505"
---
# <a name="invoke-operations-on-the-oracle-database-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して Oracle データベースに対する操作を呼び出す
操作を呼び出すことができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用して、 **IRequestChannel**または**IOutputChannel**図形をアダプターにメッセージを送信します。 基本的なパターンが、バインドを使用して、必要なチャネル形状をチャネル ファクトリを作成するには (**OracleDBBinding**) と接続 URI から作成されたエンドポイント。 作成し、**メッセージ**対象の操作のメッセージ スキーマに準拠した SOAP メッセージを表すインスタンス。 これを送信することができますし、**メッセージ**を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]チャネル ファクトリから作成されたチャネルを使用しています。 使用する場合、 **IRequestChannel**応答が届きます。 Oracle データベースに対する操作の実行に問題がある場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]スロー、 **Microsoft.ServiceModel.Channels.Common.TargetSystemException**します。  
  
 使用して操作を送信する方法の概要については、 **IRequestChannel** WCF を参照してください「クライアント チャネル レベルのプログラミング」 [ http://go.microsoft.com/fwlink/?LinkId=106081](http://go.microsoft.com/fwlink/?LinkId=106081)します。  
  
 このトピックのセクションでは、操作を呼び出してするのに役立つ情報を提供する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF チャネル モデルを使用します。  
  
## <a name="creating-and-consuming-messages-for-outbound-operations"></a>作成および送信操作のメッセージを使用します。  
 に対して操作を呼び出す、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、いずれかを使用して対象の操作の要求メッセージを送信する、 **IRequestChannel**または**IOutputChannel**します。 使用する場合、 **IRequestChannel**アダプターは、応答メッセージで、操作の結果を返します。  
  
 詳細については、要求および応答メッセージ スキーマと、各操作のメッセージ アクションを参照してください。[メッセージとメッセージ スキーマの BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)します。  
  
 要求メッセージを作成し、応答メッセージを使用する方法は、ストリーミングは、ノードまたはノード値のストリーミングがアダプターによって実行されるかどうかを判断します。 これは、さらに、サポートされている操作のエンド ツー エンドの LOB データのストリーミングを実行するかどうか判断します。  
  
### <a name="creating-the-request-message"></a>要求メッセージを作成します。  
 2 つの方法では、要求メッセージを作成できます。  
  
- ノード値に使用できるメッセージを作成するストリーミングを渡す必要がありますでメッセージ本文、 **XmlBodyWriter**ノード値のストリーミングを実装します。  
  
- ノードの使用できるメッセージを作成するストリーミングを渡すことができますでメッセージ本文、 **XmlReader**します。  
  
  通常、ノードと値のエンド ツー エンドの要求メッセージ内での Oracle LOB データのストリーミングをサポートするためにストリーミングを使用します。 この機能をサポートする唯一の操作では、UpdateLOB です。  
  
### <a name="consuming-the-response-message"></a>応答メッセージの使用  
 2 つの方法のいずれかで応答メッセージを使用することができます。  
  
- ストリーミングするノードの値を使用してメッセージを使用して呼び出す必要があります、 **WriteBodyContents**メソッドからの応答でメッセージを渡して、 **XmlDictionaryWriter**ノード値のストリーミングを実装します。  
  
- ノードのストリーミングを使用してメッセージを呼び出すことができますを使用する**GetReaderAtBodyContents**を取得する応答メッセージで、 **XmlReader**します。  
  
  通常、ノードと値のエンド ツー エンドの応答メッセージでの Oracle LOB データのストリーミングをサポートするためにストリーミングを使用します。 この機能をサポートする多くの操作があります。  
  
### <a name="lob-data-and-message-streaming-support"></a>LOB データおよびメッセージのストリーミング サポート  
 方法の詳細については[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]LOB データのストリーミング サポートを参照してください[Oracle データベース アダプターのラージ オブジェクト データ型のストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)します。  
  
 ノード値のエンド ツー エンドの LOB データのストリーミングをサポートするために、コードでは、ストリーミングの実装の詳細については、次を参照してください。[ストリーミング Oracle LOB データ型を使用してデータベース、WCF チャネル モデル](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)します。  
  
## <a name="transaction-support-on-outbound-operations-in-the-wcf-channel-model"></a>WCF チャネル モデルでの送信操作でトランザクションのサポート。  
 アダプターは、Oracle データベースで専用のトランザクション内で呼び出す各操作を実行します。 これらのトランザクションの分離レベルを設定して制御することができます、 **TransactionIsolationLevel**プロパティをバインドします。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、SCOTT を使用します。ACCOUNTACTIVITY テーブルです。 これらの成果物を生成するスクリプトは SDK のサンプルで提供されます。 SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)します。  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a>チャネルを使用して、操作を呼び出す方法  
 使用して、操作を呼び出す、 **IRequestChannel**、次の手順に従います。  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a>IRequestChannel のインスタンスを使用して、操作を呼び出す方法  
  
1. チャネル ファクトリの作成 (**ChannelFactory\<IRequestChannel\>**)。 これを行うには、バインドを指定する必要があります (**OracleDBBinding**) とエンドポイント アドレス。 コードで強制的に、または構成で宣言によって、バインディングとエンドポイント アドレスを指定できます。 構成でバインディングとエンドポイント アドレスを指定する方法の詳細については、次を参照してください。 [Oracle データベースを使用してチャネルを作成](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)です。  
  
   ```  
   // Create a binding  
   OracleDBBinding binding = new OracleDBBinding();  
   // Create an endpoint address by using the connection URI  
   EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
   // Create the channel factory  
   ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
   ```  
  
2. 使用してチャネル ファクトリの名前のパスワード資格情報をユーザーに設定、 **ClientCredentials**プロパティ。  
  
   ```  
   factory.Credentials.UserName.UserName = "SCOTT";  
   factory.Credentials.UserName.Password = "TIGER";  
   ```  
  
3. チャネル ファクトリを開きます。  
  
   ```  
   factory.Open();  
   ```  
  
4. ファクトリからチャネルを取得し、開きます。  
  
   ```  
   IRequestChannel channel = factory.CreateChannel();  
   channel.Open();  
   ```  
  
5. 作成、**メッセージ**対象の操作のインスタンス。 対象の操作のメッセージのアクションが指定されていることを確認します。 作成して、この例では、メッセージ本文が渡される、 **XmlReader**ファイル。 対象の操作は、SCOTT/EMP テーブルでの選択操作です。  
  
   ```  
   XmlReader readerIn = XmlReader.Create("SelectAllActivity.xml");  
   Message messageIn = Message.CreateMessage(MessageVersion.Default,  
       "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
       readerIn);  
   ```  
  
6. 呼び出す、**要求**メソッドにメッセージを送信するチャネルを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]したり応答を受け取ったりします。 Oracle データベースには、例外が発生すると、アダプターがスローされます、 **TargetSystemException**します。 (その他の例外は、以外の Oracle の例外の考えられる)。Oracle のエラーの説明を取得することができます、 **InnerException.Message**のプロパティ、 **TargetSystemException**します。  
  
   ```  
   try  
   {  
       Message messageOut = channel.Request(messageIn);  
   }  
   catch (Exception ex)  
   {  
       // handle exception  
   }  
   ```  
  
7. 応答を処理します。 この例で**GetReaderAtBodyContents**がメッセージの本文を取得する応答メッセージで呼び出されます。  
  
   ```  
   XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
   ```  
  
8. 完了したら、応答メッセージの処理リーダーおよびメッセージを閉じます。  
  
   ```  
   readerOut.Close();  
   messageOut.Close();  
   ```  
  
9. 完了したら、チャネルとチャネル ファクトリを使用して終了しますか。 ファクトリを閉じることで作成されたすべてのチャネルが閉じられます。  
  
    ```  
    channel.Close()  
    factory.Close();  
  
    ```  
  
   使用してメッセージを送信するのと同じ手順を行う、 **IOutputChannel**以外の図形します。  
  
-   作成する、 **ChannelFactory\<IOutputChannel\>** 手順 1 でします。  
  
-   呼び出す、**送信**手順 6. で、チャネル上のメソッド。 `channel.Send(messageIn);`。  
  
-   返される応答メッセージが表示されない、 **IOutputChannel**します。  
  
### <a name="example"></a>例  
 次の例を使用して、選択操作を呼び出す方法を示しています、 **IRequestChannel**チャネル。 使用して、応答メッセージが使用される、 **XmlReader**し、返されるレコードの数は、コンソールに書き込まれます。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
using System.Xml;  
using System.IO;  
using System.Runtime.Serialization;  
  
namespace RequestChanneSample  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The Select operation request message  
            const string selectRequestString =  
                "\<Select xmlns=\"http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY\"\>" +  
                    "<COLUMN_NAMES>*</COLUMN_NAMES>" +  
                    "<FILTER>ACCOUNT = 100002</FILTER>" +  
                "</Select>";  
            try  
            {  
                // Create binding -- specify binding properties before you open the factory.  
                OracleDBBinding odbBinding = new OracleDBBinding();  
  
                // Create address.  
                EndpointAddress odbAddress = new EndpointAddress("oracledb://ADAPTER/");  
  
                // Create channel factory from binding and address.  
                ChannelFactory<IRequestChannel> factory =   
                    new ChannelFactory<IRequestChannel>(odbBinding, odbAddress);  
  
                // Specify credentials   
                factory.Credentials.UserName.UserName = "SCOTT";  
                factory.Credentials.UserName.Password = "TIGER";  
  
                // Open the factory.  
                factory.Open();  
  
                // Get a channel.  
                IRequestChannel channel = factory.CreateChannel();  
  
                // Open the channel.  
                channel.Open();  
  
                // Create the request message from the string  
                StringReader strReader = new StringReader(selectRequestString);  
                XmlReader readerIn = XmlReader.Create(strReader);  
  
                Message requestMessage = Message.CreateMessage(MessageVersion.Default,  
                    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
                    readerIn);  
  
                Send the message and get a respone  
                Message responseMessage = channel.Request(requestMessage);  
  
                // Get an XmlReader from the message  
                XmlReader readerOut = (XmlReader) responseMessage.GetReaderAtBodyContents();  
  
                // Count the number of records returned and write to the console.  
                readerOut.MoveToContent();  
                int numberOfRecordsReturned = 0;  
                while (readerOut.Read())  
                {  
                    if (readerOut.NodeType == XmlNodeType.Element && readerOut.Name == "ACCOUNTACTIVITYRECORDSELECT")  
                        numberOfRecordsReturned++;  
                }  
  
                Console.WriteLine("{0} records returned.", numberOfRecordsReturned);  
  
                // Close the output reader and message  
                readerOut.Close();  
                responseMessage.Close();  
  
                //Close channel  
                channel.Close();  
  
                //Close the factory  
                factory.Close();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)