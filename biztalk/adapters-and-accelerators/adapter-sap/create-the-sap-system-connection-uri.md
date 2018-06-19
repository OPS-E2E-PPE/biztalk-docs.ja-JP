---
title: SAP システム接続 URI を作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI
- how to, connect using connection URI
- connecting using connection URI
- connecting to SAP, using the connection URI
ms.assetid: e41ed488-07a7-4fb7-97c0-6d626e041e95
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f9c224eb7a219cf3e5bb81f31ef8382c555295b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22219314"
---
# <a name="create-the-sap-system-connection-uri"></a>SAP システム接続 URI を作成します。
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]接続 URI には、アダプタが SAP システムへの接続を確立するために使用するプロパティが含まれています。  
  
> [!IMPORTANT]
>  既定では、SAP クライアント ライブラリ (librfc32u.dll) では、最大で 100 への接続の SAP システムをサポートしています。 この接続の数を超えた場合、例外がスローされます。 設定するか、このため、必ず、 **MaxConnectionsPerSystem**接続の数を制限するプロパティのバインドを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]が SAP システムで開くか、CPIC_MAX_CONV 環境変数を設定しようSAP クライアント ライブラリによってサポートされる接続の数を増やします。 CPIC_MAX_CONV を変更する場合は、変更を反映するには、コンピューターを再起動する必要があります。 詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
 このトピックでは、SAP 接続 URI に関する情報を提供し、その他のさまざまなプログラミング シナリオでの接続 URI を指定する方法を説明するトピックへのリンクも示します。  
  
## <a name="connection-uri-for-the-sap-adapter"></a>SAP アダプターの接続 URI  
 一般的な[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]エンドポイント アドレスの URI は次のように表されます。  
  
```  
scheme://userinfoparams@hostinfoparams?query_string  
```  
  
 エンドポイント アドレス URI には、次のコンポーネントが含まれています。  
  
-   スキームは、スキーム名です。  
  
-   userinfoparams はエンドポイントによってユーザー認証に必要なパラメーターの名前と値のコレクションです。  
  
-   hostinfoparams はホストへの接続を確立するために必要な情報たとえば、パスです。  
  
-   query_string は疑問符 (?) で区切られたパラメーターの省略可能な名前と値のコレクションです。  
  
 エンドポイント アドレス URI を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP 接続 URI を使用して SAP システムの使用方法を指定します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]この接続 URI を次のように実装します。  
  
```  
sap://user=[USER_NAME];passwd=[PASSWORD];Client=[CLIENT];lang=[LANGUAGE];[UseSnc]=[True|False]@connectiontype/conndetail1/conndetail2?GwHost=[GWHOST]?GwServ=[GWSERV]?MsServ=[MSSERV]?Group=[GROUP]?ListenerDest=[LISTENERDEST]?ListenerGwHost=[LISTENERGWHOST]?ListenerGwServ=[LISTENERGWSERV]?ListenerProgramId=[LISTENERPROGRAMID]?RfcSdkTrace=[true/false]?AbapDebug=[true/false]  
```  
  
 接続 URI のコンポーネントは、次のセクションで説明します。  
  
### <a name="the-sap-connection-uri-scheme"></a>SAP 接続 URI スキーム  
 SAP 接続 URI のスキームは、"sap"です。  
  
### <a name="user-information-in-the-sap-connection-uri"></a>SAP 接続 URI 内のユーザー情報  
 URI は、ユーザー認証、クライアントの識別情報、および言語仕様の必要なパラメーターの名前と値のコレクションとして表されます。 SAP 接続にユーザー情報 (userinfoparams)。 次の表では、これらのパラメーターについて説明します。  
  
|プロパティ|Description|  
|--------------|-----------------|  
|ユーザー|SAP システムでのユーザー名この値は大文字小文字を区別します。 設定する必要があります、 **AcceptCredentialsInUri**にプロパティのバインド**true**接続 URI のユーザー名とパスワードを指定します。 **注:** 、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]が SAP システム上の接続を開くときに、ユーザー名を入力する値の大文字小文字を保持します。|  
|Passwd|SAP システムのユーザーのパスワードこの値は大文字小文字を区別します。 設定する必要があります、 **AcceptCredentialsInUri**にプロパティのバインド**true**接続 URI のユーザー名とパスワードを指定します。 **注:** 、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]が SAP システム上の接続を開くときにパスワードを入力する値の大文字小文字を保持します。|  
|クライアント|SAP システムのクライアント id。|  
|言語|言語。|  
|UseSnc|SAP セキュリティで保護されたネットワーク通信 (SNC) が有効になっているかどうかを示す省略可能なパラメーターです。 値を指定できます True または False です。True の場合、SNC は有効です。 既定値は False<br /><br /> SNC を有効にしたときに設定する必要も、 **SncPartnerName**と**SncLibrary**プロパティをバインドします。 詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。<br /><br /> SNC が有効になっている接続 URI には、資格情報が含まれている場合は、アダプターは、例外をスローします。 **注:** UseSnc 接続パラメーターは、A と B の接続の種類に対してのみ適用接続の種類とその意味については、このトピックの後半で詳しく説明します。|  
  
