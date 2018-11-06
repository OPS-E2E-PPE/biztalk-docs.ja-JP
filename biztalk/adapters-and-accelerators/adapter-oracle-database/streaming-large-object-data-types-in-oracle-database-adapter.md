---
title: Oracle データベース アダプターのラージ オブジェクト データ型のストリーミング |Microsoft Docs
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
ms.openlocfilehash: 9caf8a7e8dafebbe3d53b751db34c8abc8d4bd62
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752898"
---
# <a name="streaming-large-object-data-types-in-oracle-database-adapter"></a>Oracle データベース アダプターのラージ オブジェクト データ型のストリーミング
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle ラージ オブジェクト (LOB) データ型のストリーミングをサポートしています。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]操作が呼び出され、SOAP メッセージを交換することで応答が返されます。 SOAP メッセージの本文は、XML ノードで構成されます。  
  
 アダプターでサポートされているメッセージ ストリーミングの 2 つの種類があります。  
  
- **ノードのストリーミング**します。 ノードでストリーミングの各ノードは、Oracle データベースに送信する前に、アダプターによってバッファー (または、クライアントに返されます)。 つまり、LOB データ型では、値全体がバッファーに読み取ります。  
  
- **ノード値のストリーミング**します。 ノード値で、ノードの実際の値をストリーミング ストリームできる Oracle データベースとクライアント間のチャンク単位で。 ノード値のストリーミングは、アダプターのクライアントと Oracle データベースの間の LOB データ型のエンド ツー エンドのストリーミングをサポートします。  
  
  これらのストリーミング モードの両方は、ストリーミング ノードおよびノード値には、WCF メッセージにストリーミングのサポートに依存します。 このため、LOB 型のストリーミングは密接に関連付けメッセージが作成され、アダプターとクライアント アプリケーションの両方を使用する方法。 この結果は、LOB 型のストリーミングのサポートがない同じであるすべてのプログラミング モデル間で。  
  
  このトピックで説明します。  
  
- WCF ではメッセージ ストリーミングをサポートする方法と、アダプターによって実装方法に関する基本的なバック グラウンド情報。  
  
- LOB データ型のストリーミングがサポートについて各プログラミング モデルで、アダプタを使用する場合について説明します。  
  
## <a name="streaming-fundamentals"></a>ストリーミングの基礎  
 によって実装されるストリーミングのサポート、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の組み合わせです。  
  
-   WCF ではメッセージ ストリーミングをサポートします。  
  
-   Oracle クライアント ライブラリ (ODP.NET) にストリーミングのサポート。  
  
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
  
### <a name="streaming-support-in-the-oracle-client-library-odpnet"></a>Oracle クライアント ライブラリ (ODP.NET) でのストリーミングのサポート  
 ODP.NET では、次の方法では、ストリーミングがサポートされています。  
  
-   ストリーミングは、Oracle LOB データ型でのみサポートされます。  
  
-   一部のテーブル (およびビュー) 操作の LOB データ型をバッファーします。 そのため、ストリーミングがサポートされていません。  
  
### <a name="internal-message-handling-by-the-adapter"></a>内部のメッセージがアダプターによって処理  
 アダプターでは、次の方法では、ストリーミングがサポートされています。  
  
-   アダプターの拡張**メッセージ**、カスタム メッセージ クラスを実装する**Microsoft.Adapters.AdapterUtilities.AdapterMessage**します。 作成、 **AdapterMessage**アダプター クライアントへのすべての WCF メッセージを提供します。 これは、すべての送信操作の応答メッセージと POLLINGSTMT 操作の要求メッセージに含まれます。 これにより、ノードと値を提供することで、ReadLOB 操作のストリーミングをサポートするために、アダプター、 **XmlReader**をサポートする**ReadValueChunk**アダプター クライアントにします。  
  
-   アダプターのカスタム実装を使用して、クライアントから受信したすべてのメッセージを消費する**XmlDictionaryWriter**します。  
  
-   アダプターのカスタム実装を使用して、クライアントに送信するすべてのメッセージを作成します。 **XmlBodyWriter**、ReadLOB 応答メッセージを除く。 (これを含むすべての送信操作の応答メッセージと POLLINGSTMT 操作の要求メッセージ。)  
  
## <a name="streaming-support-in-the-wcf-channel-model"></a>WCF チャネル モデルでのストリーミング サポート  
 次の表では、WCF チャネル モデルのストリーミングをサポートする方法の詳細について説明します。  
  
