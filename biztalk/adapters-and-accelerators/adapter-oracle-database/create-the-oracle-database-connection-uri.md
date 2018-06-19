---
title: Oracle Database 接続 URI を作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, basic format of
- connection URI, database credentials and
- connection URI, connecting to the Oracle database
- connection URI
ms.assetid: 17d0a6d3-1b0c-43d6-a705-402c09a78ee0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f7b0fcc0c83bd4a844ac1a83488e1a3e8d9a65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217474"
---
# <a name="create-the-oracle-database-connection-uri"></a>Oracle Database 接続 URI を作成します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]接続 URI には、アダプターは、Oracle データベースへの接続を確立するために使用するプロパティが含まれています。 このトピックでは、接続 tnsnames.ora を使用せずに tnsnames.ora を使用して Oracle データベースへの接続への URI を指定する方法に関する情報を提供します。 Oracle データベースに接続する接続 URI の使用に関する情報も提供します。  
  
## <a name="connection-uri-to-connect-to-the-oracle-database-using-tnsnamesora"></a>接続 URI tnsnames.ora を使用して Oracle データベースに接続するには  
  
> [!IMPORTANT]
>  -   この方法には、アダプター クライアントがインストールされた、tnsnames.ora ファイル、コンピューター上で net サービス名エントリを追加する必要があります。 Net サービス名エントリの詳細については、次を参照してください。 [Oracle データベース アダプターの Oracle クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)です。  
> -   Oracle クライアントの制限により、 **DataSourceName**トランザクションで操作を実行している場合、接続 URI のパラメーター (net サービス名) は複数の 39 文字を含めることはできません。 したがっての値が指定されていることを確認してください、 **DataSourceName**パラメーターは 39 文字以下のトランザクションで操作を実行する場合。  
  
 一般的なエンドポイント アドレスに URI[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]として表される: `scheme://userauthparams@hostinfoparams?query_string`、場所。  
  
-   スキームは、スキーム名です。  
  
-   userauthparams はエンドポイントによってユーザー認証に必要なパラメーターの名前と値のコレクションです。  
  
-   hostinfoparams はホストへの接続を確立するために必要な情報たとえば、パスです。  
  
-   query_string は疑問符 (?) で区切られたパラメーターの省略可能な名前と値のコレクションです。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続 URI はこの基本的な形式に従います、次のように実装します。  
  
```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[NET_SERVICE_NAME]?PollingId=[POLLING_ID]  
```  
  
 次の表では、接続 URI に含まれるプロパティについて説明します。  
  
|接続 URI のプロパティ|カテゴリ|Description|  
|-----------------------------|--------------|-----------------|  
|[ユーザー名]|userauthparams|Oracle データベースでの認証に使用するユーザー名たとえば、SCOTT です。 設定する必要があります、 **AcceptCredentialsInUri**にプロパティのバインド**true**接続 URI のユーザー名とパスワードを指定します。<br /><br /> **注**、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときに、ユーザー名を入力する値の大文字小文字を保持します。 Oracle データベースでユーザー名は大文字小文字を区別します。 Oracle ユーザー名を指定することを確認する必要があります、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。 通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります:"SCOTT"です。|  
|[パスワード]|userauthparams|Oracle データベースでの認証に使用するパスワードたとえば、TIGER です。 設定する必要があります、 **AcceptCredentialsInUri**にプロパティのバインド**true**接続 URI のユーザー名とパスワードを指定します。<br /><br /> **注**、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。 リリース 10 g、前の Oracle システム上のパスワードは大文字小文字が区別されません。|  
|[NET_SERVICE_NAME]|hostinfoparams|Net サービス名、コンピューター上の tnsnames.ora ファイルで指定されている場所、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]がインストールされています。 Net サービス名と tnsnames.ora に関する詳細については、次を参照してください。 [Oracle データベース アダプターの Oracle クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)です。|  
|[POLLING_ID]|query_string|アダプターによって POLLINGSTMT 操作の標準の名前空間に追加するか省略可能な文字列。 これにより、プロジェクトには、複数のポーリング操作が含まれている場合は、ポーリング操作ごとに一意の名前空間を指定できます。 POLLINGSTMT 操作の 1 つだけがプロジェクトに含まれている場合、PollingId 文字列を指定する必要はありません。|  
  