> [!NOTE]
>  SAP 接続 URI では、クライアントと言語を指定する必要があります。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェス、 **AcceptCredentialsinUri** SAP システムの資格情報を接続 URI で指定できるかどうかを制御するためにプロパティをバインドします。 これは、資格情報がプレーン テキストで、接続 URI として表される固有のセキュリティ リスクを招きますこのためです。 既定では、 **AcceptCredentialsInUri** binding プロパティが false で、資格情報が接続 URI で指定されている場合、アダプターが例外をスローします。  
  
 一部のシナリオは、接続 URI; での資格情報を指定する必要があります。たとえば、SAP から受信操作を受信するため、WCF を使用すると、システム サービス モデルまたは WCF チャネル モデル。 設定することができます、 **AcceptCredentialsInUri**これらのシナリオを true に設定します。 お勧め、ただし、接続 URI 内で直接資格情報を与えることを回避します。 安全に SAP 接続の資格情報を提供する方法の詳細については、次を参照してください。 [、SAP アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)です。  
  
> [!IMPORTANT]
>  UseSnc パラメーターを true に設定してセキュリティで保護されたネットワーク通信 (SNC) を有効にする場合、アダプターは例外をスローします。  
  
### <a name="host-information-in-the-sap-connection-uri"></a>SAP 接続 URI のホスト情報  
 SAP のホスト情報 (hostinfoparams) は、SAP 接続 URI では、次の要素によって表される:`connectiontype/conndetail1/conndetail2`です。 これらのパラメーターは、SAP システムへのクライアント接続に関する詳細を指定します。 SAP クライアント接続に関する追加情報と、SAP RFC 変換先にリスナーとの接続を確立するための詳細は、query_string で指定できます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP 接続 URI で次のクライアント接続の種類をサポートしています。  
  
-   A: アプリケーションのホスト ベース接続の接続 URI が使用するアプリケーション サーバーを指定します、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP に接続します。  
  
-   B:、負荷分散された接続の接続 URI が経由するメッセージ サーバーを指定します、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP に接続します。  
  
-   D: 先ベースの接続、接続 URI が SAP の接続パラメーターを格納している saprfc.ini ファイルの保存先を指定します。  

    > [!NOTE]
    > 接続タイプ B は、送信ポートにのみ適用されます。  受信場所を構成するときに、接続の種類または D. を選択します。
  
 次の表では、SAP 接続 URI にこれらの接続を指定する方法について説明します。  
  
|[接続の種類]|Conndetail1|Conndetail2|Description|  
|---------------------|-----------------|-----------------|-----------------|  
|A|ASHOST (アプリケーション サーバーのホスト)|SYSNR (SAP システム番号)|アプリケーション ホスト ベース接続を指定します。 アプリケーションのホスト ベース接続のオプションのゲートウェイ ホストとゲートウェイ サービスで指定できます、query_string です。|  
|B|MSHOST (メッセージ サーバー ホスト)|R3NAME (SAP R3 名)|負荷分散のメッセージ サーバー経由の接続を指定します。 負荷分散の接続では、省略可能なサーバー グループとサービスのメッセージで指定できます、query_string です。|  
|D|追加先 (宛先 saprfc.ini ファイルの接続パラメーターが含まれています)|--|移行先ベースの接続を指定します。 Saprfc.ini ファイルで指定したコピー先には、SAP 接続パラメーターが含まれています。 マップ先では、A と B の種類の接続のみを指定できます。|  
  
> [!NOTE]
>  Saprfc.ini ファイルの接続の値を指定する場合は、.exe ファイルへのアクセスまたは SAP システムで必要とする標準の場所では、同じフォルダーに保存されていることを確認してください。 詳細については、SAP のマニュアルを参照してください。  
  
### <a name="query-information-in-the-sap-connection-uri"></a>SAP 接続 URI でクエリの情報  
 SAP 接続 URI でクエリの情報 (query_string) には、次の指定に含まれることができる省略可能なパラメーターが含まれています。  
  
-   アプリケーション ホストベースの接続 (A) の追加の接続詳細です。  
  
-   追加の接続の詳細は、分散接続 (B) を読み込みます。  
  
