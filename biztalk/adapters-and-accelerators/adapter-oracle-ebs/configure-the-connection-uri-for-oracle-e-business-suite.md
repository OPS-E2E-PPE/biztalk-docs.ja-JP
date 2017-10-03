---
title: "For Oracle E-business Suite 接続 URI の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2bb02b4-4ad6-4b07-b48a-8f9a47967ffc
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cf8f0e81c7330b469070efb7457f22d1fed790d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-connection-uri-for-oracle-e-business-suite"></a>For Oracle E-business Suite 接続 URI の構成します。
接続 URI は、Oracle E-business Suite への接続に必要なパラメーターを含む接続文字列です。 使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]で[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する Oracle E-business Suite への接続に URI を指定する必要があります。 使用して、オーケストレーションの構成中に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、操作を実行する Oracle E-business Suite への接続に URI を指定する必要があります。  
  
## <a name="specifying-the-connection-uri-from-visual-studio"></a>接続を Visual Studio から URI を指定します。  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、接続 URI を使用して、指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。  
  
#### <a name="to-specify-the-connection-uri-using-consume-adapter-service-add-in"></a>接続 アダプター サービスのアドインを使用して URI を指定するには  
  
1.  BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|をクリックして**アダプター サービスの使用**です。|  
    |**[テンプレート]**|をクリックして**アダプター サービスの使用**です。|  
  
3.  開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。  
  
4.  **アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleEBSBinding**、クリックして**構成**.  
  
5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。**クライアント資格情報の種類**一覧で、 **Username**ユーザー名および Oracle E-business Suite への接続にパスワードを指定します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
    |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
    |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
    |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
6.  クリックして、 **URI プロパティ**タブをクリックし、他のパラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[for Oracle E-business Suite 接続 URI を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)です。  
  
7.  をクリックして、**バインド プロパティ**タブをクリックし、バインディングの値を指定、存在する場合、スキーマを生成する前に必要とします。 バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
8.  **[OK]**をクリックします。  
  
#### <a name="to-specify-the-connection-uri-using-add-adapter-metadata-wizard"></a>アダプター メタデータの追加ウィザードを使用して、URI の接続を指定するには  
  
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
  
7.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。**クライアント資格情報の種類**一覧で、 **Username**ユーザー名および Oracle E-business Suite への接続にパスワードを指定します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
    |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
    |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
    |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
8.  クリックして、 **URI プロパティ**タブをクリックし、他のパラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[for Oracle E-business Suite 接続 URI を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)です。  
  
9. をクリックして、**バインド プロパティ**タブをクリックし、バインディングの値を指定、存在する場合、スキーマを生成する前に必要とします。 バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
    > [!NOTE]
    >  既存の選択した場合は、Wcf-oracleebs 送信ポートをバインドのプロパティを指定する必要があります。 バインドのプロパティは、送信ポートの構成から取得されます。 ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。 このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。 ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。  
  
10. **[OK]**をクリックします。  
  
## <a name="specifying-the-connection-uri-from-the-biztalk-server-administration-console"></a>接続を BizTalk Server 管理コンソールから URI を指定します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracleebs ポートの構成の一部として、接続 URI を指定する必要があります。  
  
#### <a name="to-specify-the-connection-uri-for-the-wcf-custom-port"></a>WCF カスタム ポートの接続 URI を指定するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
3.  ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
4.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
5.  **アドレス (URI)**テキスト ボックスで、接続の Oracle E-business Suite への接続に URI を指定します。 詳細については、接続 URI の[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[for Oracle E-business Suite 接続 URI を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)です。  
  
6.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。**バインディングの種類**ドロップダウン リストで、 **oracleEBSBinding**です。  
  
7.  送信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスをクリックして、**資格情報**タブをクリックし、次のいずれかの操作します。  
  
    -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
        |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
        |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
        |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
    -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
8.  受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブをクリックし、次のいずれかの操作します。  
  
    -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
        |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
        |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
        |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
    -   選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
9. **[OK]**をクリックします。  
  
#### <a name="to-specify-the-connection-uri-for-the-wcf-oracleebs-port"></a>Wcf-oracleebs ポートの接続 URI を指定するには  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  
  
4.  ポートのプロパティ ダイアログ ボックスから、**型**一覧から、以前に追加しをクリックし、選択、Wcf-oracleebs アダプター**構成**です。  
  
    > [!NOTE]
    >  受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。  
  
5.  トランスポートのプロパティ ダイアログ ボックスをクリックして、**全般**タブです。  
  
6.  クリックして、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[for Oracle E-business Suite 接続 URI を構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)です。  
  
7.  トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブし、バインドのプロパティの値を指定します。  
  
    > [!NOTE]
    >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。 たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。  
  
8.  トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合にクリックして、**資格情報**タブをクリックし、次のいずれかの操作します。  
  
    -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
        |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
        |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
        |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
    -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
9. トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作します。  
  
    -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**Oracle データベースの資格情報を使用して接続するには**|指定、 **ClientCredentialType**にプロパティのバインド**データベース**データベース資格情報を指定して**ユーザー名**と**パスワード**テキスト ボックス。|  
        |**Oracle E-business Suite の資格情報を使用して接続するには**|指定して、 **ClientCredentialType**にプロパティのバインド**EBusiness**用 Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 この場合は、Oracle データベースの資格情報を指定する必要がありますも**OracleUserName**と**OraclePassword**プロパティをバインドします。|  
        |**ClientCredentialType が"Database"に設定されている場合は、Windows 認証を使用して接続するには**|「/」を指定して、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。|  
        |**ClientCredentialType が"EBusiness"に設定されている場合は、Windows 認証を使用して接続するには**|Oracle E-business Suite の資格情報を指定**ユーザー名**と**パスワード**テキスト ボックス。 「/」を指定することも必要があります、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。|  
  
    -   選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
10. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)   
 [Windows 認証を使用して Oracle E-business Suite に接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)