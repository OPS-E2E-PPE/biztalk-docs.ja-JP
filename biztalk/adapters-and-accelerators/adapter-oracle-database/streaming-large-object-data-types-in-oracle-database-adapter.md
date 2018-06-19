---
title: Oracle データベース アダプターのラージ オブジェクト データ型をストリーミング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- streaming, support in the WCF service model
- streaming, support for
- streaming, support in BizTalk Server
- streaming, support in the WCF channel model
ms.assetid: c6cbe870-6794-4bf1-90c1-db65a242e8fe
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda4d99eb381321139e4ed493f119f9eaf21623e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22217914"
---
# <a name="streaming-large-object-data-types-in-oracle-database-adapter"></a>Oracle データベース アダプターにストリーミングのラージ オブジェクト データ型
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle ラージ オブジェクト (LOB) データ型のストリーミングをサポートしています。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]操作が呼び出され、SOAP メッセージを交換することによって応答が返されます。 SOAP メッセージの本文は、XML ノードから構成されます。  
  
 アダプターでサポートされているメッセージ ストリーミングの 2 種類あります。  
  
-   **ノードのストリーミング**です。 内のノードの各ノードのストリーミングは、Oracle データベースに送信される前に、アダプターによってバッファリング (または、クライアントに返されます)。 したがって、LOB データ型の値全体がバッファーにします。  
  
-   **ノード値のストリーミング**です。 ノード値に、ノードの実際の値をストリーミングできますストリームに含める、Oracle データベースとクライアント間のチャンク。 ノード値のストリーミングは、エンド ツー エンドの LOB データ型のアダプターのクライアントと Oracle データベースの間のストリーミングをサポートします。  
  
 どちらのストリーミング モードは、ストリーミング ノードおよびノード値には、WCF メッセージにストリーミングのサポートに依存します。 このため、LOB 型のストリーミングが関連付けられている密接にメッセージがどのように作成され、アダプターと、クライアント アプリケーションの両方を使用します。 この結果は、LOB 型のストリーミングのサポートがない同じであるすべてのプログラミング モデル間でです。  
  
 このトピックのセクションでします。  
  
-   WCF ではメッセージ ストリーミングのサポートについてと、アダプターでの実装方法に関する基本的な背景情報です。  
  
-   LOB データ型のストリーミングはサポートについて各プログラミング モデルでアダプターを使用するときに関する情報です。  
  
## <a name="streaming-fundamentals"></a>ストリーミングの基礎  
 によって実装されたストリーミングのサポート、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の組み合わせです。  
  
-   WCF ではメッセージ ストリーミングをサポートします。  
  
-   Oracle クライアント ライブラリ (ODP.NET) でストリーミングのサポート。  
  
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
  
### <a name="streaming-support-in-the-oracle-client-library-odpnet"></a>Oracle クライアント ライブラリ (ODP.NET) でのストリーミング サポート  
 ODP.NET は、次の方法では、ストリーミングをサポートします。  
  
-   ストリーミングは、Oracle LOB データ型でのみサポートされます。  
  
-   テーブル (および表示)、一部の操作の LOB データ型はバッファーに格納します。 そのため、ストリーミングはサポートされません。  
  
### <a name="internal-message-handling-by-the-adapter"></a>内部のメッセージがアダプターによって処理  
 アダプターは、次の方法では、ストリーミングをサポートします。  
  
-   アダプターの拡張**メッセージ**カスタム メッセージ クラスを実装する**Microsoft.Adapters.AdapterUtilities.AdapterMessage**です。 作成、 **AdapterMessage**アダプター クライアントに提供するすべての WCF メッセージのです。 これには、すべての送信操作の応答メッセージと POLLINGSTMT 操作の要求メッセージが含まれます。 これにより、ノードと値を提供することによって、ReadLOB 操作のストリーミングをサポートするために、アダプター、 **XmlReader**をサポートする**ReadValueChunk**アダプター クライアントにします。  
  
-   アダプターのカスタム実装を使用して、クライアントから受信したすべてのメッセージを消費する**XmlDictionaryWriter**です。  
  
-   アダプターのカスタム実装を使用して、クライアントに送信されるすべてのメッセージを作成する**XmlBodyWriter**、ReadLOB 応答メッセージを除く。 (これを含むすべての送信操作の応答メッセージと POLLINGSTMT 操作の要求メッセージです。)  
  
## <a name="streaming-support-in-the-wcf-channel-model"></a>WCF チャネル モデルでのストリーミング サポート  
 次の表は、WCF チャネル モデルでストリーミングのサポート方法に関する詳細情報を提供します。  
  
