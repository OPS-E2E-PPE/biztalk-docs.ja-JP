---
title: Wcf-oracledb アダプターを使用して biztalk ポートの構成 |Microsoft Docs
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
ms.openlocfilehash: aee5b39d077c48317e557072c54ba032ebe82a24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009179"
---
# <a name="configure-a-port-using-the-wcf-oracledb-adapter"></a>Wcf-oracledb アダプターを使用してポートを構成します。
Wcf-oracledb を構成する方法は、送信し、受信ポートを使って Oracle データベースに送信および受信操作を実行する、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。 
  
## <a name="deploy-adapters-to-send-messages-to-oracle-database"></a>Oracle データベースにメッセージを送信アダプターを展開します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. Wcf-oracledb アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)します。  
  
3. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
4. 展開するアプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
5. 右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類 をポイントし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と Oracle データベース。  
  
6. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
7. **型**ボックスの一覧が Wcf-oracledb を選択し、クリックして**構成**します。  
  
8. トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  
  
   1. をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
   2. **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)の各操作のアクションの一覧。 たとえば、Oracle データベース内の HR スキーマ EMPLOYEE テーブルの挿入操作を呼び出すアクションは。  
  
      ```  
      http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEE/Select  
      ```  
  
   3. をクリックして、**バインド**タブによって公開されるバインドのプロパティを指定して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。
  
      > [!NOTE]
      >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。  
  
   4. をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。  
  
      -   選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Oracle データベースに接続するためのパスワードを指定します。  
  
          -   Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  
  
          -   Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  
  
      -   選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。  
  
   5. 戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。  
  
9. **送信ハンドラー**一覧で、 **BizTalkServerApplication**します。  
  
10. 選択した場合**静的な一方向送信ポート**手順 5 で、送信パイプラインを指定します。 **送信パイプライン**一覧で [xmltransmit] に対応するパイプラインを選択します。  
  
11. 選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプライン。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
12. **[OK]** をクリックします。  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-database"></a>Oracle データベースからメッセージを受信アダプターを展開します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. Wcf-oracledb アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、次を参照してください。[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)します。  
  
3. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
4. 展開するアプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
5. 右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、間の通信モード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と Oracle データベース。  
  
6. **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
7. **受信場所**] タブで [**新規**します。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
8. **受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1.  受信場所の名前を指定します。  
  
   2.  **型**ボックスの一覧が Wcf-oracledb を選択し、クリックして**構成**します。  
  
9. トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  
  
   1. をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
   2. をクリックして、**バインド** タブでバインドによって公開されるプロパティの値を指定し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。
  
      > [!NOTE]
      >  バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。 たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。  
  
   3. をクリックして、**動作** タブ、トランザクション分離レベルを設定します。 トランザクション分離レベルを設定する方法についての詳細については、次を参照してください。[トランザクション分離レベルとトランザクション タイムアウトを構成](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)します。  
  
   4. をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  
  
      -   選択**ユーザー アカウント**オプション、およびユーザー名と Oracle データベースに接続するためのパスワードを指定します。  
  
          -   Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  
  
          -   Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  
  
      -   選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。  
  
   5. 戻ります、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**。  
  
10. **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
11. 選択した場合**一方向の受信ポート**手順 5 で、受信パイプラインを指定します。 **受信パイプライン**一覧で [xmlreceive] に対応するパイプラインを選択します。  
  
12. 選択した場合**要求-応答受信ポート**手順 5 で、指定の送信および受信パイプライン。  
  
    1.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
    2.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
13. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
14. **受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
## <a name="see-also"></a>参照  
   [Oracle データベース アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)
 
 [Windows 認証を使用して Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)