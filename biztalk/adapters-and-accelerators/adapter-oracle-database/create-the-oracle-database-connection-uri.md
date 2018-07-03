---
title: Oracle Database 接続 URI の作成 |Microsoft Docs
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
ms.openlocfilehash: dee680c0e27f0d5456c54701c4f385b2c629e146
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975875"
---
# <a name="create-the-oracle-database-connection-uri"></a>Oracle Database 接続 URI を作成します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]接続 URI には、アダプターが Oracle データベースへの接続を確立するために使用するプロパティが含まれています。 このトピックでは、tnsnames.ora を使用して Oracle データベースと tnsnames.ora を使用せずに接続する接続 URI を指定する方法についての情報を提供します。 また、接続 URI を使用して Oracle データベースに接続する方法の情報も提供します。  

## <a name="connection-uri-to-connect-to-the-oracle-database-using-tnsnamesora"></a>接続 URI tnsnames.ora を使用して Oracle データベースに接続するには  

> [!IMPORTANT]
> - このアプローチでアダプター クライアントがインストールされて、コンピューターの tnsnames.ora ファイルで net サービス名のエントリを追加する必要があります。 Net サービス名のエントリの詳細については、次を参照してください。 [Oracle データベース アダプターの Oracle クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)します。  
>   -   Oracle クライアントの制限により、 **DataSourceName**トランザクションで操作を実行している場合、接続 URI のパラメーター (net サービス名) は複数の 39 文字を含めることはできません。 値が指定されているため、必ず、 **DataSourceName**パラメーターは 39 文字未満のトランザクションで操作を実行する場合。  

 一般的なエンドポイント アドレス URI で[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]として表される: `scheme://userauthparams@hostinfoparams?query_string`、場所。  

- スキームは、スキームの名前です。  

- userauthparams は、ユーザーの認証エンドポイントによって必要なパラメーターの名前と値のコレクションです。  

- hostinfoparams はホストへの接続を確立するために必要な情報は、します。たとえば、パスです。  

- クエリ文字列は、疑問符 (?) で区切られたパラメーターのオプションの名前と値のコレクションです。  

  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続 URI はこの基本的な形式に従います、次のように実装されます。  

```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[NET_SERVICE_NAME]?PollingId=[POLLING_ID]  
```  

 次の表では、接続 URI に含まれるプロパティについて説明します。  


| 接続 URI のプロパティ |    カテゴリ    |                                                                                                                                                                                                                                                                                                                                                                                           説明                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       [ユーザー名]       | userauthparams | Oracle データベースでの認証に使用するユーザー名たとえば、SCOTT です。 設定する必要があります、 **AcceptCredentialsInUri**プロパティをバインド**true**接続 URI のユーザー名とパスワードを指定します。<br /><br /> **注**、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにユーザー名を入力する値の大文字小文字を保持します。 Oracle データベースでのユーザー名は大文字小文字を区別します。 Oracle ユーザー名を指定することを確認してください、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。 通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります。"SCOTT"。 |
|       [パスワード]        | userauthparams |                                                                                                                                Oracle データベースでの認証に使用するパスワードたとえば、TIGER です。 設定する必要があります、 **AcceptCredentialsInUri**プロパティをバインド**true**接続 URI のユーザー名とパスワードを指定します。<br /><br /> **注**、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。 リリース 10 g、前の Oracle システム上のパスワードは大文字小文字を区別しない.                                                                                                                                |
|   [NET_SERVICE_NAME]    | hostinfoparams |                                                                                                                                                                            コンピューターの tnsnames.ora ファイルで指定されている net サービス名を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]がインストールされています。 Net サービス名と tnsnames.ora の詳細については、次を参照してください。 [Oracle データベース アダプターの Oracle クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)します。                                                                                                                                                                             |
|      [POLLING_ID]       |  query_string  |                                                                                                                                                                                                                     アダプターによって POLLINGSTMT 操作の標準名前空間に追加するか省略可能な文字列。 これにより、プロジェクトには、複数のポーリング操作が含まれている場合は、各ポーリング操作の一意の名前空間を指定することができます。 プロジェクトには、1 つだけの POLLINGSTMT 操作が含まれている場合は、PollingId 文字列を指定する必要はありません。                                                                                                                                                                                                                      |

