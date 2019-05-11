---
title: Biztalk WCF カスタム アダプターと SQL アダプタを使用してポートの構成 |Microsoft Docs
description: 作成 wcf-custom 送信ポートと受信ポートを BizTalk Server で SQL Server のアダプターを使用するには
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
ms.openlocfilehash: dc819e174df8e65ebc65f955d1c563fb958075cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370159"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter"></a>Wcf-custom アダプタと SQL アダプタを使用してポートを構成します。
Wcf-custom 送信を構成し、受信ポートを使用して SQL Server で送信および受信の操作を実行する手順、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。 
  
## <a name="deploy-adapters-to-send-messages-to-sql-server"></a>SQL Server にメッセージを送信アダプターを展開します。  
 使用して SQL Server にメッセージを送信するための Wcf-custom 送信ポートを構成するのには、次の手順を実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。    
 
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
4. 右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類 をポイントし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。  
  
5. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6. **型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
7. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1. をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドで、SQL Server の接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [SQL Server 接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
   2. **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)の各操作のアクションの一覧。 たとえば、SQL Server データベース内のテーブルに対する挿入操作を呼び出すアクションは。  
  
      ```  
      TableOp/Insert/dbo/Employee  
      ```  
  
      > [!NOTE]
      >  従業員は、SQL Server データベース内のテーブルの名前です。  
  
   3. をクリックして、**バインド**] タブとの間、**バインドの種類**一覧で、[ **sqlBinding**します。 によって公開されるさまざまなバインドのプロパティを指定することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 バインド プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
   4. をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  
  
      -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名の指定とパスワードを SQL Server に接続します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
          > [!NOTE]
          >  Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。 」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[SQL アダプターを使用した Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  
  
      -   選択、**使用してシングル サインオン**オプション、し、関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  
  
           BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)します。  
  
   5. 戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。  
  
8. **送信ハンドラー**一覧で、 **BizTalkServerApplication**します。  
  
9. 選択した場合**静的な一方向送信ポート**手順 4 で、送信パイプラインを指定します。 **送信パイプライン**一覧で [xmltransmit] に対応するパイプラインを選択します。  
  
10. 選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプライン。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
11. **[OK]** をクリックします。  
  
## <a name="deploy-adapters-to-receive-messages-from-sql-server"></a>SQL Server からメッセージを受信アダプターを展開します。
 以下を実行するカスタム WCF を構成する手順を使用して SQL Server からメッセージを受信するためのポートの受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
4. 右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、間の通信モード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。  
  
5. **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
6. **受信場所**] タブで [**新規**します。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
7. **受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1.  受信場所の名前を指定します。  
  
   2.  **型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
8. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1. をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドで、SQL Server の接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [SQL Server 接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
   2. をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **sqlBinding**します。 によって公開されるさまざまなバインドのプロパティを指定することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 バインド プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
   3. をクリックして、**動作** タブ、トランザクション分離レベルを設定します。 トランザクション分離レベルを設定する方法についての詳細については、次を参照してください。[トランザクション分離レベルの構成と SQL を使用したトランザクション タイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)します。  
  
   4. をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  
  
      - 選択**ユーザー アカウント**ユーザー名と SQL Server に接続するためのパスワードを指定します。 ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。  
  
        > [!NOTE]
        >  Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。 」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[SQL アダプターを使用した Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。  
  
      - 選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。  
  
         セキュリティの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)します。  
  
   5. 戻ります、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**。  
  
9. **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
10. 選択した場合**一方向の受信ポート**手順 4 で、受信パイプラインを指定します。 **受信パイプライン**一覧で [xmlreceive] に対応するパイプラインを選択します。  
  
11. 選択した場合**要求-応答受信ポート**手順 4 で、指定の送信および受信パイプライン。  
  
    1.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
    2.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
12. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
13. **受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
## <a name="see-also"></a>参照  
[SQL アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)