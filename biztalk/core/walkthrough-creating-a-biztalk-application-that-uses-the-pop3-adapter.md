---
title: 'チュートリアル: は、POP3 アダプタを使用する BizTalk アプリケーションの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, POP3 adapters
- configuring [POP3 adapters], mailboxes
- configuring [POP3 adapters], tutorials
- POP3 adapters, mailboxes
- POP3 adapters, tutorials
- configuring [POP3 adapters], Outlook Express
ms.assetid: b44c3b1d-7b4f-425c-831a-1ce5f6379595
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e677a4fb68ad4f6991585c191c8065a60b3fc337
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975944"
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter"></a>チュートリアル: POP3 アダプターを使用する BizTalk アプリケーションの作成
このセクションでは、POP3 アダプタを使用する簡単な Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを作成する手順について説明します。  
  
> [!NOTE]
>  このアプリケーションは、Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] が実行されていて電子メール サービスがインストールおよび構成されているコンピューターに、アクセスできることを前提としています。 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を電子メール サービスと共に構成する方法の詳細については、Windows Server のヘルプを参照してください。  
  
> [!NOTE]
>  この例では、電子メール クライアントに Microsoft Outlook Express を、電子メール サーバーに [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用します。 ただし、このシナリオでは任意の POP3 電子メール クライアントと RFC 準拠の POP3 サーバーを使用できます。  
  
 このアプリケーションは、まだ送信ポートまたは受信場所を作成していないことを前提としています。 既存の送信ポートまたは受信場所がある場合、手順を実行する際に適切な名前に置き換えてください。  
  
 このアプリケーションは、受信場所と送信ポートのみを使用する、コンテンツベースの単純なルーティング アプリケーションです。 受信場所を実行しているサーバー上のメールボックスから読み取り[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("Windows server"\)です。 送信ポートは、受信場所からメッセージを取得して、そのメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のローカル ファイル システム上のフォルダーに送信します。  
  
 このアプリケーションを作成するには、メールボックスの作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所と送信ポートの設定、送信ポートの開始と受信場所の有効化、およびメールボックスへのテスト メッセージの送信を行う必要があります。 次の手順に従って、アプリケーションを作成してください。  
  
## <a name="create-a-mailbox-on-windows-server-2003"></a>Windows Server 2003 でのメールボックスの作成  
 電子メール サービスがインストールされた Windows Server 2003 でメールボックスを作成するには、次の手順を実行します。  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、順にクリック**POP3 サービス**です。  
  
2.  展開 *\<servername\>* メールボックスを作成するにはドメイン をクリックします。  
  
3.  **POP3 サービス**ダイアログ ボックスの右側のウィンドウで、クリックして、**メールボックスの追加**オプション。  
  
4.  **メールボックスの追加** ダイアログ ボックスで、**メールボックス名**ボックスに、入力**EmailTest**です。  
  
5.  選択、**を作成するには、このメールボックスのユーザーが関連付けられている**チェック ボックスをオンします。  
  
6.  **パスワード**と**パスワードの確認**ボックスに、パスワードを入力し、をクリックして**OK**です。  
  
7.  メモ、**アカウント名**と**メール サーバー**にクリア テキスト認証で使用するために表示される情報のログオン、 **POP3 サービス**クリックしてダイアログ ボックスで、**OK**です。 この情報は、トランスポートの種類 POP3 で構成する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所によって使用されます。  
  
## <a name="create-the-receive-location"></a>受信場所を作成します。  
 受信場所を作成するには、次の手順を実行します。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールが既定のデータベースをダブルクリックして **\<**  *machine_name***\>です。>.biztalkmgmtdb.dbo**ここで、 *machine_name*お使いのコンピューターの名前を指定します。 をクリックして**アプリケーション**をクリックし、 **[biztalk.application.1]** です。  
  
2.  右クリック**受信ポート**をクリックして**新規**、 をクリックして**一方向受信ポート**です。  
  
3.  **受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**POP3Receive**です。  
  
4.  をクリックして**受信場所**、クリックして**新規**です。  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**POP3Receive**です。  
  
5.  **トランスポートの種類**ボックスで、 **POP3**です。  
  
6.  **受信ハンドラー**ボックスで、 **BizTalkServerApplication**です。  
  
7.  **受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**です。  
  
8.  **トランスポート**ボックスで、クリックして、**構成**ボタンをクリックします。  
  
9. **POP3 トランスポートのプロパティ** ダイアログ ボックスで、 **MIME デコードの適用**ボックスで、 **False**です。  
  
10. **メール サーバー**ボックスに、メールボックスを作成した Windows Server ベースのサーバーの名前を入力します。  
  
11. **認証スキーム**ボックスで、**基本**です。  
  
12. **パスワード**ボックス、ドロップダウン矢印をクリックし、メールボックスのパスワードを入力します。  
  
13. **ユーザー名**ボックスに、たとえば、メールボックスの完全修飾ユーザー名を入力*username@host.domain.toplevel_domainです。*  
  
14. **のポーリング間隔**ボックスに、入力**1**、 をクリックして**ok**、順にクリック**OK**もう一度です。  
  
## <a name="create-the-send-port-and-destination-folder-on-the-biztalk-server"></a>BizTalk サーバーでの送信ポートと送信先フォルダの作成  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信ポートと送信先フォルダーを作成するには、次の手順を実行します。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ファイル システムにフォルダーを作成します。 このフォルダが送信ポートの送信先になります。  
  
2.  右クリック**送信ポート**、] をクリックして **、[新規**クリックして**静的な一方向送信ポート。**  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、**トランスポートの種類**ボックスで、**ファイル**です。  
  
4.  **名前**ボックスに、入力**SendToFile**です。  
  
5.  **トランスポート**ボックスで、クリックして、**構成**ボタンをクリックします。  
  
6.  横に、**コピー先フォルダー**ボックスで、をクリックして**参照**、上に作成したフォルダーを選択して、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順にクリック **[ok]** です。  
  
7.  **ファイル名**ボックスに、入力 **%MessageID%.txt**、順にクリック**OK**です。  
  
8.  **送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**です。  
  
9. **[フィルター]** をクリックします。  
  
10. **プロパティ**ボックスで、 **BTS です。ReceivePortName**です。  
  
11. **値**ボックスに、入力**POP3Receive**、順にクリック**OK**です。  
  
## <a name="enable-the-receive-location-and-start-the-send-port"></a>受信場所を有効にして、送信ポートの開始  
 受信場所を有効にし、送信ポートを開始するには、次の手順を実行します。  
  
1.  右クリックし、 **POP3Receive**受信場所をクリックして**を有効にする**です。  
  
2.  右クリックし、 **SendToFile**送信ポートをクリックして**開始**です。  
  
 次の手順では、受信場所によって監視されているメールボックスにテスト メッセージを送信することにより、アプリケーションをテストします。  
  
## <a name="configure-outlook-express-to-send-an-e-mail-message-to-the-mailbox"></a>電子メール メッセージをメールボックスに送信するように Outlook Express を構成  
 電子メール メッセージをメールボックスに送信するように Outlook Express を構成するには、次の手順を実行します。  
  
1.  をクリックして**開始**、 をポイント**プログラム**、順にクリック**Outlook Express**です。  
  
2.  Outlook Express での**ツール** メニューのをクリックして**アカウント**です。  
  
3.  をクリックして**追加** をクリックし、**メール**です。  
  
4.  **表示名**ボックスで、表示名を入力し、をクリックして**次**です。  
  
5.  **インターネット電子メール アドレス**] ダイアログ ボックスで、**電子メール アドレス**ボックスに、入力**EmailTest @< domain_name >**、クリックして **[次へ**.  
  
     適切な値を入力することを確認 *< domain_name >* です。 この値は、Windows サーバーの POP3 サービスの管理インターフェイスでこのメールボックスを作成したドメインの名前と一致する必要があります。  
  
6.  **電子メール サーバー名** ダイアログ ボックスで、**受信メール**と**発信メール**ボックスに、サーバー名または Windows server の IP アドレスを入力し、 をクリックして**次へ**です。  
  
7.  **インターネット メール ログオン** ダイアログ ボックスで、**アカウント名**ボックスに、入力**EmailTest**です。  
  
8.  **パスワード**ボックスに、select、EmailTest アカウントのパスワードを入力、**パスワードを保存**オプションで、**次**、順にクリック**完了**.  
  
9. 作成したアカウントを選択する をクリックし、をクリックして**プロパティ**です。  
  
10. **プロパティ**ダイアログ ボックスで、をクリックして、 **詳細設定**  タブで、オプションを選択してクリックして**サーバーにメッセージのコピーを残す**、順にクリック**ok**.  
  
11. **インターネット アカウント**ダイアログ ボックスで、をクリックして**閉じる**です。  
  
12. Outlook Express を使用してテスト メッセージを作成する型**テスト**に、**サブジェクト**フィールド、および種類**EmailTest @< domain_name >** に、 **に**フィールドです。  
  
13. をクリックして**送信**テスト メッセージを送信します。 確実に、Outlook Express メッセージを送信テストすぐに、をクリックして、**送受信**Outlook Express ツールバーのボタンをクリックします。  
  
## <a name="view-the-message"></a>メッセージを表示します。  
 メッセージを表示するには、次の手順を実行します。  
  
1.  Windows エクスプ ローラーを使用して、として指定したフォルダーを開く、**コピー先フォルダー**送信ポートのです。  
  
2.  フォルダ内のドキュメントをダブルクリックし、ドキュメントの内容をメモ帳で表示します。  
  
## <a name="see-also"></a>参照  
 [POP3 アダプターについて](../core/what-is-the-pop3-adapter.md)