> [!NOTE]
>  エンドポイント アドレスを指定すると、クエリ パラメーターが接続 URI の使用も、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Metadata Exchange のクライアントです。  
  
## <a name="connection-uri-to-connect-to-the-oracle-database-without-using-tnsnamesora"></a>接続 URI tnsnames.ora を使用せず、Oracle データベースに接続するには  
  
> [!IMPORTANT]
>  -   この方法は、tnsnames.ora ファイル、または実際 tnsnames.ora ファイル自体で net サービス名が、クライアント コンピューターに存在している必要はありません。  
> -   トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限によるものです。  
  
 一般的なエンドポイント アドレスに URI[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]として表される: `scheme://userauthparams@hostinfoparams?query_string`、場所。  
  
-   スキームは、スキーム名です。  
  
-   userauthparams はエンドポイントによってユーザー認証に必要なパラメーターの名前と値のコレクションです。  
  
-   hostinfoparams はホストへの接続を確立するために必要な情報たとえば、サーバー名、ポート番号などです。  
  
-   query_string は疑問符 (?) で区切られたパラメーターの省略可能な名前と値のコレクションです。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続 URI はこの基本的な形式に従います、次のように実装します。  
  
```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[SERVER_NAME]:[PORT_NUMBER]/[SERVICE_NAME]/SERVICE_TYPE]?PollingId=[POLLING_ID]  
```  
  
 次の表では、接続 URI に含まれるプロパティについて説明します。  
  
|接続 URI のプロパティ|カテゴリ|Description|  
|-----------------------------|--------------|-----------------|  
|[ユーザー名]|userauthparams|Oracle データベースでの認証に使用するユーザー名たとえば、SCOTT です。 設定する必要があります、 **AcceptCredentialsInUri**にプロパティのバインド**true**接続 URI のユーザー名とパスワードを指定します。<br /><br /> **注**、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときに、ユーザー名を入力する値の大文字小文字を保持します。 Oracle データベースでユーザー名は大文字小文字を区別します。 Oracle ユーザー名を指定することを確認する必要があります、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。 通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります:"SCOTT"です。|  
|[パスワード]|userauthparams|Oracle データベースでの認証に使用するパスワードたとえば、TIGER です。 設定する必要があります、 **AcceptCredentialsInUri**にプロパティのバインド**true**接続 URI のユーザー名とパスワードを指定します。<br /><br /> **注**、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。 リリース 10 g、前の Oracle システム上のパスワードは大文字小文字が区別されません。|  
|[サーバー名]|hostinfoparams|Oracle データベースが実行されているサーバーの名前。 これは必須です。|  
|[PORT_NUMBER]|hostinfoparams|Oracle Net リスナー ポートです。 値が指定されていない場合、アダプターは既定値 1521 を使用します。|  
|[サービス名]|hostinfoparams|Oracle データベースのサービスの名前。 これは必須です。|  
|[SERVICE_TYPE]|hostinfoparams|Oracle サービスの型。 指定できる値は**専用**または**Shared**です。 専用のサービスを 1 つだけのユーザー プロセスを処理するのに専用のサーバー プロセスを使用します。 共有サービスは、複数のユーザー プロセスを使用できることができる共有サーバー プロセスを使用します。 既定値は**専用**です。|  
|[POLLING_ID]|query_string|アダプターによって POLLINGSTMT 操作の標準の名前空間に追加するか省略可能な文字列。 これにより、プロジェクトには、複数のポーリング操作が含まれている場合は、ポーリング操作ごとに一意の名前空間を指定できます。 POLLINGSTMT 操作の 1 つだけがプロジェクトに含まれている場合、PollingId 文字列を指定する必要はありません。|  
  
