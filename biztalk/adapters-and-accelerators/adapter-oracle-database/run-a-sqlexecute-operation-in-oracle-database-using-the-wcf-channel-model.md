---
title: WCF チャネル モデルを使用して Oracle データベースでの SQLEXECUTE 操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- running a SQLEXECUTE statement, using a channel
- how to, run a SQLEXECUTE statement by using a channel
- WCF channel model, running a SQLEXECUTE statement
ms.assetid: e1af11ef-3f44-4726-99ca-d6961d79e651
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef49976eb15f5022871549f5240b22a97b908312
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528939"
---
# <a name="run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model"></a>WCF チャネル モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。
このセクションでは、チャネルを経由する Oracle データベースに SQLEXECUTE 操作を実行する方法を示します。 SOAP メッセージでは、メッセージとメッセージのアクションの両方を指定する必要があります。 SQLEXECUTE 操作の詳細については、次を参照してください。 [WCF サービス モデルを使用して Oracle データベースで実行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)します。  
  
## <a name="the-sqlexecute-message"></a>SQLEXECUTE メッセージ  
 次の XML では、Oracle シーケンスの次の値を返す SQLEXECUTE メッセージを表示します。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- New Action: http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE -->  
<SQLEXECUTE xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE">  
    <SQLSTATEMENT>SELECT tid_seq.nextval id FROM dual</SQLSTATEMENT>  
</SQLEXECUTE>  
```  
  
 SQLEXECUTE には、パラメーターのスキーマ要素と複数のパラメーターのデータ セットを含むパラメーター ブロックを指定できます。 表示されるメッセージは、パラメーター スキーマとパラメーター ブロックを指定する要素が、メッセージ本文から省略すると、指定した SQL ステートメントの 1 つの呼び出しとです。 SQLEXECUTE 操作のメッセージのスキーマについては、次を参照してください。 [SQLEXECUTE 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)します。  
  
## <a name="specifying-the-sqlexecute-action"></a>SQLEXECUTE 操作を指定します。  
 メッセージのアクションを指定する必要があります。 次のコードの抜粋では、SQLEXECUTE メッセージのアクションを指定する方法を示します。  
  
```  
Message messageIn = Message.CreateMessage(MessageVersion.Default, "http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE", readerIn);  
```  
  
## <a name="sending-the-sqlexecute-message"></a>SQLEXECUTE のメッセージを送信します。  
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
>  SQLEXECUTE 操作を常には、厳密に型指定の結果セットを返します。  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)  
 [Oracle データベースを使用してチャネルを作成します。](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)