|操作|ストリーミング ノード|ノード値のストリーミング|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|テーブルの挿入操作|サポート*|アダプターと Oracle データベースの間ではサポートされていません。 クライアントと入り間でサポート|ODP.NET での LOB 列の値がバッファーに格納され、挿入は実行し、ために、エンド ツー エンド ノードと値のストリーミングはサポートされていません。 ただし、ノード値が、クライアントとアダプター間のストリーミングは LOB 列の場合、クライアントがメッセージを作成する場合、 **BodyWriter**です。|  
|テーブルの Select 操作|Supported|Supported|アダプターを使用して、 **BodyWriter**応答メッセージを作成します。 クライアントを使用してメッセージを消費する場合、 **XmlDictionaryWriter**ノードと値のストリーミングの LOB 列が発生します。|  
|テーブルの Update 操作|Supported|アダプターと Oracle データベースの間ではサポートされていません。 クライアントとアダプター間でサポートされます。|ODP.NET での LOB 列の値がバッファーに格納され、更新プログラムを実行し、ために、エンド ツー エンド ノードと値のストリーミングはサポートされていません。 ただし、ノード値が、クライアントとアダプター間のストリーミング LOB 列の場合は、クライアントを持つメッセージを作成する、 **BodyWriter**です。|  
|テーブル削除操作|Supported|アダプターと Oracle データベースの間ではサポートされていません。 クライアントとアダプター間でサポートされます。|ODP.NET での LOB 列の値がバッファーに格納され、削除を実行し、ために、エンド ツー エンド ノードと値のストリーミングはサポートされていません。 ただし、ノード値が、クライアントとアダプター間のストリーミング LOB 列の場合は、クライアントを持つメッセージを作成する、 **BodyWriter**です。|  
|テーブル ReadLOB 操作|Supported|Supported|ReadLOB 操作は、主に、WCF サービス モデルで LOB データ列をストリームに設計されています。 WCF チャネル モデルをクライアントがメッセージを使用して、使用する場合に、 **XmlReader** (を呼び出すことによって、 **GetReaderAtBodyContents**メソッドの応答メッセージを)、エンド ツー エンド ノードと値のストリーミングが発生します。 これは、アダプターを返すため、 **XmlReader**をサポートする**ReadValueChunk** ReadLOB 応答メッセージを呼び出します。 ただし、WCF チャネル モデルから ReadLOB 操作を使用しないことをお勧めします。 選択操作または SQLEXECUTE 操作を代わりに使用することができます。|  
|テーブル UpdateLOB 操作|Supported|Supported|アダプターを使用して、 **XmlDictionaryWriter**要求メッセージを処理します。 クライアントで使用する場合、 **BodyWriter** LOB データのストリーミング エンド ツー エンド ノードと値が発生した要求メッセージを作成します。|  
|SQLEXECUTE 操作|Supported|Supported|アダプターを使用して、 **BodyWriter**応答メッセージを作成します。<br /><br /> クライアントで使用する場合、 **XmlDictionaryWriter**応答メッセージを処理するには、LOB データのストリーミング エンド ツー エンド ノードと値が発生します。<br /><br /> エンド ツー エンド ノードと値のストリーミングは、前に、Oracle データベースで操作を呼び出すことができます、アダプターはすべてのオペランドをバッファーする必要がありますので、要求メッセージのサポートされていません。|  
|ストアド プロシージャと関数の操作|Supported|Supported|アダプターを使用して、 **BodyWriter**応答メッセージを作成します。<br /><br /> クライアントで使用する場合、 **XmlDictionaryWriter**応答メッセージを処理するには、LOB データのストリーミング エンド ツー エンド ノードと値が発生します。 (これは OUT のストリーミングがサポートされていることを意味し、IN OUT プロシージャと関数のパラメーター、応答メッセージです)。<br /><br /> エンド ツー エンド ノードと値のストリーミングは、前に、Oracle データベースで操作を呼び出すことができます、アダプターはすべてのオペランドをバッファーする必要がありますので、要求メッセージのサポートされていません。|  
|POLLINGSTMT 操作|Supported|Supported|アダプターを使用して、 **BodyWriter** POLLINGSTMT 要求メッセージを作成します。 クライアントを使用してメッセージを消費する場合、 **XmlDictionaryWriter**、ノードと値の LOB 列のストリーミングが行われます。|  
  
 LOB データ、コードでは、WCF チャネル モデルを使用すると、ストリーミングを実装する方法については、次を参照してください。[ストリーミング Oracle LOB データ型を使用してデータベース、WCF チャネル モデル](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)です。  
  