|操作|ノードのストリーミング|ノード値のストリーミング|説明|  
|---------------|--------------------|---------------------------|-----------------|  
|テーブルの挿入操作|サポートされています\*|アダプターと Oracle データベースの間はサポートされていません。 クライアントとアダプター間でサポートされます。\*|LOB の列の値によって ODP.NET、バッファーに格納され、挿入を実行し、ために、エンド ツー エンド ノードと値のストリーミングがサポートされていません。 ただし、ノードと値のクライアントとアダプター間のストリーミングは、クライアントがメッセージを作成する場合、LOB 列の可能な**BodyWriter**します。|  
|テーブルの選択の操作|Supported|Supported|アダプターを使用して、 **BodyWriter**応答メッセージを作成します。 クライアントがメッセージを使用して、使用する場合、 **XmlDictionaryWriter**ノードと値の LOB 列のストリーミングに発生します。|  
|テーブル更新操作|Supported|アダプターと Oracle データベースの間はサポートされていません。 クライアントとアダプター間でサポートされます。|LOB の列の値によって ODP.NET、バッファーに格納され、更新プログラムを実行し、ために、エンド ツー エンド ノードと値のストリーミングがサポートされていません。 ただし、ノード値が、クライアントとアダプター間のストリーミングが LOB 列のクライアントがメッセージを作成する場合、 **BodyWriter**します。|  
|テーブルの削除操作|Supported|アダプターと Oracle データベースの間はサポートされていません。 クライアントとアダプター間でサポートされます。|ODP.NET で LOB 列の値がバッファーに格納され、delete を実行し、ために、エンド ツー エンド ノードと値のストリーミングがサポートされていません。 ただし、ノード値が、クライアントとアダプター間のストリーミングが LOB 列のクライアントがメッセージを作成する場合、 **BodyWriter**します。|  
|テーブル ReadLOB 操作|Supported|Supported|ReadLOB 操作は、WCF サービス モデルでストリーム LOB データの列を主に設計されています。 クライアントがメッセージを使用して、使用する場合、WCF チャネル モデルで、 **XmlReader** (を呼び出すことによって、 **GetReaderAtBodyContents**メソッド応答メッセージを)、エンド ツー エンド ノードと値のストリーミングは発生します。 これは、アダプターを返すため、 **XmlReader**をサポートする**ReadValueChunk** ReadLOB 応答メッセージを呼び出します。 ただし、WCF チャネル モデルから ReadLOB 操作を使用しないことをお勧めします。 選択操作または SQLEXECUTE 操作を代わりに使用することができます。|  
|テーブル UpdateLOB 操作|Supported|Supported|アダプターを使用して、 **XmlDictionaryWriter**要求メッセージを処理します。 クライアントで使用する場合、 **BodyWriter**要求メッセージを作成するには、エンド ツー エンド ノードと値の LOB データ ストリーミングに発生します。|  
|SQLEXECUTE 操作|Supported|Supported|アダプターを使用して、 **BodyWriter**応答メッセージを作成します。<br /><br /> クライアントで使用する場合、 **XmlDictionaryWriter**応答メッセージを処理するには、エンド ツー エンド ノードと値を LOB データのストリーミングに発生します。<br /><br /> エンド ツー エンド ノードと値のストリーミングは、前に、Oracle データベースで操作を呼び出すことができます、アダプターはすべてのオペランドをバッファーする必要がありますので、要求メッセージのサポートされていません。|  
|ストアド プロシージャと関数の操作|Supported|Supported|アダプターを使用して、 **BodyWriter**応答メッセージを作成します。<br /><br /> クライアントで使用する場合、 **XmlDictionaryWriter**応答メッセージを処理するには、エンド ツー エンド ノードと値を LOB データのストリーミングに発生します。 (つまり、出力のストリーミングがサポートされていると IN をプロシージャと関数パラメーター、応答メッセージにします)。<br /><br /> エンド ツー エンド ノードと値のストリーミングは、前に、Oracle データベースで操作を呼び出すことができます、アダプターはすべてのオペランドをバッファーする必要がありますので、要求メッセージのサポートされていません。|  
|POLLINGSTMT 操作|Supported|Supported|アダプターを使用して、 **BodyWriter** POLLINGSTMT 要求メッセージを作成します。 クライアントがメッセージを使用して、使用する場合、 **XmlDictionaryWriter**ノードと値の LOB 列のストリーミングが行われます。|  
  
 LOB データが、コードでは WCF チャネル モデルを使用すると、ストリーミングを実装する方法については、次を参照してください。[ストリーミング Oracle LOB データ型を使用してデータベース、WCF チャネル モデル](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)します。  
  
