---
title: ストリーミングと SAP アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- streaming, support in WCF service model
- streaming, node-value
- streaming, node
- streaming, support in BizTalk Server
- streaming, and the SAP adapter
- streaming, support in WCF channel model
ms.assetid: 9fa1788b-f21b-4dec-be14-27dd8080a9d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f012073f507026a03060a4ddf6c0574fe34186ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004355"
---
# <a name="streaming-and-the-sap-adapter"></a>ストリーミングと SAP アダプター
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]メッセージ自体と、クライアント アプリケーション間のストリーミングをサポートしています。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作が呼び出され、SOAP メッセージを交換することで応答が返されます。 SOAP メッセージの本文は、XML ノードで構成されます。  
  
 アダプターでサポートされているメッセージ ストリーミングの 2 つの種類があります。  
  
-   **ノードのストリーミング**します。 ノードがストリーミングでメッセージをストリームできるノードは、クライアントとアダプター間で。 これは、ノードの値全体がバッファーに読み取るし、受信者に送信し、ことを意味します。  
  
-   **ノード値のストリーミング**します。 ノード値で、ノードの実際の値をストリーミングするストリーミングできます、クライアントとアダプター間のチャンク単位で。 ノード値のストリーミングは、送信や、SendIdoc または ReceiveIdoc 操作を使用して大規模な Idoc を受信する場合に便利ですが。 全体の IDOC が 1 つのノードに含まれているためにです。 (厳密に型ではなく送信または受信 IDOC データは多数のノードに分割する操作のみ)。  
  
> [!IMPORTANT]
>  ノード値のストリーミングは、アダプターとクライアント アプリケーションの間のみサポートされます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]エンド ツー エンド ノードと値の SAP システムを使用したストリーミングをサポートしていません。 SAP クライアント ライブラリでは、この機能はサポートされていないためにです。  
  
 これらのストリーミング モードの両方は、ストリーミング ノードおよびノード値には、WCF メッセージにストリーミングのサポートに依存します。 このため、ストリーミングは密接に関連付けメッセージが作成され、アダプターとクライアント アプリケーションの両方を使用する方法。 この結果は、メッセージ ストリーミングのサポートがない同じであるすべてのプログラミング モデル間で。  
  
 このトピックで説明します。  
  
-   WCF ではメッセージ ストリーミングをサポートする方法と、アダプターによって実装方法に関する基本的なバック グラウンド情報。  
  
-   どのメッセージ ストリーミングをサポートする各プログラミング モデルで、アダプタを使用する場合について説明します。  
  
## <a name="streaming-fundamentals"></a>ストリーミングの基礎  
 によって実装されるストリーミングのサポート、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の組み合わせです。  
  
-   WCF ではメッセージ ストリーミングをサポートします。  
  
-   SAP クライアント ライブラリのサポートをストリーミングします。  
  
-   メッセージが作成され、アダプターによって内部的に使用します。  
  
### <a name="message-streaming-support-in-wcf"></a>WCF でのメッセージのストリーミング サポート  
 メッセージの作成方法と、メッセージを使用する方法の両方で、WCF がメッセージのストリーミングがサポートする方法によって異なります。  
  
- 静的なを使用して、WCF メッセージを作成**作成**メソッドの**System.ServiceModel.Channels.Message**します。 このメソッドでは、メッセージ本文を渡すことのさまざまな方法をサポートするいくつかのオーバー ロードがあります。 WCF メッセージを使用してメッセージ本文を渡すことによって作成できます。  
  
  -   A **System.Xml.XmlReader**、または  
  
  -   A **System.ServiceModel.Channels.BodyWriter**します。  
  
- 使用して、WCF メッセージを使用できます。  
  
  -   **XmlReader**呼び出して**Message.GetReaderAtBodyContents()**、または  
  
  -   **XmlDictionaryWriter**呼び出して**Message.WriteBodyContents(XmlDictionaryWriter)** します。  
  
  次の表では、メッセージの作成との組み合わせの WCF の動作方法を示します。  
  
|作成されたメッセージ|使用されるメッセージ|WCF の動作|  
|--------------------------|---------------------------|------------------|  
|**XmlBodyWriter**|**XmlDictionaryWriter**|**ノード値のストリーミング**はサポートされています。 WCF は、ストリーミングを実現するための 2 つのライターをパイプ処理します。 両方の**XmlBodyWriter**と**XmlDictionaryWriter**ノード値が発生するストリーミングをサポートする必要があります。|  
|**XmlBodyWriter**|**XmlReader**|**ノードのストリーミング**はサポートされています。 WCF を内部的にバッファー、 **XmlReader**します。|  
|**XmlReader**|**XmlDictionaryWriter**|**ノードのストリーミング**はサポートされています。 WCF を内部的にバッファー、 **XmlReader**にコールバックし、 **XmlDictionaryWriter**します。|  
|**XmlReader**|**XmlReader**|**ノードのストリーミング**はサポートされています。 WCF を内部的にバッファー、 **XmlReader**します。|  
  
