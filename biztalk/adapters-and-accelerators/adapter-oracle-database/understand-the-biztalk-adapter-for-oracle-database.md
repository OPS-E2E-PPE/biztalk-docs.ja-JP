---
title: "Oracle データベースの BizTalk アダプターを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb2d3603bb6d7c64d355c88420167344f564ddd8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a>Oracle データベースの BizTalk アダプターを理解します。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを有効にします。 アダプターでは、次の利点をクライアントに使用します。  
  
-   **デザイン時のエクスペリエンスを一貫した**です。 アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するために共通で使いやすいデザイン時機能を提供します。  
  
-   **さまざまなプログラミング オプション**です。 など、Windows Communication Foundation (WCF) チャネル モデルを WCF プログラミング モデルの選択肢のサービス モデルでは、ADO.NET、Web サービス、または BizTalk には、モデルがサポートされているアダプターを提供します。  
  
-   **Lob の間でのエクスペリエンス、統一された**です。 アダプターは、WCF を使用して標準化および[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、でき、したがって一貫した環境での任意の LOB システムへのアクセスを取得します。  
  
 前述のように、アダプターは、上に組み込ま、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]のさまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションで使用できる統合アダプターを構築するための共通の基本を提供します。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が Windows Communication Foundation (WCF) チャネルとの統合アダプターを公開することにより、アダプター戦略の Microsoft サービスの戦略を揃えて配置します。 詳細については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を参照してください、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ドキュメント。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]と共にドキュメントがインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通常 \<インストール ドライブ\>: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents です。  
  
 Oracle データベースでの操作を実行するには、アダプターのクライアントは、関連するテーブル、関数、およびプロシージャへのアクセスが必要です。 データベース テーブルとは、Oracle データベースでの記憶域の基本単位です。 外部アプリケーションでは、追加したり、SQL ステートメントを使用してテーブルからデータを削除することができます。 アプリケーションは、ビュー、関数、およびプロシージャを使用して、テーブル内のデータもアクセスできます。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]アダプターのクライアントは、テーブル、プロシージャ、パッケージ、ビュー、および Oracle データベースでこのようなその他の項目などの成果物を参照できます。 アダプターのクライアントは、成果物がソリューションの必要があり、それらの成果物のメタデータを取得を選択できます。 これにより、ユーザーにアクセスし、Oracle データベースでのアイテムでは、操作を実行できます。  
  
 このセクションの機能の一覧、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Adapter for Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [BizTalk Adapter 用 Oracle Database の主要な機能](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [Oracle Database の BizTalk アダプターの制限事項](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a>参照  
[BizTalk Server の概要](../../core/getting-started-with-biztalk-server.md)