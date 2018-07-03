---
title: BizTalk Adapter for SQL Server について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 302a7f20-ffa2-49f1-a4c4-dd713adc23e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea21a06ad5d87e94118aaa45e2f6f541627aae9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996935"
---
# <a name="understand-biztalk-adapter-for-sql-server"></a>BizTalk Adapter for SQL Server についてください。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話することを行うサービス指向のプログラムでアクセスできます。 アダプターは、次の利点をクライアントに提供します。  
  
- **デザイン時エクスペリエンスの一貫性のある**します。 アダプターでは、参照、検索、および LOB アーティファクトのメタデータを取得するため、一般的な使いやすいもののデザイン時エクスペリエンスを提供します。  
  
- **プログラミングのオプションをさまざまな**します。 アダプターは、WCF、Windows Communication Foundation (WCF) チャネル モデルなどのプログラミング モデルの選択したサービス モデルでは、ADO.NET、Web サービス、または BizTalk には、モデルがサポートされているを提供します。  
  
- **Lob の間でのエクスペリエンス、統一された**します。 WCF を使用して、アダプターを標準化、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、し、そのため、LOB システムへのアクセスのエクスペリエンスの一貫性を提供します。  
  
  前述のように、アダプターは WCF LOB Adapter SDK の上に構築されます。 WCF LOB Adapter SDK は、さまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションが使用できる統合アダプターを構築するための共通の基盤を提供します。 WCF LOB Adapter SDK は、Windows Communication Foundation (WCF) チャネルとしての統合アダプターを公開することで、Microsoft のサービスを使用したアダプターの戦略を配置します。 WCF LOB Adapter SDK の詳細については、次を参照してください。 [WCF LOB Adapter SDK ドキュメント](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)します。
  
  SQL Server データベースで操作を実行するには、アダプター クライアントに関連するテーブル、プロシージャ、ビュー、スカラー関数は、アクセスし、テーブル値関数する必要があります。 データベース テーブルとは、SQL Server データベース内のストレージの基本単位です。 外部アプリケーションは、選択、挿入、削除、および SQL ステートメントを使用して、テーブルからデータを更新できます。 アプリケーションは、プロシージャ、ビュー、スカラー関数、およびテーブル値関数を使用して、テーブル内のデータをアクセスもできます。 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]、アダプター クライアントは、テーブル、プロシージャ、ビュー、および SQL Server データベースのような他のアイテムなどの成果物を参照できます。 アダプター クライアントでは、そのソリューションでは、必要な成果物を選択でき、それらの成果物のメタデータを取得することができます。 これにより、ユーザーにアクセスし、SQL Server データベースで、成果物の操作を実行できます。  
  
  このセクションの機能の一覧、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Adapter for SQL Server の概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)  
  
-   [BizTalk Adapter for SQL Server の主要な機能](../../adapters-and-accelerators/adapter-sql/key-features-in-biztalk-adapter-for-sql-server.md) 
  
-   [SQL Server 用 BizTalk アダプターの制限事項](../../adapters-and-accelerators/adapter-sql/limitations-of-biztalk-adapter-for-sql-server.md)  
  
## <a name="see-also"></a>参照  
[SQL 用 BizTalk アダプターを概要します。](../../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)