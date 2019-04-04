---
title: Oracle E-business Suite 接続 URI の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91eb49fa-2a69-470b-b96d-dc3a6ffafef6
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 238f1208d2a24a861c169aee448fd696bca2b34b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992851"
---
# <a name="create-the-oracle-e-business-suite-connection-uri"></a>Oracle E-business Suite 接続 URI の作成します。
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]接続 URI には、アダプターは、Oracle E-business Suite、および基になる Oracle データベースでは基本的にへの接続を確立するために使用するプロパティが含まれています。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]基になる Oracle データベースへの接続の 2 つの方法をサポートしています: tnsnames.ora を使用して tnsnames.ora を使用しない場合。 接続方法の種類に基づき、接続 URI の形式も異なります。 このトピックでは、Oracle の接続 URI に関する情報を提供し、さまざまなプログラミング シナリオで URI を指定する方法を説明するその他のトピックへのリンクもあります。  

 Oracle E-business Suite は、アプリケーション層を基になる Oracle データベースとのインターフェイスし、財務、人事、組織内のさまざまなニーズに基づくなどのさまざまなアプリケーションに分類されます。 これらの各アプリケーションは、さまざまな"forms"を基になる Oracle データベースにデータを入力できるようにするを提供します。 ユーザーが所属する組織の ID と、Oracle E-business Suite のアプリケーションの名前に関連付けられている「責任」を構成するアプリケーションのコンテキストでユーザーを関連付けることによってこれらのフォームへのアクセスが制限されているユーザー呼び出す必要があります。 Oracle E-business Suite アーティファクトに対する操作を実行するときに、アダプターは、基になるデータベースに直接接続し、フォームは、Oracle E-business Suite とのインターフェイスを使用しませんもが、必須アプリケーション コンテキストの設定ができます。 Oracle E-business suite、および Oracle データベースを基になるを使用して接続するため、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、する必要があります。  

- Oracle E-business Suite と基になる Oracle database に接続するための URI の接続を指定します。 接続を確立中には、Oracle E-business Suite または基になる Oracle データベースの資格情報を指定できます。  

