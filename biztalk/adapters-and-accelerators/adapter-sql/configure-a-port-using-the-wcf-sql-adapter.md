---
title: WCF-SQL アダプターを使用して biztalk ポートの構成 |Microsoft Docs
description: 作成 WCF-SQL 送信ポートと受信ポートを BizTalk Server で SQL Server のアダプターを使用するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8cdc032-3160-43de-9510-7ca69506083e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6a2484c23d4abf8fbe489c3b2fed3ced25b9313
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992075"
---
# <a name="configure-a-port-using-the-wcf-sql-adapter"></a>WCF-SQL アダプターを使用してポートを構成します。
このトピックでは WCF SQL を構成する方法については送受信ポートを使用して SQL サーバーの送信および受信操作を実行する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。
  
## <a name="deploy-adapters-to-send-messages-to-sql-server"></a>SQL Server にメッセージを送信アダプターを展開します。  
 使用して SQL Server にメッセージを送信するための WCF-SQL 送信ポートを構成するのには、次の手順を実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. WCF-SQL アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、[SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)を参照してください。  
  
3. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
4. 展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
5. 右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類 をポイントし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。  
  
6. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
7. **型**ドロップダウン リストでは、先ほど追加した WCF-SQL アダプターを選択し、順にクリックします**構成**します。  
  
8. トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  
  
   1. をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
   2. **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)の各操作のアクションの一覧。 たとえば、SQL Server データベース内のテーブルに対する挿入操作を呼び出すアクションは。  
  
      ```  
      TableOp/Insert/dbo/Employee  
      ```  
  
      > [!NOTE]
      >  従業員は、SQL Server データベース内のテーブルの名前です。  
  
   3. をクリックして、**バインド** タブでバインドによって公開されるプロパティの値を指定し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 バインド プロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。  
  
      > [!NOTE]
      >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。  
  
   4. をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  
  
      -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名の指定とパスワードを SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
          > [!NOTE]
          >  Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。 」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  
  
      -   選択、**使用してシングル サインオン**オプション、し、関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  
  
           BizTalk Server に関するセキュリティの詳細については、[SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)を参照してください。  
  
   5. 戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。  
  
9. **送信ハンドラー**一覧で、 **BizTalkServerApplication**します。  
  
10. 作成した場合**静的な一方向送信ポート**手順 5 で、送信パイプラインを指定します。 **送信パイプライン**一覧で [xmltransmit] に対応するパイプラインを選択します。  
  
11. 作成した場合**静的な送信請求-応答ポート**手順 5 で、指定の送信および受信パイプライン。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
12. **[OK]** をクリックします。  
  
## <a name="deploy-adapters-to-receive-messages-from-sql-server"></a>SQL Server からメッセージを受信アダプターを展開します。  
 以下を実行する WCF SQL を構成する手順を使用して SQL Server からメッセージを受信するためのポートの受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. WCF-SQL アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、[SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)を参照してください。  
  
3. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
4. 展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
5. 右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、間の通信モード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。  
  
6. **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
7. **受信場所**] タブで [**新規**します。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
8. **受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1.  受信場所の名前を指定します。  
  
   2.  **型**ドロップダウン リストでは、先ほど追加した WCF-SQL アダプターを選択し、順にクリックします**構成**します。  
  
9. トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  
  
   1. をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
   2. をクリックして、**バインド** タブでバインドによって公開されるプロパティの値を指定し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 バインド プロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。  
  
      > [!NOTE]
      >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。  
  
   3. をクリックして、**動作** タブ、トランザクション分離レベルを設定します。 トランザクション分離レベルを設定する方法についての詳細については、[トランザクション分離レベルの構成と SQL を使用したトランザクション タイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)を参照してください。  
  
   4. をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  
  
      - 選択**ユーザー アカウント**ユーザー名と SQL Server に接続するためのパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
        > [!NOTE]
        >  Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。 」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  
  
      - 選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。  
  
         セキュリティの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)します。  
  
   5. 戻ります、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**。  
  
10. **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
11. 作成した場合**一方向の受信ポート**手順 5 で、受信パイプラインを指定します。 **受信パイプライン**一覧で [xmlreceive] に対応するパイプラインを選択します。  
  
12. 作成した場合**要求-応答受信ポート**手順 5 で、指定の送信および受信パイプライン。  
  
    1.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
    2.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
13. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
14. **受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
## <a name="see-also"></a>参照  
[SQL アダプターを物理ポートのバインドを手動で構成します。 ](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)