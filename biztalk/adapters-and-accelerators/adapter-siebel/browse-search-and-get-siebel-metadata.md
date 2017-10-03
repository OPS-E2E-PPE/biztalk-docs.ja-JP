---
title: "参照、検索、および Siebel メタデータの取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metadata, retrieving
- metadata, surfacing
- retrieving, metadata
- metadata, browsing
- browsing, metadata
- metadata, searching
- searching, metadata
ms.assetid: 48fc3bb1-b949-4b8d-ab62-a41cd8c2f0a0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef1ed7d74b4e69f56c53beda8273533bb6891a55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-siebel-metadata"></a>参照、検索、および Siebel メタデータの取得
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプターを使用して、Siebel システムと通信するためのメッセージ構造を記述する Siebel システムからのサーフェス メタデータ。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
-   によって提供される MetadataExchange[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。 WCF は、クライアントが Siebel システムからメタデータを取得することができますにすべての WCF バインドをメタデータ交換エンドポイントに提供します。  
  
-   によって提供される IMetadataRetrievalContract、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]をサポートするメタデータ参照とアダプターの機能を検索します。  
  
 目的、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]を WCF サービスとしての Siebel システムに公開されます。 アダプターは、アダプターのクライアントが呼び出すことのできる操作として Siebel の成果物 (ビジネス オブジェクト、およびビジネス サービス) を表示します。  
  
 アダプター クライアントできます参照、検索、およびモデルを使用して、WCF サービス、WCF チャネル モデルを使用してメタデータを取得または BizTalk を作成することで、プロジェクトで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 使用する必要があります、WCF サービス モデルを使用する場合、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] Siebel システムの操作を実行するためのプロキシ クラスを生成します。 使用する必要があります、BizTalk プロジェクトを使用する場合、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] Siebel システム上で実行する操作のメタデータを生成します。 閲覧、検索、およびを使用してメタデータの取得の詳細については、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Siebel 操作の Visual Studio でのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)です。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ビジネス オブジェクト、および Siebel システムによって公開されるビジネス サービスを参照するアダプターのクライアントを有効にします。 メタデータの参照操作の一環としては、アダプターは、アイテムを複数の論理レベルに分類し、アダプターのクライアントにメタデータの階層ビューを公開します。 Siebel システムからのメタデータは、次のノードの下にある分類されます。  
  
-   **ビジネス オブジェクト**です。 このノードには、ビジネス コンポーネントの論理的なコレクションの Siebel システムのビジネス オブジェクトが含まれています。 ビジネス オブジェクトは、さらに、ビジネス コンポーネントとして分類されます。 階層の最下位レベルで、ビジネス コンポーネントを呼び出すことのできる操作です。  
  
-   **ビジネス サービス**です。 このノードには、Siebel システムによって公開されるビジネス サービスが含まれています。 Siebel ビジネス サービスは、Siebel システムで直接呼び出すことがあるビジネス サービス メソッドまたは関数のコレクションです。  
  
 メタデータを分類する方法の詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)です。  
  
## <a name="searching-metadata"></a>メタデータの検索  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]の Siebel システム メタデータを検索するアダプターのクライアントを有効にします。 この機能を使用するには、Siebel と互換性のある検索式は、メタデータの参照に使用される Siebel リポジトリ ビジネス コンポーネントの [名前] フィールドに演算子などの有効な Siebel を使用します。 次の表には、Siebel 成果物および検索することができますをメタデータの階層が一覧表示します。  
  
|成果物|GUI でのノードの下の検索|  
|--------------|----------------------------------------|  
|ビジネス オブジェクト|/ビジネス オブジェクト|  
|ビジネス コンポーネント|/ビジネス オブジェクト/ビジネス オブジェクトの名前|  
|ビジネス サービス|/ビジネス サービス|  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|? (疑問符 (?))|1 文字と一致します。<br /><br /> たとえば、A か。AB、AC、AD と一致します。|  
|* (アスタリスク)|0 個以上の文字と一致します。<br /><br /> たとえば、A * A、AB、ABC に一致します。|  
  
## <a name="retrieving-metadata"></a>メタデータの取得  
 メタデータを取得するときに、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]すべてまたは一部のビジネス オブジェクトまたはビジネス パラメーターを持つサービス、該当する操作をなど、スキーマの下でメタデータを抽出できます。 XML 内の要素名として、Siebel システムからエンティティを表示します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアントの詳細なメタデータの特徴を含む、Siebel システムのメタデータを取得できるようにします。  
  
-   ビジネス コンポーネントの場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]とビジネス オブジェクトの名前、ビジネス コンポーネント名、フィールド名、データ型、フィールド長、フィールドが必ず含ま、省略可能なフィールドは、候補リストのフィールドには、このような項目を取得します。 アダプターには、INSERT、UPDATE、DELETE、およびクエリなど、ビジネス コンポーネントの実行可能な操作も取得します。  
  
-   ビジネス サービス メソッドの場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ビジネス サービス名、メソッド名 (操作と同じ)、メソッドのパラメーター、およびパラメーターのデータ型などの項目を取得します。  
  
 メタデータの取得の詳細については、次を参照してください。 [Siebel 操作の Visual Studio でのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk adapter 用 Siebel eBusiness Applications の概要](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)