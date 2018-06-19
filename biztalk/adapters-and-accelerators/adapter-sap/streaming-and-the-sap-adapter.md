---
title: ストリーミングと SAP アダプター |Microsoft ドキュメント
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
ms.openlocfilehash: 48b97b0349822dcca1ae6486e4a0b515778b4d4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218250"
---
# <a name="streaming-and-the-sap-adapter"></a>ストリーミングと SAP アダプター
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]メッセージ自体と、クライアント アプリケーションのストリーミングをサポートしています。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作が呼び出され、SOAP メッセージを交換することによって応答が返されます。 SOAP メッセージの本文は、XML ノードから構成されます。  
  
 アダプターでサポートされているメッセージ ストリーミングの 2 種類あります。  
  
-   **ノードのストリーミング**です。 ノードがストリーミングでメッセージ ストリーミングできるは、ノードは、クライアントとアダプター間で。 これは、ノードの値全体がバッファーに読み込まれ、受信者に送信し、ことを意味します。  
  
-   **ノード値のストリーミング**です。 ノード値に、ノードの実際の値をストリーミングできますストリームに含めるクライアントとアダプター間のチャンク。 ノード値のストリーミングは、SendIdoc または ReceiveIdoc 操作を使用して大規模な Idoc を送受信するために便利です。 全体の IDOC が 1 つのノードに含まれているためにです。 (、厳密に型指定ではなく送信または受信 IDOC データは多数のノードに分割する操作のみ)。  
  
> [!IMPORTANT]
>  ノード値のストリーミングは、アダプターと、クライアント アプリケーション間でのみサポートされます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]はエンド ツー エンド ノードと値の SAP システムでストリーミングをサポートしていません。 SAP クライアント ライブラリでは、この機能はサポートされていないためにです。  
  
 どちらのストリーミング モードは、ストリーミング ノードおよびノード値には、WCF メッセージにストリーミングのサポートに依存します。 このため、ストリーミングが関連付けられている密接にメッセージがどのように作成され、アダプターと、クライアント アプリケーションの両方を使用します。 この結果は、メッセージのストリーミングのサポートがない同じであるすべてのプログラミング モデル間でです。  
  
 このトピックのセクションでします。  
  
-   WCF ではメッセージ ストリーミングのサポートについてと、アダプターでの実装方法に関する基本的な背景情報です。  
  
-   どのメッセージ ストリーミングがサポートされているか、アダプターを各プログラミング モデルで使用する場合の情報。  
  
## <a name="streaming-fundamentals"></a>ストリーミングの基礎  
 によって実装されたストリーミングのサポート、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の組み合わせです。  
  
-   WCF ではメッセージ ストリーミングをサポートします。  
  
-   SAP クライアント ライブラリでのサポートをストリーミングします。  
  
-   方向のメッセージは、作成され、アダプターによって内部的に使用します。  
  
### <a name="message-streaming-support-in-wcf"></a>WCF でメッセージのストリーミング サポート  
 WCF のメッセージのストリーミングがサポートされる方法は、メッセージの作成方法と、メッセージがどのように消費される両方に応じて決まります。  
  
-   静的なを使用して WCF メッセージを作成**作成**メソッドの**System.ServiceModel.Channels.Message**です。 このメソッドでは、さまざまなメッセージの本文を渡す方法をサポートするいくつかのオーバー ロードがあります。 WCF メッセージを使用してメッセージ本文を渡すことによって作成できます。  
  
    -   A **System.Xml.XmlReader**、または  
  
    -   A **System.ServiceModel.Channels.BodyWriter**です。  
  
-   使用して WCF メッセージを消費することができます。  
  
    -   **XmlReader**を呼び出して**Message.GetReaderAtBodyContents()**、または  
  
    -   **XmlDictionaryWriter**を呼び出して**Message.WriteBodyContents(XmlDictionaryWriter)** です。  
  
 次の表では、WCF のさまざまな組み合わせを作成して、メッセージを処理の動作方法を示します。  
  
|によって作成されるメッセージ|メッセージの消費|WCF 動作|  
|--------------------------|---------------------------|------------------|  
|**XmlBodyWriter**|**XmlDictionaryWriter**|**ノード値のストリーミング**はサポートされています。 WCF のストリーミングを実現するための 2 つのライター、パイプを使用します。 両方の**XmlBodyWriter**と**XmlDictionaryWriter**ノード値が発生するようストリーミングをサポートする必要があります。|  
|**XmlBodyWriter**|**XmlReader**|**ノードのストリーミング**はサポートされています。 WCF が内部バッファー、 **XmlReader**です。|  
|**XmlReader**|**XmlDictionaryWriter**|**ノードのストリーミング**はサポートされています。 WCF が内部バッファー、 **XmlReader**にコールバック、 **XmlDictionaryWriter**です。|  
|**XmlReader**|**XmlReader**|**ノードのストリーミング**はサポートされています。 WCF が内部バッファー、 **XmlReader**です。|  
  
