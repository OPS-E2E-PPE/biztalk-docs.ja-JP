---
title: "Oracle データベース アダプターで WCF サービス モデルの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, overview
- invoking operations
- WCF service, creating and implementing
ms.assetid: 8ed765e5-b5e6-46bd-bcd6-282219caf75d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 100bacfeaf2e06d7ff491ec77f88e00980a96fa1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-database-adapter"></a>Oracle データベース アダプターで WCF サービス モデルの概要
操作を使用する際にする、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスは、コードは、機能、クライアントと、アダプターにサービスのどちらかです。 ほぼすべての操作を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス、コードは、クライアントです。 つまり、アプリケーションが; アダプターの操作を呼び出すたとえば、Oracle テーブルにレコードを挿入します。 コードにサービスとして機能する唯一の操作、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSMT 操作です。 この場合、アダプターは、アプリケーションに、ポーリング クエリ操作の結果を送信します。  
  
 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作は、このインターフェイスのメソッドとして表されます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF が使用するアダプターを公開するメタデータから対象となる操作について、このインターフェイスを生成するツールを提供します。 これらのツールでは、サービス インターフェイスの公開操作の呼び出しに使用できる WCF クライアント クラスも作成します。 クライアント アプリケーションは、アダプターの操作の呼び出しに WCF クライアント クラスのメソッドを呼び出すことができます。 POLLINGSTMT 操作を受信するサービスを実装する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、POLLINGSTMT 操作に対して生成されたインターフェイスを実装します。  
  
 次のセクションでは、モデルを使用して、WCF サービスのクライアントとサービスのコードを作成する方法を説明する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
## <a name="creating-and-invoking-operations-on-a-wcf-client-by-using-the-oracle-database-adapter"></a>作成して、Oracle データベース アダプターを使用して、WCF クライアントでの操作を呼び出す  
 モデルを使用して、WCF サービスで操作を呼び出す、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、まず対象の操作用の WCF クライアント クラスを生成する必要があります。 このクラスでは、WCF クライアントのインスタンスを作成し、Oracle データベースで操作を実行するには、そのメソッドを呼び出すことができます。  
  
#### <a name="to-invoke-operations-on-the-oracle-database-adapter"></a>Oracle データベース アダプターの操作を呼び出す  
  
1.  WCF クライアント クラスとヘルパー コードを生成します。 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) Oracle のデータベース成果物を対象と WCF クライアント クラスを生成する作業します。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [Oracle のデータベース成果物の WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)です。  
  
2.  クライアントのバインディングを指定することによって、WCF クライアントのインスタンスを作成します。 クライアントのバインディングを指定するには、バインドと WCF クライアントが使用するエンドポイント アドレスを指定する必要があります。 これは、コードで命令として記述または構成で宣言によって行うことができます。 クライアントのバインディングを指定する方法の詳細については、次を参照してください。 [、クライアントが Oracle データベースのバインディングを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)です。 次のコードでは、Oracle データベース テーブル (SCOTT/ACCOUNTACTIVITY) でデータ操作言語 (DML) 操作を実行するために使用する WCF クライアントを作成します。 また、Oracle データベースの資格情報を設定します。 WCF クライアントは、構成から初期化されます。  
  
    ```  
    SCOTTTableACCOUNTACTIVITYClient aaTableClient =   
        new SCOTTTableACCOUNTACTIVITYClient("OracleDBBinding_SCOTT.Table.ACCOUNTACTIVITY");  
  
    aaTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
    aaTableClient.ClientCredentials.UserName.Password = "TIGER";  
    ```  
  
3.  WCF クライアントを開きます。  
  
    ```  
    aaTableClient.Open();  
    ```  
  
4.  Oracle データベースで操作を実行する手順 2. で作成された WCF クライアントでメソッドを呼び出します。 次のコードを呼び出す、**選択**ACCOUNTACTIVITY テーブルで、次の SQL SELECT クエリを実行する WCF クライアントのメソッド:`SELECT * FROM ACCOUNTACTIVITY`です。  
  
    ```  
    // create a record set parameter to hold the SELECT query result set and invoke the Select operation;  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
    selectRecords = aaTableClient.Select("*", null);  
    ```  
  
5.  WCF クライアントを閉じます。  
  
    ```  
    aaTableClient.Close();  
    ```  
  
 テーブルやビュー上に示した Select 操作をなどの DML 操作の実行の詳細については、次を参照してください。[を実行する基本的な Insert、Update、Delete、および WCF サービス モデルを使用して操作を選択](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)です。  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-oracle-database-adapter"></a>作成して、Oracle データベース アダプターを使用して WCF サービスの実装  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベース テーブルまたはビューに対するポーリングを実行できます。 この機能を使用して、SQL SELECT クエリ、アダプターは、Oracle データベースに対して定期的に実行する必要がありますを指定できます。 このクエリの結果は、特別な操作、POLLINGSTMT 操作を使用してアプリケーションに返されます。 アプリケーション、ポーリング クエリの結果を受信する必要があります、サービスを実装するコントラクトを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]POLLINGSTMT 操作用に公開します。  
  
 POLLINGSTMT 操作を受信するサービスを実装する、(WCF サービス コントラクトとも呼ばれます) によって公開されるサービス コントラクトを表す .NET インターフェイスを生成する必要があります最初、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作します。 これを行う方法の詳細については、次を参照してください。 [Oracle のデータベース成果物の WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)です。  
  
 生成されたインターフェイスを実装することで WCF サービスを実装します。 このクラスには、POLLINGSTMT メッセージを処理して、アダプターに応答を返すビジネス ロジックが含まれています。 サービス ホストを使用して (**System.ServiceModel.ServiceHost**) をこのサービスのインスタンスをホストします。 詳細についてを参照してください。 [WCF サービス モデルを使用してデータの変更メッセージをポーリングの受信に基づく](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)です。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)