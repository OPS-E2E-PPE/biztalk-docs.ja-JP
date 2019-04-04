---
title: SQL アダプターの資格情報で、サインオンの構成 |Microsoft Docs
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
ms.openlocfilehash: 5dbc153e559e60b91f2ccfd04132a102b946505c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977651"
---
# <a name="configure-the-sign-in-credentials-for-the-sql-adapter"></a>SQL アダプターの資格情報で、サインオンを構成します。
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントのクライアント資格情報を提供する必要があります。 アダプターは、SQL Server でユーザーを認証し、接続を確立するために、これらの資格情報を使用します。  

 アダプター クライアントのクライアント資格情報の両方を使用する場合を提供できます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用する場合と、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する資格情報が必要です。 使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、資格情報が SQL Server で操作を実行するために必要です。  

 このセクションで、クライアントの資格情報を指定する方法について説明します[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

## <a name="enter-credentials-from-visual-studio"></a>Visual Studio からの資格情報を入力します。  
 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して資格情報を指定することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。  

### <a name="using-consume-adapter-service-add-in"></a>アダプターを使用してを使用して追加のサービス  

1.  BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。  

2.  **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**カテゴリ**|クリックして**アダプター サービスの使用**します。|  
    |**[テンプレート]**|クリックして**アダプター サービスの使用**します。|  

3.  開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。  

4.  **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sqlBinding**、順にクリックします**構成**します。  

5.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ボックスの一覧で、次のいずれかの操作を行います。  

    > [!NOTE]
    >  」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要があります Windows 認証を使用して SQL Server に接続する場合[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  

    |このボタンをクリックします。|目的|  
    |----------------|----------------|  
    |**なし**|Windows 認証を使用して、SQL Server に接続します。|  
    |**Windows**|Windows 認証を使用して、SQL Server に接続します。|  
    |**ユーザー名**|ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。 **注:** のままにする場合、**ユーザー名**と**パスワード**フィールドを空白、アダプターが Windows 認証を使用して SQL Server に接続します。|  

6.  **[OK]** をクリックします。  

### <a name="using-add-adapter-metadata-wizard"></a>アダプター メタデータのウィザードを使用して追加  

1. BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。  

2. **生成した項目の追加** ダイアログ ボックスで、次の操作を行います。  


   |    プロパティ    |           目的            |
   |----------------|---------------------------------|
   | **カテゴリ** |     クリックして**アダプターを追加**します。      |
   | **[テンプレート]**  | クリックして**アダプター メタデータの追加**します。 |


3. **[追加]** をクリックします。 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。  

4. アダプターの追加ウィザードで選択**WCF-SQL**します。 BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。  

   > [!IMPORTANT]
   >  BizTalk で構成されている WCF SQL ポートが既にあるを場合からポートの選択、**ポート**一覧。  

5. **[次へ]** をクリックします。  

6. **Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sqlBinding**、順にクリックします**構成**します。  

7. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ボックスの一覧で、次のいずれかの操作を行います。  

   > [!NOTE]
   >  」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要があります Windows 認証を使用して SQL Server に接続する場合[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  

   |  このボタンをクリックします。  |                                                                                                                                                               目的                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **なし**   |                                                                                                                                         Windows 認証を使用して、SQL Server に接続します。                                                                                                                                         |
   | **Windows**  |                                                                                                                                         Windows 認証を使用して、SQL Server に接続します。                                                                                                                                         |
   | **ユーザー名** | ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。 **注:** のままにする場合、**ユーザー名**と**パスワード**フィールドを空白、アダプターが Windows 認証を使用して SQL Server に接続します。 |


8. **[OK]** をクリックします。  

## <a name="enter-credentials-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールから資格情報を入力します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または WCF SQL ポートの構成の一部として、資格情報を指定することができます。  

### <a name="enter-credentials-for-the-wcf-custom-port"></a>WCF カスタム ポートの資格情報を入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

3. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

4. 送信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  

   -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と SQL Server に接続するためのパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  

       > [!NOTE]
       >  Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。 」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  

   -   選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  

5. 受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  

   -   選択、**ユーザー アカウント**オプション、およびユーザー名と SQL Server に接続するためのパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  

       > [!NOTE]
       >  Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。 」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  

   -   選択、**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。  

6. **[OK]** をクリックします。  

### <a name="enter-credentials-for-the-wcf-sql-port"></a>WCF SQL ポートの資格情報を入力します。  

1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. WCF-SQL アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、[SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)を参照してください。  

3. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。 右側のウィンドウでは、ポートを作成または既存のポートを選択できます。  

4. ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した WCF-SQL アダプターを選択し、順にクリックします**構成**します。  

   > [!NOTE]
   >  受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。  

5. トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合は、クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  

   -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と SQL Server に接続するためのパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  

       > [!NOTE]
       >  Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。 」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  

   -   選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  

6. トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  

   -   選択、**ユーザー アカウント**オプション、およびユーザー名と SQL Server に接続するためのパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  

       > [!NOTE]
       >  Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。 」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  

   -   選択、**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。  

7. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)