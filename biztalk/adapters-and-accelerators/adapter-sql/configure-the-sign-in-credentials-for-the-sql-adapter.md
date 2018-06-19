---
title: SQL アダプタの資格情報 で、サインオンの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c20e177-0e64-4df3-a3dd-dca3fcf314db
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f07a3840524988e5f643ca89799b7c7f23ff0fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226242"
---
# <a name="configure-the-sign-in-credentials-for-the-sql-adapter"></a>SQL アダプタの資格情報 で、サインオンを構成します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアント クライアントの資格情報を提供する必要があります。 アダプターは、SQL Server でユーザーを認証し、接続を確立するために、これらの資格情報を使用します。  
  
 アダプターのクライアントがクライアント資格情報を両方を使用する場合を提供することができます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用する場合と、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する資格情報が必要です。 使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、資格情報が SQL Server で操作を実行するために必要です。  
  
 このセクションでクライアントの資格情報を指定することに関する情報が[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
## <a name="enter-credentials-from-visual-studio"></a>Visual Studio からの資格情報を入力してください。  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して資格情報を指定することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
### <a name="using-consume-adapter-service-add-in"></a>使用してアダプターを使用する追加のサービス  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、し、**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
    |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
3.  開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。  
  
4.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sqlBinding**、順にクリック**構成**です。  
  
5.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ボックスの一覧で、次のいずれかの操作します。  
  
    > [!NOTE]
    >  SQL server で記録される Windows ユーザーを追加する必要があります Windows 認証を使用して SQL Server に接続する場合」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    |このボタンをクリックします。|目的|  
    |----------------|----------------|  
    |**なし**|Windows 認証を使用して SQL Server に接続します。|  
    |**Windows**|Windows 認証を使用して SQL Server に接続します。|  
    |**ユーザー名**|ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。 **注:** のままにする場合、**ユーザー名**と**パスワード**フィールドを空白には、アダプターが Windows 認証を使用して SQL Server に接続します。|  
  
6.  **[OK]** をクリックします。  
  
### <a name="using-add-adapter-metadata-wizard"></a>アダプター メタデータのウィザードを使用して追加  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、し、**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプターを追加**です。|  
    |**[テンプレート]**|をクリックして**アダプター メタデータの追加**です。|  
  
3.  **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  
  
4.  アダプターの追加ウィザードで選択**WCF-SQL**です。 BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。  
  
    > [!IMPORTANT]
    >  BizTalk で構成されている WCF SQL ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。  
  
5.  **[次へ]** をクリックします。  
  
6.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sqlBinding**、順にクリック**構成**です。  
  
7.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ボックスの一覧で、次のいずれかの操作します。  
  
    > [!NOTE]
    >  SQL server で記録される Windows ユーザーを追加する必要があります Windows 認証を使用して SQL Server に接続する場合」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    |このボタンをクリックします。|目的|  
    |----------------|----------------|  
    |**なし**|Windows 認証を使用して SQL Server に接続します。|  
    |**Windows**|Windows 認証を使用して SQL Server に接続します。|  
    |**ユーザー名**|ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。 **注:** のままにする場合、**ユーザー名**と**パスワード**フィールドを空白には、アダプターが Windows 認証を使用して SQL Server に接続します。|  
  
8.  **[OK]** をクリックします。  
  
## <a name="enter-credentials-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールから資格情報を入力してください。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または WCF SQL ポートの構成の一部として、資格情報を指定することができます。  
  
### <a name="enter-credentials-for-the-wcf-custom-port"></a>WCF カスタム ポートの資格情報を入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
4.  送信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスをクリックして、**資格情報**タブをクリックし、次のいずれかの操作します。  
  
    -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
        > [!NOTE]
        >  Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。 SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
5.  受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブをクリックし、次のいずれかの操作します。  
  
    -   選択、**ユーザー アカウント**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
        > [!NOTE]
        >  Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。 SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    -   選択、**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
6.  **[OK]** をクリックします。  
  
### <a name="enter-credentials-for-the-wcf-sql-port"></a>WCF SQL ポートの資格情報を入力します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  WCF-SQL アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF-SQL アダプターを選択し、をクリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合にクリックして、**資格情報**タブをクリックし、次のいずれかの操作します。  
  
    -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
        > [!NOTE]
        >  Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。 SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
6.  トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作します。  
  
    -   選択、**ユーザー アカウント**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
        > [!NOTE]
        >  Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。 SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    -   選択、**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
7.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
[SQL アダプタを BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)