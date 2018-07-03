---
title: Wcf-custom アダプターと Oracle データベース アダプターを使用してポートの構成 |Microsoft Docs
description: 作成 wcf-custom 送信ポートと受信ポートを BizTalk Server で Oracle DB アダプターを使用するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c99ff526-ad97-4095-812f-0ce88b071e7f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 513d848d9bf95e75b8b6b983dde7019ce24ecf46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006483"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter"></a>Wcf-custom アダプターと Oracle データベース アダプターを使用してポートを構成します。
Wcf-custom 送信を構成し、受信ポートを使用して Oracle データベースでの送信および受信の操作を実行する方法、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。 参照してください[を展開して、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)アクセス許可のガイダンスについてはします。
  
## <a name="deploy-adapters-for-sending-messages-to-an-oracle-database"></a>Oracle データベースにメッセージを送信するためのアダプターを展開します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 展開するアプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
4. 右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類をポイント[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と Oracle データベース。  
  
5. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6. **型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
7. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1. をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドで、Oracle データベースの接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
   2. **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)の各操作のアクションの一覧。 たとえば、Oracle データベース内の HR スキーマ EMPLOYEE テーブルの挿入操作を呼び出すアクションは。  
  
      ```  
      http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEE/Select  
      ```  
  
   3. をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **oracleDBBinding**します。 によって公開されるさまざまなバインドのプロパティを指定することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。  
  
   4. をクリックして、**資格情報**タブし、次のいずれかの操作を行います。  
  
      - 選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Oracle データベースに接続するためのパスワードを指定します。  
  
        -   Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  
  
        -   Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  
  
      - 選択、**使用してシングル サインオン**オプション、および SSO 関連アプリケーションを指定します。  
  
        BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [Oracle データベース アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)します。  
  
        戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。  
  
8. **送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
9. 選択した場合**静的な一方向送信ポート**手順 4 で、送信パイプラインを指定します。 **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
10. 選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプライン。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
11. **[OK]** をクリックします。  
  
## <a name="deploy-adapters-for-receiving-messages-from-an-oracle-database"></a>Oracle データベースからメッセージを受信するためのアダプターを展開します。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 展開するアプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
4. 右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、BizTalk Server と Oracle データベース間の通信のモードです。  
  
5. **受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。  
  
6. **受信場所**] タブで [**新規**します。 **受信場所のプロパティ** ダイアログ ボックスが表示されます。  
  
7. **受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1.  受信場所の名前を指定します。  
  
   2.  **型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
8. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1. をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドで、Oracle データベースの接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
   2. をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **oracleDBBinding**します。 によって公開されるさまざまなバインドのプロパティを指定することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。  
  
   3. をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。  
  
      - 選択**ユーザー アカウント**ユーザー名と Oracle データベースに接続するためのパスワードを指定します。  
  
        -   Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。  
  
        -   Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。  
  
      - 選択**関連アプリケーションから資格情報を Get**オプション、および関連アプリケーションを指定します。  
  
        BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [Oracle データベース アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)します。
  
        戻ります、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**。  
  
9. **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
10. 選択した場合**一方向の受信ポート**手順 4 で、受信パイプラインを指定します。 **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
11. 選択した場合**要求-応答受信ポート**手順 4 で、指定の送信および受信パイプライン。  
  
    1.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
    2.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
12. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
13. **受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  
  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)   
 [Windows 認証を使用して Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)