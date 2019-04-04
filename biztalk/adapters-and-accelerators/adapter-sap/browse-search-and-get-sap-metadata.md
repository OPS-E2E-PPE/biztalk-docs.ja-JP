---
title: 参照、検索、および SAP メタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata
- adapters, surfacing metadata
- TRFC
- RFC
- metadata, browsing, searching, retrieving
- adapters, operations
- BAPI
- IDOC
ms.assetid: 5f0d7c1f-d6e1-4c56-8d8e-1f5d537aa3ce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa942786cda8c5e1070b3fa1c66e3300ffd16d4f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984059"
---
# <a name="browse-search-and-get-sap-metadata"></a>参照、検索、および SAP メタデータの取得
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムからのサーフェスのメタデータ。 このメタデータには、アダプターを使用して SAP システムと通信するためのメッセージの構造について説明します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
- **MetadataExchange**によって提供される[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。 WCF は、これにより、SAP システムからメタデータを取得するクライアントにすべての WCF バインドのメタデータ交換エンドポイントに提供します。  
  
- **IMetadataRetrievalContract**によって提供される、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、閲覧と検索機能を備えたアダプターのメタデータをサポートしています。  
  
  目標の 1 つ、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は WCF サービスとしての SAP システムを公開します。 アダプターでは、アダプターのクライアントが呼び出すことができる操作として SAP アイテム (Rfc、Bapi、Idoc) が表示されます。 アダプターでは、送信または SAP システムから Idoc を受信するために使用できるいくつかの特定の操作も表示されます。 これらの操作は、このトピックで後で表示されます。  
  
  参照、検索、および WCF チャネル モデルを使用して、WCF サービス モデルを使用してメタデータを取得または BizTalk を作成してプロジェクトを行うことが[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  
  
  使用する必要があります、WCF サービス モデルを使用する場合、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] SAP システムの操作を実行するためのプロキシ クラスを生成します。 使用する必要がある BizTalk プロジェクトを使用する場合、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]SAP システムで実行する操作のメタデータを生成します。  
  
  参照、検索、およびメタデータを使用した取得の詳細については[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Visual Studio で SAP 操作のメタデータの取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)します。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントが Rfc、Trfc、Bapi、および SAP システムによって公開される Idoc を参照できるようにします。 メタデータの参照操作の一環として、アダプターは操作として Rfc および Bapi を表示します。 、Idoc のアダプターには、Idoc を送受信するための操作が表示されます。 これらの操作はから利用可能な[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 SAP メタデータは、次のノードの下に分類されます。  
  
- **RFC**します。 このノードは、SAP システムによって公開されている Rfc を含み、SAP で関数モジュールを表します。 アダプターは、Rfc を複数の論理レベルに分類し、アダプターのクライアントを階層ビューを公開します。 RFC がこの階層の最下位レベルであり、外部アプリケーションによって呼び出すことができる操作として公開されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC SDK を使用して、Rfc のメタデータを生成します。 アダプターは、メタデータを生成できます Rfc のみを呼び出すことができます。  
  
   以外の操作として Rfc を表示するには、アダプターもサーフェスのいくつかの特定の操作など**RfcGetAttributes**します。 これらの操作の詳細については、[SAP で Rfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)を参照してください。  
  
- **TRFC**. このノードには、SAP システムによって公開される Trfc が含まれています。 Trfc は、SAP システムが Rfc を呼び出すためのメカニズムではなくで従来の成果物ではありません。 Trfc は、メタデータ特性が Rfc に異なるため、個別のノード下に分類されます。 具体的には、Rfc には、エクスポートのパラメーターも含まれます。 アダプターは、Trfc を複数の論理レベルに分類し、アダプターのクライアントを階層ビューを公開します。 TRFC がこの階層の最下位レベルであり、外部アプリケーションによって呼び出すことができる操作として公開されます。  
  
   以外の操作として Trfc を提示するには、アダプターもサーフェスのいくつかの特定の操作など**RfcConfirmTransID**します。 これらの操作の詳細については、[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)を参照してください。  
  
- **BAPI**します。 このノードには、SAP システムによって公開される Bapi が含まれています。 アダプターは、Bapi を複数の論理レベルに分類し、アダプターのクライアントを階層ビューを公開します。 BAPI がこの階層の最下位レベルであり、外部アプリケーションによって呼び出すことができる操作として公開されます。  
  
- **IDOC**します。 このノードには、SAP システムによって公開される Idoc が含まれています。 アダプターは、Idoc を複数の論理レベルに分類し、アダプターのクライアントを階層ビューを公開します。 アダプターが、Idoc 用に公開する操作は次のとおりです。  
  
  - **送信**と**受信**します。 アダプターのクライアントは、厳密に型指定されたスキーマを使用して SAP システムから Idoc を送受信するこれらの操作を使用できます。  
  
  - **SendIdoc**と**ReceiveIdoc**します。 アダプターのクライアントは、厳密に型指定のスキーマを使用して SAP システムから Idoc を送受信するこれらの操作を使用できます。  
  
    これらの操作の詳細については、[sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)を参照してください。  
  
  メタデータの分類方法の詳細については、[メタデータ ノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)を参照してください。  
  
## <a name="searching-metadata"></a>メタデータの検索  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、アダプター クライアントは、基になる Rfc に依存する検索式を使用して SAP システムでメタデータを検索することができる[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用します。 次の表は、SAP アイテムとメタデータの階層をアダプター クライアントを検索できます。  
  
|成果物|GUI でノードの下の検索|  
|--------------|------------------------------------|  
|RFC|-   /RFC<br />-/RFC/[アプリケーション グループ]|  
|tRFC|-   /TRFC<br />-/TRFC/[アプリケーション グループ]|  
|BAPI|-/BAPI|  
|IDOC|-/IDOC|  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|+ (プラス)|1 つだけの文字と一致します。<br /><br /> たとえば、A + と一致する AB、AC、AD|  
|* (アスタリスク)|0 個以上の文字と一致します。<br /><br /> たとえば、A * A、AB ABC に一致します。|  
  
## <a name="retrieving-metadata"></a>メタデータの取得  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]によりアダプターでクライアントに詳細なメタデータ特性を含め、SAP システムのメタデータを取得します。  
  
- RFC、用、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]インポート、エクスポート、変更、およびテーブル パラメーターと共に RFC 名前を取得します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]もパラメーター、パラメーター、フィールド長のデータ型を必須および省略可能なパラメーターをさらに取得します。  
  
