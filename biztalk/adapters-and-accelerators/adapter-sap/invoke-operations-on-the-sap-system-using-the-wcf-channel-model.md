---
title: WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, supporting BAPI transactions
- WCF channel model, invoking operations on the SAP system
ms.assetid: 80ed85ff-360d-4b7f-a119-cd2a99c21cf4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 408d2ce053a30a4692b6e17a73087b13c648ab2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997339"
---
# <a name="invoke-operations-on-the-sap-system-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す
操作を呼び出す、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用して、 **IRequestChannel**または**IOutputChannel**チャネル形状は、アダプターにメッセージを送信します。 基本的なパターンが、バインドを使用して、必要なチャネル形状をチャネル ファクトリを作成するには (**SAPBinding**) と接続 URI から作成されたエンドポイント。 作成し、**メッセージ**対象の操作のメッセージ スキーマに準拠した SOAP メッセージを表すインスタンス。 これを送信することができますし、**メッセージ**を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]チャネル ファクトリから作成されたチャネルを使用しています。 使用する場合、 **IRequestChannel**応答が届きます。 SAP システムの操作の実行に問題がある場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]スロー、 **Microsoft.ServiceModel.Channels.Common.TargetSystemException**します。  
  
 使用して操作を送信する方法の概要については、 **IRequestChannel** WCF では、次を参照してください。[クライアント チャネル レベルのプログラミング](https://msdn.microsoft.com/library/ms788970.aspx)します。  
  
 このトピックのセクションでは、操作を呼び出してするのに役立つ情報を提供する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF チャネル モデルを使用します。  
  
## <a name="supporting-bapi-transactions-in-the-wcf-channel-model"></a>WCF チャネル モデルでの BAPI トランザクションのサポート  
 SAP システムで、同じ論理ユニットの作業 (LUW) またはトランザクションの一部であるすべての Bapi の同じ SAP 接続を使用して呼び出されます。 各 WCF チャネルは、SAP システムに一意の接続を表します。 BAPI トランザクションがを WCF を使用してチャネルをサポートするには、モデルの。  
  
- すべての BAPI を LUW (トランザクション) でが同じチャネル経由で送信されることを確認します。 これには、BAPI_TRANSACTION コミットまたは BAPI_TRANSACTION_ROLLBACK 操作が含まれます。  
  
- チャネルで、[次へ] の BAPI を呼び出す前に、BAPI の受信した応答メッセージを閉じることを確認します。 (すべての操作に対して、これを行う必要がありますが Bapi にとって特に重要ですが)。  
  
  BAPI トランザクションの詳細については、次を参照してください。 [SAP の Bapi に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)します。  
  
## <a name="streaming-flat-file-idocs-to-the-sap-adapter"></a>ストリーミングのフラット ファイル Idoc を SAP アダプター  
 フラット ファイル (string) IDOC をアダプターに送信するのにには、SendIdoc 操作を使用します。 IDOC データは、この操作で 1 つのノードの下の文字列として表されます。 このため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ノード値の要求メッセージのストリーミングをサポートしています。 ノード値のストリーミングを実行するのを使用して SendIdoc 操作の要求メッセージを作成する必要があります、 **System.ServiceModel.Channels.BodyWriter**が IDOC データをストリーミングできます。 これを行う方法については、次を参照してください。 [WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc のストリーミング](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)します。  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a>チャネルを使用して、操作を呼び出す方法  
 使用して、操作を呼び出す、 **IRequestChannel**、次の手順に従います。  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a>IRequestChannel のインスタンスを使用して、操作を呼び出す方法  
  
1. チャネル ファクトリの作成 (**ChannelFactory\<IRequestChannel\>**)。 これを行うには、バインドを指定する必要があります (**SAPBinding**) とエンドポイント アドレス。 コードで強制的に、または構成で宣言によって、バインディングとエンドポイント アドレスを指定できます。 プロパティは、送信すること、ファクトリを開く前に、操作に必要な任意のバインディングを設定する必要があります。 構成でバインディングとエンドポイント アドレスを指定する方法の詳細については、次を参照してください。 [SAP を使用してチャネルを作成](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)です。  
  
   ```  
   // Create a binding  
   SAPBinding binding = new SAPBinding();  
   // Create an endpoint address by using the connection URI  
   EndpointAddress endpointAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
   // Create the channel factory  
   ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
   ```  
  
2. 使用してチャネル ファクトリの名前のパスワード資格情報をユーザーに設定、 **ClientCredentials**プロパティ。  
  
   ```  
   factory.Credentials.UserName.UserName = "YourUserName";  
   factory.Credentials.UserName.Password = "YourPassword";  
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
  
5. 作成、**メッセージ**対象の操作のインスタンス。 対象の操作のメッセージのアクションが指定されていることを確認します。 作成して、この例では、メッセージ本文が渡される、 **XmlReader**経由での文字列。 対象の操作では、SAP システムで SD_RFC_CUSTOMER_GET RFC を呼び出します。  
  
   ```  
   string inputXml = "\<SD_RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
   //create an XML reader from the input XML  
   XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
   //create a WCF message from our XML reader  
   Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
   ```  
  
6. 呼び出す、**要求**メソッドにメッセージを送信するチャネルを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]したり応答を受け取ったりします。 SAP システムには、例外が発生すると、アダプターがスローされます、 **TargetSystemException**します。 (その他の例外は、SAP ではない例外の可能性)。SAP からのエラーの説明を取得できます、 **InnerException.Message**のプロパティ、 **TargetSystemException**します。  
  
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
  
10. 
  
    使用してメッセージを送信するのと同じ手順を行う、 **IOutputChannel**以外の図形します。  
  
-   作成する、 **ChannelFactory\<IOutputChannel\>** 手順 1 でします。  
  
-   呼び出す、**送信**手順 6. で、チャネル上のメソッド。 `channel.Send(messageIn);`。  
  
-   返される応答メッセージが表示されない、 **IOutputChannel**します。  
  
### <a name="example"></a>例  
 次の例を使用して、RFC を呼び出す方法を示しています、 **IRequestChannel**チャネル。 この例では、"AB"で始まる名前の顧客の一覧を取得する SD_RFC_CUSTOMER_GET RFC を呼び出します。 使用して、応答メッセージが表示される、 **XmlReader**し、返された各顧客の名前と顧客の数は、コンソールに書き込まれます。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.Xml;  
using System.IO;  
  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel.Channels;  
  
namespace SapRfcClientCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //create a binding  
            SAPBinding binding = new SAPBinding();  
  
            //set up an endpoint address.  
            EndpointAddress endpointAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
            //create a channel factory, capable of sending a request to SAP and receiving a reply (IRequestChannel)  
            ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress);  
  
            // add credentials  
            factory.Credentials.UserName.UserName = "YourUserName";  
            factory.Credentials.UserName.Password = "YourPassword";  
  
            //open the factory  
            factory.Open();  
  
            //obtain a channel from the factory by specifying the address you want to connect to  
            IRequestChannel channel = factory.CreateChannel();  
  
            //open the channel  
            channel.Open();  
  
            //create an XML message to send to the SAP system  
            //We are invoking the SD_RFC_CUSTOMER_GET RFC.  
            //The XML below specifies that we want to search for customers with names starting with "AB"  
            string inputXml = "<SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
            //create an XML reader from the input XML  
            XmlReader readerOut = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
            //create a WCF message from the XML reader  
            Message messageOut = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", readerOut);  
  
            //send the message to SAP and obtain a reply  
            Message messageIn = channel.Request(messageOut);  
  
            // Write the KUNNR and NAME1 fields for each returned record to the Console  
            Console.WriteLine("Results of SD_RFC_CUSTOMER_GET");  
            Console.WriteLine("KUNNR\t\tNAME1");  
  
            XmlReader readerIn = messageIn.GetReaderAtBodyContents();  
  
            while (readerIn.Read())  
            {  
                if (readerIn.IsStartElement())  
                {  
                    switch (readerIn.Name)  
                    {  
                        case "RFCCUST":  
                            Console.Write("\n");  
                            break;  
  
                        case "KUNNR":  
                            readerIn.Read();  
                            Console.Write(readerIn.ReadString() + "\t");  
                            break;  
  
                        case "NAME1":  
                            readerIn.Read();  
                            Console.Write(readerIn.ReadString() + "\t");  
                            break;  
  
                        default:  
                            break;  
                    }  
                }  
            }  
  
            // return the cursor  
            Console.WriteLine();  
  
            // Close the input reader  
            readerIn.Close();  
  
            // Close the input message. You should do this for every message you   
            // send on the channel  
            messageIn.Close();  
  
            // close the channel when you are done using it.  
            channel.Close();  
  
            //close the factory  
            //note: closing the factory will close all of its channels.  
            factory.Close();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)