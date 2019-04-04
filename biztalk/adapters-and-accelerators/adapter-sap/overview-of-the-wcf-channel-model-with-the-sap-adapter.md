---
title: SAP アダプターを使用した WCF チャネル モデルの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, overview
- WCF channel model, creating messages for the SAP adapter
ms.assetid: 6192d637-efac-4580-8880-b5bae9d16f31
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81eba8c28b3bf11eea38624e0a017d8bca9eb9a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013187"
---
# <a name="overview-of-the-wcf-channel-model-with-the-sap-adapter"></a>SAP アダプターを使用した WCF チャネル モデルの概要
SAP システムでは、Rfc、Trfc、Bapi を呼び出すまたは IDOC を SAP システムに送信するには、コードが WCF クライアントとして機能し、送信操作をアダプターに送信します。 WCF チャネル モデルでは、コードは、チャネル経由で要求メッセージを送信することによって、アダプターでの操作を呼び出します。  
  
 TRFC または SAP システムへの RFC サーバーとして機能しには、コードは、WCF サービスとして動作します。 アダプターが、コードで受信操作を呼び出す、-など、RFC または ReceiveIdoc 操作 (SAP システムからの文字列形式で IDOC を受信する)。 このシナリオでは、コードは、アダプターからチャネルを操作の要求メッセージを受け取ります。  
  
 このセクションのトピックの使用の概要を提供する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF チャネル モデルを使用します。  
  