### <a name="streaming-support-in-the-sap-client-library"></a>SAP クライアント ライブラリでのストリーミング サポート  
 SAP クライアント ライブラリは、ストリーミングをサポートしていません。 そのためノードと値のエンド ツー エンドのストリーミングはサポートされていませんが、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
### <a name="internal-message-handling-by-the-adapter"></a>内部のメッセージがアダプターによって処理  
 アダプターでは、次の方法では、ストリーミングがサポートされています。  
  
-   アダプターのカスタム実装を使用して、クライアントから受信した SendIdDoc 要求メッセージを消費する**XmlDictionaryWriter**します。 使用してクライアントから受信したその他のすべてのメッセージを消費する**XmlReader**します。  
  
-   アダプターのカスタム実装を使用して、クライアントに送信する ReceiveIdoc 要求メッセージを作成します**XmlBodyWriter**します。 使用してクライアントに送信されるその他のすべてのメッセージを作成、 **XmlReader**します。  
  
## <a name="streaming-support-in-the-wcf-channel-model"></a>WCF チャネル モデルでのストリーミング サポート  
 次の表では、WCF チャネル モデルのストリーミングをサポートする方法の詳細について説明します。  
  
|演算|ノードのストリーミング|ノード値のストリーミング|説明|  
|---------------|--------------------|---------------------------|-----------------|  
|(アダプターのクライアント) からの送信の RFC および BAPI 操作|サポートされていません|サポートされていません||  
|(アダプターのクライアント) から送信 tRFC 操作|サポートされていません|サポートされていません||  
|IDOC の送信操作が (厳密に型指定)|サポートされていません|サポートされていません||  
|IDOC の受信操作が (厳密に型指定)|Supported|サポートされていません||  
|SendIdoc 操作 (文字列)|Supported|Supported|アダプターを使用して、 **XmlDictionaryWriter**要求メッセージを処理します。 クライアントがメッセージを作成する場合、 **BodyWriter**ノードと値のアダプターに、クライアントからのストリーミングに発生します。|  
|ReceiveIdoc 操作 (文字列)|Supported|Supported|アダプターを使用して、 **BodyWriter**要求メッセージを作成します。 クライアントがメッセージを使用して、使用する場合、 **XmlDictionaryWriter**ノードと値をクライアントにアダプターからのストリーミングに発生します。|  
|RFC 操作を受信します。|サポートされていません|サポートされていません||  
|受信 tRFC 操作|サポートされていません|サポートされていません||  
  
 ノード値を送信し、SendIdoc および ReceiveIdoc 操作を使用してフラット ファイル (string) Idoc を受信するコードでは、ストリーミングを実装する方法については、次を参照してください。 [WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc の Stream](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)します。  
  
## <a name="streaming-support-in-the-wcf-service-model"></a>WCF サービス モデルでのストリーミング サポート  
 メッセージの XML 表現とメッセージのマネージ コード オブジェクトの表現の間を逆シリアル化のシリアル化とは、メッセージ全体をメモリに読み書きが必要です。 このため、ストリーミング ノードもノード値のストリーミングもが WCF サービス モデルからサポートされます。  
  
## <a name="streaming-support-in-biztalk-server"></a>BizTalk Server でのストリーミング サポート  
 次の表では、BizTalk Server でのストリーミングのサポートについての詳細について説明します。  
  
|演算|ノードのストリーミング|ノード値のストリーミング|説明|  
|---------------|--------------------|---------------------------|-----------------|  
|(アダプターのクライアント) からの RFC および BAPI の操作|サポートされていません|サポートされていません||  
|tRFC 操作 (アダプターのクライアント) から|サポートされていません|サポートされていません||  
|IDOC の送信操作が (厳密に型指定)|サポートされていません|サポートされていません||  
|IDOC の受信操作が (厳密に型指定)|Supported|サポートされていません||  
|SendIdoc 操作 (文字列)|Supported|Supported|Wcf-custom アダプターを使用して、 **BodyWriter**ノード値のストリーミングをサポートするために、要求メッセージを作成します。|  
|ReceiveIdoc 操作 (文字列)|Supported|Supported|Wcf-custom アダプターを使用して、 **XmlDictionaryWriter**ノード値のストリーミングをサポートするために、要求メッセージを使用します。|  
|RFC 操作を受信します。|サポートされていません|サポートされていません||  
|受信 tRFC 操作|サポートされていません|サポートされていません||  
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)