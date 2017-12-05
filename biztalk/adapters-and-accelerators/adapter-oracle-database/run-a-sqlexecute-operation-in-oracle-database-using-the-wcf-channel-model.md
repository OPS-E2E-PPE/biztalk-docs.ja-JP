---
title: "WCF チャネル モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- running a SQLEXECUTE statement, using a channel
- how to, run a SQLEXECUTE statement by using a channel
- WCF channel model, running a SQLEXECUTE statement
ms.assetid: e1af11ef-3f44-4726-99ca-d6961d79e651
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5bb458af94d61ceb89a725f80606d8dda2af579
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="645a7-102">WCF チャネル モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="645a7-102">Run a SQLEXECUTE Operation in Oracle Database using the WCF Channel Model</span></span>
<span data-ttu-id="645a7-103">このセクションでは、チャネルを経由する Oracle データベースに SQLEXECUTE 操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="645a7-103">This section shows how to perform a SQLEXECUTE operation on an Oracle database over a channel.</span></span> <span data-ttu-id="645a7-104">SOAP メッセージのメッセージとメッセージのアクションの両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="645a7-104">You must specify both a message and a message action on the SOAP message.</span></span> <span data-ttu-id="645a7-105">SQLEXECUTE 操作の詳細については、次を参照してください。 [WCF サービス モデルを使用して Oracle データベースで実行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="645a7-105">For more information about the SQLEXECUTE operation, see [Run SQLEXECUTE operation in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
## <a name="the-sqlexecute-message"></a><span data-ttu-id="645a7-106">SQLEXECUTE メッセージ</span><span class="sxs-lookup"><span data-stu-id="645a7-106">The SQLEXECUTE Message</span></span>  
 <span data-ttu-id="645a7-107">次の XML では、Oracle シーケンスの次の値を返す SQLEXECUTE メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="645a7-107">The following XML shows a SQLEXECUTE message that returns the next value of an Oracle SEQUENCE.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- New Action: http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE -->  
<SQLEXECUTE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
    <SQLSTATEMENT>SELECT tid_seq.nextval id FROM dual</SQLSTATEMENT>  
</SQLEXECUTE>  
```  
  
 <span data-ttu-id="645a7-108">SQLEXECUTE には、パラメーターのスキーマ要素とを複数のパラメーター データ セットを含むパラメーター ブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="645a7-108">The SQLEXECUTE can specify a parameter schema element and a parameter block that contains multiple sets of parameter data.</span></span> <span data-ttu-id="645a7-109">表示されるメッセージは、パラメーター スキーマとパラメーターのブロックを指定する要素は、メッセージ本文から省略されるので、指定した SQL ステートメントの 1 つの呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="645a7-109">The message shown is for a single invocation of the specified SQL statement so the elements that specify the parameter schema and parameter block are omitted from the message body.</span></span> <span data-ttu-id="645a7-110">SQLEXECUTE 操作のメッセージ スキーマについては、次を参照してください。 [SQLEXECUTE 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)です。</span><span class="sxs-lookup"><span data-stu-id="645a7-110">For information about the message schema for the SQLEXECUTE operation, see [Message Schemas for the SQLEXECUTE Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md).</span></span>  
  
## <a name="specifying-the-sqlexecute-action"></a><span data-ttu-id="645a7-111">SQLEXECUTE 操作を指定してください。</span><span class="sxs-lookup"><span data-stu-id="645a7-111">Specifying the SQLEXECUTE Action</span></span>  
 <span data-ttu-id="645a7-112">メッセージのアクションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="645a7-112">You must specify an action for the message.</span></span> <span data-ttu-id="645a7-113">次のコードの抜粋では、SQLEXECUTE メッセージのアクションを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="645a7-113">The following code excerpt shows how to specify the action for the SQLEXECUTE message.</span></span>  
  
```  
Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
```  
  
## <a name="sending-the-sqlexecute-message"></a><span data-ttu-id="645a7-114">SQLEXECUTE メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="645a7-114">Sending the SQLEXECUTE Message</span></span>  
 <span data-ttu-id="645a7-115">次のコードの抜粋では、チャネルを経由する Oracle データベースに SQLEXECUTE 操作を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="645a7-115">The following code excerpt demonstrates how to invoke a SQLEXECUTE operation on an Oracle database over a channel.</span></span>  
  
```  
// Create Endpoint  
EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
  
// Create Binding  
OracleDBBinding binding = new OracleDBBinding();  
  
// Create Channel Factory  
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
factory.Open();  
  
// Create Request Channel  
IRequestChannel channel = factory.CreateChannel();  
channel.Open();  
  
// Send Request  
System.Xml.XmlReader readerIn = System.Xml.XmlReader.Create("SQLExecute.xml");  
  
Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
Message messageOut = channel.Request(messageIn);  
  
// Get Response XML  
XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
  
// Get tid_seq SEQUENCE  
string id = null;  
XmlDocument doc = new XmlDocument();  
doc.Load(readerOut);  
XmlNodeList list = doc.GetElementsByTagName("ColumnValue");  
if (list.Count > 0) id = list[0].InnerXml;  
```  
  
> [!NOTE]
>  <span data-ttu-id="645a7-116">SQLEXECUTE 操作を常には、弱い型指定の結果セットを返します。</span><span class="sxs-lookup"><span data-stu-id="645a7-116">The SQLEXECUTE operation always returns a weakly-typed result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645a7-117">参照</span><span class="sxs-lookup"><span data-stu-id="645a7-117">See Also</span></span>  
 [<span data-ttu-id="645a7-118">WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="645a7-118">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)  
 [<span data-ttu-id="645a7-119">Oracle データベースを使用して、チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="645a7-119">Create a channel using Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)