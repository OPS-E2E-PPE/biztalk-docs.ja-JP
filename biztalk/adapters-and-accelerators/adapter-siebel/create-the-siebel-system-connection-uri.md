---
title: Siebel システム接続 URI を作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI
- connecting to Siebel, using the connection URI
- how to, connect using connection URI
- connecting using connection URI
ms.assetid: 8cc78149-1c20-40db-aece-aab520ee04e7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9370ba739c9edc0fc80c6fa3dcfdfc9d8349c75e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224554"
---
# <a name="create-the-siebel-system-connection-uri"></a>Siebel システム接続 URI を作成します。
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]接続 URI には、アダプターは、Siebel システムへの接続を確立するために使用するプロパティが含まれています。  
  
 このトピックでは、Siebel 接続 URI に関する情報を提供し、その他のさまざまなプログラミング シナリオでの接続 URI を指定する方法を説明するトピックへのリンクも示します。  
  
## <a name="connection-uri-for-the-siebel-adapter"></a>Siebel アダプターの接続 URI  
 一般的な[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]エンドポイント アドレスの URI は次のように表されます。  
  
```  
scheme://userinfoparams@hostinfoparams?query_string  
```  
  
 エンドポイント アドレス URI には、次のコンポーネントが含まれています。  
  
-   スキームは、スキーム名です。  
  
-   userinfoparams はエンドポイントによってユーザー認証に必要なパラメーターの名前と値のコレクションです。  
  
-   hostinfoparams はホストへの接続を確立するために必要な情報たとえば、パスです。  
  
-   query_string は疑問符 (?) で区切られたパラメーターの省略可能な名前と値のコレクションです。  
  
 Siebel 接続 URI は、この一般的な形式に従ってし、は次のように実装されています。  
  
```  
siebel://Username=[USER_NAME];Password=[PASSWORD]@[SERVER]:[PORT]?SiebelObjectManager=[SIEBEL_OBJECT_MANAGER_NAME]&SiebelEnterpriseServer=[SERVER_NAME]&Language=[LANGUAGE]&Transport=[TRANSPORT]&Encryption=[ENCRYPTION]&Compression=[COMPRESSION]&SiebelServer=[SIEBEL_SERVER_NAME]&SiebelRepository=[SIEBEL_REPOSITORY_NAME]  
```  
  
 次のセクションでは、Siebel 接続 URI の各コンポーネントを実装しているプロパティについて説明します。  
  
### <a name="the-scheme-for-the-siebel-connection-uri"></a>Siebel 接続 URI のスキーム  
 Siebel 接続 URI のスキームは、"siebel"です。  
  
### <a name="user-information-in-the-siebel-connection-uri"></a>Siebel 接続 URI 内のユーザー情報  
 既定では、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムの資格情報が接続 URI で指定した場合は例外をスローします。 これは、これらの資格情報がプレーン テキストは、固有のセキュリティ リスクをもたらすとして表されるためです。 設定することができます、 **AcceptCredentialsInUri**接続 URI は、資格情報を含めることができるかどうか、プロパティをコントロールにバインドします。 場合、 **AcceptCredentialsInUri**プロパティは**false**、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]プロパティの場合、接続 URI には、資格情報が含まれている場合に例外をスロー **true**、例外はスローされません。  
  
> [!IMPORTANT]
>  プレーン テキストとしての文字列に資格情報を渡すことによってもたらされる特有のセキュリティ リスクのため、接続 URI の Siebel システムの資格情報を指定しないことはお勧めします。  
  
 接続 URI で指定することがなく Siebel システムの資格情報を指定するいくつかの方法はあります。  
  
-   コードでは、設定することができます、 **ClientCredentials**適切なオブジェクトのプロパティです。  
  
-   使用すると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択して、資格情報を入力することができます、**セキュリティ**のタブ、**アダプターの構成** ダイアログ ボックス。  
  
-   送信ポートを指定または受信場所のバインドにする場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを選択して、資格情報を入力することができます、**セキュリティ**適切なダイアログ ボックスのタブです。  
  
 URI は、ユーザーの認証に必要なパラメーターの名前と値のコレクションとして表されます。 Siebel 接続でユーザー情報 (userinfoparams)。 次の表では、これらのパラメーターについて説明します。  
  
|プロパティ|Description|  
|--------------|-----------------|  
|[ユーザー名]|Siebel システムでのユーザー名この値は大文字小文字を区別します。 設定する必要があります、 **AcceptCredentialsInUri**にプロパティのバインド**true**接続 URI のユーザー名とパスワードを指定します。 **注:** 、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システム上の接続が開くときに、ユーザー名を入力する値の大文字小文字を保持します。|  
|Password|Siebel システムのユーザーのパスワードこの値は大文字小文字を区別します。 設定する必要があります、 **AcceptCredentialsInUri**にプロパティのバインド**true**接続 URI のユーザー名とパスワードを指定します。 **注:** 、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システム上の接続が開くときにパスワードを入力する値の大文字小文字を保持します。|  
  
