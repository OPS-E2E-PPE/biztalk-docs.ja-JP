---
title: SQL アダプターの接続 URI の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6460b22-48e4-4b7e-b82e-151e7dab1e09
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9959a88f9799730cb60d2b05358f226b31d0f84c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226794"
---
# <a name="configure-the-connection-uri-for-the-sql-adapter"></a>SQL アダプターの接続 URI を構成します。
接続 URI は、SQL Server への接続に必要なパラメーターを含む接続文字列です。 使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]で[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する SQL Server に接続する URI を指定する必要があります。 構成、送信または受信ポートを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、操作を実行する SQL Server に接続する URI を指定する必要があります。  
  
## <a name="enter-the-connection-uri-from-visual-studio"></a>Visual Studio からの接続 URI を入力します。  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、接続 URI を使用して、指定することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
### <a name="use-the-consume-adapter-service-add-in"></a>使用して、アダプターを使用する追加のサービス  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
    |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
3.  開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。  
  
4.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sqlBinding**、順にクリック**構成**です。  
  
5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。**クライアント資格情報の種類**ボックスの一覧で、次のいずれかの操作します。  
  
    > [!NOTE]
    >  SQL server で記録される Windows ユーザーを追加する必要があります Windows 認証を使用して SQL Server に接続する場合」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    |このボタンをクリックします。|目的|  
    |----------------|----------------|  
    |**なし**|Windows 認証を使用して SQL Server に接続します。|  
    |**Windows**|Windows 認証を使用して SQL Server に接続します。|  
    |**ユーザー名**|ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。 **注:** のままにする場合、**ユーザー名**と**パスワード**フィールドを空白には、アダプターが Windows 認証を使用して SQL Server に接続します。|  
  
6.  クリックして、 **URI プロパティ**タブをクリックし、他のパラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI を作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
7.  クリックして、**バインド プロパティ**タブをクリックし、値を指定、バインドのプロパティの場合は、スキーマを生成する前に必要なです。 バインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
8.  **[OK]** をクリックします。  
  
### <a name="use-the-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用します。  
  
1.  BizTalk プロジェクトを右クリックし、**追加**、クリックして**生成した項目の追加**です。  
  
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
  
6.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、順にクリック**構成**.  
  
7.  **アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、次のいずれかの操作。  
  
    > [!NOTE]
    >  SQL server で記録される Windows ユーザーを追加する必要があります Windows 認証を使用して SQL Server に接続する場合」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    |このボタンをクリックします。|目的|  
    |----------------|----------------|  
    |**なし**|Windows 認証を使用して SQL Server に接続します。|  
    |**Windows**|Windows 認証を使用して SQL Server に接続します。|  
    |**ユーザー名**|ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。 **注:** のままにする場合、**ユーザー名**と**パスワード**フィールドを空白には、アダプターが Windows 認証を使用して SQL Server に接続します。|  
  
8.  クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI を作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
9. クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。 バインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
    > [!NOTE]
    >  既存の WCF-SQL 送信ポートを選択した場合、バインドのプロパティを指定する必要はありません。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。 このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。 ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。  
  
10. **[OK]** をクリックします。  
  
## <a name="enter-the-connection-uri-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールから、接続 URI を入力します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または WCF SQL ポートの構成の一部として接続 URI を指定することができます。  
  
### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a>WCF カスタム ポートの接続 URI を入力してください。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
4.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
5.  **アドレス (URI)** テキスト ボックスで、接続の SQL Server に接続する URI を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI を作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
6.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。**バインディングの種類**ドロップダウン リストで、 **sqlBinding**です。  
  
7.  送信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスをクリックして、**資格情報**タブをクリックし、次のいずれかの操作します。  
  
    -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
        > [!NOTE]
        >  Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。 SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
8.  受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブをクリックし、次のいずれかの操作します。  
  
    -   選択**ユーザー アカウント**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
        > [!NOTE]
        >  Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。 SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    -   選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
9. **[OK]** をクリックします。  
  
### <a name="enter-the-connection-uri-for-the-wcf-sql-port"></a>WCF SQL ポートの接続 URI を入力してください。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  WCF-SQL アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF-SQL アダプターを選択し、をクリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスをクリックして、**全般**タブです。  
  
6.  クリックして、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI を作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
7.  トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブし、バインドのプロパティの値を指定します。  
  
    > [!NOTE]
    >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。 たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。  
  
8.  トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合にクリックして、**資格情報**タブをクリックし、次のいずれかの操作します。  
  
    -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
        > [!NOTE]
        >  Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。 SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
9. トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作します。  
  
    -   選択**ユーザー アカウント**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
        > [!NOTE]
        >  Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。 SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
    -   選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
10. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
[SQL アダプタを BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)