## <a name="streaming-support-in-the-wcf-service-model"></a>WCF サービス モデルでのストリーミング サポート  
 メッセージの XML 表現とメッセージのマネージ コード オブジェクトの表現の間を逆シリアル化のシリアル化とは、メッセージ全体をメモリに読み書きが必要です。 このため、ストリーミング ノードもノード値のストリーミングもはほとんどの操作サポートされています。  
  
 唯一の例外は、ReadLOB 操作です。 この操作は、WCF サービス モデルでテーブルおよびビューの LOB 列を読み取るためのエンド ツー エンドのストリーミングをサポートするには、具体的には実装されます。  
  
## <a name="streaming-support-in-biztalk-server"></a>BizTalk Server でのストリーミング サポート  
 次の表では、BizTalk Server でのストリーミングのサポートについての詳細について説明します。 (すべての参照に「アダプター」を参照して、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; このテーブルの完全な名前で、Wcf-custom アダプターが常に参照する)。  
  
|操作|ノードのストリーミング|ノード値のストリーミング|説明|  
|---------------|--------------------|---------------------------|-----------------|  
|テーブルの挿入操作|サポートされています\*|アダプターと Oracle データベースの間はサポートされていませんただし、BizTalk Server とアダプター間のデータがストリーミングされます。|ODP.NET で LOB 列の値がバッファーに格納され、挿入を実行し、ために、エンド ツー エンド ノードと値のストリーミングがサポートされていません。 ノード値が BizTalk Server とアダプター間のストリーミングが LOB データ型のサポートされている Wcf-custom アダプターがメッセージを作成するため、ただし、 **BodyWriter**します。|  
|テーブルの選択の操作|Supported|Supported|Wcf-custom アダプターを使用して、 **XmlDictionaryWriter**エンド ツー エンド ノードと値の LOB 型のストリーミングがサポートされているため、応答メッセージを使用します。|  
|テーブル更新操作|Supported|アダプターと Oracle データベースの間はサポートされていませんただし、BizTalk Server とアダプター間のデータがストリーミングされます。|ODP.NET で LOB 列の値がバッファーに格納され、更新プログラムを実行し、ために、エンド ツー エンド ノードと値のストリーミングがサポートされていません。 ノード値が BizTalk Server とアダプター間のストリーミングが LOB データ型のサポートされている Wcf-custom アダプターがメッセージを作成するため、ただし、 **BodyWriter**します。|  
|テーブルの削除操作|Supported|アダプターと Oracle データベースの間はサポートされていませんただし、BizTalk Server とアダプター間のデータがストリーミングされます。|ODP.NET で LOB 列の値がバッファーに格納され、delete を実行し、ために、エンド ツー エンド ノードと値のストリーミングがサポートされていません。 ノード値が BizTalk Server とアダプター間のストリーミングが LOB データ型のサポートされている Wcf-custom アダプターがメッセージを作成するため、ただし、 **BodyWriter**します。|  
|テーブル ReadLOB 操作|BizTalk Server では、ReadLOB 操作はサポートされていません。|BizTalk Server では、ReadLOB 操作はサポートされていません。|BizTalk Server では、ReadLOB 操作はサポートされていません。 代わりに、選択操作または SQLEXECUTE 操作を使用します。|  
|テーブル UpdateLOB 操作|Supported|Supported|Wcf-custom アダプターを使用して、 **BodyWriter**エンド ツー エンド ノードと値のストリームの LOB データ型がサポートされているため、要求メッセージを作成します。|  
|SQLEXECUTE 操作|Supported|Supported|Wcf-custom アダプターを使用して、 **XmlDictionaryWriter**エンド ツー エンド ノードと値を応答メッセージの LOB データ型のストリーミングがサポートされているため、応答メッセージを使用します。<br /><br /> エンド ツー エンド ノードと値のストリーミングは、前に、Oracle データベースで操作を呼び出すことができます、アダプターはすべてのオペランドをバッファーする必要がありますので、要求メッセージのサポートされていません。|  
|ストアド プロシージャと関数の操作|Supported|Supported|Wcf-custom アダプターを使用して、 **XmlDictionaryWriter**エンド ツー エンド ノードと値を応答メッセージの LOB データ型のストリーミングがサポートされているため、応答メッセージを使用します。 (つまり、出力のストリーミングがサポートされていると IN をプロシージャと関数パラメーター、応答メッセージにします)。<br /><br /> エンド ツー エンド ノードと値のストリーミングは、前に、Oracle データベースで操作を呼び出すことができます、アダプターはすべてのオペランドをバッファーする必要がありますので、要求メッセージのサポートされていません。|  
|POLLINGSTMT 操作|Supported|Supported|Wcf-custom アダプターを使用して、 **XmlDictionaryWriter**エンド ツー エンド ノードと値のストリームの LOB データ型がサポートされているため、(受信) の要求メッセージを使用します。|  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションの開発](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)