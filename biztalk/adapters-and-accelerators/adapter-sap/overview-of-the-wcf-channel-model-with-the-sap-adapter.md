---
title: "SAP アダプターを使用して WCF チャネル モデルの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF channel model, overview
- WCF channel model, creating messages for the SAP adapter
ms.assetid: 6192d637-efac-4580-8880-b5bae9d16f31
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8083f7dc691010f4128b3ddb99729b0b2b1ebd1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-channel-model-with-the-sap-adapter"></a>SAP アダプターを使用して WCF チャネル モデルの概要
Rfc、tRFCs、または呼び出す Bapi の SAP システムで、または、IDOC を SAP システムに送信するには、コードは WCF クライアントとして機能し、送信操作をアダプターに送信します。 WCF チャネル モデルでは、コードは、チャネル経由で要求メッセージを送信することによって、アダプターでの操作を呼び出します。  
  
 TRFC または SAP システムに RFC サーバーとして機能しに、コードは、WCF サービスとして動作します。 つまり、アダプターが、コードで受信操作を呼び出す — たとえば、RFC または ReceiveIdoc 操作 (IDOC を SAP システムから文字列の形式で受信)。 このシナリオでは、コードは、アダプターからチャネル経由で、操作の要求メッセージを受信します。  
  
 このセクションのトピックを使用しての概要を説明する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF チャネル モデルとします。  
  
