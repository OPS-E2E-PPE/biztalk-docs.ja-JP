---
title: SAP システム接続 URI の作成 |Microsoft Docs
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
ms.openlocfilehash: a1a54dc12b4bca6418cea1ea4ae63c6c63dcba6e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969491"
---
# <a name="create-the-sap-system-connection-uri"></a>SAP システム接続 URI を作成します。
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]接続 URI には、アダプターが SAP システムへの接続を確立するために使用するプロパティが含まれています。  

> [!IMPORTANT]
>  既定では、SAP クライアント ライブラリ (librfc32u.dll) では、SAP システムに 100 個の接続の最大数をサポートしています。 この接続の数を超過した場合、例外がスローされます。 ため、設定する必要があります、 **MaxConnectionsPerSystem**接続の数を制限するプロパティをバインドする、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は SAP システムを開くか、CPIC_MAX_CONV の環境変数を設定しようSAP クライアント ライブラリによってサポートされる接続の数を増やします。 CPIC_MAX_CONV を変更する場合は、変更を反映するためコンピューターを再起動する必要があります。 詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  

 このトピックでは、SAP 接続 URI に関する情報を提供し、さまざまなプログラミング シナリオでの接続 URI を指定する方法を説明するその他のトピックへのリンクもあります。  

## <a name="connection-uri-for-the-sap-adapter"></a>SAP アダプターの接続 URI  
 一般的な[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]エンドポイント アドレスの URI は次のように表されます。  

```  
scheme://userinfoparams@hostinfoparams?query_string  
```  

 エンドポイント アドレス URI には、次のコンポーネントが含まれています。  

- スキームは、スキームの名前です。  

- userinfoparams は、ユーザーの認証エンドポイントによって必要なパラメーターの名前と値のコレクションです。  

- hostinfoparams はホストへの接続を確立するために必要な情報は、します。たとえば、パスです。  

- クエリ文字列は、疑問符 (?) で区切られたパラメーターのオプションの名前と値のコレクションです。  

  エンドポイント アドレス URI を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP 接続 URI を使用して SAP システムの使用方法を指定します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]この接続の URI を次のように実装します。  

```  
sap://user=[USER_NAME];passwd=[PASSWORD];Client=[CLIENT];lang=[LANGUAGE];[UseSnc]=[True|False]@connectiontype/conndetail1/conndetail2?GwHost=[GWHOST]?GwServ=[GWSERV]?MsServ=[MSSERV]?Group=[GROUP]?ListenerDest=[LISTENERDEST]?ListenerGwHost=[LISTENERGWHOST]?ListenerGwServ=[LISTENERGWSERV]?ListenerProgramId=[LISTENERPROGRAMID]?RfcSdkTrace=[true/false]?AbapDebug=[true/false]  
```  

 接続 URI のコンポーネントは、次のセクションについて説明します。  

### <a name="the-sap-connection-uri-scheme"></a>SAP 接続 URI スキーム  
 SAP 接続 URI のスキームは、"sap"です。  

### <a name="user-information-in-the-sap-connection-uri"></a>SAP 接続 URI のユーザー情報  
 URI は、ユーザー認証、クライアント id、および言語仕様に必要なパラメーターの名前と値のコレクションとして表されます。 SAP 接続にユーザー情報 (userinfoparams)。 次の表では、これらのパラメーターについて説明します。  