> [!NOTE]
>  エンドポイント アドレスを指定すると、クエリ パラメーターが接続 URI の使用も、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Metadata Exchange クライアント。  

## <a name="connection-uri-to-connect-to-the-oracle-database-without-using-tnsnamesora"></a>接続 URI tnsnames.ora を使用せずに、Oracle データベースに接続するには  

> [!IMPORTANT]
> - この方法は、tnsnames.ora ファイル、または実際の tnsnames.ora ファイル自体で net サービス名がクライアント コンピューターに存在する必要はありません。  
>   -   トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限です。  

 一般的なエンドポイント アドレス URI で[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]として表される: `scheme://userauthparams@hostinfoparams?query_string`、場所。  

- スキームは、スキームの名前です。  

- userauthparams は、ユーザーの認証エンドポイントによって必要なパラメーターの名前と値のコレクションです。  

- hostinfoparams はホストへの接続を確立するために必要な情報は、します。たとえば、サーバー名、ポート番号などです。  

- クエリ文字列は、疑問符 (?) で区切られたパラメーターのオプションの名前と値のコレクションです。  

  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続 URI はこの基本的な形式に従います、次のように実装されます。  

```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[SERVER_NAME]:[PORT_NUMBER]/[SERVICE_NAME]/SERVICE_TYPE]?PollingId=[POLLING_ID]  
```  

 次の表では、接続 URI に含まれるプロパティについて説明します。  


| 接続 URI のプロパティ |    カテゴリ    |                                                                                                                                                                                                                                                                                                                                                                                           説明                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       [ユーザー名]       | userauthparams | Oracle データベースでの認証に使用するユーザー名たとえば、SCOTT です。 設定する必要があります、 **AcceptCredentialsInUri**プロパティをバインド**true**接続 URI のユーザー名とパスワードを指定します。<br /><br /> **注**、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにユーザー名を入力する値の大文字小文字を保持します。 Oracle データベースでのユーザー名は大文字小文字を区別します。 Oracle ユーザー名を指定することを確認してください、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。 通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります。"SCOTT"。 |
|       [パスワード]        | userauthparams |                                                                                                                                Oracle データベースでの認証に使用するパスワードたとえば、TIGER です。 設定する必要があります、 **AcceptCredentialsInUri**プロパティをバインド**true**接続 URI のユーザー名とパスワードを指定します。<br /><br /> **注**、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。 リリース 10 g、前の Oracle システム上のパスワードは大文字小文字を区別しない.                                                                                                                                |
|      [サーバー名]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                          Oracle データベースが実行されているサーバーの名前。 これは必須です。                                                                                                                                                                                                                                                                                                                                                          |
|      [PORT_NUMBER]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                Oracle Net リスナー ポートです。 値が指定されていない場合、アダプターは、既定値 1521 を使用します。                                                                                                                                                                                                                                                                                                                                                 |
|     [サービス名]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                       Oracle データベースのサービスの名前。 これは必須です。                                                                                                                                                                                                                                                                                                                                                                       |
|     [SERVICE_TYPE]      | hostinfoparams |                                                                                                                                                                                                                                                  Oracle サービスの型。 指定できる値は**Dedicated**または**Shared**します。 専用のサービスでは、1 つだけのユーザー プロセスを処理するために専用のサーバー プロセスを使用します。 共有サービスは、複数のユーザー プロセスを使用できることができる共有サーバー プロセスを使用します。 既定値は**Dedicated**します。                                                                                                                                                                                                                                                   |
|      [POLLING_ID]       |  query_string  |                                                                                                                                                                                                                     アダプターによって POLLINGSTMT 操作の標準名前空間に追加するか省略可能な文字列。 これにより、プロジェクトには、複数のポーリング操作が含まれている場合は、各ポーリング操作の一意の名前空間を指定することができます。 プロジェクトには、1 つだけの POLLINGSTMT 操作が含まれている場合は、PollingId 文字列を指定する必要はありません。                                                                                                                                                                                                                      |

