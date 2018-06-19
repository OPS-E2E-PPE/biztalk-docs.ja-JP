---
title: Oracle E-business Suite 接続 URI を作成 |Microsoft ドキュメント
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
ms.openlocfilehash: b3f6e3be6604e8786ff9481ab463f27a31bf1e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22219010"
---
# <a name="create-the-oracle-e-business-suite-connection-uri"></a>Oracle E-business Suite 接続 URI を作成します。
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]接続 URI には、アダプターは、Oracle E-business Suite と基本的に基になる Oracle データベースへの接続を確立するために使用されるプロパティが含まれています。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]基になる Oracle データベースに接続する 2 つの方法をサポートしています: tnsnames.ora を使用して tnsnames.ora を使用せずします。 接続方法の種類に基づき、接続 URI の形式も異なります。 このトピックでは、Oracle 接続 URI に関する情報を提供し、その他のさまざまなプログラミング シナリオでの URI を指定する方法を説明するトピックへのリンクも示します。  
  
 Oracle E-business Suite は、基になる Oracle データベースとのインターフェイスし、財務や人事部、組織内のさまざまなニーズに基づくなどの別のアプリケーションに分類されますをアプリケーション層です。 それぞれのアプリケーションは、さまざまな"forms"を基になる Oracle データベースにデータを入力できるようにするを提供します。 ユーザーが所属する組織の ID、ユーザー、および Oracle E-business Suite アプリケーションの名前に関連付けられている「役割」で構成されたアプリケーションのコンテキストとユーザーを関連付けることによってこれらのフォームへのアクセスが制限されているユーザー起動しようとしています。 Oracle E-business Suite の成果物の操作を実行するときに、アダプターは、基になるデータベースに直接接続し、Oracle E-business Suite とのインターフェイスにフォームを使用しませんもが必須アプリケーション コンテキストを設定するされています。 Oracle E-business suite と Oracle データベースを基になるを使用してに接続する、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、する必要があります。  
  
-   Oracle E-business Suite と基になる Oracle データベースに接続する URI の接続を指定します。 接続を確立中には、Oracle E-business Suite または基になる Oracle データベースの資格情報を指定できます。  
  
-   ユーザーのアプリケーション コンテキストを設定します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]資格情報であり、責任をそのまま使用する特定のバインディング プロパティを公開します。 これらのバインド プロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。 アプリケーション コンテキストの設定の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
 このセクションでは、接続 tnsnames.ora を使用して、基になるデータベースと tnsnames.ora を使用せずに接続する URI を指定する方法についての情報を提供します。 Oracle E-business Suite に接続する接続 URI の使用に関する情報も提供します。  
  
## <a name="connect-using-tnsnamesora"></a>Tnsnames.ora を使用して接続します。  
  
> [!IMPORTANT]
>  -   この方法には、アダプター クライアントがインストールされた、tnsnames.ora ファイル、コンピューター上で net サービス名エントリを追加する必要があります。 Net サービス名のエントリについては、次を参照してください。 [E-business Suite アダプター用の Oracle クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)です。  
> -   Oracle クライアントの制限により、 **DataSourceName**トランザクションで操作を実行している場合、接続 URI のパラメーター (net サービス名) は複数の 39 文字を含めることはできません。 したがっての値が指定されていることを確認してください、 **DataSourceName**パラメーターは 39 文字以下のトランザクションで操作を実行する場合。  
  
 接続 URI は、接続する Oracle E-business Suite サービスの識別に使用される Oracle net サービス名を含めることができます。 Oracle クライアントは、Oracle の名前付け方法を使用するように構成するの階層構造に従って、Oracle E-business Suite サービスの接続情報への接続 URI で指定する Oracle net サービス名を解決します。 1 つの一般的な名前付け方法は、ローカルの名前付けは呼び出されます。 ローカルの名前付けでは、Oracle クライアントは、Oracle net サービス名を解決するのには tnsnames.ora をという名前のファイルを使用します。  
  
 一般的なエンドポイント アドレスに URI[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]として表される: `scheme://userauthparams@hostinfoparams`、場所。  
  
-   スキームは、スキーム名です。  
  
-   userauthparams はエンドポイントによってユーザー認証に必要なパラメーターの名前と値のコレクションです。  
  
-   hostinfoparams はホストへの接続を確立するために必要な情報たとえば、net サービス名です。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接続 URI はこの基本的な形式に従います、次のように実装します。  
  
```  
oracleebs://User=[USER_NAME];Password=[PASSWORD]@[NET_SERVICE_NAME]  
```  
  
 次の表では、接続 URI に含まれるプロパティについて説明します。  
  
