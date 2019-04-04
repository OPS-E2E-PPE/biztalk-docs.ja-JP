---
title: Oracle データベースの BizTalk アダプターの理解 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF LOB Adapter SDK
- features of Oracle database adapter
- table
- adapter client
- service model
- WCF
- artifacts
- database tables
- adapters, features
- Windows Communication Foundation
- adapter features
- channel model
ms.assetid: a8691957-0430-4cba-83f8-b60c21a86849
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fda25d77571a3c0128317a557e5f9d15bbc472
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994619"
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a>Oracle データベースの BizTalk アダプターを理解します。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを使用します。 アダプターは、次の利点をクライアントに提供します。  
  
- **デザイン時エクスペリエンスの一貫性のある**します。 アダプターでは、参照、検索、および LOB アーティファクトのメタデータを取得するため、一般的な使いやすいもののデザイン時エクスペリエンスを提供します。  
  
- **プログラミングのオプションをさまざまな**します。 アダプターは、WCF、Windows Communication Foundation (WCF) チャネル モデルなどのプログラミング モデルの選択したサービス モデルでは、ADO.NET、Web サービス、または BizTalk には、モデルがサポートされているを提供します。  
  
- **Lob の間でのエクスペリエンス、統一された**します。 WCF を使用して、アダプターを標準化および[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、し、そのため、LOB システムへのアクセスのエクスペリエンスの一貫性を提供します。  
  
  前述のように、アダプターは WCF LOB Adapter SDK の上に構築されます。 WCF LOB Adapter SDK は、さまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションが使用できる統合アダプターを構築するための共通の基盤を提供します。 WCF LOB Adapter SDK は、Windows Communication Foundation (WCF) チャネルとしての統合アダプターを公開することで、Microsoft のサービスを使用したアダプターの戦略を配置します。 WCF LOB Adapter SDK の詳細については、[WCF LOB Adapter SDK ドキュメント](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)を参照してください。
  
  Oracle データベースで操作を実行するには、アダプター クライアントは、関連するテーブル、関数、およびプロシージャにアクセスする必要があります。 データベース テーブルとは、Oracle データベース内のストレージの基本単位です。 外部のアプリケーションでは、追加したり、SQL ステートメントを使用してテーブルからデータを削除することができます。 アプリケーションは、ビュー、関数、およびプロシージャを使用して、テーブル内のデータをアクセスもできます。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]、アダプター クライアントは、テーブル、プロシージャ、パッケージ、ビュー、および Oracle データベースでこのようなその他の項目などの成果物を参照できます。 アダプター クライアントは、成果物がソリューションの必要があり、それらの成果物のメタデータの取得を選択できます。 これにより、ユーザーにアクセスし、Oracle データベースで、成果物の操作を実行できます。  
  
  このセクションの機能の一覧、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Adapter for Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [BizTalk Adapter for Oracle Database の主要な機能](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [Oracle Database の BizTalk アダプターの制限事項](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a>参照  
[BizTalk Server の概要](../../core/getting-started-with-biztalk-server.md)