### <a name="host-information-in-the-siebel-connection-uri"></a>Siebel 接続 URI のホスト情報  
 Siebel のホスト情報 (hostinfoparams) は、次の形式で Siebel システムのアドレスを指定します。 [サーバー]: [PORT] です。 Siebel サーバー バージョンに応じて、Siebel のホスト情報は異なる値を受け取ります。  
  
-   **Siebel 7.5 およびそれ以前のバージョンの**、ホスト情報パラメーターはどの Siebel ゲートウェイ サーバーがインストールされていると、Siebel ゲートウェイのポート番号でコンピューターの名前を取得します。  
  
-   **Siebel 7.7 およびそれ以降のバージョンの**、ホスト情報パラメーターは、コンピューターをサーバーがインストールされている Siebel と Siebel 接続ブローカーのポート番号の名前を取得します。  
  
    > [!IMPORTANT]
    >  使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]Siebel システムに接続するには、"SiebelGateway"接続プロパティのホスト情報が指定する必要があります。  
  
### <a name="query-information-in-the-siebel-connection-uri"></a>Siebel 接続 URI でクエリの情報  
 Siebel 接続 URI のクエリ情報 (query_string) は、追加の接続プロパティを指定する使用されます。  
  
|プロパティ|Description|  
|--------------|-----------------|  
|SiebelObjectManager|エンタープライズ サーバー上の Siebel オブジェクト マネージャーの名前。 このパラメーターは必須です。|  
|SiebelEnterpriseServer|Siebel エンタープライズ サーバーの名前。 このパラメーターは必須です。|  
|言語|オブジェクト マネージャーの言語です。 このパラメーターはオプションです。 指定されていない場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]既定値 (enu) を提供します。|  
|[Transport]|トランスポートです。tcpip のみがサポートされます。 このパラメーターはオプションです。 指定されていない場合、Siebel システムは、既定値 (tcpip) を提供します。|  
|暗号化|間で使用する暗号化の種類、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]と Siebel システムです。 サポートされている値は none、mscrypto、または rsa です。 このパラメーターはオプションです。 指定されていない場合、Siebel システムは、既定値は (なし) を提供します。|  
|Compresssion|間で使用する圧縮アルゴリズム、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]と Siebel システムです。 サポートされている値は、none または zlib です。 このパラメーターはオプションです。 指定されていない場合、Siebel システムは、既定値 (zlib) を提供します。|  
|SiebelServer|Siebel サーバーです。 すべての Siebel 7.5 サーバー接続に必要な (7.5.2、7.5.3 などです。)。それ以外の場合、このパラメーターを設定しません。|  
|SiebelRepository|Siebel リポジトリ。 複数のリポジトリがサーバー上に存在するかどうかに必要なそれ以外の場合、省略可能です。 **注:** サーバーで複数のリポジトリが存在する場合は、SiebelRepository パラメーターで、ターゲットのリポジトリを指定する必要があります。|  
  
 クエリの情報に設定されている Siebel パラメーターの詳細については、Siebel のドキュメントを参照してください。  
  
## <a name="using-reserved-characters-in-the-connection-uri"></a>接続 URI で予約された文字の使用  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]パラメーター値のいずれかの特殊文字が含まれている URI の接続の指定をサポートしていません。 接続パラメーター値に特殊文字が含まれている場合は、次のいずれかの操作を確認します。  
  
-   内の URI を指定する場合は[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、として指定する必要があります-では、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。 直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
-   送信の作成中に URI を指定する、または、受信ポートのかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール、および接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
## <a name="using-the-connection-uri-to-connect-to-the-siebel-system"></a>Siebel システムに接続する接続 URI を使用します。  
 サンプルの Siebel 接続 URI を次に示します。  
  
```  
siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=entserver&Language=enu  
```  
  
> [!NOTE]
>  このサンプル URI にはには、Siebel システムの資格情報が含まれています。設定する必要があります、 **AcceptCredentialsInUri**にプロパティのバインド**true**接続資格情報を含む URI を使用します。  
  
 場合 (接続プロパティの設定を含む)、Siebel システムへの接続を確立する方法については、します。  
  
-   使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[Siebel 操作の Visual Studio でのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)です。  
  
-   送信ポートを構成するか、受信ポート (場所) で、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[Siebel アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)です。
  
-   プログラミング ソリューションで、WCF チャネル モデルを使用して、参照してください[Siebel を使用して、チャネルの作成](../../adapters-and-accelerators/adapter-siebel/create-a-channel-using-siebel.md)です。  
  
-   プログラミング ソリューションで WCF サービス モデルを使用して、参照してください[Siebel システムの WCF クライアントを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)です。  
  
-   使用する WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を参照してください[BizTalk adapter 用 Siebel eBusiness Applications ServiceModel メタデータ ユーティリティ ツールを使用して](../../adapters-and-accelerators/adapter-siebel/use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [Siebel システムへの接続を作成します。](../../adapters-and-accelerators/adapter-siebel/create-a-connection-to-the-siebel-system.md)   
[Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)   
 [WCF チャネル Model3 を使用した Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md)   
 [WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)