| プロパティ |                                                                                                                                                                                                                                                                                                                                                                                                          説明                                                                                                                                                                                                                                                                                                                                                                                                          |
|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   ユーザー   |                                                                                                                                                                                                            SAP システムのユーザー名この値は大文字小文字を区別します。 設定する必要があります、 **AcceptCredentialsInUri**プロパティをバインド**true**接続 URI のユーザー名とパスワードを指定します。 **注:** 、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]上の SAP システムの接続を開くときにユーザー名を入力する値の大文字小文字を保持します。                                                                                                                                                                                                             |
|  Passwd  |                                                                                                                                                                                                       SAP システムのユーザーのパスワードこの値は大文字小文字を区別します。 設定する必要があります、 **AcceptCredentialsInUri**プロパティをバインド**true**接続 URI のユーザー名とパスワードを指定します。 **注:** 、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]上の SAP システムの接続を開くときにパスワードを入力する値の大文字小文字を保持します。                                                                                                                                                                                                       |
|  クライアント  |                                                                                                                                                                                                                                                                                                                                                                                                   SAP システムのクライアント id。                                                                                                                                                                                                                                                                                                                                                                                                   |
| [言語] |                                                                                                                                                                                                                                                                                                                                                                                                           言語。                                                                                                                                                                                                                                                                                                                                                                                                           |
|  UseSnc  | SAP セキュリティで保護されたネットワーク通信 (SNC) が有効になっているかどうかを指定する省略可能なパラメーター。 値は True または False です。True の場合、SNC が有効にします。 既定値は False<br /><br /> 設定する必要がある SNC を有効にすると、 **SncPartnerName**と**SncLibrary**プロパティをバインドします。 詳細については、[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。<br /><br /> SNC が有効になっている接続の URI には、資格情報が含まれている場合は、アダプターは例外をスローします。 **注:** UseSnc 接続パラメーターは、A と B の接続の種類に対してのみ適用異なる接続の種類とその重要性については、このトピックの後半で詳しく説明します。 |

> [!NOTE]
>  SAP 接続 URI では、クライアントと言語を指定する必要があります。  

 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェス、 **AcceptCredentialsinUri**接続 URI で SAP システムの資格情報を指定できるかどうかを制御できるように、プロパティをバインドします。 資格情報はプレーン テキストで、接続 URI として表され、固有のセキュリティ リスクが生じないためにです。 既定で、 **AcceptCredentialsInUri**バインド プロパティが false と資格情報が接続 URI で指定されている場合、アダプターが例外をスローします。  

 一部のシナリオは、接続 URI; で資格情報を指定する必要があります。たとえば、SAP から受信操作を受信する WCF を使用すると、システム サービス モデルまたは WCF チャネル モデル。 設定することができます、 **AcceptCredentialsInUri**プロパティをこれらのシナリオを true にします。 ベスト プラクティスは、接続 URI で直接資格情報を提供することを回避するためにただし、これは。 SAP 接続の資格情報をより安全に提供する方法の詳細については、[SAP アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)を参照してください。  

> [!IMPORTANT]
>  UseSnc パラメーターを true に設定してセキュリティで保護されたネットワーク通信 (SNC) を有効にした場合、アダプターは例外をスローします。  

### <a name="host-information-in-the-sap-connection-uri"></a>SAP 接続 URI のホスト情報  
 SAP ホスト情報 (hostinfoparams) は、SAP 接続 URI では、次の要素によって表される:`connectiontype/conndetail1/conndetail2`します。 これらのパラメーターは、SAP システムへのクライアント接続に関する詳細を指定します。 SAP クライアントの接続に関する追加情報と SAP RFC 転送先にリスナーとしての接続を確立するための詳細は、クエリ文字列で指定できます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP 接続 URI で次のクライアント接続の種類をサポートしています。  

- A: 使用して、アプリケーション ホスト ベース接続を使用して、アプリケーション サーバーを指定する接続 URI、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP に接続します。  

- B:、負荷分散された接続の接続 URI が経由するメッセージ サーバーを指定します、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP に接続します。  

- D: SAP 用の接続パラメーターを含む saprfc.ini ファイルの宛先を指定する接続 URI をを先ベースの接続。  

  > [!NOTE]
  > 接続タイプ B は、送信ポートにのみ適用されます。  受信場所を構成する場合は、接続の種類、または D. を選択します。

  次の表では、SAP 接続 URI でこれらの接続を指定する方法について説明します。  

|[接続の種類]|Conndetail1|Conndetail2|説明|  
|---------------------|-----------------|-----------------|-----------------|  
|A|ASHOST (アプリケーション サーバーのホスト)|SYSNR (SAP システム数)|アプリケーションのホスト ベース接続を指定します。 アプリケーションのホスト ベース接続オプションのゲートウェイ ホストとゲートウェイ サービス、query_string で指定することができます。|  
|B|MSHOST (メッセージ サーバー ホスト)|R3NAME (SAP R3 名)|負荷分散のメッセージ サーバー経由の接続を指定します。 接続を分散するロード、省略可能なサーバー グループとメッセージ サービス、query_string で指定することができます。|  
|D|DEST (Destination saprfc.ini ファイルの接続パラメーターが含まれています)|--|移行先ベースの接続を指定します。 Saprfc.ini ファイルで指定したコピー先は、SAP 接続パラメーターに格納されます。 マップ先では、A と B の種類の接続のみを指定できます。|  

> [!NOTE]
>  Saprfc.ini ファイルの接続値を指定する場合、ファイルにアクセスした .exe または SAP システムで必要と標準的な場所にある同じフォルダーに保存されていることを確認します。 詳細については、SAP のマニュアルを参照してください。  

### <a name="query-information-in-the-sap-connection-uri"></a>SAP 接続 URI のクエリ情報  
 SAP 接続 URI のクエリ情報 (query_string) には、次の指定を含めることができる省略可能なパラメーターが含まれています。  

- アプリケーションのホスト ベース接続 (A) の追加の接続詳細です。  

- 追加の接続の詳細は、分散接続 (B) を読み込みます。  

- SAP システムが、Rfc、Trfc、および Idoc を送信できる SAP システムの RFC 転送先を指定するリスナーの詳細、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  

- SAP セキュリティで保護されたネットワーク通信 (SNC) を有効にするかどうか。  

- デバッグの構成を指定の詳細。  

  クエリ パラメーターは省略可能です。ただしのリスナーの詳細を指定する必要があります、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC サーバーとして機能します。  

  次の表では、クエリ パラメーターについて説明し、SAP 接続の種類が有効なことを示します。  

|       値       | 有効な接続の種類 |                                                                                                                                                                                                                                    説明                                                                                                                                                                                                                                     |
|-------------------|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      GwHost       |           A           |                                                                                                                                                                                              アプリケーションのホスト ベース接続で、省略可能なゲートウェイ ホストの名前を指定します。                                                                                                                                                                                               |
|      GwServ       |           A           |                                                                                                                                                                                             アプリケーションのホスト ベース接続では、省略可能なゲートウェイ サービスの名前を指定します。                                                                                                                                                                                             |
|      MsServ       |           B           |                                                                                                                                                                                                 負荷分散接続では、省略可能なメッセージ サービスの名前を指定します。                                                                                                                                                                                                  |
|       [グループ]       |           B           |                                                                                                                                                                                                 負荷分散接続をアプリケーション サーバーの任意のグループを指定します。                                                                                                                                                                                                 |
|   ListenerDest    |          (R)          |                                                                                                                                                                      Rfc サーバー接続で saprfc.ini ファイルで、省略可能な変換先を指定します。 変換先は、接続を R 型を指定する必要があります。                                                                                                                                                                      |
|  ListenerGwHost   |          (R)          |                                                                                      Rfc サーバー接続のゲートウェイ ホストを指定します。 このパラメーターは省略可能です。ただし、場合 LISTENERDEST が指定されていない、saprfc.ini ファイルの変換先でゲートウェイのホストが指定されていない環境、または rfc サーバー接続が必要な場合、LISTENERGWHOST も有効なゲートウェイのホストに含める必要があります。                                                                                      |
|  ListenerGwServ   |          (R)          |                                                                                 Rfc サーバー接続のゲートウェイ サービスを指定します。 このパラメーターは省略可能です。ただし、場合 LISTENERDEST が指定されていない、saprfc.ini ファイルの変換先でゲートウェイ サービスが指定されていない環境、または rfc サーバー接続が必要な場合、LISTENERGWSERV も有効なゲートウェイ サービスに含める必要があります。                                                                                  |
| ListenerProgramId |          (R)          |                                                                                  Rfc サーバー接続のプログラム id を指定します。 このパラメーターは省略可能です。ただし、場合 LISTENERDEST が指定されていない、saprfc.ini ファイルの変換先でゲートウェイ サービスが指定されていない環境、または rfc サーバー接続が必要な場合、LISTENERPROGRAMID も有効なゲートウェイ サービスに含める必要があります。                                                                                   |
|    RfcSdkTrace    |          All          | RFC ライブラリ トレースが有効になっているかどうかを指定する省略可能なパラメーター。 値は True または False です。True の場合は、RFC ライブラリ トレースが有効にします。 既定値は False です。<br /><br /> RfcSdkTrace パラメーターで有効になっているトレースのレベルは、RFC_TRACE 環境変数に依存します。<br /><br /> -RFC_TRACE 存在する、または 0 に設定されていない場合は、最小レベルのトレースが有効にします。<br />-1 または 2 のトレース レベルを上げる RFC_TRACE を設定できます。 |
|     AbapDebug     |          All          |                                                                                             省略可能なパラメーターを指定するかどうかからデバッグを ABAP[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を有効にします。 値は True または False です。True の場合、ABAP デバッグが有効になっています。 既定値は False です。 AbapDebug が True の場合は、SAP GUI が開かれます。                                                                                             |

 クエリ文字列パラメーターは、SAP パラメーターとその値は、SAP によって定義されます。 これらのパラメーターの詳細については、SAP のマニュアルを参照してください。  

 アプリケーションのホスト ベース接続のサンプルの接続 URI を次に示します。  

```  
sap://Client=800;lang=EN@A/YourSAPHOST/00  
```  

## <a name="connection-uri-properties-in-the-configure-adapter-dialog-box"></a>接続 URI のプロパティで、アダプターのダイアログ ボックスの構成  
 使用して SAP システムに接続する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]接続からの URI パラメーターを設定する、 **URI プロパティ** タブで、**アダプターの構成** ダイアログ ボックス。 次の表に、URI のプロパティを表示する方法、 **URI プロパティ**シート。 (URI のプロパティは、URI のプロパティ シートに表示される順序でグループを一覧表示されます)。  

|カテゴリ|URI プロパティ|URI の一部|  
|--------------|------------------|--------------|  
|アプリケーション サーバー|アプリケーション サーバーのホスト|Conndetail1 (ホスト A の種類の情報の接続)|  
|アプリケーション サーバー|ゲートウェイ ホスト|GwHost (クエリ文字列)|  
|アプリケーション サーバー|ゲートウェイ サービス|GwServ (クエリ文字列)|  
|アプリケーション サーバー|システム番号|Conndetail2 (ホスト A の種類の情報の接続)|  
|[Destination]|宛先名|Conndetail1 (ホスト情報の接続の種類 D)|  
|診断|RFC トレース|RfcSdkTrace (クエリ文字列)|  
|診断|ABAP デバッグ|AbapDebug (クエリ文字列)|  
|ログイン情報|クライアント|クライアント (userinfoparams)|  
|ログイン情報|[言語]|言語 (userinfoparams)|  
|メッセージ サーバー|アプリケーション サーバー グループ名|グループ (クエリ文字列)|  
|メッセージ サーバー|メッセージ サーバー ホスト|Conndetail1 (ホスト情報の接続の種類 B)|  
|メッセージ サーバー|メッセージ サーバー サービス|MsServ (クエリ文字列)|  
|メッセージ サーバー|R/3 システム名|Conndetail2 (ホスト情報の接続の種類 B)|  
|その他|[接続の種類]|接続の種類 (ホスト情報: A、B、または D)|  
|RFC サーバー|宛先名|ListenerDest (クエリ文字列)|  
|RFC サーバー|ゲートウェイ ホスト|ListenerGwHost (クエリ文字列)|  
|RFC サーバー|ゲートウェイ サービス|ListenerGwServ (クエリ文字列)|  
|RFC サーバー|プログラム Id|ListenerProgramId (クエリ文字列)|  
|SNC|UseSnc|UseSnc (ユーザー情報)|  

## <a name="how-to-specify-a-connection-uri-for-rfc-server-connections"></a>RFC サーバー接続の接続 URI を指定する方法。  
 使用されるエンドポイント アドレスを作成する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC サーバーとして機能する、SAP プログラム id、SAP ゲートウェイ ホスト、および SAP システムの RFC 転送先に対応する SAP ゲートウェイ サービスを指定する必要があります。 SAP で RFC 転送先をセットアップする方法については、[RFC を作成する、RFC 転送先、および送信 SAP から RFC](creating-an-rfc-in-an-sap-system.md)を参照してください。  

 接続で 2 つの方法のいずれかの URI では、プログラム id、ゲートウェイ ホスト、およびゲートウェイ サービスを指定できます。  

-   ListenerGwHost、ListenerGwServ、および ListenerProgramId クエリ パラメーターを設定  

-   saprfc.ini ファイルの宛先へ ListenerDest クエリ パラメーターを設定して、R の種類の接続を指定します。  

> [!NOTE]
>  Saprfc.ini ファイルの接続値を指定する場合、ファイルにアクセスした .exe と同じ場所にある、または SAP システムで必要とする標準の場所にファイルが存在することを確認します。 詳細については、SAP のマニュアルを参照してください。  

 RFC サーバー接続の接続 URI を指定するには、次の例のように、クエリ文字列で指定された RFC 転送先で通常のクライアント接続を指定します。  

```  
sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
```  

 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接続 URI の userinfoparams と hostinfoparams の一部に含まれる情報を使用して、SAP システムからメタデータを取得し、として自身を登録するリスナーのクエリ文字列パラメーターによって提供される情報を使用して、SAP RFC 転送先にリスナー。  

## <a name="using-reserved-characters-in-the-connection-uri"></a>接続 URI の予約文字の使用  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接続パラメーター値のいずれかの特殊文字を含む URI を指定することはできません。 接続パラメーターの値に特殊文字が含まれている場合は、次のいずれかの操作を確認します。  

- URI を指定する場合は[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、として指定する必要があります-では、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せず。 直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  

- 送信の作成中に、URI を指定する、または、受信ポートのかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール、および接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  

## <a name="using-the-connection-uri-to-connect-to-the-sap-system"></a>SAP システムに接続する接続 URI を使用します。  
 SAP システムへの接続を確立する方法についてはときにします。  

- 使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)します。  

- 送信ポートを構成または受信ポート (場所) で、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)します。  

- プログラミング ソリューションで WCF チャネル モデルを使用して、参照してください[SAP を使用してチャネルを作成](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)です。  

- プログラミング ソリューションで WCF サービス モデルを使用して、参照してください[のバインド、SAP システムのクライアントを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)します。  

- 使用して WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を参照してください[ServiceModel メタデータ ユーティリティ ツールを BizTalk adapter for mySAP Business Suite を使用して](../../adapters-and-accelerators/adapter-sap/use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md)します。  

## <a name="see-also"></a>参照  
 [SAP システムへの接続を作成する](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)