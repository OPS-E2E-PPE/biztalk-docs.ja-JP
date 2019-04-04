---
title: 参照、検索、および Siebel メタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77a02e62bcea6a1647859b8578279ee97f2349d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980539"
---
# <a name="browse-search-and-get-siebel-metadata"></a>参照、検索、および Siebel メタデータの取得
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプターを使用して Siebel システムと通信するためのメッセージ構造を記述する Siebel システムからのサーフェスのメタデータ。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
- によって提供される MetadataExchange[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。 WCF は、クライアントが Siebel システムからメタデータを取得できるようにするにすべての WCF バインドのメタデータ交換エンドポイントに提供します。  
  
- によって提供される IMetadataRetrievalContract、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、閲覧と検索機能を備えたアダプターのメタデータをサポートしています。  
  
  目標、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]は WCF サービスとしての Siebel システムを公開します。 アダプターでは、アダプターのクライアントが呼び出すことができる操作として Siebel の成果物 (ビジネス オブジェクトおよびビジネス サービス) が表示されます。  
  
  アダプター クライアント参照、検索と WCF チャネル モデルを使用して、WCF サービス モデルを使用してメタデータを取得したりするには、BizTalk プロジェクト[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 使用する必要があります、WCF サービス モデルを使用する場合、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] Siebel システムの操作を実行するためのプロキシ クラスを生成します。 使用する必要がある BizTalk プロジェクトを使用する場合、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] Siebel システム上で実行する操作のメタデータを生成します。 参照、検索、およびメタデータを使用した取得の詳細については、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Visual Studio で Siebel 操作のメタデータの取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)します。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアントが、ビジネス オブジェクトと Siebel システムによって公開されるビジネス サービスを参照できるようにします。 メタデータの参照操作の一環として、アダプターは、成果物を複数の論理レベルに分類し、メタデータをアダプター クライアントの階層ビューを公開します。 Siebel システムからのメタデータは、次のノードの下に分類されます。  
  
- **ビジネス オブジェクト**します。 このノードには、Siebel ビジネス コンポーネントの論理コレクションであるシステムでのビジネス オブジェクトが含まれています。 さらに、ビジネス オブジェクトは、ビジネス コンポーネントとして分類されます。 階層の最下位レベルでは、ビジネス コンポーネントを呼び出すことができる操作を示します。  
  
- **ビジネス サービス**します。 このノードには、Siebel システムによって公開されるビジネス サービスが含まれています。 Siebel ビジネス サービスは、Siebel システムで直接呼び出すことがあるビジネス サービス メソッドまたは関数のコレクションです。  
  
  メタデータの分類方法の詳細については、[メタデータ ノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)を参照してください。  
  
## <a name="searching-metadata"></a>メタデータの検索  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアントが Siebel システムでメタデータを検索できるようにします。 この機能を使用するには、Siebel と互換性のある検索式は、メタデータを参照するために使用する Siebel リポジトリ ビジネス コンポーネントの [名前] フィールドで演算子などの有効な Siebel を使用します。 次の表は、Siebel の成果物とメタデータの階層を検索することができます。  
  
|成果物|GUI でノードの下の検索|  
|--------------|----------------------------------------|  
|ビジネス オブジェクト|/ビジネス オブジェクト|  
|ビジネス コンポーネント|/ビジネス オブジェクト/ビジネス オブジェクトの名前|  
|ビジネス サービス|/ビジネス サービス|  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|? (疑問符)|1 つだけの文字と一致します。<br /><br /> たとえば、A か。AB、AC、AD と一致します。|  
|* (アスタリスク)|0 個以上の文字と一致します。<br /><br /> たとえば、A * A、AB ABC に一致します。|  
  
## <a name="retrieving-metadata"></a>メタデータの取得  
 メタデータを取得するときに、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]すべてまたはビジネス オブジェクトまたはビジネス サービスに、それぞれの操作パラメーターのサブセットを含むスキーマの下でメタデータを抽出することができます。 XML 内の要素名として、Siebel システムからエンティティを表示します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]によりアダプターでクライアントに詳細なメタデータ特性を含め、Siebel システムのメタデータを取得します。  
  
- ビジネス コンポーネントの場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ビジネス オブジェクトの名前、ビジネス コンポーネント名、フィールド名、データ型、フィールド長、必須フィールドであり、省略可能なフィールドは、および候補リスト フィールドには、このような項目を取得します。 アダプターでは、INSERT、UPDATE、DELETE、およびクエリなど、ビジネス コンポーネントの実行可能な操作も取得します。  
  
- ビジネス サービス メソッドの場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ビジネス サービス名、メソッド名 (操作と同じ)、メソッド パラメーター、およびパラメーターのデータ型としては、このような項目を取得します。  
  
  メタデータの取得の詳細については、[Visual Studio で Siebel 操作のメタデータの取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Siebel eBusiness Applications の概要](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)