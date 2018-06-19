---
title: BizTalk の Wcf-oracledb アダプターを使用してポートを構成する |Microsoft ドキュメント
description: Wcf-oracledb 送信を作成し、BizTalk Server で Oracle DB アダプターを使用する受信ポート
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9eafefb-9b30-4801-9be9-6034ae0d3b7d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1e910d3a4d76444495de5ee4e20ada352a7a42b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215874"
---
# <a name="configure-a-port-using-the-wcf-oracledb-adapter"></a>Wcf-oracledb アダプターを使用してポートを構成します。
Wcf-oracledb を構成する方法は、送信し、受信ポートを使用して Oracle データベースの送信および受信操作を実行する、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]です。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループまたは BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)です。 
  
## <a name="deploy-adapters-to-send-messages-to-oracle-database"></a>Oracle データベースにメッセージを送信アダプターを展開します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  Wcf-oracledb アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
4.  展開するアプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
5.  右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類 をポイントし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と Oracle データベース。  
  
6.  **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
7.  **型**ドロップダウン リストが Wcf-oracledb を選択し、クリックして**構成**です。  
  
8.  トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。  
  
    1.  をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
    2.  **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)各操作のアクションの一覧についてはします。 たとえば、Oracle データベースで HR スキーマ EMPLOYEE テーブルの挿入操作を呼び出すアクションは。  
  
        ```  
        http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEE/Select  
        ```  
  
    3.  クリックして、**バインディング**タブによって公開されているバインドのプロパティを指定して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 バインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。
  
        > [!NOTE]
        >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。 たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。  
  
    4.  クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  
  
        -   選択、**シングル サインオンを使用しない**オプション、およびユーザー名と、Oracle データベースへの接続にパスワードを指定します。  
  
            -   Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  
  
            -   Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。  
  
        -   選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。  
  
    5.  戻るには、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
9. **送信ハンドラー**一覧で、 **BizTalkServerApplication**です。  
  
10. 選択した場合**静的な一方向送信ポート**手順 5 で、送信パイプラインを指定します。 **送信パイプライン**一覧で、[xmltransmit] に対応するパイプラインを選択します。  
  
11. 選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプラインです。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
12. **[OK]** をクリックします。  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-database"></a>Oracle データベースからメッセージを受信アダプターを展開します。  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  Wcf-oracledb アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 手順については、次を参照してください。 [BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)です。  
  
3.  コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。  
  
4.  展開するアプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
5.  右クリック**受信ポート**、指す**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、間の通信モード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と Oracle データベース。  
  
6.  **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
7.  **受信場所** タブで、をクリックして**新規**です。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
8.  **受信場所のプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  受信場所の名前を指定します。  
  
    2.  **型**ドロップダウン リストが Wcf-oracledb を選択し、クリックして**構成**です。  
  
9. トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。  
  
    1.  をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
    2.  クリックして、**バインディング**タブによって公開されるプロパティのバインドを指定して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 バインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。
  
        > [!NOTE]
        >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。 たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。  
  
    3.  クリックして、**動作**タブは、トランザクション分離レベルを設定します。 トランザクション分離レベルの設定の詳細については、次を参照してください。[トランザクション分離レベルとトランザクションのタイムアウト構成](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)です。  
  
    4.  クリックして、**他**タブをクリックし、次のいずれかの操作します。  
  
        -   選択**ユーザー アカウント**オプション、およびユーザー名と、Oracle データベースへの接続にパスワードを指定します。  
  
            -   Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  
  
            -   Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。  
  
        -   選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。  
  
    5.  戻るには、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
10. **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。  
  
11. 選択した場合**一方向の受信ポート**手順 5 で、受信パイプラインを指定します。 **受信パイプライン**一覧で、[xmlreceive] に対応するパイプラインを選択します。  
  
12. 選択した場合**要求-応答受信ポート**手順 5 で、指定の送信および受信パイプラインです。  
  
    1.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
    2.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
13. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
14. **受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
   [Oracle データベース アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)
 
 [Windows 認証を使用して Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)