-   SAP システムを使用する Rfc、TRFCs、および Idoc を送信できます SAP システムで、RFC 変換先を指定するリスナーの詳細、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   SAP セキュリティで保護されたネットワーク通信 (SNC) を有効にするかどうか。  
  
-   デバッグ構成を指定の詳細。  
  
 クエリ パラメーターは省略可能です。ただし、リスナーの詳細に指定する必要があります、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC サーバーとして機能します。  
  
 次の表は、クエリ パラメーターについて説明し、SAP 接続の種類は有効なことを示します。  
  
|値|有効な接続の種類|Description|  
|-----------|---------------------------|-----------------|  
|GwHost|A|アプリケーション ホストベースの接続では、省略可能なゲートウェイ ホストの名前を指定します。|  
|GwServ|A|アプリケーション ホストベースの接続では、省略可能なゲートウェイ サービスの名前を指定します。|  
|MsServ|B|負荷分散の接続では、省略可能なメッセージ サービスの名前を指定します。|  
|[グループ]|B|負荷分散の接続でのアプリケーション サーバーの任意のグループを指定します。|  
|ListenerDest|(R)|Rfc サーバー接続で saprfc.ini ファイルで、省略可能な変換先を指定します。 変換先は、R 型接続を指定する必要があります。|  
|ListenerGwHost|(R)|Rfc サーバー接続のゲートウェイ ホストを指定します。 このパラメーターは省略可能です。ただし、rfc サーバー接続が必要な場合と LISTENERDEST が指定されていないまたは saprfc.ini ファイルの変換先でゲートウェイのホストが指定されていない、し LISTENERGWHOST も有効なゲートウェイのホストに含める必要があります。|  
|ListenerGwServ|(R)|Rfc サーバー接続用ゲートウェイ サービスを指定します。 このパラメーターは省略可能です。ただし、rfc サーバー接続が必要な場合と LISTENERDEST が指定されていないまたは saprfc.ini ファイルの変換先でゲートウェイ サービスが指定されていない、し LISTENERGWSERV も有効なゲートウェイ サービスに含める必要があります。|  
|ListenerProgramId|(R)|Rfc サーバー接続のプログラム id を指定します。 このパラメーターは省略可能です。ただし、rfc サーバー接続が必要な場合と LISTENERDEST が指定されていないまたは saprfc.ini ファイルの変換先でゲートウェイ サービスが指定されていない、し LISTENERPROGRAMID も有効なゲートウェイ サービスに含める必要があります。|  
|RfcSdkTrace|すべて|RFC ライブラリ トレースが有効になっているかどうかを示す省略可能なパラメーターです。 値を指定できます True または False です。True の場合は、RFC ライブラリ トレースが有効にします。 既定値は False です。<br /><br /> RfcSdkTrace パラメーターで有効になっているトレースのレベルは、RFC_TRACE 環境変数に依存します。<br /><br /> -RFC_TRACE 存在する、またはしていない場合は 0 に設定、最小レベルのトレースは有効です。<br />-1 または 2 のトレースのレベルを上げる RFC_TRACE を設定できます。|  
|AbapDebug|すべて|省略可能なパラメーターを指定するかどうかからデバッグを ABAP[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を有効にします。 値を指定できます True または False です。True の場合、ABAP デバッグが有効になっています。 既定値は False です。 AbapDebug が True の場合は、SAP GUI が開かれます。|  
  
 クエリ文字列パラメーターは、SAP パラメーターとその値は、SAP によって定義されます。 これらのパラメーターの詳細については、SAP のマニュアルを参照してください。  
  
 アプリケーション ホストベースの接続用のサンプルの接続 URI を次に示します。  
  
```  
sap://Client=800;lang=EN@A/YourSAPHOST/00  
```  
  
## <a name="connection-uri-properties-in-the-configure-adapter-dialog-box"></a>接続 URI のプロパティで、アダプターのダイアログ ボックスを構成します。  
 使用して SAP システムに接続する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]接続からの URI パラメーターを設定する、 **URI プロパティ** タブで、**アダプターの構成** ダイアログ ボックス。 次の表に、URI のプロパティを表示する方法、 **URI プロパティ**シートです。 (URI のプロパティが表示されます、URI のプロパティ シートに表示される順にグループ化します。)  
  
