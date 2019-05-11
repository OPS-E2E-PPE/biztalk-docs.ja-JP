---
title: SELECT ステートメントを使用して、WCF チャネル モデルとポーリング Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495b9010-856f-4782-bd19-1522bc3eb950
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57288b62249e7ba3de7fb9fb8e5667c3247f5829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375007"
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model"></a>SELECT ステートメントを使用して、WCF チャネル モデルとポーリング Oracle E-business Suite
構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を継続的に、インターフェイス テーブルをポーリングする SELECT ステートメントを使用して、定期的なデータ変更メッセージを受信するビュー、テーブル、および Oracle E-business Suite でのビューのインターフェイスします。 Oracle E-business Suite をポーリングするアダプターを定期的に実行するポーリング ステートメントと SELECT ステートメントを指定できます。 ポスト ポーリング PL/SQL コード ブロックを指定することも、アダプターがポーリング ステートメントが実行された後に実行します。  

 ポーリングを有効にする、このトピックの説明に従って、特定のバインド プロパティの条件を指定する必要があります。 アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[受信呼び出しのポーリングを使用してサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)します。  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a>Oracle E-business Suite アダプターのバインドのプロパティをポーリング操作を構成します。  
 次の表にまとめたものです、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージのバインドのプロパティを使用するデータを受信するアダプターの構成を変更します。 ポーリング アプリケーションを実行中に、これらのバインドのプロパティを指定する必要があります。  


|         プロパティのバインド         |                                                                                                                                                                                                                            説明                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                          実行するかどうかを指定します**ポーリング**または**通知**操作を受信します。 既定値は**ポーリング**します。                                                                                                                                                                          |
| **PolledDataAvailableStatement** |                                                                                                             すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 指定した SELECT ステートメントのレコードを使用できる場合にのみ、 **PollingInput**プロパティのバインドが実行されます。                                                                                                              |
|       **PollingInterval**        | 秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔は、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプターが間隔内の残りの時間の間スリープします。 |
|         **PollingInput**         |                         ポーリング ステートメントを指定します。 SELECT ステートメントを使用してポーリングする、このバインドのプロパティの SELECT ステートメントを指定する必要があります。 既定値は null です。<br /><br /> 値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。                          |
|        **PollingAction**         |                                                                                                                ポーリング操作のアクションを指定します。 使用して、操作に対して生成されたサービスのインターフェイスからポーリング アクションを決定することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。                                                                                                                |
|      **PostPollStatement**       |                                                                                                                                                                  指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。                                                                                                                                                                  |
|      **PollWhileDataFound**      |                                    指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータがポーリングされるテーブルで使用できる場合に、ポーリング ステートメントを実行します。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。 既定値は false です。                                     |

 これらのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。 使用する方法の詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースをポーリングするには、このトピックの残りの部分を参照します。  

## <a name="how-this-topic-demonstrates-polling"></a>このトピックでポーリングしていますか  
 示すために、このトピックの「方法、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] SELECT ステートメントを使用してメッセージを変更するデータの受信をサポート、ポーリングすると、 **MS_SAMPLE_EMPLOYEE**インターフェイス テーブルに、**アプリケーション オブジェクト ライブラリ**アプリケーション。 Oracle E-business Suite でこれらのオブジェクトを作成するサンプルで提供される create_apps_artifacts.sql スクリプトを実行するときに、このテーブルが作成されます。  

 ポーリング操作を説明するために、次の項目行います。  

-   SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある場所インターフェイス テーブルの中にポーリングされます (MS_SAMPLE_EMPLOYEE) を決定するプロパティをバインドします。 この例では、としては、このバインド プロパティを設定できます。  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     これにより、MS_SAMPLE_EMPLOYEE インターフェイス テーブルにいくつかのレコードがある場合にのみ、アダプターがポーリング ステートメントを実行します。  

-   SELECT ステートメントを指定、 **PollingInput**プロパティをバインドします。 このステートメントは、MS_SAMPLE_EMPLOYEE インターフェイス テーブル内のすべての行を取得します。 この例では、としては、このバインド プロパティを設定できます。  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  SELECT ステートメントで使用される FOR UPDATE 句の詳細については、次を参照してください。 [Oracle E-business Suite からのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)します。  

-   DELETE ステートメントを指定の一部として、 **PostPollStatement**プロパティをバインドします。 このステートメントは、すべてのデータを MS_SAMPLE_EMPLOYEE インターフェイス テーブルから削除されます。 この例では、としては、このバインド プロパティを設定できます。  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     このような場合は、次回の指定されたステートメント**PollingInput**は実行すると、それをフェッチできませんすべてのデータ。  

-   多くのデータは MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加されるまで、新しいレコードを含む MS_SAMPLE_EMPLOYEE インターフェイス テーブルを再作成する必要がありますのでにポーリング メッセージを取得できません。 サンプルで提供される insert_apps_data.sql スクリプトを実行して行うことができます。 このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。  

## <a name="consuming-the-polling-request-message"></a>ポーリング要求メッセージの使用  
 アダプターは、Oracle E-business Suite をポーリングするようにコードでは、ポーリング操作を呼び出します。 つまり、アダプターは、IInputChannel のチャネル形状の上に表示されるポーリング要求メッセージを送信します。 ポーリング要求メッセージにはで指定されたクエリの結果セットが含まれています、 **PollingInput**プロパティをバインドします。 2 つの方法のいずれかでポーリング メッセージを使用することができます。  

-   ノード値のストリーミングを使用してメッセージを処理するには、呼び出す必要がある、 **WriteBodyContents**メソッドからの応答でメッセージを渡して、 **XmlDictionaryWriter**ノード値のストリーミングを実装します。  

-   ノードのストリーミングを使用してメッセージを処理するには、呼び出すことができます**GetReaderAtBodyContents**を取得する応答メッセージで、 **XmlReader**します。  

## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングします。 テーブルを生成するスクリプトは、サンプルで提供されます。 サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)します。 サンプルについては、 **SelectPolling_ChannelModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。  

## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用してポーリング操作の着信メッセージを受信  
 このセクションを使用してポーリングの受信メッセージを受信する .NET アプリケーション (チャネル モデル) を作成する方法に関する説明、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  

#### <a name="to-receive-polling-messages-from-the-adapter"></a>アダプターからポーリング メッセージを受信するには  

1. Microsoft Visual C#® プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 このトピックでは、コンソール アプリケーションを作成します。  

2. ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`します。  

3. Program.cs ファイルを開き、次の名前空間を追加します。  

   -   `Microsoft.Adapters.OracleEBS`  

   -   `System.ServiceModel`  

   -   `System.ServiceModel.Description`  

   -   `System.ServiceModel.Channels`  

   -   `System.Xml`  

4. 接続 URI を指定します。 アダプターの接続 URI の詳細については、次を参照してください。 [Oracle E-business Suite 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)です。  

   ```  
   Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
   ```  

5. インスタンスを作成**OracleEBSBinding**ポーリングを構成するために必要なバインドのプロパティを設定します。 設定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingInput**、および**PollingAction**プロパティをバインドします。 ポーリングを構成するためのプロパティのバインドの詳細については、次を参照してください。[受信呼び出しのポーリングを使用してサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)します。  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
   binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
   binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
   binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
   ```  

6. インターフェイス テーブルをポーリングするため、アプリケーションのコンテキストを設定する必要もあります。 アプリケーションのコンテキストとアプリケーション コンテキストの設定に必要なバインドのプロパティの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  

   ```  
   binding.OracleUserName = "<Enter user name here>";  
   binding.OraclePassword = "<Enter password here>";  
   binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  
   ```  

7. バインディング パラメーターのコレクションを作成し、資格情報を設定します。  

   ```  
   ClientCredentials credentials = new ClientCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  

   BindingParameterCollection bindingParams = new BindingParameterCollection();  
   bindingParams.Add(credentials);  
   ```  

8. チャネル リスナーを作成し、開きます。 呼び出すことによって、リスナーを作成する**BuildChannelListener < IInputChannel\>** メソッドを**OracleEBSBinding**します。  

   ```  
   IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
   listener.Open();  
   ```  

9. 取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**メソッド リスナーを開きます。  

    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  

10. 呼び出す**受信**アダプターから次の受信メッセージを取得するチャネル。  

    ```  
    Message message = channel.Receive();  
    ```  

11. 受信操作によって返される結果セットを使用します。 いずれかを使用してメッセージを処理することができます、 **XmlReader**または**XmlDictionaryWriter**します。  

    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  

12. 要求の処理が完了したら、チャネルを閉じます。  

    ```  
    channel.Close()  
    ```  

    > [!IMPORTANT]
    >  受信操作の処理が完了した後、チャネルを閉じる必要があります。 チャネルを閉じない、コードの動作に影響を与える可能性があります。  

13. データ変更メッセージの受信が完了したら、リスナーを閉じます。  

    ```  
    listener.Close()  
    ```  

    > [!IMPORTANT]
    >  リスナーを閉じる、リスナーを使用して作成されるチャネルは閉じられません。 各チャネル リスナーを使用して作成を明示的に閉じる必要があります。  

### <a name="example"></a>例  
 次の例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするポーリング アプリケーションを示します。 **PollingInput**プロパティには、MS_SAMPLE_EMPLOYEE テーブルからすべてのデータを読み取る select ステートメントが含まれているし、ポーリング後ステートメントは、同じテーブルからすべてのデータを削除します。 ポーリング メッセージを書き込む`C:\PollingOutput.xml`します。  

 後続のポーリング メッセージではより多くのデータが MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加されるまで任意のレコードは含まれません。 サンプルで提供される insert_apps_data.sql スクリプトを実行して行うことができます。 このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。 アダプターのポーリングを押して、サービス ホストを終了するまでは引き続き\<返す\>します。  

```  
using System;  
using Microsoft.Adapters.OracleEBS;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Xml;  

namespace SelectPolling_ChannelModel  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Console.WriteLine("Sample started. This sample will poll 5 times and will perform the following tasks:");  
            Console.WriteLine("Press any key to start polling...");  
            Console.ReadLine();  
            IChannelListener<IInputChannel> listener = null;  

            IInputChannel channel = null;  

            try  
            {  
                TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  

                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "<Enter user name here>";  
                binding.OraclePassword = "<Enter password here>";  
                binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  

                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name?");  

                ClientCredentials credentials = new ClientCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  

                BindingParameterCollection bindingParams = new BindingParameterCollection();  
                bindingParams.Add(credentials);  

                listener = binding.BuildChannelListener<IInputChannel>(ConnectionUri, bindingParams);  
                listener.Open();  

                channel = listener.AcceptChannel();  
                channel.Open();  

                Console.WriteLine("Channel and Listener opened...");  
                Console.WriteLine("\nWaiting for polled data...");  
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

                    XmlDocument doc = new XmlDocument();  
                    doc.Load(reader);  
                    using (XmlWriter writer = XmlWriter.Create("C:\\PollingOutput.xml"))  
                    {  
                        doc.WriteTo(writer);  
                        Console.WriteLine("The polling response is saved at 'C:\\PollingOutput.xml'");  
                    }  
                    // return the cursor  
                    Console.WriteLine();  

                    // close the reader  
                    reader.Close();  

                    message.Close();  
                }  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                Console.ReadLine();  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                    Console.ReadLine();  
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
 [WCF チャネル モデルを使用して Oracle E-business Suite のアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)