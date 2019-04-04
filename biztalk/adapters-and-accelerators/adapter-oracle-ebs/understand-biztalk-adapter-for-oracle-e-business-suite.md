---
title: BizTalk Adapter for Oracle E-business Suite について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77a3f0a8-fc64-42cd-bb7c-0a6f527622e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebf84eef3d5e1ec4730926dd34b6533e1a7491f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980547"
---
# <a name="understand-biztalk-adapter-for-oracle-e-business-suite"></a>BizTalk Adapter for Oracle E-business Suite についてください。
## <a name="biztalk-adapter-pack-features"></a>BizTalk Adapter Pack の機能
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを使用します。 アダプターは、次の利点をクライアントに提供します。  
  
- **デザイン時エクスペリエンスの一貫性のある**します。 アダプターでは、参照、検索、および LOB アーティファクトのメタデータを取得するため、一般的な使いやすいもののデザイン時エクスペリエンスを提供します。  
  
- **プログラミングのオプションをさまざまな**します。 アダプターは、WCF、Windows Communication Foundation (WCF) チャネル モデルなどのプログラミング モデルの選択したサービス モデルでは、ADO.NET、Web サービス、または BizTalk Server でサポートされるモデルを提供します。  
  
- **Lob の間でのエクスペリエンス、統一された**します。 WCF を使用して、アダプターを標準化および[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、し、そのため、LOB システムへのアクセスのエクスペリエンスの一貫性を提供します。  
  
  前述のように、アダプターは WCF LOB Adapter SDK の上に構築されます。 WCF LOB Adapter SDK は、さまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションが使用できる統合アダプターを構築するための共通の基盤を提供します。 WCF LOB Adapter SDK は、Windows Communication Foundation (WCF) チャネルとしての統合アダプターを公開することで、Microsoft のサービスを使用したアダプターの戦略を配置します。 WCF LOB Adapter SDK の詳細については、[WCF LOB Adapter SDK ドキュメント](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)を参照してください。

## <a name="overview-of-the-oracle-ebs-adapter"></a>Oracle EBS アダプターの概要
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] WCF サービスとしての Oracle E-business Suite を公開します。 アダプター クライアントは、アダプターを使用した SOAP メッセージを交換することで、Oracle E-business Suite での操作を実行できます。 アダプターは、SOAP メッセージを使用し、操作を実行する適切な ODP.NET 呼び出しを行います。 アダプターは、Oracle E-business Suite から SOAP メッセージの形式でクライアントに応答を返します。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]Oracle E-business Suite の成果物 (PL/SQL Api、インターフェイス テーブル/ビュー、同時実行プログラム、および要求のセット) と、基になる Oracle データベース アイテム (テーブル、関数、プロシージャなど) を記述するメタデータを表示します。Web サービス記述言語 (WSDL) の形式で SOAP メッセージの構造体。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]アダプター クライアントの操作のメタデータを取得できるようにします。 アダプターには、プログラミング ソリューションで使用できるプログラミングの成果物も生成されます。 詳細については[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)します。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite との通信に Oracle Data Provider for .NET (ODP.NET) 11.1.0.7 を使用します。 ODP.NET 11.1.0.7 では、Oracle Data Access Components (ODAC) のコンポーネントの 1 つです。 使用することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の方法で、Oracle E-business Suite と通信します。  
  
- BizTalk アプリケーションを開発しています。 詳細については、[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)を参照してください。  
  
- 使用して、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル。 詳細については、[開発 Oracle データベース アプリケーションを使用して WCF サービス モデル](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)を参照してください。  
  
- WCF チャネル モデルを使用します。 詳細については、[WCF チャネル モデルを使用して SQL アプリケーションの開発](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)を参照してください。  

## <a name="access-to-oracle-e-business-suite"></a>Oracle E-business Suite へのアクセス
 Oracle E-business Suite で操作を実行するには、アダプター クライアントは、Oracle E-business Suite で関連する成果物へのアクセスが必要です。 外部のアプリケーションでは、追加したり、SQL ステートメントを使用して Oracle E-business Suite のインターフェイス テーブルと、データベース テーブル内のデータを削除することができます。 アプリケーションは、ビュー、関数、およびプロシージャを使用して、インターフェイス テーブルおよびデータベース テーブルのデータにアクセスできます。 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]、アダプター クライアントは、Oracle E-business Suite にも、基になるデータベースとの成果物を参照できます。 Oracle E-business suite でアダプター クライアントできます。 インターフェイス テーブル、インターフェイス ビュー、同時実行プログラムを参照して、基になる Oracle データベースのセットを要求、アダプターのクライアントは、テーブル、ビュー、ストアド プロシージャ、関数、PL/SQL Api を参照できます。、およびパッケージ。 アダプター クライアントは、成果物がソリューションの必要があり、それらの成果物のメタデータの取得を選択できます。 これにより、ユーザーにアクセスし、Oracle E-business Suite と基になる Oracle データベースで、成果物の操作を実行できます。  
  
 このセクションの機能の一覧、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]します。  
  
## <a name="more-good-stuff"></a>便利な機能  
  
-    [アダプターを使用して Oracle E-Business Suite に接続する](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-the-adapter.md)

- [参照、検索、および Oracle E-business Suite のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-oracle-e-business-suite-metadata.md)

- [Oracle E-business Suite アダプターによってサポートされる操作](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)

- [Oracle データベース アダプターでトランザクションを処理します。](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md) 

- [Oracle EBS アダプター クライアント用の機能](../../adapters-and-accelerators/adapter-oracle-ebs/features-for-oracle-ebs-adapter-clients.md) 

-   [BizTalk Adapter for Oracle E-business Suite の主要な機能](../../adapters-and-accelerators/adapter-oracle-ebs/key-features-in-biztalk-adapter-for-oracle-e-business-suite.md)  
  
-   [BizTalk adapter for Oracle E-business Suite の制限事項](../../adapters-and-accelerators/adapter-oracle-ebs/limitations-of-biztalk-adapter-for-oracle-e-business-suite.md)  
  
## <a name="see-also"></a>参照  
[開始するには](../../adapters-and-accelerators/adapter-oracle-ebs/get-started-with-the-biztalk-adapter-for-oracle-e-business-suite.md)