|接続 URI のプロパティ|カテゴリ|Description|  
|-----------------------------|--------------|-----------------|  
|[ユーザー名]|userauthparams|認証に使用するユーザー名。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 **ClientCredentialType**クライアントが接続を確立するように指定する Oracle クライアント資格情報の種類を指定するプロパティをバインドします。 値は、使用可能な**ClientCredentialType**プロパティのバインドは、**データベース**と**EBusiness**です。 このバインディングのプロパティの値は、関連する資格情報を指定する必要があります。 詳細については、次を参照してください。 [Oracle 資格情報と接続 URI](#BKMK_OraCreds)です。 **注:** 設定する必要があります、 **AcceptCredentialsInUri**にプロパティのバインド**true**接続 URI のユーザー名とパスワードを指定します。 **注:** 、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続するときに、ユーザー名を入力する値の大文字と小文字は保持されません。 SQL の標準的な規則を使用して Oracle E-business Suite に渡されるユーザー名 * とします。 ただし、保持するユーザー名の大文字と小文字の場合、または特殊文字を格納しているユーザー名を入力する場合は、二重引用符で囲まれた値を指定する必要があります。|  
|[パスワード]|userauthparams|認証に使用するパスワードです。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 **ClientCredentialType**クライアントが接続を確立するように指定する Oracle クライアント資格情報の種類を指定するプロパティをバインドします。 場合、 **ClientCredentialType**プロパティに設定されている**データベース**クライアントは、Oracle データベース ユーザーのパスワードを指定する必要があります。 場合、 **ClientCredentialType**プロパティに設定されている**EBusiness**クライアントは、Oracle E-business Suite ユーザーのパスワードを指定する必要があります。 **注:** 、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite への接続時にパスワードを入力する値の大文字と小文字は保持されません。 SQL の標準的な規則を使用して Oracle E-business Suite に渡されるユーザー名 * とします。 ただし、保持するパスワードの大文字と小文字の場合、または特殊文字を含むパスワードを入力する場合は、二重引用符で囲まれた値を指定する必要があります。|  
|[NET_SERVICE_NAME]|hostinfoparams|Net サービス名、コンピューター上の tnsnames.ora ファイルで指定されている場所、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]がインストールされています。 Net サービス名と tnsnames.ora については、次を参照してください。 [E-business Suite アダプター用の Oracle クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)です。|  
  
## <a name="connect-without-using-tnsnamesora"></a>Tnsnames.ora を使用せずに接続します。  
  
> [!IMPORTANT]
>  -   この方法を使用するは必要ありません net サービス名エントリ、tnsnames.ora でします。 また、する必要はありませんでもアダプター クライアントがインストールされたコンピューターで tnsnames.ora ファイルが必要です。  
> -   トランザクションで操作を実行している場合、この接続のモードがサポートされていません。 これは、Oracle クライアントの制限によるものです。  
  
 一般的なエンドポイント アドレスに URI[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]として表される: `scheme://userauthparams@hostinfoparams`、場所。  
  
-   スキームは、スキーム名です。  
  
-   userauthparams はエンドポイントによってユーザー認証に必要なパラメーターの名前と値のコレクションです。  
  
-   hostinfoparams はホストへの接続を確立するために必要な情報たとえば、サーバー名、ポート番号などです。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接続 URI はこの基本的な形式に従います、次のように実装します。  
  
```  
oracleebs://User=[USER_NAME];Password=[PASSWORD]@[SERVER_NAME]:[PORT_NUMBER]/[SERVICE_NAME]/[SERVICE_TYPE]   
```  
  
 次の表では、接続 URI に含まれるプロパティについて説明します。  
  
|接続 URI のプロパティ|カテゴリ|Description|  
|-----------------------------|--------------|-----------------|  
|[ユーザー名]|userauthparams|認証に使用するユーザー名。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 **ClientCredentialType**クライアントが接続を確立するように指定する Oracle クライアント資格情報の種類を指定するプロパティをバインドします。 値は、使用可能な**ClientCredentialType**プロパティのバインドは、**データベース**と**EBusiness**です。 このバインディングのプロパティの値は、関連する資格情報を指定する必要があります。 詳細については、次を参照してください。 [Oracle 資格情報と接続 URI](#BKMK_OraCreds)です。 **注:** 設定する必要があります、 **AcceptCredentialsInUri**にプロパティのバインド**true**接続 URI のユーザー名とパスワードを指定します。 **注:** 、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite に接続するときに、ユーザー名を入力する値の大文字と小文字は保持されません。 SQL の標準的な規則を使用して Oracle E-business Suite に渡されるユーザー名 * とします。 ただし、保持するユーザー名の大文字と小文字の場合、または特殊文字を格納しているユーザー名を入力する場合は、二重引用符で囲まれた値を指定する必要があります。|  
|[パスワード]|userauthparams|認証に使用するパスワードです。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 **ClientCredentialType**クライアントが接続を確立するように指定する Oracle クライアント資格情報の種類を指定するプロパティをバインドします。 場合、 **ClientCredentialType**プロパティに設定されている**データベース**クライアントは、Oracle データベース ユーザーのパスワードを指定する必要があります。 場合、 **ClientCredentialType**プロパティに設定されている**EBusiness**クライアントは、Oracle E-business Suite ユーザーのパスワードを指定する必要があります。 **注:** 、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite への接続時にパスワードを入力する値の大文字と小文字は保持されません。 SQL の標準的な規則を使用して Oracle E-business Suite に渡されるユーザー名 * とします。 ただし、保持するパスワードの大文字と小文字の場合、または特殊文字を含むパスワードを入力する場合は、二重引用符で囲まれた値を指定する必要があります。|  
|[サーバー名]|hostinfoparams|Oracle E-business Suite が実行されているサーバーの名前。 これは必須です。|  
|[PORT_NUMBER]|hostinfoparams|Oracle Net リスナー ポートです。 1521 の既定値。|  
|[サービス名]|hostinfoparams|Oracle データベースのサービスの名前。 これは必須です。|  
|[SERVICE_TYPE]|hostinfoparams|Oracle サービスの型。 指定できる値は**専用**または**Shared**です。 専用のサービスを 1 つだけのユーザー プロセスを処理するのに専用のサーバー プロセスを使用します。 共有サービスは、複数のユーザー プロセスを使用できる共有サーバー プロセスを使用します。 既定値は**専用**です。|  
  
##  <a name="BKMK_OraCreds"></a>Oracle 資格情報と接続 URI  
 既定では、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle 資格情報が接続 URI で指定した場合は例外をスローします。 これは、これらの資格情報は、接続 URI にプレーン テキストとして表されます。 セキュリティ上のリスクを伴いますこのためです。 設定することができます、 **AcceptCredentialsInUri**接続 URI は、Oracle データベースの資格情報を含めることができるかどうか、プロパティをコントロールにバインドします。 場合、 **AcceptCredentialsInUri**プロパティは**false**、これは、既定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]プロパティがの場合、接続URIにOracle資格情報が含まれている場合に例外をスロー**true**例外はスローされません。  
  
