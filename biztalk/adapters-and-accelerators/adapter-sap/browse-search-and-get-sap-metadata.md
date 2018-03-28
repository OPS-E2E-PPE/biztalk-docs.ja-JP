---
title: 参照、検索、および SAP メタデータの取得 |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40cc1bd6592b38dbda9c9bff3ad01d6cdaf8a707
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="browse-search-and-get-sap-metadata"></a>参照、検索、および SAP メタデータの取得
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムからのサーフェス メタデータ。 このメタデータは、アダプターを使用して SAP システムと通信するためのメッセージの構造を記述します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
-   **MetadataExchange**によって提供される[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。 WCF は、クライアントが、SAP システムからメタデータを取得することができますにすべての WCF バインドをメタデータ交換エンドポイントに提供します。  
  
-   **IMetadataRetrievalContract**によって提供される、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]をサポートするメタデータ参照とアダプターの機能を検索します。  
  
 目標の 1 つ、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、WCF サービスとして SAP システムを公開します。 アダプターは、アダプターのクライアントが呼び出すことのできる操作として SAP アイテム (Rfc、Bapi、および Idoc) を表示します。 アダプターでは、いくつかを特定の操作を送信または SAP システムから Idoc を受信することできますも明らかです。 これらの操作は、このトピックの後半に一覧表示されます。  
  
 参照、検索、およびモデルを使用して、WCF サービス、WCF チャネル モデルを使用してメタデータを取得または BizTalk を作成することで、プロジェクトで行うことが[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
 使用する必要があります、WCF サービス モデルを使用する場合、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] SAP システムでの操作を実行するプロキシ クラスを生成します。 BizTalk プロジェクトを使用する場合は、使用、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]SAP システムで実行する操作のメタデータを生成します。  
  
 閲覧、検索、およびを使用してメタデータの取得の詳細については[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Visual Studio での SAP 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)です。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Rfc、tRFCs、Bapi、および Idoc が SAP システムによって公開されているを参照するアダプターのクライアントを有効にします。 メタデータの参照操作の一環として、アダプター サーフェスの Rfc および Bapi の操作として。 Idoc、アダプターは Idoc を送受信するための操作を表示します。 これらの操作はから利用可能な[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 SAP メタデータは、次のノードの下にある分類されます。  
  
-   **RFC**. このノードは、SAP システムによって公開されている Rfc が含まれています、SAP の関数モジュールを表します。 アダプターは、Rfc では複数の論理レベルに分類し、アダプターのクライアントを階層ビューを公開します。 RFC は、この階層の最下位レベルにあるし、外部アプリケーションから呼び出すことができる操作として公開されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC SDK を使用して、Rfc のメタデータを生成します。 アダプターは、対象のメタデータが生成できます Rfc のみを呼び出すことができます。  
  
     以外の操作として、Rfc を提示するには、アダプターも明らかによって特定の操作など**RfcGetAttributes**です。 これらの操作の詳細については、次を参照してください。 [SAP Rfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)です。  
  
-   **TRFC**. このノードには、SAP システムによって公開される tRFCs が含まれています。 tRFCs で、SAP システムが Rfc を呼び出すためのメカニズムではなく、従来の成果物ではありません。 そのメタデータの特性は Rfc 異なるのでは個別のノード下 tRFCs に分類されます。 具体的には、Rfc には、エクスポートのパラメーターも含まれます。 アダプターは、tRFCs を複数の論理レベルに分類し、アダプターのクライアントを階層ビューを公開します。 TRFC はこの階層の最下位レベルにあるし、外部アプリケーションから呼び出すことができる操作として公開されます。  
  
     以外の操作として tRFCs を提示するには、アダプターも明らかによって特定の操作など**RfcConfirmTransID**です。 これらの操作の詳細については、次を参照してください。 [SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。  
  
-   **BAPI**. このノードには、SAP システムによって公開される Bapi が含まれています。 アダプターでの Bapi は複数の論理レベルに分類し、アダプターのクライアントを階層ビューを公開します。 BAPI はこの階層の最下位レベルにあるし、外部アプリケーションから呼び出すことができる操作として公開されます。  
  
-   **IDOC**. このノードには、SAP システムによって公開される Idoc が含まれています。 アダプターは、Idoc を複数の論理レベルに分類し、アダプターのクライアントを階層ビューを公開します。 アダプターは、Idoc の公開される操作は次のとおりです。  
  
    -   **送信**と**受信**です。 アダプターのクライアントは、厳密に型指定されたスキーマを使用して SAP システムから Idoc を送受信するこれらの操作を使用できます。  
  
    -   **SendIdoc**と**ReceiveIdoc**です。 アダプターのクライアントは、弱い型指定のスキーマを使用して SAP システムから Idoc を送受信するこれらの操作を使用できます。  
  
     これらの操作の詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)です。  
  
 メタデータを分類する方法の詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。  
  
## <a name="searching-metadata"></a>メタデータの検索  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、アダプターのクライアントは、基になる Rfc に依存する検索式を使用して SAP システムでメタデータを検索することを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用します。 次の表は、SAP アイテムとメタデータ階層をアダプターのクライアントを検索できます。  
  
|成果物|GUI でのノードの下の検索|  
|--------------|------------------------------------|  
|RFC|-   /RFC<br />-   /RFC/[Application Group]|  
|tRFC|-   /TRFC<br />-/TRFC/[アプリケーション グループ]|  
|BAPI|-   /BAPI|  
|IDOC|-   /IDOC|  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|+ (プラス)|1 文字と一致します。<br /><br /> たとえば、A + 一致 AB、AC、AD|  
|* (アスタリスク)|0 個以上の文字と一致します。<br /><br /> たとえば、A * A、AB、ABC に一致します。|  
  
## <a name="retrieving-metadata"></a>メタデータの取得  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントが、詳細なメタデータの特徴を含む、SAP システムのメタデータを取得できるようにします。  
  
-   RFC、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]インポート、エクスポート、変更、およびテーブルのパラメーターと共に RFC 名を取得します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]も、パラメーターのフィールドの長さのパラメーターのデータ型を必須およびオプションのパラメーターをさらに取得します。  
  
