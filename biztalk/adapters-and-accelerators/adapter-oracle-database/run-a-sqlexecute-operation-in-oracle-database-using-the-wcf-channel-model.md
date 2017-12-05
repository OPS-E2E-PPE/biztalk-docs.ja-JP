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
# <a name="run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。
このセクションでは、チャネルを経由する Oracle データベースに SQLEXECUTE 操作を実行する方法を示します。 SOAP メッセージのメッセージとメッセージのアクションの両方を指定する必要があります。 SQLEXECUTE 操作の詳細については、次を参照してください。 [WCF サービス モデルを使用して Oracle データベースで実行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)です。  
  
## <a name="the-sqlexecute-message"></a>SQLEXECUTE メッセージ  
 次の XML では、Oracle シーケンスの次の値を返す SQLEXECUTE メッセージを表示します。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- New Action: http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE -->  
<SQLEXECUTE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
    <SQLSTATEMENT>SELECT tid_seq.nextval id FROM dual</SQLSTATEMENT>  
</SQLEXECUTE>  
```  
  
 SQLEXECUTE には、パラメーターのスキーマ要素とを複数のパラメーター データ セットを含むパラメーター ブロックを指定できます。 表示されるメッセージは、パラメーター スキーマとパラメーターのブロックを指定する要素は、メッセージ本文から省略されるので、指定した SQL ステートメントの 1 つの呼び出しです。 SQLEXECUTE 操作のメッセージ スキーマについては、次を参照してください。 [SQLEXECUTE 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)です。  
  
## <a name="specifying-the-sqlexecute-action"></a>SQLEXECUTE 操作を指定してください。  
 メッセージのアクションを指定する必要があります。 次のコードの抜粋では、SQLEXECUTE メッセージのアクションを指定する方法を示します。  
  
```  
Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
```  
  
## <a name="sending-the-sqlexecute-message"></a>SQLEXECUTE メッセージを送信します。  
 次のコードの抜粋では、チャネルを経由する Oracle データベースに SQLEXECUTE 操作を呼び出す方法を示します。  
  
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
>  SQLEXECUTE 操作を常には、弱い型指定の結果セットを返します。  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)  
 [Oracle データベースを使用して、チャネルを作成します。](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)