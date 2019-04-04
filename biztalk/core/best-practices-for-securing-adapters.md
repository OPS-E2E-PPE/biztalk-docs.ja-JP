---
title: アダプターをセキュリティで保護するためのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, security
- best practices, adapters
- adapters, permissions
- security, adapters
- permissions, adapters
- best practices, security
- adapters, best practices
ms.assetid: 004e1a01-b316-4eee-967f-5a806431de2b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbc38ddedf1b71cba0df4306359df9bdb5c96c15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966315"
---
# <a name="best-practices-for-securing-adapters"></a>アダプターをセキュリティで保護するためのベスト プラクティス
このトピックでは、アダプターのセキュリティに関するベスト プラクティスについて説明します。  
  
 **コンピューターで信頼されていないアダプターをインストールしないでください。認定されたアダプター開発パートナーのみを使用します。**  
  
 **既定のアダプター スキーマでは、顧客の機密データを格納しないでください。**  
  
 ユーザー名とパスワードの情報を構成するのは、アダプターの展開後にしてください。 アダプターの展開後であれば、それらの情報は SSO データベースに格納されます。 SSO データベースの詳細については、[を使用して SSO](../core/using-sso.md)を参照してください。  
  
 **共有フォルダー (受信フォルダーと送信フォルダー) 選択し、ファイルおよび EDI アダプターを使用してファイルの削除に使用するには、次の権限を付与するには。**  
  
- **受信フォルダー**  
  
   ファイル アダプターで使用する受信フォルダーは、受信場所で構成できます。 EDI アダプターで使用する受信フォルダーは、受信ハンドラーで構成できます。 ファイルを取得する BizTalk ホストのサービス アカウントには、ファイルシステム レベルで次のアクセス許可を付与する必要があります。  
  
  - フォルダーの一覧表示/データの読み取り  
  
  - サブフォルダーとファイルを削除します。  
  
    受信フォルダーがネットワーク共有上にある場合、ファイル共有レベルで次のアクセス許可を付与する必要があります。  
  
  - ファイルを取得する BizTalk ホストのサービス アカウントには、フル コントロール アクセス許可が必要です。  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者には、トラブルシューティングのためにフル コントロール アクセス許可が必要です。  
  
  - この場所にファイルをドロップする外部のユーザーまたはプログラムには、書き込みアクセス許可が必要です。  
  
- **送信フォルダー**  
  
   ファイル アダプターおよび EDI アダプターで使用する送信フォルダーは、送信ポートで構成できます。  
  
  - ファイルをドロップする BizTalk ホストのサービス アカウントには、書き込みアクセス許可が必要です。  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者には、フル コントロール アクセス許可が必要です。  
  
  - ファイルを取得する外部のユーザーまたはプログラムには、読み取りアクセス許可が必要です。  
  
  **EDI サービスが BTS_HOST_USERS SQL ロールに実行されているユーザー アカウントを追加します。**  
  
  これは、機能は、管理者権限のない BizTalk エクスプ ローラー オブジェクトの管理 (OM) へのアクセスを取得できるように、必要です。 ユーザー アカウントを追加するには、BizTalk 管理データベース BizTalkMgmtDb の BTS_HOST_USERS ロールに "EDI Subsystem Users" を追加します。  
  
  SQL Server 2005 で BTS_HOST_USERS ロールに "EDI Subsystem Users" を追加するには、次の手順を実行します。  
  
1. SQL Server Management Studio を起動**スタートでは、プログラム、Microsoft SQL Server 2008**します。  
  
2. BizTalk 管理データベースを格納する SQL Server に接続します。  
  
3. オブジェクト エクスプローラーでこのサーバーを展開します。  
  
4. 展開**データベース**、BizTalk 管理データベースを順に展開します。  
  
5. 展開**セキュリティ**、展開**ロール**、クリックして選択し、**データベース ロール**  
  
6. 詳細ペインで BTS_HOST_USERS ロールを右クリックし をクリックし、**プロパティ**します。  
  
7. BTS_HOST_USERS ダイアログ ボックスで、**追加**、 をクリックして**参照**、EDI Subsystem Users グループに追加の横にあるボックスを確認します。  
  
    追加するユーザーの一覧に EDI Subsystem Users グループが表示されない場合、EDI Subsystem Users グループを新しいデータベース ユーザーとして BizTalk 管理データベースに追加する必要があります。 EDI Subsystem Users グループを新しいデータベース ユーザーとして追加するには、SQL Server Management Studio で次の手順を実行します。  
  
   1.  BizTalk 管理データベースを展開します。  
  
   2.  展開**セキュリティ**します。  
  
   3.  右クリック**ユーザー**クリック**新しいユーザー**します。  
  
   4.  テキスト ボックスの横にある省略記号 (...) ボタンをクリックします。**ログイン名**を表示する、**ログインの選択** ダイアログ ボックス。  
  
   5.  参照 ボタンをクリックして、入力、 **EDI Subsystem Users**グループ化、および順にクリックします**ok をクリックします。** メッセージが表示されたら、**見つかった複数のオブジェクト**ダイアログ ボックスで、 **EDI Subsystem Users**ログインとクリック **[ok]** します。  
  
   6.  **データベース ユーザー - 新規**ダイアログ ボックスの入力**EDI Subsystem Users**の**ユーザー名**テキスト ボックス をクリック**ok**します。  
  
   **BizTalk サービスが EDI Subsystem Users グループに実行されているユーザー アカウントを追加します。**  
  
   次の手順に従い、BizTalk サービス用のユーザー アカウントを EDI Subsystem Users グループに追加します。  
  
-   **BizTalk Server を構成するにはドメイン グループを使用する: 場合**  
  
    1.  ドメイン内の Windows Server コンピューターにログオンします。  
  
    2.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**管理ツール**、順にクリックします**Active Directory ユーザーとコンピューター**します。  
  
        > [!NOTE]
        >  オブジェクトを変更する適切なドメイン レベルのアクセス許可が必要、 **Active Directory ユーザーとコンピューター**インターフェイス。  
  
    3.  ドメインのコンテナーを展開し、クリックして展開、**ユーザー**コンテナー。  
  
    4.  ダブルクリック、 **EDI Subsystem Users**グループをこのグループのプロパティを表示します。  
  
    5.  をクリックして、**メンバー**のタブ、 **EDI Subsystem Users**グループ ダイアログ ボックス。  
  
    6.  をクリックして、**追加**このグループに BizTalk サービスのユーザー アカウントを追加するボタンをクリックします。  
  
    7.  **[OK]** をクリックします。  
  
-   **BizTalk Server を構成して、ローカル グループを使用します。 場合、**  
  
    1.  BizTalk Server にログオンします。  
  
    2.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**管理ツール**、順にクリックします**コンピュータの管理**します。  
  
    3.  クリックして展開**システム ツール**をクリックして展開**ローカル ユーザーとグループ**をクリックして展開**グループ**します。  
  
    4.  ダブルクリック、 **EDI Subsystem Users**グループをこのグループのプロパティを表示します。  
  
    5.  をクリックして、**追加**BizTalk サービスのユーザー アカウントをこのグループに追加するボタンをクリックします。  
  
    6.  **[OK]** をクリックします。