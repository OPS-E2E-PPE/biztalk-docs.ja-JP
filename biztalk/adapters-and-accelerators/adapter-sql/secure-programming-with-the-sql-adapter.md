---
title: SQL アダプタを使用したセキュリティで保護されたプログラミング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c84744a-6595-4d93-afe7-39a7ccf1b6a0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6241a6e36b15c7e7efc1a796662782f783676318
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368033"
---
# <a name="secure-programming-with-the-sql-adapter"></a>SQL アダプタを使用したプログラミングをセキュリティで保護します。
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>保護するには資格情報を使用する場合、アダプター サービス参照を Visual Studio プラグインを追加しますか?  
 使用すると、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントを作成するには、ユーザー名と SQL Server データベースのパスワードを指定する必要があります。 資格情報を入力する必要があります、**セキュリティ** タブで、**アダプターの構成** ダイアログ ボックス。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI の一部として、ユーザー名とパスワードを指定するオプションは提供されません。 これにより、次に。  
  
- 資格情報は表示されません、 **URI の構成**のフィールド、 **Adapter Service Reference プラグインの追加**ダイアログ ボックスで、コンピューターの画面にアクセスできる人が読み取ることができます。  
  
- 資格情報は、構成には表示されませんファイルを[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。  
  
  使用して WCF クライアントを生成する方法について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください、SQL Server データベースのユーザー名とパスワードを入力する方法を含む[SQLアダプタを使用してVisualStudioでSQLServer操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>コードで資格情報の設定のベスト プラクティスとは  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 提供します、 **ClientCredentials**などのクライアント通信オブジェクトを資格情報を構成するためのクラス、 **ChannelFactory**を使用して、サービスで自身を認証します。 使用して、 **ClientCredentials**クラス、することを確認 WCF はどのような認証メカニズムは、そのオブジェクトのチャネル スタックで指定された、クライアントとサービス間の交換に適用します。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がホストされているプロセス内のコンシューマー側アプリケーションを使用する命令型、 **ClientCredentials**コンシューマー側アプリケーションが使用する通信オブジェクトをクライアントの資格情報を設定するクラス。 ただし、これを行うことをお勧めと捉えられます、します。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の使用が必要です、 **ClientCredentials**資格情報をプログラムで渡すためのクラス。 **AcceptCredentialsInUri**プロパティのバインドでは無視されます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] URI 内の資格情報を渡すようにします。  
  
 次の例は、使用する方法を示します、**資格情報**で SQL Server データベースの資格情報を設定するプロパティを**ChannelFactory**します。  
  
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
  
 次の例は、使用する方法を示します、 **ClientCredentials** WCF クライアントでの SQL Server データベースの資格情報を設定するクラス。  
  
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
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>な方法はより安全なデータの交換プロセスの境界を越えてでしょうか。  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]がホストされているアプリケーションまたはサービスで使用することでインプロセスでします。 アダプターがホストされるため、インプロセスで、コンシューマーとコンシューマー間で交換されるメッセージのセキュリティを提供する必要はありません、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 ただし、使用するアプリケーションまたはサービスを別のサービスまたはクライアントのプロセス境界を越えて機密性の高いデータベースの情報を含むメッセージを送信する場合は、環境内でこのデータを適切に保護を提供するメジャーを行う必要があります。 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] セキュリティで保護されたメッセージがクライアントとサービス間で送信する際に役立つ多くのオプションを提供します。 セキュリティで保護されたメッセージがクライアントとサービスの間で送信することの詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を参照してください[Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx)します。 セキュリティに関する一般的な情報の機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますを参照してください[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)します。
  
## <a name="see-also"></a>参照  
[SQL アプリケーションをセキュリティで保護する](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[SQL アダプタをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)