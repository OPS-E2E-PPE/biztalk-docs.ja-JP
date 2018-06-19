---
title: Biztalk wcf-custom アダプタと SQL アダプタを使用してポートを構成する |Microsoft ドキュメント
description: Wcf-custom 送信を作成し、BizTalk Server で SQL Server のアダプターを使用する受信ポート
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d44d9932-0a5e-4072-a480-2f8dc544ca79
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c2a47cf267bd3316600ad68a241a204090f3da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226034"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter"></a>Wcf-custom アダプタと SQL アダプタを使用してポートを構成します。
Wcf-custom 送信ポートと受信ポートを使用して SQL サーバーの送信および受信の操作を実行する手順、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループまたは BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)です。 
  
## <a name="deploy-adapters-to-send-messages-to-sql-server"></a>SQL Server にメッセージを送信アダプターを展開します。  
 使用して SQL サーバーにメッセージを送信するための Wcf-custom 送信ポートを構成するのには、次の手順を実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。    
 
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
4.  右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類 をポイントし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。  
  
5.  **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6.  **型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
7.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  クリックして、**全般**] タブで、し、[、**アドレス (URI)** フィールドで、SQL Server の接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
    2.  **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)各操作のアクションの一覧についてはします。 たとえば、SQL Server データベース内のテーブルに対する挿入操作を呼び出すアクションは。  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
        > [!NOTE]
        >  従業員は、SQL Server データベース内のテーブルの名前です。  
  
    3.  クリックして、**バインド**] タブとの間、**バインディングの種類**一覧で、[ **sqlBinding**です。 によって公開されている別のバインディング プロパティを指定することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 バインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
    4.  クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  
  
        -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名を指定とパスワードを SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
            > [!NOTE]
            >  Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。 SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[SQL アダプターと Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
        -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
             BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SQL アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)です。  
  
    5.  戻るには、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
8.  **送信ハンドラー**一覧で、 **BizTalkServerApplication**です。  
  
9. 選択した場合**静的な一方向送信ポート**手順 4 で、送信パイプラインを指定します。 **送信パイプライン**一覧で、[xmltransmit] に対応するパイプラインを選択します。  
  
10. 選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプラインです。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
11. **[OK]** をクリックします。  
  
## <a name="deploy-adapters-to-receive-messages-from-sql-server"></a>SQL Server からメッセージを受信アダプターを展開します。
 次の実行 Wcf-custom を構成する手順を使用して SQL サーバーからメッセージを受信するためのポートの受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
4.  右クリック**受信ポート**、指す**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、間の通信モード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。  
  
5.  **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
6.  **受信場所** タブで、をクリックして**新規**です。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
7.  **受信場所のプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  受信場所の名前を指定します。  
  
    2.  **型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
8.  **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  クリックして、**全般**] タブで、し、[、**アドレス (URI)** フィールドで、SQL Server の接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
    2.  クリックして、**バインド** タブとの間、**バインディングの種類**ドロップダウン リストで、 **sqlBinding**です。 によって公開されている別のバインディング プロパティを指定することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 バインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
    3.  クリックして、**動作**タブは、トランザクション分離レベルを設定します。 トランザクション分離レベルの設定の詳細については、次を参照してください。[トランザクション分離レベルの構成と SQL を使用したトランザクションのタイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)です。  
  
    4.  クリックして、**他**タブをクリックし、次のいずれかの操作します。  
  
        -   選択**ユーザー アカウント**ユーザー名と SQL Server に接続するためのパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
            > [!NOTE]
            >  Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。 SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[SQL アダプターと Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。  
  
        -   選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
             関連するセキュリティの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)です。  
  
    5.  戻るには、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
9. **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。  
  
10. 選択した場合**一方向の受信ポート**手順 4 で、受信パイプラインを指定します。 **受信パイプライン**一覧で、[xmlreceive] に対応するパイプラインを選択します。  
  
11. 選択した場合**要求-応答受信ポート**手順 4 で、指定の送信および受信パイプラインです。  
  
    1.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
    2.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
12. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
13. **受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
[SQL アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)