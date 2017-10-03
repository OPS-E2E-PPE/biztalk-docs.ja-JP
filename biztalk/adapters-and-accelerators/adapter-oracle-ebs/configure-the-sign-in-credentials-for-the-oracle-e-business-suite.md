---
title: "Oracle E-business Suite のサインイン資格情報の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 743ced51-706b-4788-b5a8-e0ed8ffb3b48
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acbfc92f962982292b8db73ff225dbe6699a16f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-sign-in-credentials-for-the-oracle-e-business-suite"></a>Oracle E-business Suite のサインイン資格情報を構成します。
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアント クライアントの資格情報を提供する必要があります。 アダプターは、Oracle E-business Suite でユーザーを認証して、接続を確立するために、これらの資格情報を使用します。  
  
 アダプターのクライアントがクライアント資格情報を両方を使用する場合を提供することができます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用する場合と、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する資格情報が必要です。 使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、資格情報が Oracle E-business Suite で操作を実行するために必要です。  
  
> [!IMPORTANT]
>  Oracle E-business Suite または基になる Oracle データベースの資格情報を指定できます。 接続し、メタデータを生成するには、すべての資格情報を指定できます。 ただし、Oracle E-business Suite の成果物を起動するための操作を実行中に、呼び出し先の Oracle E-business Suite アプリケーションのアプリケーション コンテキストを設定する必要があるため Oracle E-business Suite 資格情報を指定する必要があります。 アプリケーション コンテキストの設定に関する詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
 このセクションでクライアントの資格情報を指定することに関する情報が[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
## <a name="specifying-credentials-from-visual-studio"></a>Visual Studio からの資格情報の指定  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
#### <a name="to-specify-credentials-using-consume-adapter-service-add-in"></a>アダプター サービスのアドインを使用して資格情報を指定するには  
  
1.  BizTalk プロジェクトを右クリックし **生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
    |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
3.  開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。  
  
4.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleEBSBinding**、クリックして**構成**.  
  
5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**] タブとの間、**クライアント資格情報の種類**一覧で、[ **Username**とユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
    |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
    |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
    |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
6.  **[OK]**をクリックします。  
  
#### <a name="to-specify-credentials-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用して資格情報を指定するには  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプターを追加**です。|  
    |**[テンプレート]**|をクリックして**アダプター メタデータの追加**です。|  
  
3.  **[追加]**をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  
  
4.  [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] **Wcf-oracleebs**です。 BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。  
  
    > [!IMPORTANT]
    >  BizTalk で構成された Wcf-oracleebs ポートがある場合は、ポートの一覧から、ポートを選択します。  
  
5.  **[次へ]**をクリックします。  
  
6.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleEBSBinding**、クリックして**構成**.  
  
7.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**] タブとの間、**クライアント資格情報の種類**一覧で、[ **Username**とユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
    |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
    |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
    |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
8.  **[OK]**をクリックします。  
  
## <a name="specifying-credentials-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールから資格情報の指定  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracleebs ポートの構成の一部として、資格情報を指定する必要があります。  
  
#### <a name="to-specify-credentials-for-the-wcf-custom-port"></a>WCF カスタム ポートの資格情報を指定するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
4.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。**バインディングの種類**ドロップダウン リストで、 **oracleEBSBinding**です。  
  
5.  送信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスをクリックして、**資格情報**タブをクリックし、次のいずれかの操作します。  
  
    -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
        |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
        |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
        |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
    -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
6.  受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブをクリックし、次のいずれかの操作します。  
  
    -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
        |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
        |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
        |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
    -   選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
7.  **[OK]**をクリックします。  
  
#### <a name="to-specify-credentials-for-the-wcf-oracleebs-port"></a>Wcf-oracleebs ポート用の資格情報を指定するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-oracleebs**、クリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
5.  ポートのプロパティ ダイアログ ボックスをクリックして、**バインド**タブです。**バインディングの種類**ドロップダウン リストで、 **oracleEBSBinding**です。  
  
6.  トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合にクリックして、**資格情報**タブをクリックし、次のいずれかの操作します。  
  
    -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
        |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
        |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
        |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
    -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
7.  トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作します。  
  
    -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
        |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
        |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
        |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
    -   選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
8.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)   
 [Windows 認証を使用して Oracle E-business Suite に接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)