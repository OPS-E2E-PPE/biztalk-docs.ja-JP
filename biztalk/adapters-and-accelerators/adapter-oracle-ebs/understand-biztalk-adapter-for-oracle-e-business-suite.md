---
title: "Oracle E-business Suite の BizTalk アダプターを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77a3f0a8-fc64-42cd-bb7c-0a6f527622e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1fa12862600cd1d1d5661e278b87c82cc45697b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="understand-biztalk-adapter-for-oracle-e-business-suite"></a>Oracle E-business Suite の BizTalk アダプターを理解します。
## <a name="biztalk-adapter-pack-features"></a>BizTalk Adapter Pack の機能
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを有効にします。 アダプターでは、次の利点をクライアントに使用します。  
  
-   **デザイン時のエクスペリエンスを一貫した**です。 アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するために共通で使いやすいデザイン時機能を提供します。  
  
-   **さまざまなプログラミング オプション**です。 など、Windows Communication Foundation (WCF) チャネル モデルを WCF プログラミング モデルの選択肢のサービス モデルでは、ADO.NET、Web サービス、または BizTalk Server には、モデルがサポートされているアダプターを提供します。  
  
-   **Lob の間でのエクスペリエンス、統一された**です。 アダプターは、WCF を使用して標準化および[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、でき、したがって一貫した環境での任意の LOB システムへのアクセスを取得します。  
  
 前述のように、アダプターは、上に組み込ま、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 この SDK には、さまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションで使用できる統合アダプターを構築するための共通の基本が用意されています。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] WCF チャネルとして統合アダプターを公開することにより、アダプター戦略の Microsoft サービスの戦略を揃えて配置します。 詳細については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を参照してください、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ドキュメント。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]と共にドキュメントがインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通常  \<*インストール ドライブ*>: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents です。  

## <a name="overview-of-the-oracle-ebs-adapter"></a>Oracle EBS アダプターの概要
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle E-business Suite を WCF サービスとして公開します。 アダプターのクライアントは、アダプターと SOAP メッセージを交換することで、Oracle E-business Suite での操作を実行できます。 アダプターは、SOAP メッセージを処理し、操作を実行する適切な ODP.NET 呼び出しします。 アダプターは、SOAP メッセージの形式でクライアントに、Oracle E-business Suite から応答を返します。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]Oracle E-business Suite の成果物 (PL/SQL Api、インターフェイス テーブル/ビュー、同時実行プログラム、および要求のセット) と、基になる Oracle データベース アイテム (テーブル、関数、プロシージャなど) を記述するメタデータが表示されますWeb サービス記述言語 (WSDL) の形式で SOAP メッセージの構造体。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]アダプター クライアント操作のメタデータを取得できるようにします。 アダプターでは、プログラミング ソリューションで使用できるプログラミングの成果物も生成します。 詳細については[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)です。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite で通信するために Oracle Data Provider for .NET (ODP.NET) 11.1.0.7 を使用します。 ODP.NET 11.1.0.7 では、Oracle データ アクセス コンポーネント (ODAC) のコンポーネントの 1 つです。 使用することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite では、次の方法で通信します。  
  
-   BizTalk アプリケーションを開発することによりします。 詳細については、次を参照してください。 [BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)です。  
  
-   使用して、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル。 詳細については、次を参照してください。[開発 Oracle データベース アプリケーションでモデルを使用して WCF サービス](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)です。  
  
-   WCF チャネル モデルを使用します。 詳細については、次を参照してください。 [WCF チャネル モデルを使用して SQL アプリケーションを開発](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)です。  

## <a name="access-to-oracle-e-business-suite"></a>Oracle E-business Suite へのアクセス
 Oracle E-business Suite での操作を実行するには、アダプターのクライアントは、Oracle E-business Suite で関連する成果物へのアクセスが必要です。 外部アプリケーションでは、追加したり、SQL ステートメントを使用して Oracle E-business Suite のインターフェイス テーブルやデータベース テーブル内のデータを削除することができます。 アプリケーションは、ビュー、関数、およびプロシージャを使用して、インターフェイス テーブルと、データベース テーブル内のデータもアクセスできます。 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]アダプターのクライアントが、基になるデータベースと同様に Oracle E-business Suite 同様の成果物を参照できます。 Oracle E-business suite アダプター クライアント インターフェイス テーブル、インターフェイス ビュー、同時実行プログラムを参照しているときに、基になる Oracle データベースでのセットを要求、アダプターのクライアントは、テーブル、ビュー、ストアド プロシージャ、関数、PL/SQL Api を参照できます。、およびパッケージです。 アダプターのクライアントは、成果物がソリューションの必要があり、それらの成果物のメタデータを取得を選択できます。 これにより、ユーザーにアクセスし、Oracle E-business Suite と基になる Oracle データベースでのアイテムでは、操作を実行できます。  
  
 このセクションの機能の一覧、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]です。  
  
## <a name="more-good-stuff"></a>便利な機能  
  
-    [アダプターを使用して Oracle E-business Suite への接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-the-adapter.md)

- [参照、検索、および Oracle E-business Suite のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-oracle-e-business-suite-metadata.md)

- [どのような操作、Oracle E-business Suite アダプターによってサポートされます。](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)

- [Oracle データベース アダプターでトランザクションを処理します。](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md) 

- [Oracle EBS アダプターのクライアントの機能](../../adapters-and-accelerators/adapter-oracle-ebs/features-for-oracle-ebs-adapter-clients.md) 

-   [BizTalk Adapter for Oracle E-business Suite の主要な機能](../../adapters-and-accelerators/adapter-oracle-ebs/key-features-in-biztalk-adapter-for-oracle-e-business-suite.md)  
  
-   [BizTalk adapter for Oracle E-business Suite の制限事項](../../adapters-and-accelerators/adapter-oracle-ebs/limitations-of-biztalk-adapter-for-oracle-e-business-suite.md)  
  
## <a name="see-also"></a>参照  
[開始するには](../../adapters-and-accelerators/adapter-oracle-ebs/get-started-with-the-biztalk-adapter-for-oracle-e-business-suite.md)