---
title: Oracle E-business Suite の重要な機能によって BizTalk adapter |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a43091ab-f81c-4c4f-bcc3-e6abe16d3d77
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d89da490f604e50924544e54cb5ffe7018a8724e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218290"
---
# <a name="key-features-in-biztalk-adapter-for-oracle-e-business-suite"></a>BizTalk adapter for Oracle E-business Suite の主な機能
このセクションでは、主要な機能を示します[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]です。  
  
## <a name="technology-related-features"></a>テクノロジに関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|Windows Communication Foundation (WCF) の使用|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の上に構築された、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] ([!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)])。 さらに、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] WCF に基づいて構築されます。 アダプターは、アダプターのクライアントに WCF チャネルとして公開されます。 これにより、接続、メタデータ交換、および外部システムとビジネス データを交換します。|  
|WCF チャネル モデルと WCF サービス モデルのサポート|Wcf*チャネル*モデルでは、アダプターのクライアントが使用できる、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]直接 XML メッセージを送受信しています。<br /><br /> Wcf*サービス*モデルでは、アダプターのクライアント クラスを生成できます .NET プロキシから、Web サービス記述言語 (WSDL) を使用して取得[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。|  
|ODP.NET の使用|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite のインターフェイスを Oracle Data Provider for .NET (ODP.NET) を使用します。|  
|Oracle E-business Suite に接続する 2 つの方法|アダプターのクライアントは、tnsnames.ora ファイルで net サービス名を使用するか、または直接接続パラメーターを指定して、net サービス名または tnsnames.ora ファイルを使用する必要があるので、Oracle E-business Suite に接続できます。 Oracle E-business Suite への接続に tnsnames.ora ファイルを必要としない済むため手間接続パラメーター (net サービス名) を手動で更新をすべてのクライアント コンピューターで tnsnames.ora ファイルで追加またはで Oracle サーバーを更新するとき、環境。 詳細については、次を参照してください。 [Oracle E-business Suite への接続を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)です。|  
|Windows 認証のサポート|アダプターのクライアントは、Oracle E-business Suite への接続に Windows 認証を使用できます。 Windows 認証では、Windows のログオン資格情報に基づくユーザーの id を確認することができますあり、したがって、Windows 環境の組み込みのセキュリティを活用することができます。 Windows 認証の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle E-business Suite を使用して Windows 認証への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)です。|  
|使用するためのサポート、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]と Microsoft Office SharePoint Server (MOSS)|アダプターを使用して、MOSS ポータルに Oracle E-business Suite からデータを表示することができます。 詳細については、次を参照してください。[で Microsoft Office SharePoint Server、Oracle E-business アダプターを使用して](https://msdn.microsoft.com/library/dd788485.aspx)です。|  
  
## <a name="metadata-related-features"></a>メタデータに関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|メタデータのバッチの取得|アダプターのクライアントでは、参照でき、Oracle E-business Suite と基になるデータベースによって公開されているすべての成果物のメタデータを検索することができます。 成果物は、接続しているユーザーの資格情報に基づいてが表示されは。<br /><br /> -Oracle E-business Suite 成果物のためには、各アプリケーションでグループ化されます。<br />-Oracle E-business Suite と基になるデータベース内の各アイテムによってグループ化されます。<br />基になるデータベース成果物のためには、各スキーマによってグループ化されます。|  
  
## <a name="performance-related-features"></a>パフォーマンス関連の機能  
  
|機能|解説|  
|-------------|-------------|  
|接続プール|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]により、クライアントは、ODP.NET 構成して接続プールを使用する、 **UseOracleConnectionPool**プロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。|  
|キャッシュ管理|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]により、クライアントは管理を使用する、ODP.NET キャッシュを構成して、 **StatementCachePurge**と**StatementCacheSize**プロパティをバインドします。 このバインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。|  
|パフォーマンス カウンターのサポート|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントで使用する WCF ベースのパフォーマンス カウンターをサポートしています。 パフォーマンス カウンターの詳細については、次を参照してください。 [SQL アダプターで使用するパフォーマンス カウンター](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)です。|  
  
