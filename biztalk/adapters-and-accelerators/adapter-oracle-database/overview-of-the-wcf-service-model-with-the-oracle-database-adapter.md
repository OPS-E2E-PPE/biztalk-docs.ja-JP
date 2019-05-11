---
title: Oracle データベース アダプターで WCF サービス モデルの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, overview
- invoking operations
- WCF service, creating and implementing
ms.assetid: 8ed765e5-b5e6-46bd-bcd6-282219caf75d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1884c5f8cf558bfa2901f34fb71858d4281a21db
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528974"
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-database-adapter"></a>Oracle データベース アダプターで WCF サービス モデルの概要
操作を使用するが、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスは、クライアントまたはアダプターにサービスとして、コードが機能します。 ほぼすべての操作を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスは、コードは、クライアントです。 つまり、アプリケーションは、アダプター操作を呼び出すたとえば、Oracle テーブルにレコードを挿入します。 唯一の操作をサービスとして動作するコードを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]POLLINGSMT 操作です。 この場合、アダプターは、ポーリング クエリ操作の結果をアプリケーションに送信します。  
  
 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作はこのインターフェイスのメソッドとして表されます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF アダプターを公開するメタデータからの対象となる操作には、このインターフェイスを生成するためのツールを提供するとします。 これらのツールでは、サービス インターフェイスで公開されている操作の呼び出しに使用できる WCF クライアント クラスも作成します。 クライアント アプリケーションでは、アダプターの操作を呼び出すための WCF クライアント クラスのメソッドを呼び出すことができます。 POLLINGSTMT 操作を受信するサービスを実装するために、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、POLLINGSTMT 操作用に生成するインターフェイスを実装します。  
  
 次のセクションでは、WCF サービス モデルを使用して、クライアントとサービスのコードを作成する方法を説明します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
## <a name="creating-and-invoking-operations-on-a-wcf-client-by-using-the-oracle-database-adapter"></a>作成して、Oracle データベース アダプターを使用して、WCF クライアントの操作を呼び出す  
 WCF サービス モデルを使用して、操作を呼び出してする、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、まずターゲットの WCF クライアント クラスを生成する必要があります。 WCF クライアントでは、このクラスのインスタンスを作成し、Oracle データベースで操作を実行するには、そのメソッドを呼び出すことができます。  
  
#### <a name="to-invoke-operations-on-the-oracle-database-adapter"></a>Oracle データベース アダプターの操作を呼び出す  
  
1. WCF クライアント クラスとヘルパー コードを生成します。 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)、Oracle データベース アイテムを対象とした WCF クライアント クラスを生成する作業します。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [Oracle データベース アイテムの WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)します。  
  
2. クライアントのバインディングを指定することで、WCF クライアントのインスタンスを作成します。 クライアントのバインディングを指定するには、バインドと WCF クライアントを使用するエンドポイント アドレスを指定する必要があります。 コードで強制的に、または構成で宣言的に、これを行うことができます。 クライアントのバインディングを指定する方法の詳細については、次を参照してください。 [for Oracle Database バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)します。 次のコードでは、Oracle データベース テーブル (SCOTT/ACCOUNTACTIVITY) でのデータ操作言語 (DML) 操作を実行するために使用する WCF クライアントを作成します。 また、Oracle データベースの資格情報を設定します。 WCF クライアントは、構成から初期化されます。  
  
   ```  
   SCOTTTableACCOUNTACTIVITYClient aaTableClient =   
       new SCOTTTableACCOUNTACTIVITYClient("OracleDBBinding_SCOTT.Table.ACCOUNTACTIVITY");  
  
   aaTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
   aaTableClient.ClientCredentials.UserName.Password = "TIGER";  
   ```  
  
3. WCF クライアントを開きます。  
  
   ```  
   aaTableClient.Open();  
   ```  
  
4. Oracle データベースで操作を実行する手順 2. で作成された WCF クライアントでメソッドを呼び出します。 次のコードを呼び出す、**選択**ACCOUNTACTIVITY テーブルで、次の SQL SELECT クエリを実行する WCF クライアントのメソッド:`SELECT * FROM ACCOUNTACTIVITY`します。  
  
   ```  
   // create a record set parameter to hold the SELECT query result set and invoke the Select operation;  
   microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
   selectRecords = aaTableClient.Select("*", null);  
   ```  
  
5. WCF クライアントを閉じます。  
  
   ```  
   aaTableClient.Close();  
   ```  
  
   テーブルとビューで、上で使用する選択操作での DML 操作の実行の詳細については、次を参照してください。[を実行する基本的な Insert、Update、Delete、および WCF サービス モデルを使用して操作を選択します](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)します。  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-oracle-database-adapter"></a>作成して、Oracle データベース アダプターを使用して WCF サービスを実装します。  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースのテーブルまたはビューに対してポーリングを実行できます。 この機能を使用して、アダプターに、Oracle データベースに対して定期的に実行する SQL SELECT クエリを指定できます。 特別な操作、POLLINGSTMT 操作を使用してアプリケーションには、このクエリの結果が返されます。 アプリケーション、ポーリング クエリの結果を受信する必要があります実装、サービス コントラクトを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]POLLINGSTMT 操作のために公開します。  
  
 POLLINGSTMT 操作を受信するサービスを実装する (WCF サービス コントラクトとも呼ばれます) によって公開されるサービス コントラクトを表す .NET インターフェイスを最初に生成する必要があります、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作。 これを行う方法の詳細については、次を参照してください。 [Oracle データベース アイテムの WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)します。  
  
 その後、WCF サービスを実装するには、生成されたインターフェイスを実装します。 このクラスには、POLLINGSTMT メッセージを処理し、アダプターに応答を返すビジネス ロジックが含まれています。 サービス ホストを使用して (**System.ServiceModel.ServiceHost**) このサービスのインスタンスをホストします。 詳細についてを参照してください。 [WCF サービス モデルを使用して、データ変更メッセージのポーリングの受信に基づく](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)します。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベースのアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)