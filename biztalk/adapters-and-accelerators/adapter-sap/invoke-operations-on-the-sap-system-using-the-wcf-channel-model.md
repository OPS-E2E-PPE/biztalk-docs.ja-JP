---
title: WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す |Microsoft ドキュメント
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
ms.openlocfilehash: 1030e0a743a9b06d856bc593198f4afebc1ffa38
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965624"
---
# <a name="invoke-operations-on-the-sap-system-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す
に対して操作を呼び出す、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用して、 **IRequestChannel**または**IOutputChannel**チャネル形状をアダプターにメッセージを送信します。 基本的なパターンは、バインドを使用して、必要なチャネル形状をチャネル ファクトリを作成する (**SAPBinding**) と接続 URI から作成されたエンドポイント。 作成し、**メッセージ**をターゲットの操作用のメッセージ スキーマに準拠する SOAP メッセージを表すインスタンス。 これを送信することができますし、**メッセージ**を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]チャネル ファクトリから作成されたチャネルを使用しています。 使用している場合、 **IRequestChannel**応答を受信します。 SAP システムで操作の実行に問題がある場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]スロー、 **Microsoft.ServiceModel.Channels.Common.TargetSystemException**です。  
  
 使用して操作を送信する方法の概要については、 **IRequestChannel** WCF では、次を参照してください。[クライアント チャネル レベルのプログラミング](https://msdn.microsoft.com/library/ms788970.aspx)です。  
  
 このトピックのセクションでは、操作の呼び出しに役立つ情報を提供する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF チャネル モデルを使用します。  
  
## <a name="supporting-bapi-transactions-in-the-wcf-channel-model"></a>WCF チャネル モデルでの BAPI のトランザクションのサポート  
 SAP システムで、同じ論理ユニットの作業 (LUW) またはトランザクションの一部であるすべての Bapi の同じ SAP 接続を使用して呼び出されます。 各 WCF チャネルは、SAP システムへの一意の接続を表します。 サポートするためには、WCF を使用して BAPI トランザクションは、モデルをチャネルします。  
  
-   すべての BAPI、LUW (トランザクション) でが同じチャネル経由で送信されることを確認します。 これには、BAPI_TRANSACTION コミットまたは BAPI_TRANSACTION_ROLLBACK 操作が含まれます。  
  
-   チャネルで [次へ] の BAPI を呼び出す前に、BAPI を受信した応答メッセージを閉じることを確認します。 (すべての操作を行いますが Bapi にとって特に重要である)。  
  
 BAPI のトランザクションの詳細については、次を参照してください。 [SAP での Bapi の操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)です。  
  
## <a name="streaming-flat-file-idocs-to-the-sap-adapter"></a>ストリーミングのフラット ファイル Idoc を SAP アダプター  
 SendIdoc 操作を使用して、フラット ファイル (string) IDOC をアダプターに送信します。 IDOC データは、この操作で 1 つのノードの下の文字列として表されます。 このため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ノード値の要求メッセージのストリーミングをサポートします。 ノード値のストリーミングを実行するのを使用して SendIdoc 操作の要求メッセージを作成する必要があります、 **System.ServiceModel.Channels.BodyWriter**が IDOC データをストリーミング可能です。 これを行う方法については、次を参照してください。 [WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc のストリーミング](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)です。  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a>チャネルを使用して、操作を呼び出す方法  
 使用して、操作を呼び出す、 **IRequestChannel**、次の手順を実行します。  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a>IRequestChannel のインスタンスを使用して、操作を呼び出す方法  
  
1.  チャネル ファクトリを作成 (**ChannelFactory\<IRequestChannel\>**)。 これを行うには、バインドを指定する必要があります (**SAPBinding**) およびエンドポイント アドレス。 コードで命令として記述または構成で宣言によって、バインドとエンドポイント アドレスを指定できます。 プロパティは、送信すること、ファクトリを開く前に、操作に必要な任意のバインディングを設定する必要があります。 構成でバインディングとエンドポイント アドレスを指定する方法の詳細については、次を参照してください。 [SAP を使用して、チャネルの作成](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)です。  
  
    ```  
    // Create a binding  
    SAPBinding binding = new SAPBinding();  
    // Create an endpoint address by using the connection URI  
    EndpointAddress endpointAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
    // Create the channel factory  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    ```  
  
2.  使用してチャネル ファクトリの名前のパスワードの資格情報をユーザーに設定、 **ClientCredentials**プロパティです。  
  
    ```  
    factory.Credentials.UserName.UserName = "YourUserName";  
    factory.Credentials.UserName.Password = "YourPassword";  
    ```  
  
3.  チャネル ファクトリを開きます。  
  
    ```  
    factory.Open();  
    ```  
  
4.  工場出荷時にチャネルを取得し、開きます。  
  
    ```  
    IRequestChannel channel = factory.CreateChannel();  
    channel.Open();  
    ```  
  
5.  作成、**メッセージ**ターゲット操作のインスタンス。 ターゲットの操作のメッセージ アクションが指定されていることを確認します。 この例では、メッセージ本文が作成することで渡される、 **XmlReader**文字列にします。 ターゲットの操作では、SAP システムで SD_RFC_CUSTOMER_GET RFC を呼び出します。  
  
    ```  
    string inputXml = "\<SD_RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
    //create an XML reader from the input XML  
    XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
    //create a WCF message from our XML reader  
    Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
    ```  
  
6.  呼び出す、**要求**メッセージを送信するチャネルのメソッド、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]と返信を受信します。 SAP システムには、例外が発生すると、アダプターをスロー、 **TargetSystemException**です。 (その他の例外は、非 SAP 例外の)。SAP からのエラーの説明を取得できます、 **InnerException.Message**のプロパティ、 **TargetSystemException**です。  
  
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
  
7.  応答を処理します。 この例では**GetReaderAtBodyContents**メッセージ本文を取得する応答メッセージで呼び出されるとします。  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    ```  
  
8.  完了したら、リーダーとメッセージを閉じる、応答メッセージを処理します。  
  
    ```  
    readerOut.Close();  
    messageOut.Close();  
    ```  
  
9. 完了すると、チャネルおよびチャネル ファクトリを使用してそれらを閉じます。 ファクトリを閉じると、それを使用して作成されたすべてのチャネルが閉じられます。  
  
    ```  
    channel.Close()  
    factory.Close();  
    ```  
  
10.  
  
 同じ手順を使用してメッセージを送信する、 **IOutputChannel**以外の図形します。  
  
-   作成する、 **ChannelFactory\<IOutputChannel\>** 手順 1 でします。  
  
-   呼び出す、**送信**手順 6. でチャネル上のメソッドです。 `channel.Send(messageIn);`」をご覧ください。  
  
-   に対して返される応答メッセージが表示されない、 **IOutputChannel**です。  
  
### <a name="example"></a>例  
 次の例を使用して、RFC を呼び出す方法を示しています、 **IRequestChannel**チャネル。 この例では、"AB"で始まる名前の顧客の一覧を取得する SD_RFC_CUSTOMER_GET RFC を呼び出します。 使用して、応答メッセージが表示される、 **XmlReader**し、顧客番号と返される各顧客の名前は、コンソールに書き込まれます。  
  
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