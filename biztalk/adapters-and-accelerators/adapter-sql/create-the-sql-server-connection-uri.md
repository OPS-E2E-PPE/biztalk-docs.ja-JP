---
title: SQL Server 接続 URI の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 688e2215-a4d8-4f55-a37c-7d91c3de080f
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c58812b9fc3404b9922cf05c84717f3c95e05435
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007579"
---
# <a name="create-the-sql-server-connection-uri"></a>SQL Server 接続 URI を作成します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]接続 URI には、アダプターが SQL Server データベースへの接続を確立するために使用するプロパティが含まれています。 このトピックでは、SQL Server の接続 URI、に関する情報を提供し、その他のさまざまなプログラミング シナリオで URI を指定する方法を説明するトピックへのリンクを提供します。  
  
##  <a name="FailoverPartner"></a> SQL アダプターの接続 URI  
 一般的なエンドポイント アドレスで WCF の URI として表されます。 `scheme://hostinfoparams?query_string`、場所。  
  
- スキームは、スキームの名前です。  
  
- hostinfoparams はホストへの接続を確立するために必要な情報は、します。たとえば、サーバー名です。  
  
- クエリ文字列は、疑問符 (?) で区切られたパラメーターのオプションの名前と値のコレクションです。  
  
  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI はこの基本的な形式に従います、次のように実装されます。  
  
```  
  
mssql://[Server_Name[:Portno]]/[Database_Instance_Name]/[Database_Name]?FailoverPartner=[Partner_Server_Name]&InboundId=[Inbound_ID]  
```  
  
 ここで、`mssql`用 SQL Server の接続 URI のスキームです。  
  
 次の表では、接続 URI に含まれるプロパティについて説明します。  
  
|接続 URI のプロパティ|カテゴリ|説明|  
|-----------------------------|--------------|-----------------|  
|[サーバー名]|hostinfoparams|SQL Server がインストールされているサーバーの名前。 値を指定しない場合、アダプターは、サーバー名として"localhost"を前提としていて、ローカル サーバー上の SQL Server データベースとの接続を確立します。|  
|[PORTNO]|hostinfoparams|接続が確立されているポート番号。 値を指定しない場合、アダプターは、既定のポートを介して接続します。|  
|[データベース インスタンス名]|hostinfoparams|接続に SQL Server インスタンスの名前。 値を指定しない場合、アダプターは、既定のデータベース インスタンスに接続します。|  
|[DATABASE_NAME]|hostinfoparams|接続するデータベースの名前。 値を指定しない場合、アダプターは、既定のデータベースに接続します。|  
|[PARTNER_SERVER_NAME]|query_string|場合に、プライマリ SQL Server データベースの接続にフェールオーバーの SQL Server データベースの名前は使用できません。 高可用性の SQL Server についての詳細については、[SQL Server データベースのミラーリング](https://msdn.microsoft.com/library/5h52hef8.aspx)を参照してください。|  
|[INBOUND_ID]|query_string|接続して一意の URI に追加するための識別子です。 メタデータを生成する場合は、この接続のパラメーターを指定する必要があります、 **TypedPolling**操作を受信します。 また、BizTalk アプリケーションでは、複数の受信場所が、同じデータベースをポーリングした場合受信 ID が、接続をアダプター クライアント異なる上の同じデータベースからポーリング メッセージを受信できるように一意である URI の受信場所。 詳細については、[受信ポーリング メッセージ間で複数受信ポートから BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)を参照してください。|  
  
> [!NOTE]
>  これらの接続文字列プロパティの詳細については、[SqlConnection.ConnectionString プロパティ](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx)を参照してください。
  
## <a name="sql-server-credentials-and-the-connection-uri"></a>SQL Server 資格情報と接続 URI  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI で指定する資格情報をサポートしていません。 使用するアプリケーションで資格情報の指定の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)します。  
  
## <a name="using-special-characters-in-the-connection-uri"></a>接続 URI で特殊文字の使用  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続パラメーター値のいずれかの特殊文字を含む URI を指定することはできません。 接続パラメーターの値に特殊文字が含まれている場合は、次のいずれかの操作を確認します。  
  
- URI を指定する場合は[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、として指定する必要があります-では、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せず。 直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、特殊文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
   たとえば、URI の接続に名前を持つパラメーター `sql server`、として指定する必要があります`sql%20server`します。  
  
- 送信の作成中に、URI を指定する、または、受信ポートのかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール、および接続パラメーターは、特殊文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
## <a name="using-the-connection-uri-to-connect-to-the-sql-server-database"></a>SQL Server データベースに接続する接続 URI を使用します。  
 次に、サンプルの接続 URI の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
```  
mssql://sql_server/sql_server_instance//  
```  
  
 前の例では、"sql_server"は、SQL Server がインストールされている"sql_server_instance"に接続するデータベース インスタンスの名前には、コンピューターの名前です。 データベース名が指定されていないため、アダプターは、既定のデータベースに接続します。  
  
 接続と同じコンピューターに SQL Server データベースがインストールされている URI の例を次に、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 この例では、アダプターは、"my_database"ローカル コンピューターの"sql_server_instance"データベース インスタンスのデータベースに接続します。  
  
```  
mssql://localhost/sql_server_instance/my_database/  
```  
  
 この例では、アダプターは、ローカル コンピューターで実行されている既定のインスタンスの既定のデータベースに接続します。  
  
```  
mssql://localhost///  
```  
  
 SQL Server への接続を指定する方法についてはデータベースの場合にします。  
  
- 使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[SQL アダプターを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)します。  
  
- 送信ポートを構成または BizTalk Server ソリューションでの受信ポート (場所) を参照してください[SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。
  
- プログラミング ソリューションで WCF チャネル モデルを使用して、参照してください[SQL アダプターを使用してチャネルを作成](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)です。  
  
- プログラミング ソリューションで WCF サービス モデルを使用して、参照してください[クライアント バインディングを構成、SQL アダプターの](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)します。  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)