## <a name="streaming-support-in-the-wcf-service-model"></a>WCF サービス モデルでのストリーミング サポート  
 メッセージの XML 表現と、マネージ コードのオブジェクト表現をメッセージを逆シリアル化のシリアル化とは、書き込みをメモリにメッセージ全体を読み取る必要があります。 このため、ストリーミング ノードもノード値のストリーミングもはほとんどの操作。  
  
 唯一の例外は、ReadLOB 操作です。 この操作は、WCF サービス モデルでのテーブルとビューの LOB 列を読み取るためのエンド ツー エンド ストリーミングをサポートするために実装されます。  
  
## <a name="streaming-support-in-biztalk-server"></a>BizTalk Server でのストリーミング サポート  
 次の表は、BizTalk Server にストリーミングのサポートについての詳細についてを説明します。 (を参照してください「アダプター」に対するすべての参照、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; Wcf-custom アダプターは常に参照によってこのテーブルの完全な名前です)。  
  
|操作|ストリーミング ノード|ノード値のストリーミング|Description|  
|---------------|--------------------|---------------------------|-----------------|  
|テーブルの挿入操作|サポート*|アダプターと Oracle データベースの間でサポートされていませんただし、データは、BizTalk Server とアダプター間でストリーミングされます。|ODP.NET での LOB 列の値がバッファーに格納され、挿入は実行し、ために、エンド ツー エンド ノードと値のストリーミングはサポートされていません。 ただし、ノードと値の BizTalk Server とアダプター間のストリーミングはサポートされて LOB データ型の WCF カスタム アダプターを持つメッセージが作成されるため、 **BodyWriter**です。|  
|テーブルの Select 操作|Supported|Supported|WCF カスタム アダプターを使用して、 **XmlDictionaryWriter**をエンド ツー エンド ノードと値の LOB 型のストリーミングがサポートされているため、応答メッセージを使用します。|  
|テーブルの Update 操作|Supported|アダプターと Oracle データベースの間でサポートされていませんただし、データは、BizTalk Server とアダプター間でストリーミングされます。|ODP.NET での LOB 列の値がバッファーに格納され、更新プログラムを実行し、ために、エンド ツー エンド ノードと値のストリーミングはサポートされていません。 ただし、ノードと値の BizTalk Server とアダプター間のストリーミングはサポートされて LOB データ型の WCF カスタム アダプターを持つメッセージが作成されるため、 **BodyWriter**です。|  
|テーブル削除操作|Supported|アダプターと Oracle データベースの間でサポートされていませんただし、データは、BizTalk Server とアダプター間でストリーミングされます。|ODP.NET での LOB 列の値がバッファーに格納され、削除を実行し、ために、エンド ツー エンド ノードと値のストリーミングはサポートされていません。 ただし、ノードと値の BizTalk Server とアダプター間のストリーミングはサポートされて LOB データ型の WCF カスタム アダプターを持つメッセージが作成されるため、 **BodyWriter**です。|  
|テーブル ReadLOB 操作|BizTalk Server では、ReadLOB 操作はサポートされていません。|BizTalk Server では、ReadLOB 操作はサポートされていません。|BizTalk Server では、ReadLOB 操作はサポートされていません。 代わりに、Select 操作または SQLEXECUTE 操作を使用します。|  
|テーブル UpdateLOB 操作|Supported|Supported|WCF カスタム アダプターを使用して、 **BodyWriter**をエンド ツー エンド ノードと値のストリームの LOB データ型がサポートされているため、要求メッセージを作成します。|  
|SQLEXECUTE 操作|Supported|Supported|WCF カスタム アダプターを使用して、 **XmlDictionaryWriter**をエンド ツー エンド ノードと値の LOB データ型の応答メッセージでストリーミングがサポートされているため、応答メッセージを使用します。<br /><br /> エンド ツー エンド ノードと値のストリーミングは、前に、Oracle データベースで操作を呼び出すことができます、アダプターはすべてのオペランドをバッファーする必要がありますので、要求メッセージのサポートされていません。|  
|ストアド プロシージャと関数の操作|Supported|Supported|WCF カスタム アダプターを使用して、 **XmlDictionaryWriter**をエンド ツー エンド ノードと値の LOB データ型の応答メッセージでストリーミングがサポートされているため、応答メッセージを使用します。 (これは OUT のストリーミングがサポートされていることを意味し、IN OUT プロシージャと関数のパラメーター、応答メッセージです)。<br /><br /> エンド ツー エンド ノードと値のストリーミングは、前に、Oracle データベースで操作を呼び出すことができます、アダプターはすべてのオペランドをバッファーする必要がありますので、要求メッセージのサポートされていません。|  
|POLLINGSTMT 操作|Supported|Supported|WCF カスタム アダプターを使用して、 **XmlDictionaryWriter**メッセージを処理 (受信) 要求、エンド ツー エンド ノードと値のストリームの LOB データ型がサポートされているためです。|  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションの開発](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)