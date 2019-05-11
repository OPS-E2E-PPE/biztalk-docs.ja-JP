---
title: Oracle データベース アダプターを使用したプログラミングにセキュリティで保護された |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- credentials
- adapter, security considerations when programming on
- credentials, setting in code
- credentials, protecting
- security
ms.assetid: 06213c14-42b8-4d4a-b238-0aedbc27ab6a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e35a150cd6e57287e409d7373cfa1873c37866cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376312"
---
# <a name="secure-programming-with-the-oracle-database-adapter"></a>Oracle データベース アダプターを使用したプログラミングをセキュリティで保護します。
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>保護するには資格情報を使用する場合、アダプター サービス参照を Visual Studio プラグインを追加しますか?  
 使用すると、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアントを作成するには、ユーザー名と Oracle データベースのパスワードを入力する必要があります。 これからをのみ行う必要があります、**セキュリティ** タブで、**アダプターの構成** ダイアログ ボックス。 Oracle を入力してから資格情報を**セキュリティ**に直接の代わりにタブ、 **URI の構成**フィールドに、以下を確認すること。  
  
- 資格情報は表示されません、 **Uri**のフィールド、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ダイアログ ボックスで、コンピューターの画面にアクセスできる人が読み取ることができます。  
  
- 資格情報は、構成には表示されませんファイルを[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。  
  
  使用して WCF クライアントを生成する方法について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください、Oracle データベースのユーザー名とパスワードを入力する方法を含む[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)します。  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>コードで資格情報の設定のベスト プラクティスとは  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 提供します、 **ClientCredentials**などのクライアント通信オブジェクトを資格情報を構成するためのクラス、 **ChannelFactory**を使用して、サービスで自身を認証します。 使用して、 **ClientCredentials**クラス、することを確認 WCF はどのような認証メカニズムは、そのオブジェクトのチャネル スタックで指定された、クライアントとサービス間の交換に適用します。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]がホストされているプロセス内のコンシューマー側アプリケーションを使用する命令型、 **ClientCredentials**コンシューマー側アプリケーションが使用する通信オブジェクトをクライアントの資格情報を設定するクラス。 ただし、これを行うことをお勧めと捉えられます、します。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の使用が推奨、 **ClientCredentials**クラス。 このプロパティは、アダプターは、ユーザー名と URI の接続で Oracle データベースのパスワードを受け入れますかどうかを指定します。 **AcceptCredentialsInUri**の既定値は**false**、つまり、接続 URI には、資格情報が含まれている場合に、アダプターが例外をスローします。 設定することができます**AcceptCredentialsInUri**に**true**接続 URI の資格情報を提供します。  
  
 次の例は、使用する方法を示します、**資格情報**で Oracle データベースの資格情報を設定するプロパティを**ChannelFactory**します。  
  
```  
// Create binding and endpoint  
OracleDBBinding binding = new OracleDBBinding();  
EndpointAddress endpointAddress = new EndpointAddress("oracleDB://Adapter");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open the channel factory  
factory.Open();  
```  
  
 次の例は、使用する方法を示します、 **ClientCredentials** WCF クライアントでの Oracle データベースの資格情報を設定するクラス。  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
SQLEXECUTEClient sqlExecuteClient = new SQLEXECUTEClient("OracleDBBinding_SQLEXECUTE");  
  
// Set user name and password  
sqlExecuteClient.ClientCredentials.UserName.UserName = "SCOTT";  
sqlExecuteClient.ClientCredentials.UserName.Password = "TIGER";  
  
// Open the client  
sqlExecuteClient.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>な方法はより安全なデータの交換プロセスの境界を越えてでしょうか。  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]がホストされているアプリケーションまたはサービスで使用することでインプロセスでします。 アダプターがホストされるため、インプロセスで、コンシューマーとコンシューマー間で交換されるメッセージのセキュリティを提供する必要はありません、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 ただし、使用するアプリケーションまたはサービスを別のサービスまたはクライアントのプロセス境界を越えて機密性の高いデータベースの情報を含むメッセージを送信する場合は、環境内でこのデータを適切に保護を提供するメジャーを行う必要があります。 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] セキュリティで保護されたメッセージがクライアントとサービス間で送信する際に役立つ多くのオプションを提供します。 セキュリティで保護されたメッセージがクライアントとサービスの間で送信することの詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を参照してください[Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx)します。 セキュリティに関する一般的な情報の機能の[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供しますを参照してください[Windows Communication Foundation セキュリティ](https://msdn.microsoft.com/library/ms732362.aspx)します。 
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)   
[ベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)