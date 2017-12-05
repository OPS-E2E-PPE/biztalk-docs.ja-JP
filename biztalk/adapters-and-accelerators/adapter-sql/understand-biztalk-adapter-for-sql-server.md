---
title: "SQL Server の BizTalk アダプターを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 302a7f20-ffa2-49f1-a4c4-dd713adc23e1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fc14b7d9da40edd56c4c4cc4fa6b795386518db
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="understand-biztalk-adapter-for-sql-server"></a>SQL Server の BizTalk アダプターを理解します。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話できるようにするサービス指向のプログラムによるアクセスを有効にします。 アダプターでは、次の利点をクライアントに使用します。  
  
-   **デザイン時のエクスペリエンスを一貫した**です。 アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するために共通で使いやすいデザイン時機能を提供します。  
  
-   **さまざまなプログラミング オプション**です。 など、Windows Communication Foundation (WCF) チャネル モデルを WCF プログラミング モデルの選択肢のサービス モデルでは、ADO.NET、Web サービス、または BizTalk には、モデルがサポートされているアダプターを提供します。  
  
-   **Lob の間でのエクスペリエンス、統一された**です。 WCF を使用して、アダプターが標準化され、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、でき、したがって一貫した環境での任意の LOB システムへのアクセスを取得します。  
  
 前述のように、アダプターは、上に組み込ま、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]のさまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションで使用できる統合アダプターを構築するための共通の基本を提供します。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が Windows Communication Foundation (WCF) チャネルとの統合アダプターを公開することにより、アダプター戦略の Microsoft サービスの戦略を揃えて配置します。 詳細については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を参照してください、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ドキュメント。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]と共にドキュメントがインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通常 \<インストール ドライブ\>: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents です。  
  
 SQL Server データベースでの操作を実行するには、アダプター クライアントに関連するテーブル、プロシージャ、ビュー、スカラー関数は、アクセスし、テーブル値関数します。 データベース テーブルとは、SQL Server データベース内のストレージの基本単位です。 外部アプリケーションは、選択、挿入、削除、および SQL ステートメントを使用して、テーブルからデータを更新できます。 アプリケーションは、プロシージャ、ビュー、スカラー関数、およびテーブル値関数を使用して、テーブル内のデータもアクセスできます。 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アダプターのクライアントは、テーブル、プロシージャ、ビュー、および SQL Server データベースでこのようなその他の項目などの成果物を参照できます。 アダプターのクライアントでは、そのソリューションに必要な成果物を選択でき、それらの成果物のメタデータを取得することができます。 これにより、ユーザーにアクセスし、SQL Server データベースのアイテムでは、操作を実行できます。  
  
 このセクションの機能の一覧、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Adapter for SQL Server の概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)  
  
-   [BizTalk Adapter for SQL Server の主要な機能](../../adapters-and-accelerators/adapter-sql/key-features-in-biztalk-adapter-for-sql-server.md) 
  
-   [BizTalk adapter for SQL Server の制限事項](../../adapters-and-accelerators/adapter-sql/limitations-of-biztalk-adapter-for-sql-server.md)  
  
## <a name="see-also"></a>参照  
[SQL 用 BizTalk アダプターを概要します。](../../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)