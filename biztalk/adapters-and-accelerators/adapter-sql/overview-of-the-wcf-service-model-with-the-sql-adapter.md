---
title: SQL アダプターで WCF サービス モデルの概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7641bcc7-3845-4914-9b1b-cb86b998ea6d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3afbf1822945f0a47b09a93b3ac3cc2f8ac8653d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222890"
---
# <a name="overview-of-the-wcf-service-model-with-the-sql-adapter"></a>SQL アダプターで WCF サービス モデルの概要
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は WCF サービスとしての SQL Server 操作を公開します。 ストアド プロシージャを呼び出す例については、SQL Server の成果物の操作を実行するには、さらに、SQL Server で操作を実行すると、アダプターでの操作を呼び出します。 したがって、コードは、アダプターによって提示される WCF サービスのクライアントとして機能します。  
  
 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作は、このインターフェイスのメソッドとして表されます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF が使用するアダプターを公開するメタデータから対象となる操作について、このインターフェイスを生成するツールを提供します。 これらのツールでは、サービス インターフェイスの公開操作の呼び出しに使用できる WCF クライアント クラスも作成します。 クライアント アプリケーションは、アダプターの操作の呼び出しに WCF クライアント クラスのメソッドを呼び出すことができます。 受信操作を受信するサービスを実装する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、受信操作に対して生成されたインターフェイスを実装します。  
  
 次のセクションでは、モデルを使用して、WCF サービスと WCF クライアントの操作を呼び出す方法について説明します。  
  
## <a name="invoking-operations-on-the-sql-server-with-a-wcf-client"></a>WCF クライアントで SQL Server での操作を呼び出す  
 モデルを使用して、WCF サービスで操作を呼び出す、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、まず対象の操作用の WCF クライアント クラスを生成する必要があります。 WCF クライアントは、このクラスのインスタンスを作成し、SQL Server のシステムでこれらの操作を実行するには、そのメソッドを呼び出すことができます。 このセクションでは、一般的な .NET アダプター クライアント アプリケーションの外観方法の概要を示します。 アダプターを使用して、SQL Server データベースに対して別の操作を実行する方法の詳細な説明については、特定のトピックで提供されます。  
  
#### <a name="to-invoke-operations-on-the-sql-adapter"></a>SQL アダプターでの操作を呼び出す  
  
1.  WCF クライアント クラスとヘルパー コードを生成します。 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]操作する SQL Server のデータベース成果物を対象とした WCF クライアント クラスを生成します。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。  
  
2.  WCF クライアント インスタンスを作成し、WCF クライアントを構成します。 WCF クライアントを構成すると、バインディングと、クライアントが使用するエンドポイント アドレス (接続 URI) を指定することがあります。 これは、コードで命令として記述または構成で宣言によって行うことができます。 次のコードを作成する WCF クライアントを対象とする、**選択**での操作、**従業員**SQL Server データベースのテーブルにします。 また、SQL Server データベースの資格情報を設定します。 WCF クライアントは、構成から初期化されます。  
  
    ```  
    TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee"); //picking the binding and address from the app.config  
  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!NOTE]
    >  コードでクライアントのバインディングとエンドポイント アドレスを指定するか、app.config 構成ファイルで宣言することができます。 上記のコード スニペットは、後者は使用します。 いずれかのアプローチを使用する方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)です。  
  
3.  WCF クライアントを開きます。  
  
    ```  
    client.Open();  
    ```  
  
4.  SQL server データベースでの選択操作を実行する前の手順で作成された WCF クライアントでメソッドを呼び出します。 次のコードでは、SQL Server データベース テーブルの SELECT ステートメントを呼び出す、WCF クライアントの選択メソッドを呼び出します。  
  
    ```  
    client.Select("*", "where [Name] = ‘John Smith’");  
    ```  
  
5.  WCF クライアントを閉じます。  
  
    ```  
    client.Close();  
    ```  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)