- ユーザーのアプリケーションのコンテキストを設定します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]資格情報と、責任をそのまま使用する特定のバインド プロパティを公開します。 これらのバインド プロパティの詳細については、[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。 アプリケーションのコンテキストを設定する方法についての詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。  

  このセクションでは、tnsnames.ora を使用して基になるデータベースと tnsnames.ora を使用せずに接続する接続 URI を指定する方法について説明します。 Oracle E-business Suite に接続する接続 URI の使用に関する情報も提供します。  

## <a name="connect-using-tnsnamesora"></a>Tnsnames.ora を使用して接続します。  

> [!IMPORTANT]
> - このアプローチでアダプター クライアントがインストールされて、コンピューターの tnsnames.ora ファイルで net サービス名のエントリを追加する必要があります。 Net サービス名のエントリについては、[E-business Suite アダプター用の Oracle クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)を参照してください。  
>   -   Oracle クライアントの制限により、 **DataSourceName**トランザクションで操作を実行している場合、接続 URI のパラメーター (net サービス名) は複数の 39 文字を含めることはできません。 値が指定されているため、必ず、 **DataSourceName**パラメーターは 39 文字未満のトランザクションで操作を実行する場合。  

 接続 URI に接続する Oracle E-business Suite サービスを識別するために使用される Oracle net サービス名を含めることができます。 Oracle クライアントでは、Oracle の名前付け方法を使用するように構成するの階層に従って、Oracle E-business Suite サービスの接続情報への接続 URI で指定した Oracle net サービス名を解決します。 1 つの一般的な名前付け方法は、ローカルの名前付けは呼び出されます。 ローカルの名前付けでは、Oracle クライアントは、Oracle net サービス名を解決するのには tnsnames.ora という名前のファイルを使用します。  

 一般的なエンドポイント アドレス URI で[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]として表される: `scheme://userauthparams@hostinfoparams`、場所。  

- スキームは、スキームの名前です。  

- userauthparams は、ユーザーの認証エンドポイントによって必要なパラメーターの名前と値のコレクションです。  

- hostinfoparams はホストへの接続を確立するために必要な情報は、します。たとえば、net サービス名です。  

  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接続 URI はこの基本的な形式に従います、次のように実装されます。  

```  
oracleebs://User=[USER_NAME];Password=[PASSWORD]@[NET_SERVICE_NAME]  
```  

 次の表では、接続 URI に含まれるプロパティについて説明します。  


| 接続 URI のプロパティ |    カテゴリ    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      説明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-------------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       [ユーザー名]       | userauthparams | 認証に使用するユーザー名。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 **ClientCredentialType**クライアントが接続を確立するを指定する Oracle クライアントの資格情報の種類を指定するプロパティをバインドします。 使用可能な値を**ClientCredentialType**プロパティのバインドは**データベース**と**EBusiness**します。 このバインドのプロパティの値に応じて関連する資格情報を指定する必要があります。 詳細については、[Oracle 資格情報と接続 URI](#BKMK_OraCreds)を参照してください。 **注:** 設定する必要があります、 **AcceptCredentialsInUri**プロパティをバインド**true**接続 URI のユーザー名とパスワードを指定します。 **注:** 、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続する場合に、ユーザー名を入力する値の大文字と小文字は保持されません。 SQL の標準の規則を使用して Oracle E-business Suite にユーザー名が渡される\*とします。 ただし、保持するユーザー名の大文字と小文字の場合、または特殊文字を含むユーザー名を入力する場合は、二重引用符で囲まれた値を指定する必要があります。 |
|       [パスワード]        | userauthparams |                                                                                認証に使用するパスワード。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 **ClientCredentialType**クライアントが接続を確立するを指定する Oracle クライアントの資格情報の種類を指定するプロパティをバインドします。 場合、 **ClientCredentialType**プロパティに設定されて**データベース**クライアントは、Oracle データベース ユーザーのパスワードを指定する必要があります。 場合、 **ClientCredentialType**プロパティに設定されて**EBusiness**クライアントは、Oracle E-business Suite ユーザーのパスワードを指定する必要があります。 **注:** 、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続するときにパスワードを入力する値の大文字と小文字は保持されません。 SQL の標準の規則を使用して Oracle E-business Suite にユーザー名が渡される\*とします。 ただし、保持するパスワードの大文字と小文字の場合、または特殊文字を含むパスワードを入力する場合は、二重引用符で囲まれた値を指定する必要があります。                                                                                |
|   [NET_SERVICE_NAME]    | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                                                    コンピューターの tnsnames.ora ファイルで指定されている net サービス名を[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]がインストールされています。 Net サービス名と tnsnames.ora の詳細については、[E-business Suite アダプター用の Oracle クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)を参照してください。                                                                                                                                                                                                                                                                                                                                                                                                     |

## <a name="connect-without-using-tnsnamesora"></a>Tnsnames.ora を使用せずに接続します。  

> [!IMPORTANT]
> - このアプローチで必要ありません、net サービス名のエントリで、tnsnames.ora します。 またも必要はありませんアダプター クライアントがインストールされているコンピューターの tnsnames.ora ファイルがあるようにします。  
>   -   トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限です。  

 一般的なエンドポイント アドレス URI で[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]として表される: `scheme://userauthparams@hostinfoparams`、場所。  

- スキームは、スキームの名前です。  

- userauthparams は、ユーザーの認証エンドポイントによって必要なパラメーターの名前と値のコレクションです。  

- hostinfoparams はホストへの接続を確立するために必要な情報は、します。たとえば、サーバー名、ポート番号などです。  

  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接続 URI はこの基本的な形式に従います、次のように実装されます。  

```  
oracleebs://User=[USER_NAME];Password=[PASSWORD]@[SERVER_NAME]:[PORT_NUMBER]/[SERVICE_NAME]/[SERVICE_TYPE]   
```  

 次の表では、接続 URI に含まれるプロパティについて説明します。  


| 接続 URI のプロパティ |    カテゴリ    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      説明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-------------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       [ユーザー名]       | userauthparams | 認証に使用するユーザー名。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 **ClientCredentialType**クライアントが接続を確立するを指定する Oracle クライアントの資格情報の種類を指定するプロパティをバインドします。 使用可能な値を**ClientCredentialType**プロパティのバインドは**データベース**と**EBusiness**します。 このバインドのプロパティの値に応じて関連する資格情報を指定する必要があります。 詳細については、[Oracle 資格情報と接続 URI](#BKMK_OraCreds)を参照してください。 **注:** 設定する必要があります、 **AcceptCredentialsInUri**プロパティをバインド**true**接続 URI のユーザー名とパスワードを指定します。 **注:** 、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続する場合に、ユーザー名を入力する値の大文字と小文字は保持されません。 SQL の標準の規則を使用して Oracle E-business Suite にユーザー名が渡される\*とします。 ただし、保持するユーザー名の大文字と小文字の場合、または特殊文字を含むユーザー名を入力する場合は、二重引用符で囲まれた値を指定する必要があります。 |
|       [パスワード]        | userauthparams |                                                                                認証に使用するパスワード。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 **ClientCredentialType**クライアントが接続を確立するを指定する Oracle クライアントの資格情報の種類を指定するプロパティをバインドします。 場合、 **ClientCredentialType**プロパティに設定されて**データベース**クライアントは、Oracle データベース ユーザーのパスワードを指定する必要があります。 場合、 **ClientCredentialType**プロパティに設定されて**EBusiness**クライアントは、Oracle E-business Suite ユーザーのパスワードを指定する必要があります。 **注:** 、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続するときにパスワードを入力する値の大文字と小文字は保持されません。 SQL の標準の規則を使用して Oracle E-business Suite にユーザー名が渡される\*とします。 ただし、保持するパスワードの大文字と小文字の場合、または特殊文字を含むパスワードを入力する場合は、二重引用符で囲まれた値を指定する必要があります。                                                                                |
|      [サーバー名]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 Oracle E-business Suite を実行しているサーバーの名前。 これは必須です。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|      [PORT_NUMBER]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 Oracle Net リスナー ポートです。 1521 の既定値。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|     [サービス名]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Oracle データベースのサービスの名前。 これは必須です。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|     [SERVICE_TYPE]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Oracle サービスの型。 指定できる値は**Dedicated**または**Shared**します。 専用のサービスでは、1 つだけのユーザー プロセスを処理するために専用のサーバー プロセスを使用します。 共有サービスは、複数のユーザー プロセスを使用できる共有サーバー プロセスを使用します。 既定値は**Dedicated**します。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

##  <a name="BKMK_OraCreds"></a> Oracle 資格情報と接続 URI  
 既定で、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle 資格情報が接続 URI で指定した場合に例外をスローします。 これらの資格情報はプレーン テキストで、接続、URI として表され、セキュリティ リスクが生じないためにです。 設定することができます、 **AcceptCredentialsInUri**接続 URI は、Oracle データベースの資格情報を含めることができるかどうか、プロパティをコントロールにバインドします。 場合、 **AcceptCredentialsInUri**プロパティは**false**、これは、既定、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] プロパティの場合、接続URIには、Oracle資格情報が含まれている場合に例外をスローします**true**例外はスローされません。  

> [!IMPORTANT]
>  原因として、プレーン テキストの文字列で資格情報を渡すことによって生じるセキュリティ リスク、URI の接続で Oracle データベース接続の資格情報を指定することを避ける必要があります。 Oracle データベースの資格情報をより安全に提供する方法の詳細については、[、Oracle EBS アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)を参照してください。  

 データベースの資格情報または Oracle E-business Suite への接続を確立するための Oracle E-business Suite の資格情報のいずれかを指定することもできます。 アダプターは、この動作を有効にする 3 つのバインド プロパティを公開します: **ClientCredentialType**、 **OracleUserName**、 **OraclePassword**します。  

 使用可能な値を**ClientCredentialType**プロパティのバインドは**データベース**と**EBusiness**します。  

-   場合、 **ClientCredentialType**プロパティに設定されて**データベース**クライアントは、データベースの資格情報を指定する必要があります。  

-   場合、 **ClientCredentialType**プロパティに設定されて**EBusiness**クライアントは、Oracle E-business Suite の資格情報を指定する必要があります。 この場合、アダプター クライアントにはのデータベースの資格情報が指定する必要がありますも、 **OracleUserName**と**OraclePassword**プロパティをバインドします。  

> [!IMPORTANT]
>  アダプターのクライアントが設定して、Oracle E-business Suite に接続するデータベース資格情報を指定するシナリオで、 **ClientCredentialType**プロパティをバインド**データベース**Oracle を呼び出すが、E-business Suite の成果物の値が指定された**OracleUserName**と**OraclePassword**アプリケーション コンテキストを設定するためのバインドのプロパティを使用します。 アプリケーションのコンテキストを設定することは、Oracle E-business Suite での成果物を呼び出すために必須です。 アプリケーションのコンテキストを設定する方法についての詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。  

## <a name="using-reserved-characters-in-the-connection-uri"></a>接続 URI の予約文字の使用  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接続パラメーター値のいずれかの特殊文字を含む URI を指定することはできません。 接続パラメーターの値に特殊文字が含まれている場合は、次のいずれかの操作を確認します。  

- URI を指定する場合は[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、として指定する必要があります-では、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せず。 直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  

- 送信の作成中に、URI を指定する、または、受信ポートのかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール、および接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  

## <a name="using-the-connection-uri-to-connect-to-oracle-e-business-suite"></a>Oracle E-business Suite に接続する接続 URI を使用します。  
 接続 URI の例を次の[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]tnsnames.ora を使用します。  

```  
oracleebs://ADAPTER  
```  

 この例では、アダプターは、tnsnames.ora のターゲットの Oracle データベースのサービス名と接続情報に関連付けられている net サービス名です。  

 接続 URI の例を次の[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]tnsnames.ora を使用せずします。  

```  
oracleebs://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated  
```  

 この例では、サーバー名が"yourOracleServer"とサービス名が"yourOracleDatabaseServiceName"。  

 Oracle E-business Suite への接続を確立する方法についてはときにします。  

- 使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)します。  

- 送信ポートを構成または受信ポート (場所) で、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[Oracle E-business アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)します。  

## <a name="see-also"></a>参照  
 [Oracle E-business Suite アダプターのクライアントを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)   
 [Windows 認証を使用して Oracle E-business Suite への接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)  
 [Oracle E-business Suite への接続を作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)