### <a name="streaming-support-in-the-sap-client-library"></a>SAP クライアント ライブラリでのストリーミング サポート  
 SAP クライアント ライブラリは、ストリーミングをサポートしていません。 そのため、エンド ツー エンド ノードと値のストリーミングでサポートされていない、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
### <a name="internal-message-handling-by-the-adapter"></a>内部のメッセージがアダプターによって処理  
 アダプターは、次の方法では、ストリーミングをサポートします。  
  
-   アダプターのカスタム実装を使用して、クライアントから受信した SendIdDoc 要求メッセージを処理する**XmlDictionaryWriter**です。 使用してクライアントから受信した他のすべてのメッセージを消費する、 **XmlReader**です。  
  
-   アダプターのカスタム実装を使用して、クライアントに送信する ReceiveIdoc 要求メッセージを作成する**XmlBodyWriter**です。 使用してクライアントに送信されるその他のすべてのメッセージを作成、 **XmlReader**です。  
  
## <a name="streaming-support-in-the-wcf-channel-model"></a>WCF チャネル モデルでのストリーミング サポート  
 次の表は、WCF チャネル モデルでストリーミングのサポート方法に関する詳細情報を提供します。  
  
|操作|ストリーミング ノード|ノード値のストリーミング|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|(アダプターにクライアント) の RFC および BAPI の操作を送信|サポートされていません|サポートされていません||  
|(アダプターにクライアント) から送信 tRFC 操作|サポートされていません|サポートされていません||  
|IDOC の送信操作が (厳密に型指定)|サポートされていません|サポートされていません||  
|IDOC の受信の操作 (厳密に型指定)|Supported|サポートされていません||  
|SendIdoc 操作 (文字列)|Supported|Supported|アダプターを使用して、 **XmlDictionaryWriter**要求メッセージを処理します。 クライアントがメッセージを作成する場合、 **BodyWriter**ノードの値をアダプターに、クライアントからのストリーミングが発生します。|  
|ReceiveIdoc 操作 (文字列)|Supported|Supported|アダプターを使用して、 **BodyWriter**要求メッセージを作成します。 クライアントを使用してメッセージを消費する場合、 **XmlDictionaryWriter**ノード値がクライアントに、アダプターからのストリーミングが発生します。|  
|RFC 操作を受信します。|サポートされていません|サポートされていません||  
|TRFC 操作を受信します。|サポートされていません|サポートされていません||  
  
 ノード値を送信し、SendIdoc および ReceiveIdoc 操作を使用してフラット ファイル (string) Idoc を受信するようにコードでは、ストリーミングを実装する方法については、次を参照してください。 [WCF チャネル モデルを使用して SAP のフラット ファイル Idoc をストリーム](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)です。  
  
## <a name="streaming-support-in-the-wcf-service-model"></a>WCF サービス モデルでのストリーミング サポート  
 メッセージの XML 表現と、マネージ コードのオブジェクト表現をメッセージを逆シリアル化のシリアル化とは、書き込みをメモリにメッセージ全体を読み取る必要があります。 このため、ストリーミング ノードもノード値のストリーミングもが、WCF サービスのモデルからサポートされます。  
  
## <a name="streaming-support-in-biztalk-server"></a>BizTalk Server でのストリーミング サポート  
 次の表は、BizTalk Server にストリーミングのサポートについての詳細についてを説明します。  
  
|操作|ストリーミング ノード|ノード値のストリーミング|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|(からアダプターにクライアント) の RFC および BAPI の操作|サポートされていません|サポートされていません||  
|tRFC 操作 (、クライアントからアダプターに)|サポートされていません|サポートされていません||  
|IDOC の送信操作が (厳密に型指定)|サポートされていません|サポートされていません||  
|IDOC の受信の操作 (厳密に型指定)|Supported|サポートされていません||  
|SendIdoc 操作 (文字列)|Supported|Supported|WCF カスタム アダプターを使用して、 **BodyWriter**ノード値のストリーミングがサポートされているため、要求メッセージを作成します。|  
|ReceiveIdoc 操作 (文字列)|Supported|Supported|WCF カスタム アダプターを使用して、 **XmlDictionaryWriter**ノード値のストリーミングがサポートされているため、要求メッセージを使用します。|  
|RFC 操作を受信します。|サポートされていません|サポートされていません||  
|TRFC 操作を受信します。|サポートされていません|サポートされていません||  
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)