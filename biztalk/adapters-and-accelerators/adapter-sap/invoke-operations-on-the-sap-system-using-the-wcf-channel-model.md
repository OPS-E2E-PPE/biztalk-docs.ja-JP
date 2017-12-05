---
title: "WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF channel model, supporting BAPI transactions
- WCF channel model, invoking operations on the SAP system
ms.assetid: 80ed85ff-360d-4b7f-a119-cd2a99c21cf4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1030e0a743a9b06d856bc593198f4afebc1ffa38
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-operations-on-the-sap-system-using-the-wcf-channel-model"></a><span data-ttu-id="9a12a-102">WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="9a12a-102">Invoke Operations on the SAP System Using the WCF Channel Model</span></span>
<span data-ttu-id="9a12a-103">に対して操作を呼び出す、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用して、 **IRequestChannel**または**IOutputChannel**チャネル形状をアダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-103">You invoke operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using an **IRequestChannel** or **IOutputChannel** channel shape to send messages to the adapter.</span></span> <span data-ttu-id="9a12a-104">基本的なパターンは、バインドを使用して、必要なチャネル形状をチャネル ファクトリを作成する (**SAPBinding**) と接続 URI から作成されたエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="9a12a-104">The basic pattern is to create a channel factory for the required channel shape by using a binding (**SAPBinding**) and an endpoint created from a connection URI.</span></span> <span data-ttu-id="9a12a-105">作成し、**メッセージ**をターゲットの操作用のメッセージ スキーマに準拠する SOAP メッセージを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9a12a-105">You then create a **Message** instance that represents a SOAP message that conforms to the message schema for your target operation.</span></span> <span data-ttu-id="9a12a-106">これを送信することができますし、**メッセージ**を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]チャネル ファクトリから作成されたチャネルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="9a12a-106">You can then send this **Message** to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using a channel created from the channel factory.</span></span> <span data-ttu-id="9a12a-107">使用している場合、 **IRequestChannel**応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-107">If you are using an **IRequestChannel**, you receive a response.</span></span> <span data-ttu-id="9a12a-108">SAP システムで操作の実行に問題がある場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]スロー、 **Microsoft.ServiceModel.Channels.Common.TargetSystemException**です。</span><span class="sxs-lookup"><span data-stu-id="9a12a-108">If there is a problem executing the operation on the SAP system, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] throws a **Microsoft.ServiceModel.Channels.Common.TargetSystemException**.</span></span>  
  
 <span data-ttu-id="9a12a-109">使用して操作を送信する方法の概要については、 **IRequestChannel** WCF では、次を参照してください。[クライアント チャネル レベルのプログラミング](https://msdn.microsoft.com/library/ms788970.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="9a12a-109">For an overview of how to send operations using an **IRequestChannel** in WCF, see [Client Channel-Level Programming](https://msdn.microsoft.com/library/ms788970.aspx).</span></span>  
  
 <span data-ttu-id="9a12a-110">このトピックのセクションでは、操作の呼び出しに役立つ情報を提供する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-110">The sections in this topic provide information to help you invoke operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] using the WCF channel model.</span></span>  
  
## <a name="supporting-bapi-transactions-in-the-wcf-channel-model"></a><span data-ttu-id="9a12a-111">WCF チャネル モデルでの BAPI のトランザクションのサポート</span><span class="sxs-lookup"><span data-stu-id="9a12a-111">Supporting BAPI Transactions in the WCF Channel Model</span></span>  
 <span data-ttu-id="9a12a-112">SAP システムで、同じ論理ユニットの作業 (LUW) またはトランザクションの一部であるすべての Bapi の同じ SAP 接続を使用して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9a12a-112">All BAPIs that are invoked using the same SAP connection are part of the same Logical Unit of Work (LUW) -- or transaction -- on the SAP system.</span></span> <span data-ttu-id="9a12a-113">各 WCF チャネルは、SAP システムへの一意の接続を表します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-113">Each WCF channel represents a unique connection to the SAP system.</span></span> <span data-ttu-id="9a12a-114">サポートするためには、WCF を使用して BAPI トランザクションは、モデルをチャネルします。</span><span class="sxs-lookup"><span data-stu-id="9a12a-114">To support BAPI transactions using the WCF channel model:</span></span>  
  
-   <span data-ttu-id="9a12a-115">すべての BAPI、LUW (トランザクション) でが同じチャネル経由で送信されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-115">Ensure that every BAPI in an LUW (transaction) is sent over the same channel.</span></span> <span data-ttu-id="9a12a-116">これには、BAPI_TRANSACTION コミットまたは BAPI_TRANSACTION_ROLLBACK 操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9a12a-116">This includes the BAPI_TRANSACTION COMMIT or the BAPI_TRANSACTION_ROLLBACK operations.</span></span>  
  
-   <span data-ttu-id="9a12a-117">チャネルで [次へ] の BAPI を呼び出す前に、BAPI を受信した応答メッセージを閉じることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-117">Ensure that you close any response message received for a BAPI before you invoke the next BAPI on the channel.</span></span> <span data-ttu-id="9a12a-118">(すべての操作を行いますが Bapi にとって特に重要である)。</span><span class="sxs-lookup"><span data-stu-id="9a12a-118">(You should do this for every operation; but it is especially important for BAPIs.)</span></span>  
  
 <span data-ttu-id="9a12a-119">BAPI のトランザクションの詳細については、次を参照してください。 [SAP での Bapi の操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="9a12a-119">For more information about BAPI transactions, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
## <a name="streaming-flat-file-idocs-to-the-sap-adapter"></a><span data-ttu-id="9a12a-120">ストリーミングのフラット ファイル Idoc を SAP アダプター</span><span class="sxs-lookup"><span data-stu-id="9a12a-120">Streaming Flat File IDOCs to the SAP Adapter</span></span>  
 <span data-ttu-id="9a12a-121">SendIdoc 操作を使用して、フラット ファイル (string) IDOC をアダプターに送信します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-121">You use the SendIdoc operation to send a flat file (string) IDOC to the adapter.</span></span> <span data-ttu-id="9a12a-122">IDOC データは、この操作で 1 つのノードの下の文字列として表されます。</span><span class="sxs-lookup"><span data-stu-id="9a12a-122">The IDOC data is represented as a string under a single node in this operation.</span></span> <span data-ttu-id="9a12a-123">このため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ノード値の要求メッセージのストリーミングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9a12a-123">For this reason, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports node-value streaming on the request message.</span></span> <span data-ttu-id="9a12a-124">ノード値のストリーミングを実行するのを使用して SendIdoc 操作の要求メッセージを作成する必要があります、 **System.ServiceModel.Channels.BodyWriter**が IDOC データをストリーミング可能です。</span><span class="sxs-lookup"><span data-stu-id="9a12a-124">To perform node-value streaming, you must create the request message for the SendIdoc operation by using a **System.ServiceModel.Channels.BodyWriter** that is capable of streaming the IDOC data.</span></span> <span data-ttu-id="9a12a-125">これを行う方法については、次を参照してください。 [WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc のストリーミング](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="9a12a-125">For information about how to do this, see [Streaming Flat-File IDOCs in SAP using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a><span data-ttu-id="9a12a-126">チャネルを使用して、操作を呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="9a12a-126">How Do I Invoke an Operation by Using a Channel?</span></span>  
 <span data-ttu-id="9a12a-127">使用して、操作を呼び出す、 **IRequestChannel**、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-127">To invoke an operation by using an **IRequestChannel**, perform the following steps.</span></span>  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a><span data-ttu-id="9a12a-128">IRequestChannel のインスタンスを使用して、操作を呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="9a12a-128">How to invoke an operation by using an instance of IRequestChannel</span></span>  
  
1.  <span data-ttu-id="9a12a-129">チャネル ファクトリを作成 (**ChannelFactory\<IRequestChannel\>**)。</span><span class="sxs-lookup"><span data-stu-id="9a12a-129">Build a channel factory (**ChannelFactory\<IRequestChannel\>**).</span></span> <span data-ttu-id="9a12a-130">これを行うには、バインドを指定する必要があります (**SAPBinding**) およびエンドポイント アドレス。</span><span class="sxs-lookup"><span data-stu-id="9a12a-130">To do this, you must specify a binding (**SAPBinding**) and an endpoint address.</span></span> <span data-ttu-id="9a12a-131">コードで命令として記述または構成で宣言によって、バインドとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9a12a-131">You can specify the binding and endpoint address either imperatively in your code or declaratively in configuration.</span></span> <span data-ttu-id="9a12a-132">プロパティは、送信すること、ファクトリを開く前に、操作に必要な任意のバインディングを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a12a-132">You should set any binding properties required for the operations that you will send before you open the factory.</span></span> <span data-ttu-id="9a12a-133">構成でバインディングとエンドポイント アドレスを指定する方法の詳細については、次を参照してください。 [SAP を使用して、チャネルの作成](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="9a12a-133">For more information about how to specify the binding and endpoint address in configuration, see [Create a channel using SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md).</span></span>  
  
    ```  
    // Create a binding  
    SAPBinding binding = new SAPBinding();  
    // Create an endpoint address by using the connection URI  
    EndpointAddress endpointAddress = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
    // Create the channel factory  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    ```  
  
2.  <span data-ttu-id="9a12a-134">使用してチャネル ファクトリの名前のパスワードの資格情報をユーザーに設定、 **ClientCredentials**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="9a12a-134">Set the user name password credentials for the channel factory by using the **ClientCredentials** property.</span></span>  
  
    ```  
    factory.Credentials.UserName.UserName = "YourUserName";  
    factory.Credentials.UserName.Password = "YourPassword";  
    ```  
  
3.  <span data-ttu-id="9a12a-135">チャネル ファクトリを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a12a-135">Open the channel factory.</span></span>  
  
    ```  
    factory.Open();  
    ```  
  
4.  <span data-ttu-id="9a12a-136">工場出荷時にチャネルを取得し、開きます。</span><span class="sxs-lookup"><span data-stu-id="9a12a-136">Get a channel from the factory and open it.</span></span>  
  
    ```  
    IRequestChannel channel = factory.CreateChannel();  
    channel.Open();  
    ```  
  
5.  <span data-ttu-id="9a12a-137">作成、**メッセージ**ターゲット操作のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9a12a-137">Create a **Message** instance for the target operation.</span></span> <span data-ttu-id="9a12a-138">ターゲットの操作のメッセージ アクションが指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-138">Be sure that the message action for the target operation is specified.</span></span> <span data-ttu-id="9a12a-139">この例では、メッセージ本文が作成することで渡される、 **XmlReader**文字列にします。</span><span class="sxs-lookup"><span data-stu-id="9a12a-139">In this example, the message body is passed by creating an **XmlReader** over a string.</span></span> <span data-ttu-id="9a12a-140">ターゲットの操作では、SAP システムで SD_RFC_CUSTOMER_GET RFC を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-140">The target operation invokes the SD_RFC_CUSTOMER_GET RFC on an SAP system.</span></span>  
  
    ```  
    string inputXml = "\<SD_RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
    //create an XML reader from the input XML  
    XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
    //create a WCF message from our XML reader  
    Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
    ```  
  
6.  <span data-ttu-id="9a12a-141">呼び出す、**要求**メッセージを送信するチャネルのメソッド、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]と返信を受信します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-141">Invoke the **Request** method on the channel to send the message to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and receive the reply.</span></span> <span data-ttu-id="9a12a-142">SAP システムには、例外が発生すると、アダプターをスロー、 **TargetSystemException**です。</span><span class="sxs-lookup"><span data-stu-id="9a12a-142">If the SAP system encounters an exception, the adapter throws a **TargetSystemException**.</span></span> <span data-ttu-id="9a12a-143">(その他の例外は、非 SAP 例外の)。SAP からのエラーの説明を取得できます、 **InnerException.Message**のプロパティ、 **TargetSystemException**です。</span><span class="sxs-lookup"><span data-stu-id="9a12a-143">(Other exceptions are possible for non SAP exceptions.) You can get a description of the SAP error from the **InnerException.Message** property of the **TargetSystemException**.</span></span>  
  
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
  
7.  <span data-ttu-id="9a12a-144">応答を処理します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-144">Process the response.</span></span> <span data-ttu-id="9a12a-145">この例では**GetReaderAtBodyContents**メッセージ本文を取得する応答メッセージで呼び出されるとします。</span><span class="sxs-lookup"><span data-stu-id="9a12a-145">In this example, **GetReaderAtBodyContents** is called on the response message to get the message body.</span></span>  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    ```  
  
8.  <span data-ttu-id="9a12a-146">完了したら、リーダーとメッセージを閉じる、応答メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-146">When you are done processing the response message, close the reader and the message.</span></span>  
  
    ```  
    readerOut.Close();  
    messageOut.Close();  
    ```  
  
9. <span data-ttu-id="9a12a-147">完了すると、チャネルおよびチャネル ファクトリを使用してそれらを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9a12a-147">When you are done using the channel and the channel factory, close them.</span></span> <span data-ttu-id="9a12a-148">ファクトリを閉じると、それを使用して作成されたすべてのチャネルが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="9a12a-148">Closing the factory will close all channels that were created with it.</span></span>  
  
    ```  
    channel.Close()  
    factory.Close();  
    ```  
  
10.  
  
 <span data-ttu-id="9a12a-149">同じ手順を使用してメッセージを送信する、 **IOutputChannel**以外の図形します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-149">You follow the same steps to send a message using the **IOutputChannel** shape except:</span></span>  
  
-   <span data-ttu-id="9a12a-150">作成する、 **ChannelFactory\<IOutputChannel\>** 手順 1 でします。</span><span class="sxs-lookup"><span data-stu-id="9a12a-150">You create a **ChannelFactory\<IOutputChannel\>** in step 1.</span></span>  
  
-   <span data-ttu-id="9a12a-151">呼び出す、**送信**手順 6. でチャネル上のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="9a12a-151">You call the **Send** method on the channel in step 6.</span></span> <span data-ttu-id="9a12a-152">`channel.Send(messageIn);`」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9a12a-152">`channel.Send(messageIn);`.</span></span>  
  
-   <span data-ttu-id="9a12a-153">に対して返される応答メッセージが表示されない、 **IOutputChannel**です。</span><span class="sxs-lookup"><span data-stu-id="9a12a-153">There is no response message returned for an **IOutputChannel**.</span></span>  
  
### <a name="example"></a><span data-ttu-id="9a12a-154">例</span><span class="sxs-lookup"><span data-stu-id="9a12a-154">Example</span></span>  
 <span data-ttu-id="9a12a-155">次の例を使用して、RFC を呼び出す方法を示しています、 **IRequestChannel**チャネル。</span><span class="sxs-lookup"><span data-stu-id="9a12a-155">The following example shows how to invoke an RFC by using an **IRequestChannel** channel.</span></span> <span data-ttu-id="9a12a-156">この例では、"AB"で始まる名前の顧客の一覧を取得する SD_RFC_CUSTOMER_GET RFC を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9a12a-156">This example invokes the SD_RFC_CUSTOMER_GET RFC to get a list of customers whose names start with "AB".</span></span> <span data-ttu-id="9a12a-157">使用して、応答メッセージが表示される、 **XmlReader**し、顧客番号と返される各顧客の名前は、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9a12a-157">The response message is consumed by using an **XmlReader** and the customer number and name of each customer returned is written to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9a12a-158">参照</span><span class="sxs-lookup"><span data-stu-id="9a12a-158">See Also</span></span>  
[<span data-ttu-id="9a12a-159">WCF チャネル モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="9a12a-159">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)