---
title: SQL アダプターを使用した WCF サービス モデルの概要 |Microsoft Docs
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
ms.openlocfilehash: 121b425abe1c7c34ba75e535799770031b931525
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997331"
---
# <a name="overview-of-the-wcf-service-model-with-the-sql-adapter"></a>SQL アダプターを使用した WCF サービス モデルの概要
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] WCF サービスとしての SQL Server の操作を公開します。 、ストアド プロシージャを呼び出す例については、SQL Server のアイテムに対して操作を実行するには、さらに、SQL Server 上の操作を実行すると、アダプターでの操作を呼び出します。 そのため、コードは、アダプターによって提示される WCF サービスのクライアントとして機能します。  
  
 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデルでは、クライアントとサービス間に存在するサービス コントラクトは、.NET インターフェイスとして表されます、操作はこのインターフェイスのメソッドとして表されます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF アダプターを公開するメタデータからの対象となる操作には、このインターフェイスを生成するためのツールを提供するとします。 これらのツールでは、サービス インターフェイスで公開されている操作の呼び出しに使用できる WCF クライアント クラスも作成します。 クライアント アプリケーションでは、アダプターの操作を呼び出すための WCF クライアント クラスのメソッドを呼び出すことができます。 受信操作を受信するサービスを実装するために、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、受信操作に対して生成されたインターフェイスを実装します。  
  
 次のセクションでは、WCF クライアントでの操作を呼び出す、WCF サービス モデルを使用する方法について説明します。  
  
## <a name="invoking-operations-on-the-sql-server-with-a-wcf-client"></a>WCF クライアントでの SQL Server での操作を呼び出す  
 WCF サービス モデルを使用して、操作を呼び出してする、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、まずターゲットの WCF クライアント クラスを生成する必要があります。 WCF クライアントでは、このクラスのインスタンスを作成し、SQL Server システムでこれらの操作を実行するには、そのメソッドを呼び出すことができます。 このセクションでは、一般的な .NET アダプター クライアント アプリケーションの外観の概要を示します。 アダプターを使用して SQL Server データベースでさまざまな操作を実行する方法の詳細な説明については、特定のトピックで提供されます。  
  
#### <a name="to-invoke-operations-on-the-sql-adapter"></a>SQL アダプターの操作を呼び出す  
  
1. WCF クライアント クラスとヘルパー コードを生成します。 使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]WCF クライアント クラスを生成する作業する SQL Server データベースのアイテムを対象としました。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。  
  
2. WCF クライアントのインスタンスを作成し、WCF クライアントを構成します。 WCF クライアントを構成するには、バインドと、クライアントが使用するエンドポイント アドレス (URI の接続) を指定する必要があります。 コードで強制的に、または構成で宣言的に、これを行うことができます。 次のコード作成、WCF クライアントを対象とする、**選択**操作、**従業員**SQL Server データベースのテーブル。 また、SQL Server データベースの資格情報を設定します。 WCF クライアントは、構成から初期化されます。  
  
   ```  
   TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee"); //picking the binding and address from the app.config  
  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
   > [!NOTE]
   >  コードでクライアント バインディングとエンドポイント アドレスを指定するか、app.config 構成ファイルで宣言します。 上記のコード スニペットは、後者は使用します。 いずれかのアプローチを使用する方法の詳細については、次を参照してください。[クライアント バインディングを構成、SQL アダプターの](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)します。  
  
3. WCF クライアントを開きます。  
  
   ```  
   client.Open();  
   ```  
  
4. SQL server データベースでの選択操作を実行する前の手順で作成された WCF クライアントでメソッドを呼び出します。 次のコードでは、SQL Server データベース テーブルに SELECT ステートメントを呼び出す、WCF クライアントの選択メソッドを呼び出します。  
  
   ```  
   client.Select("*", "where [Name] = ‘John Smith’");  
   ```  
  
5. WCF クライアントを閉じます。  
  
   ```  
   client.Close();  
   ```  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)