> [!NOTE]
>  エンドポイント アドレスを指定すると、クエリ パラメーターが接続 URI の使用も、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Metadata Exchange クライアント。  

## <a name="oracle-database-credentials-and-the-connection-uri"></a>Oracle データベースの資格情報と接続 URI  
 既定で、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースの資格情報が接続 URI で指定した場合に例外をスローします。 これらの資格情報はプレーン テキストで、接続、URI として表され、セキュリティ リスクが生じないためにです。 設定することができます、 **AcceptCredentialsInUri**接続 URI は、Oracle データベースの資格情報を含めることができるかどうか、プロパティをコントロールにバインドします。 場合、 **AcceptCredentialsInUri**プロパティは**false**、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]プロパティの場合、接続 URI には、Oracle データベース資格情報が含まれている場合に例外をスローします**は true。** 例外はスローされません。 いくつかの限られたシナリオでは URI での接続で資格情報を指定する必要があります。たとえば、受信 POLLINGSTMT を受信する WCF を使用するときにサービス モデルまたは WCF チャネル モデル。 ほとんどの場合、ただし、する必要がありますしないようにする接続 URI 内の資格情報を提供します。 Oracle データベースの資格情報をより安全に提供する方法の詳細については、次を参照してください。 [Oracle データベース アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)します。  

> [!IMPORTANT]
>  原因として、プレーン テキストの文字列で資格情報を渡すことによって生じるセキュリティ リスク、URI の接続で Oracle データベース接続の資格情報を指定することを避ける必要があります。  

## <a name="using-reserved-characters-in-the-connection-uri"></a>接続 URI の予約文字の使用  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続パラメーター値のいずれかの特殊文字を含む URI を指定することはできません。 接続パラメーターの値に特殊文字が含まれている場合は、次のいずれかの操作を確認します。  

- URI を指定する場合は[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、として指定する必要があります-では、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せず。 直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  

- 送信の作成中に、URI を指定する、または、受信ポートのかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール、および接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  

## <a name="using-the-connection-uri-to-connect-to-the-oracle-database"></a>Oracle データベースに接続する接続 URI を使用します。  
 接続 URI の例を次の[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  

|Tnsnames.ora の使用|Tnsnames.ora を使用せず|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER`<br /><br /> この例では、アダプターは、tnsnames.ora のターゲットの Oracle データベースのサービス名と接続情報に関連付けられている net サービス名です。|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated`<br /><br /> この例では、サーバー名が"yourOracleServer"とサービス名が"yourOracleDatabaseServiceName"。|  

 次に POLLINGSTMT 操作の接続 URI の例を示します。 この URI には、POLLINGSTMT 操作の名前空間を変更する PollingId パラメーターが含まれています。  

|Tnsnames.ora の使用|Tnsnames.ora を使用せず|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER?PollingId=MyPollingNotification1`|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated? PollingId=MyPollingNotification1`|  

 上記の接続、Uri、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作に対して次の名前空間を作成します。  

```  
http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTMyPollingNotification1  
```  

 Oracle への接続を確立する方法についてはデータベースの場合にします。  

- 使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[Consume Adapter Service を使用して Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)します。  

- 送信ポートを構成または受信ポート (場所) で、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[、Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)します。  

- プログラミング ソリューションで WCF チャネル モデルを使用して、参照してください[Oracle データベースを使用してチャネルを作成](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)です。  

- プログラミング ソリューションで WCF サービス モデルを使用して、参照してください[for Oracle Database バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)します。  

- 使用して WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を参照してください[BizTalk adapter for Oracle Database、ServiceModel メタデータ ユーティリティ ツールを使用して](../../adapters-and-accelerators/adapter-oracle-database/use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md)します。  

## <a name="see-also"></a>参照  
[Oracle データベースへの接続を作成します。](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)   
 [Oracle データベース アダプターの Oracle クライアントを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)