-   A tRFC の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]エクスポート パラメーターを除き、RFC のような詳細情報を取得します。 TRFC の呼び出しは非同期であるために、出力パラメーターは取得されません。  
  
-   BAPI、用、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ビジネス オブジェクトの名前、ビジネス オブジェクトのメソッド名、および Rfc のようなその他の特定の情報を取得します。  
  
-   IDOC の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]IDOC の種類、リリース番号、バージョン、IDOC 制御レコード、IDOC データ レコード、およびその他の IDOC セグメント情報を取得します。  
  
    > [!NOTE]
    >  IDOC のメタデータには、データ型の場合は、低、高の両方の値 (範囲) が含まれている場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を文字列として公開します。 メタデータには、不足値のみが含まれている場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]列挙型として公開します。  
  
> [!NOTE]
>  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP 関数定義でパラメーターの順序付け方法に関係なく、アルファベット順に SAP 関数のパラメーターを公開します。 これは、次の理由です。  
>   
>  -   異なるバージョンの SAP RFC SDK は、異なる順序で SAP 関数のパラメーターを返します。 そのため、アダプターのユーザーに一貫した使用環境を提供するために、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アルファベット順では、パラメーターを公開します。  
> -   異なる SAP サーバーに同じ Rfc 関数のパラメーターを公開するための順序が異なることができます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]この違いは透過的に実行したユーザー一貫性のあるアルファベット順では、パラメーターを公開することによりします。  
  
> [!NOTE]
>  SAP システムを使用して、データを取得中に、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 65536 以上のノードを持つメッセージを逆シリアル化ではありません。 応答メッセージに 65536 のノード少ないがあることを確認してください。 この制限は、アプリケーションの app.config ファイルを変更することで回避できます。 手順については、次を参照してください。[運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)です。  
  
 詳細については、参照、検索、およびメタデータを取得するを参照してください[Visual Studio での SAP 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk adapter 用 mySAP Business Suite のアーキテクチャの概要](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)