## <a name="wcf-channel-model-overview"></a>WCF チャネル モデルの概要  
 クライアントとサービスは、SOAP メッセージを交換して通信します。 WCF チャネル モデルは、このメッセージ交換の低レベルの抽象化です。 インターフェイスとすると、チャネル スタックと呼ばれる階層状のプロトコル スタックを使用してメッセージを送受信できるようにする型を提供します。 スタックの各層は、チャネルから成るされ、WCF バインドから各チャネルが作成されます。 最下位の層で、トランスポート チャネルです。 トランスポート チャネルがサービスとクライアント間の基になるトランスポート機構を実装し、として上の層 (と最終的に処理を行うアプリケーション) を各メッセージを表示、 **System.ServiceModel.Message**です。 WCF**メッセージ**クラスは、SOAP メッセージの抽象化します。 WCF には、基本的な SOAP メッセージ交換パターンをモデルなどの要求/応答または一方向チャネル形状と呼ばれるいくつかのチャネル インターフェイスが用意されています。 WCF トランスポート バインディングは、1 つの実装を提供またはレイヤーの高い複数のチャネル形状がメッセージの送受信に使用できます。 WCF チャネル モデルの詳細については、次を参照してください。[チャネル モデルの概要](https://msdn.microsoft.com/library/ms729840.aspx)です。
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は、WCF サービスとして SAP システムを公開する WCF カスタム トランスポート バインディングです。  
  
## <a name="supported-channel-shapes-for-the-sap-adapter"></a>SAP アダプターのチャネル形状をサポート  
 アダプターでは、次の WCF チャネル形状を実装します。  
  
-   **IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。 **IRequestChannel**インターフェイスは、クライアント側の要求/応答メッセージ交換を実装します。 使用することができます、 **IRequestChannel**にデータを返す、SAP システムの RFC を呼び出す例については、応答を消費する操作を実行します。  
  
-   **IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。 この図形では、クライアント側の一方向メッセージ交換を実装します。 使用することができます、 **IOutputChannel**を任意のデータを返さない SAP システムの RFC を呼び出す例については、応答を使用する必要のない、操作を呼び出します。  
  
-   **IReplyChannel** (**System.ServiceModel.Channels.IReplyChannel**)。 この図形では、要求/応答メッセージ交換のサービス側を実装します。 使用することができます、 **IReplyChannel** RFC または tRFC サーバーを実装する、または SAP システムから Idoc を受信します。  
  
 任意の WCF バインドと同様に、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ファクトリ パターンを使用してアプリケーション コードへのチャネルを提供します。 使用する、 **Microsoft.Adapters.SAPBinding**オブジェクトのインスタンスを作成します。  
  
-   **System.ServiceModel.ChannelFactory\<IRequestChannel >**を提供する**IRequestChannel**チャネル アダプターの要求-応答操作の呼び出しに使用することができます。  
  
-   **System.ServiceModel.ChannelFactory\<IOutputChannel >**を提供する**IOutputChannel**チャネル アダプターの一方向の操作の呼び出しに使用することができます。  
  
-   **System.ServiceModel.IChannelListener\<IReplyChannel >**を提供する**IReplyChannel**チャネル アダプターから受信要求-応答操作を行うこともできます。  
  
## <a name="creating-messages-for-the-sap-adapter-in-the-wcf-channel-model"></a>WCF チャネル モデル内の SAP アダプターのメッセージを作成  
 WCF では、 **System.ServiceModel.Channels.Message**クラスは、メモリに SOAP メッセージの表現。 作成する、**メッセージ**、静的なを呼び出すことによってインスタンス**Message.Create**メソッドです。  
  
 必要がありますを指定することを構築する場合、SOAP メッセージに 2 つの重要な部分、**メッセージ**インスタンスに送信する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   メッセージのアクションは、SOAP メッセージ ヘッダーの一部である文字列です。 メッセージのアクションで呼び出される操作を識別する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 SAP システムで SD_RFC_CUSTOMER_GET RFC 呼び出しに指定されているメッセージのアクションを次に示します:`http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET`です。  
  
-   メッセージの本文には、操作のパラメーターのデータが含まれています。 メッセージ本文がによって予期されるメッセージ スキーマに対応する整形式 xml で構成される、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要求された操作にします。 次のメッセージ本文には、SAP システムで SD_RFC_CUSTOMER_GET RFC のパラメーターが含まれています。  
  
    ```  
    <SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>  
    ```  
  
 については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージ スキーマと操作のアクションのメッセージを参照してください[メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)です。  
  
 **Message.Create**メソッドはオーバー ロードされ、メッセージ本文を提供するためのさまざまなオプションを提供します。 次のコードを作成する方法を示しています、**メッセージ**インスタンスを使用して、 **System.Xml.XmlReader**をメッセージ本文を指定します。 このコードでは、文字列定数をメッセージ本文が読み取られます。  
  
```  
//create an XML message to send to the SAP system  
//We are invoking the SD_RFC_CUSTOMER_GET RFC.  
//The XML below specifies that we want to search for customers with names starting with "AB"  
string inputXml = "\<SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> \<KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
//create an XML reader from the input XML  
XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
//create a WCF message from the XML reader  
Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
```  
  
> [!IMPORTANT]
>  メッセージのアクションを指定する必要があります、**メッセージ**インスタンス。 通常、これを行うときに、**メッセージ**インスタンスを作成します。  
  
## <a name="streaming-support-on-the-sap-adapter-in-the-wcf-channel-model"></a>WCF チャネル モデル内の SAP アダプターでのストリーミング サポート  
 作成および SAP アダプターで送受信されるメッセージを処理する方法は、コードとアダプターの間、メッセージをストリーミングする方法を決定します。  
  
### <a name="node-streaming"></a>ストリーミング ノード  
 ノードのストリーミングは、ストリーミング、SendIdoc および ReceiveIdoc 操作を除くすべての操作はサポートされてのみのレベルです。  
  
 ノードが、メッセージのストリーミングを実行します。  
  
-   使用して、送信メッセージを作成、 **XmlReader**をメッセージ本文を指定します。  
  
-   使用して、受信メッセージを消費する**XmlReader**です。 呼び出してリーダーを取得する、 **GetReaderAtBodyContents**受信メソッド**メッセージ**です。  
  
### <a name="node-value-streaming"></a>ノード値のストリーミング  
 SendIdoc と ReceiveIdoc 操作には、1 つの XML ノードの下の文字列内の IDOC データが含まれているため (\<idocData >)、アダプター サポートしているノードの値ストリーミングこれらの操作にします。  
  
 ノード値のストリームのこれらの操作を実行するのには、次のことができます。  
  
-   SendIdoc 要求メッセージ (送信) を使用して、作成、 **BodyWriter**ノード値が、メッセージ本文を指定するストリーミングを実装します。  
  
-   ReceiveIdoc 要求メッセージが処理 (受信) を呼び出して、 **WriteBodyContents**メソッドを持つメッセージを**XmlDictionaryWriter**ノード値のストリーミングを実装します。  
  
 WCF チャネル モデルを使用してフラット ファイル (string) Idoc をストリーミングの詳細については、次を参照してください。 [WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc のストリーミング](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)です。  
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)