> [!IMPORTANT]
>  プレーン テキストとしての文字列に資格情報を渡すことによってもたらされるセキュリティ リスクのため、接続 URI の Oracle データベース接続の資格情報を指定することを避ける必要があります。 安全に Oracle データベースの資格情報を提供する方法の詳細については、次を参照してください。 [Oracle EBS アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)です。  
  
 また、データベースの資格情報または Oracle E-business Suite への接続を確立するための Oracle E-business Suite の資格情報を指定することもできます。 アダプターはこの動作を有効にする 3 つのバインド プロパティを公開: **ClientCredentialType**、 **OracleUserName**、 **OraclePassword**です。  
  
 値は、使用可能な**ClientCredentialType**プロパティのバインドは、**データベース**と**EBusiness**です。  
  
-   場合、 **ClientCredentialType**プロパティに設定されている**データベース**クライアントは、データベースの資格情報を指定する必要があります。  
  
-   場合、 **ClientCredentialType**プロパティに設定されている**EBusiness**クライアントは、Oracle E-business Suite の資格情報を指定する必要があります。 この場合、アダプターのクライアントで必要がありますのデータベース資格情報を指定も、 **OracleUserName**と**OraclePassword**プロパティをバインドします。  
  
> [!IMPORTANT]
>  アダプターのクライアントが設定して、Oracle E-business Suite に接続するデータベースの資格情報を指定するシナリオで、 **ClientCredentialType**にプロパティのバインド**データベース**Oracle の呼び出しが、E-business Suite の成果物の値が指定された**OracleUserName**と**OraclePassword**アプリケーション コンテキストを設定するためのバインドのプロパティを使用します。 Oracle E-business Suite での成果物を呼び出すために必須では、アプリケーションのコンテキストを設定できます。 アプリケーション コンテキストの設定の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
## <a name="using-reserved-characters-in-the-connection-uri"></a>接続 URI で予約された文字の使用  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]パラメーター値のいずれかの特殊文字が含まれている URI の接続の指定をサポートしていません。 接続パラメーター値に特殊文字が含まれている場合は、次のいずれかの操作を確認します。  
  
-   内の URI を指定する場合は[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、として指定する必要があります-では、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。 直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
-   送信の作成中に URI を指定する、または、受信ポートのかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール、および接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
## <a name="using-the-connection-uri-to-connect-to-oracle-e-business-suite"></a>Oracle E-business Suite に接続する接続 URI を使用します。  
 接続 URI の例を次に示しますの[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]tnsnames.ora を使用します。  
  
```  
oracleebs://ADAPTER  
```  
  
 この例では、アダプターは、tnsnames.ora でターゲットの Oracle データベースのサービス名と接続情報に関連付けられている net サービス名です。  
  
 接続 URI の例を次に示しますの[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]tnsnames.ora を使用せずします。  
  
```  
oracleebs://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated  
```  
  
 この例では、サーバー名が"yourOracleServer"にあり、サービス名は"yourOracleDatabaseServiceName"です。  
  
 Oracle E-business Suite への接続を確立する方法についてはときにします。  
  
-   使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)です。  
  
-   送信ポートを構成するか、受信ポート (場所) で、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[Oracle E-business アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [Oracle クライアント E-business Suite アダプターを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md)   
 [Windows 認証を使用して Oracle E-business Suite への接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)  
 [Oracle E-business Suite への接続を作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)