---
title: "SQL アダプタをセキュリティで保護された使用したプログラミング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c84744a-6595-4d93-afe7-39a7ccf1b6a0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44886b490ce63e8c34e1a5bdb41554c96a0873ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="secure-programming-with-the-sql-adapter"></a>SQL アダプタをセキュリティで保護された使用したプログラミング
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>どのように保護する資格情報を使用する場合、アダプター サービス参照を Visual Studio プラグインを追加しますか?  
 使用すると、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントを作成するには、ユーザー名と SQL Server データベースのパスワードを指定する必要があります。 資格情報を入力する必要があります、**セキュリティ**タブで、**アダプターの構成** ダイアログ ボックス。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI の一部として、ユーザー名とパスワードを指定するオプションが用意されていません。 これにより、次に。  
  
-   資格情報は表示されません、 **URI の構成**のフィールド、**アダプター サービス参照のプラグインの追加** ダイアログ ボックスが、コンピューター画面にアクセスできる人が読み取ることができます。  
  
-   構成では、資格情報は表示されませんファイルを[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。  
  
 使用して、WCF クライアントを生成する方法について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください、SQL Server データベースのユーザー名とパスワードを入力する方法を含む[SQLアダプターを使用してVisualStudioでのSQLServer操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>コードで資格情報の設定のベスト プラクティスとは  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供、 **ClientCredentials**などのクライアント通信オブジェクトの資格情報を構成するためのクラス、 **ChannelFactory**サービスで自身を認証に使用します。 使用して、 **ClientCredentials**クラス、することを確認 WCF はどのような認証メカニズムは、そのオブジェクトのチャネル スタックで指定し、クライアントとサービス間の交換に適用します。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がホストされている、インプロセスでその処理を行うアプリケーションでは使用する命令型、 **ClientCredentials**クラスを利用するアプリケーションが使用している通信オブジェクトはクライアントで資格情報を設定します。 これを行うことをお勧めただしと見なされます、します。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の使用を要求、 **ClientCredentials**をプログラムで資格情報を渡すためのクラスです。 **AcceptCredentialsInUri**プロパティのバインドでは無視されます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] URI 内の資格情報を渡すようにします。  
  
 次の例を使用する方法を示しています、**資格情報**で SQL Server データベースの資格情報を設定するプロパティ、 **ChannelFactory**です。  
  
```  
// Create binding and endpoint  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 次の例を使用する方法を示しています、 **ClientCredentials** WCF クライアントで SQL Server データベースの資格情報を設定するクラス。  
  
```  
// Initialize a new client for the SELECT operation on the Employee table   
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient(binding,address);  
  
// Set user name and password  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
// Open the client  
client.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>どのことができます提供するにはより安全なデータ交換プロセス境界を越えてしますか。  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がホストされているアプリケーションまたはサービスを利用するとインプロセスでします。 アダプターがホストされているので、インプロセスでコンシューマーとコンシューマー間で交換されるメッセージのセキュリティを提供する必要はありません、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 ただし、使用のアプリケーションまたはサービスは、別のサービスまたはクライアントにプロセス境界を越えて機密データベースの情報を含むメッセージを送信する場合は、環境内でこのデータの適切な保護対策を提供するメジャーを行う必要があります。 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]クライアントとサービス間で送信されるセキュリティで保護されたメッセージに役立つ多くのオプションを提供します。 クライアントとサービス間で送信されるセキュリティで保護されたメッセージに保護の詳細について[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を参照してください[Services のセキュリティ保護とクライアント](https://msdn.microsoft.com/library/ms734736.aspx)です。 セキュリティに関する一般情報についての機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供を参照してください[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)です。
  
## <a name="see-also"></a>参照  
[SQL アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[SQL アダプタをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)