- TRFC は、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]エクスポート パラメーターを除き、RFC のような詳細を取得します。 TRFC の呼び出しは非同期であるために、出力パラメーターは取得されません。  
  
- BAPI、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ビジネス オブジェクトの名前、ビジネス オブジェクトのメソッド名、および Rfc のようなその他の特定の情報を取得します。  
  
- IDOC での[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]IDOC の種類、リリース番号、バージョン、IDOC 制御レコード、IDOC データ レコード、およびその他の IDOC のセグメント情報を取得します。  
  
  > [!NOTE]
  >  IDOC のメタデータには、データ型の場合は、下限と上限の両方の値 (範囲) が含まれている場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を文字列として公開します。 メタデータには、低値のみが含まれている場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]列挙型として公開します。  
  
> [!NOTE]
>  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP 関数定義でパラメーターが順序付け方法に関係なく、アルファベット順で SAP 関数のパラメーターを公開します。 これは、次の理由。  
> 
> - 異なるバージョンの SAP の RFC SDK は、異なる順序での SAP の関数のパラメーターを返します。 そのため、アダプターのユーザーに一貫したエクスペリエンスを提供するために、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アルファベット順の順序でパラメーターを公開します。  
>   - 異なる SAP サーバーに同じ Rfc には、別の順序の関数のパラメーターを公開する可能性があります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]一貫性のあるアルファベット順にパラメーターを公開することで、この違いをユーザーに透過的なにより、します。  
> 
> [!NOTE]
>  使用して SAP システムからデータを取得中に、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 65536 の複数のノードを持つメッセージを逆シリアル化ではありません。 応答メッセージが 65536 のノード以下を確認します。 この制限を回避するには、アプリケーションの app.config ファイルを変更します。 手順については、[運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)を参照してください。  
  
 詳細については、参照、検索、およびメタデータを取得するを参照してください[Visual Studio で SAP 操作のメタデータの取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter 用 mySAP Business Suite のアーキテクチャの概要](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)