## <a name="operations-related-features"></a>操作に関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|インターフェイスのテーブルとのインターフェイス ビューで操作のサポート|アダプターのクライアントには、基本的な Insert、Update、Delete、および Oracle E-business Suite のインターフェイス テーブルに対する Select 操作を実行できます。 のみ Oracle E-business Suite のインターフェイス ビューで選択操作を実行できます。|  
|PL/SQL Api を実行するためのサポート|アダプターのクライアントは、Oracle E-business Suite で PL/SQL Api を実行することができます。 PL/SQL Api には、ストアド プロシージャおよびパッケージ内で関数が含まれています。|  
|同時実行プログラムを実行するためのサポート|アダプターのクライアントは、Oracle E-business Suite で同時実行プログラムを実行することができます。|  
|要求のセットを実行するためのサポート|アダプターのクライアントは、Oracle E-business Suite で要求のセットを実行できます。 要求セットは、同時実行プログラムのセットは、および定義済みのパラメーターを持つ複数の同時実行プログラムを実行するために使用できます。 要求のセットは、段階的に実行されます。 要求のセットの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=129539](http://go.microsoft.com/fwlink/?LinkId=129539)です。|  
|挿入操作のインラインの値を指定するためのサポート|使用することができます、 **InlineValue**インターフェイス テーブルとの Oracle データベース テーブルに計算値を挿入する Insert 操作での属性です。 これは省略可能な属性は、すべての単純なデータ レコードは挿入操作で使用可能です。 この属性の値を指定する場合は、指定されたレコードの値が上書きされます。 InlineValue 属性の詳細については、次を参照してください。[インターフェイス テーブルとのインターフェイス ビューで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)です。|  
|ポーリングの受信呼び出しのサポート|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] 「ポーリング ベース」のデータ変更のメッセージを受信アダプターが指定された SQL ステートメント、ストアド プロシージャ、関数、または、パッケージ内の手順を実行する機能をサポートしていますが、データを取得し、結果をクライアントに提供します。|  
|関数およびプロシージャを呼び出すためのサポート|アダプターのクライアントには、関数、および基になる Oracle データベースでプロシージャを呼び出すことができます。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]関数およびプロシージャを基になる Oracle データベースで実行できる操作として表示します。|  
|複合操作のサポート|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite で複合操作を実行するアダプターのクライアントを有効にします。 複合操作は、次の操作、および任意の順序で任意の数を含めることができます。<br /><br /> -インターフェイスのテーブル、インターフェイス ビュー、テーブル、およびビューに対する操作。<br />ストアド プロシージャ、関数、および表示されたパッケージ内のプロシージャ、アダプターでの操作として。|  
|任意の SQL ステートメントおよび PL/SQL ブロックを実行するためのサポート|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが任意の SQL ステートメントまたは PL/SQL ブロック ExecuteReader、ExecuteScalar、および ExecuteNonQuery 操作を使用して実行できるようにします。 これらの操作の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)です。|  
|ユーザー定義型 (Udt)、ブール型パラメーター、および PL/SQL テーブル型のサポート|アダプターのクライアントでは、ストアド プロシージャおよび関数のブール値パラメーターと PL/SQL テーブル型を含むで Udt を含む成果物の操作および操作をサポートできます。 UDT のサポートについては、次を参照してください。 [Oracle User-Defined 型のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-oracle-user-defined-types2.md)です。|  
|入力をサポートし、REF CURSOR 出力|アダプターのクライアントは、プロシージャと関数の入力と出力の REF CURSOR で操作できます。|  
|PL/SQL レコードのデータ型のサポート|アダプターのクライアントは、レコードと、ストアド プロシージャおよび関数で入れ子になったレコードの種類で操作できます。|  
|オーバー ロードされた関数およびプロシージャ PL/SQL API でサポート|アダプターのクライアントには、オーバー ロードされた関数および PL/SQL Api でプロシージャを呼び出すことができます。 ただし、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]厳密に型指定され、弱い型指定の REF カーソルを使用するオーバー ロードされたプロシージャの使用をサポートしていません。 内部的には、アダプターは、REF CURSOR だけとして厳密に型指定され、弱い型指定の両方の REF CURSOR を扱います。|  
|データベースの変更通知のサポート|アダプターのクライアントは、トリガーを起動する SELECT ステートメントに基づいて、Oracle データベースからデータベースの変更通知を受信できます。 としてアダプター クライアントと、結果セットの SELECT ステートメントの変更時に、Oracle データベースで通知が送信されます。 データベースの変更通知の詳細については、次を参照してください。[データベース変更通知の受信、ORacle データベース アダプターの使用に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)です。|  
|シノニムのサポート|アダプターのクライアントは、テーブル、ビュー、ストアド プロシージャ、関数、およびパッケージ用に作成されたシノニムに対する操作を実行できます。 シノニム、および使用する方法の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]にシノニムに対して操作を実行するには、次を参照してください。[シノニムに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-synonyms2.md)です。|  
  
## <a name="other-features"></a>その他の機能  
  
|機能|解説|  
|-------------|-------------|  
|複数言語サポート (MLS)|アダプターのクライアントが使用できる、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite と複数の言語パックがインストールされているが、基になるデータベースで操作を実行します。 これは、アダプターのクライアントが複数の言語でのデータの処理を実行できることを意味します。 たとえば、インターフェイス ビューでは、ローカライズ (英語以外の) データを表示またはローカライズされたデータをテーブルに挿入できます。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]基になる Oracle E-business Suite のインストールでサポートされているものと同数の言語をサポートします。<br /><br /> [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 **MlsSettings**複数言語のサポート機能を構成するプロパティをバインドします。 バインディング プロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。|  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)