> [!NOTE]
>  エンドポイント アドレスを指定すると、クエリ パラメーターが接続 URI の使用も、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Metadata Exchange のクライアントです。  
  
## <a name="oracle-database-credentials-and-the-connection-uri"></a>Oracle データベースの資格情報と接続 URI  
 既定では、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースの資格情報が接続 URI で指定した場合は例外をスローします。 これは、これらの資格情報は、接続 URI にプレーン テキストとして表されます。 セキュリティ上のリスクを伴いますこのためです。 設定することができます、 **AcceptCredentialsInUri**接続 URI は、Oracle データベースの資格情報を含めることができるかどうか、プロパティをコントロールにバインドします。 場合、 **AcceptCredentialsInUri**プロパティは**false**、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]プロパティの場合、接続 URI には、Oracle データベース資格情報が含まれている場合に例外をスロー**は true。** 例外はスローされません。 いくつかの限られたシナリオは、接続 URI; での資格情報を指定する必要があります。たとえば、受信 POLLINGSTMT を受信する WCF を使用するときにサービス モデルまたは WCF チャネル モデル。 ほとんどの場合、ただし、しないで接続 URI 内の資格情報を提供します。 安全に Oracle データベースの資格情報を提供する方法の詳細については、次を参照してください。 [、Oracle データベース アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)です。  
  
> [!IMPORTANT]
>  プレーン テキストとしての文字列に資格情報を渡すことによってもたらされるセキュリティ リスクのため、接続 URI の Oracle データベース接続の資格情報を指定することを避ける必要があります。  
  
## <a name="using-reserved-characters-in-the-connection-uri"></a>接続 URI で予約された文字の使用  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]パラメーター値のいずれかの特殊文字が含まれている URI の接続の指定をサポートしていません。 接続パラメーター値に特殊文字が含まれている場合は、次のいずれかの操作を確認します。  
  
-   内の URI を指定する場合は[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、として指定する必要があります-では、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。 直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
-   送信の作成中に URI を指定する、または、受信ポートのかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール、および接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
## <a name="using-the-connection-uri-to-connect-to-the-oracle-database"></a>Oracle データベースに接続する接続 URI を使用します。  
 接続 URI の例を次に示しますの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
|Tnsnames.ora を使用します。|Tnsnames.ora を使用せず|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER`<br /><br /> この例では、アダプターは、tnsnames.ora でターゲットの Oracle データベースのサービス名と接続情報に関連付けられている net サービス名です。|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated`<br /><br /> この例では、サーバー名が"yourOracleServer"にあり、サービス名は"yourOracleDatabaseServiceName"です。|  
  
 POLLINGSTMT 操作用の接続 URI の例を次に示します。 この URI には、POLLINGSTMT 操作の名前空間を変更する PollingId パラメーターが含まれています。  
  
|Tnsnames.ora を使用します。|Tnsnames.ora を使用せず|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER?PollingId=MyPollingNotification1`|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated? PollingId=MyPollingNotification1`|  
  
 上記の接続 Uri、用、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作の次の名前空間を作成します。  
  
```  
http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTMyPollingNotification1  
```  
  
 Oracle への接続を確立する方法についてはデータベースの場合にします。  
  
-   使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[アダプター サービスの使用を使用して Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)です。  
  
-   送信ポートを構成するか、受信ポート (場所) で、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)です。  
  
-   プログラミング ソリューションで、WCF チャネル モデルを使用して、参照してください[Oracle データベースを使用して、チャネルの作成](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)です。  
  
-   プログラミング ソリューションで WCF サービス モデルを使用して、参照してください[、クライアントが Oracle データベースのバインディングを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)です。  
  
-   使用する WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を参照してください[BizTalk アダプターに、ServiceModel メタデータ ユーティリティ ツールを使用して Oracle データベースの](../../adapters-and-accelerators/adapter-oracle-database/use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md)します。  
  
## <a name="see-also"></a>参照  
[Oracle データベースへの接続を作成します。](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)   
 [Oracle データベース アダプターの Oracle クライアントを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)