|カテゴリ|URI プロパティ|URI の一部|  
|--------------|------------------|--------------|  
|アプリケーション サーバー|アプリケーション サーバーのホスト|Conndetail1 (A の種類については接続をホストする)|  
|アプリケーション サーバー|ゲートウェイ ホスト|GwHost (クエリ文字列)|  
|アプリケーション サーバー|ゲートウェイ サービス|GwServ (クエリ文字列)|  
|アプリケーション サーバー|システム番号|Conndetail2 (A の種類については接続をホストする)|  
|転送先|移行先の名前|Conndetail1 (ホスト情報接続の種類 D)|  
|診断|RFC トレース|RfcSdkTrace (クエリ文字列)|  
|診断|ABAP デバッグ|AbapDebug (クエリ文字列)|  
|ログイン情報|クライアント|クライアント (userinfoparams)|  
|ログイン情報|言語|言語 (userinfoparams)|  
|メッセージ サーバー|アプリケーション サーバー グループ名|グループ (クエリ文字列)|  
|メッセージ サーバー|メッセージ サーバー ホスト|Conndetail1 (ホスト情報接続タイプ B)|  
|メッセージ サーバー|メッセージ サーバー サービス|MsServ (クエリ文字列)|  
|メッセージ サーバー|R/3 システム名|Conndetail2 (ホスト情報接続タイプ B)|  
|その他|[接続の種類]|接続の種類 (ホスト情報: A、B、または D)|  
|RFC サーバー|移行先の名前|ListenerDest (クエリ文字列)|  
|RFC サーバー|ゲートウェイ ホスト|ListenerGwHost (クエリ文字列)|  
|RFC サーバー|ゲートウェイ サービス|ListenerGwServ (クエリ文字列)|  
|RFC サーバー|プログラム Id|ListenerProgramId (クエリ文字列)|  
|SNC|UseSnc|UseSnc (ユーザーの情報)|  
  
## <a name="how-to-specify-a-connection-uri-for-rfc-server-connections"></a>RFC サーバー接続の接続 URI を指定する方法。  
 使用するエンドポイント アドレスを作成する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC サーバーとして機能できる、SAP プログラム id、SAP ゲートウェイ ホスト、および SAP システムで、RFC 変換先に対応する SAP ゲートウェイ サービスを指定する必要があります。 SAP に、RFC 変換先をセットアップする方法については、次を参照してください。 [Create RFC、RFC 変換先、および送信 SAP RFC](creating-an-rfc-in-an-sap-system.md)です。  
  
 接続で 2 つの方法のいずれかの URI では、プログラム id、ゲートウェイのホスト、およびゲートウェイ サービスを指定できます。  
  
-   ListenerGwHost、ListenerGwServ、および ListenerProgramId クエリ パラメーターを設定  
  
-   saprfc.ini ファイルで送信先へ ListenerDest クエリ パラメーターを設定して、R の種類の接続を指定します。  
  
> [!NOTE]
>  Saprfc.ini ファイルの接続の値を指定する場合、.exe ファイルへのアクセスと同じ場所または SAP システムで必要とする標準の場所にファイルが存在することを確認します。 詳細については、SAP のマニュアルを参照してください。  
  
 RFC サーバー接続の接続 URI を指定するには、次の例のように、クエリ文字列で指定された、RFC 変換先で通常のクライアント接続を指定します。  
  
```  
sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
```  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接続 URI の userinfoparams と hostinfoparams の一部に含まれる情報を使用して SAP システムからメタデータを取得して、クエリ文字列内のリスナーのパラメーターが提供する情報を使用して、自身を登録する、SAP RFC 転送先にリスナー。  
  
## <a name="using-reserved-characters-in-the-connection-uri"></a>接続 URI で予約された文字の使用  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]パラメーター値のいずれかの特殊文字が含まれている URI の接続の指定をサポートしていません。 接続パラメーター値に特殊文字が含まれている場合は、次のいずれかの操作を確認します。  
  
-   内の URI を指定する場合は[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、として指定する必要があります-では、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。 直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
-   送信の作成中に URI を指定する、または、受信ポートのかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール、および接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
## <a name="using-the-connection-uri-to-connect-to-the-sap-system"></a>SAP システムに接続する接続 URI を使用します。  
 SAP システムへの接続を確立する方法についてはときにします。  
  
-   使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)です。  
  
-   送信ポートを構成するか、受信ポート (場所) で、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)です。  
  
-   プログラミング ソリューションで、WCF チャネル モデルを使用して、参照してください[SAP を使用して、チャネルの作成](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)です。  
  
-   プログラミング ソリューションで WCF サービス モデルを使用して、参照してください[クライアントを SAP システムのバインド構成](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)です。  
  
-   使用する WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を参照してください[BizTalk adapter 用 mySAP Business Suite、ServiceModel メタデータ ユーティリティ ツールを使用して](../../adapters-and-accelerators/adapter-sap/use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md)です。  
  
## <a name="see-also"></a>参照  
 [SAP システムへの接続を作成します。](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)