## <a name="wcf-channel-model-overview"></a>WCF チャネル モデルの概要  
 クライアントとサービスは、SOAP メッセージを交換して通信します。 WCF チャネル モデルとは、このメッセージ交換の低レベルの抽象化です。 インターフェイスおよびチャネル スタックと呼ばれる複数層のプロトコル スタックを使用してメッセージを送受信するための型を提供します。 チャネルのスタックの各層がで構成され、WCF バインドから各チャネルが作成されます。 最下位の層では、トランスポート チャネルです。 トランスポート チャネルがサービスとクライアント間の基盤トランスポート メカニズムを実装し、として上位レイヤー (および最終的には、コンシューマー側アプリケーション) には、各メッセージを表示、 **System.ServiceModel.Message**します。 WCF**メッセージ**クラスは、SOAP メッセージの抽象化します。 WCF には、基本的な SOAP メッセージ交換パターンなどの要求/応答または一方向のモデル化するチャネル形状と呼ばれるいくつかのチャネル インターフェイスが用意されています。 WCF トランスポート バインディングは、1 つの実装を提供します。 または、レイヤーの高い複数のチャネル形状はメッセージの送受信に使用できます。 WCF チャネル モデルの詳細については、[チャネル モデルの概要](https://msdn.microsoft.com/library/ms729840.aspx)を参照してください。
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は WCF サービスとしての SAP システムを公開する WCF カスタム トランスポート バインドします。  
  
## <a name="supported-channel-shapes-for-the-sap-adapter"></a>SAP アダプターのチャネル形状をサポート  
 アダプターは、次の WCF チャネル形状を実装します。  
  
- **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**インターフェイスは、クライアント側の要求/応答メッセージの交換を実装します。 使用することができます、 **IRequestChannel**にデータを返す、SAP システムの RFC を呼び出す例については、応答を使用する操作を実行します。  
  
- **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 この図形は、クライアント側の一方向メッセージ交換を実装します。 使用することができます、 **IOutputChannel**を任意のデータを返さない SAP システムの RFC を呼び出す例については、応答を使用する必要のない操作を呼び出します。  
  
- **IReplyChannel** (**System.ServiceModel.Channels.IReplyChannel**)。 この図形は、要求/応答メッセージ交換のサービス側を実装します。 使用することができます、 **IReplyChannel** RFC、tRFC またはサーバーを実装するか、SAP システムから Idoc を受信します。  
  
  などの任意の WCF バインド、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ファクトリ パターンを使用して、アプリケーション コードへのチャネルを提供します。 使用する、 **Microsoft.Adapters.SAPBinding**オブジェクトのインスタンスを作成します。  
  
- **System.ServiceModel.ChannelFactory\<IRequestChannel\>** を提供する**IRequestChannel**チャネル アダプターの要求-応答操作の呼び出しに使用することができます。  
  
- **System.ServiceModel.ChannelFactory\<IOutputChannel\>** を提供する**IOutputChannel**チャネル アダプターの一方向の操作の呼び出しに使用することができます。  
  
- **System.ServiceModel.IChannelListener\<IReplyChannel\>** を提供する**IReplyChannel**チャネル アダプターから受信要求-応答操作に使用することができます。  
  
## <a name="creating-messages-for-the-sap-adapter-in-the-wcf-channel-model"></a>WCF チャネル モデルで SAP アダプターのメッセージを作成します。  
 WCF では、 **System.ServiceModel.Channels.Message**クラスでのメモリを提供する SOAP メッセージの表現。 作成する、**メッセージ**静的を呼び出すことによってインスタンス**Message.Create**メソッド。  
  
 2 つの重要な部分を SOAP メッセージを構築する際に指定する必要があります、**メッセージ**インスタンスに送信する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- メッセージのアクションは、SOAP メッセージ ヘッダーの一部である文字列です。 メッセージのアクションを呼び出す必要がある操作を識別する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 SAP システムで SD_RFC_CUSTOMER_GET RFC を呼び出すように指定したメッセージのアクションを次に示します:`http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET`します。  
  
- メッセージの本文には、操作のパラメーターのデータが含まれています。 メッセージ本文が想定されているメッセージのスキーマに対応する、整形式 xml で構成される、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要求された操作をします。 次のメッセージ本文には、SAP システムで SD_RFC_CUSTOMER_GET RFC のパラメーターが含まれています。  
  
  ```  
  <SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>  
  ```  
  
  については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージ スキーマと操作のアクションのメッセージを参照してください[メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)します。  
  
  **Message.Create**メソッドがオーバー ロードされ、メッセージ本文を提供するためのさまざまなオプションを提供します。 次のコードを作成する方法を示しています、**メッセージ**インスタンスを使用して、 **System.Xml.XmlReader**メッセージ本文を指定します。 このコードは、メッセージ本文は文字列定数から読み取られます。  
  
```  
//create an XML message to send to the SAP system  
//We are invoking the SD_RFC_CUSTOMER_GET RFC.  
//The XML below specifies that we want to search for customers with names starting with "AB"  
string inputXml = "<SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
//create an XML reader from the input XML  
XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
//create a WCF message from the XML reader  
Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
```  
  
> [!IMPORTANT]
>  メッセージのアクションを指定する必要があります、**メッセージ**インスタンス。 これは、通常はときに、**メッセージ**インスタンスが作成されます。  
  
## <a name="streaming-support-on-the-sap-adapter-in-the-wcf-channel-model"></a>WCF チャネル モデルで SAP アダプターのストリーミング サポート  
 作成し、SAP アダプターと交換するメッセージを使用する方法、コードとアダプター間のメッセージをストリーミングする方法を決定します。  
  
### <a name="node-streaming"></a>ノードのストリーミング  
 ノードのストリーミングは、ストリーミング、SendIdoc および ReceiveIdoc 操作を除くすべての操作はサポートされてのみレベルです。  
  
 ノードが、メッセージのストリーミングを実行すること。  
  
-   使用して、送信メッセージを作成、 **XmlReader**メッセージ本文を指定します。  
  
-   受信メッセージを使用して、処理、 **XmlReader**します。 呼び出すことで、リーダーを取得する、 **GetReaderAtBodyContents**受信メソッド**メッセージ**します。  
  
### <a name="node-value-streaming"></a>ノード値のストリーミング  
 SendIdoc と ReceiveIdoc 操作には、1 つの XML ノードの下の文字列で IDOC データが含まれるので (\<idocData\>)、アダプターがサポートされますノード-値これらの操作にストリーミングします。  
  
 ノード値のストリームのこれらの操作を実行するのには、次のことができます。  
  
- SendIdoc 要求メッセージ (送信) を使用して、作成、 **BodyWriter**ノード値が、メッセージ本文を指定するストリーミングを実装します。  
  
- ReceiveIdoc 要求メッセージを処理 (受信) を呼び出して、 **WriteBodyContents**メソッドを持つメッセージを**XmlDictionaryWriter**ノード値のストリーミングを実装します。  
  
  WCF チャネル モデルを使用してフラット ファイル (string) Idoc をストリームの詳細については、[WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc のストリーミング](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)を参照してください。  
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)