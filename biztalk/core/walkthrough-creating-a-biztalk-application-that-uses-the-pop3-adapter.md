---
title: 'チュートリアル: POP3 アダプタを使用する BizTalk アプリケーションの作成 |Microsoft Docs'
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
ms.openlocfilehash: 6f94c34361eb69f2e9838da26a3ea30f95cb3a85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250208"
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter"></a>チュートリアル: POP3 アダプタを使用する BizTalk アプリケーションの作成
このセクションで簡単な Microsoft の作成手順は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]POP3 アダプターを使用するアプリケーション。  
  
> [!NOTE]
>  アプリケーションでは、Microsoft を実行しているコンピューターへのアクセスがあると想定[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]電子メール サービスをインストールして構成します。 構成について[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]を電子メール サービスと共に Windows Server のヘルプを参照してください。  
> 
> [!NOTE]
>  この例での電子メール クライアントとして Microsoft Outlook Express を使用し、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]電子メール サーバーとして使用されます。 ただし、任意の POP3 電子メール クライアントと RFC 準拠の POP3 サーバーをこのシナリオで使用できます。  
  
 このアプリケーションは、または受信場所、送信ポートにまだ作成するいないと仮定します。 既存の送信ポートまたは受信場所がある場合、手順を実行する際に適切な名前に置き換えてください。  
  
 アプリケーションは、単純なコンテンツ ベース ルーティング アプリケーションのみを受信場所と送信ポートを使用しています。 受信場所を実行しているサーバー上のメールボックスから読み取り[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("Windows server"\)します。 送信ポートの受信場所からメッセージを受け取るし、のローカル ファイル システム上のフォルダーに送信します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 アプリケーションを作成するには、メールボックスの作成、設定する必要がある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信場所と送信ポート、送信ポートの開始し、受信場所を有効にして、メールボックスにテスト メッセージを送信します。 アプリケーションを作成するのには、次の手順に従います。  
  
## <a name="create-a-mailbox-on-windows-server-2003"></a>Windows Server 2003 でメールボックスを作成します。  
 電子メール サービスがインストールされている Windows Server 2003 のメールボックスを作成するには、次の手順を実行します。  
  
1. クリックして**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、順にクリックします**POP3 サービス**します。  
  
2. 展開*\<servername\>* メールボックスを作成するドメインをクリックします。  
  
3. **POP3 サービス**ダイアログ ボックスの右側のウィンドウで、クリックして、**メールボックスの追加**オプション。  
  
4. **メールボックスの追加** ダイアログ ボックスで、**メールボックス名**ボックスに「 **EmailTest**します。  
  
5. 選択、**を作成するには、このメールボックスのユーザーが関連付けられている**チェック ボックスをオンします。  
  
6. **パスワード**と**パスワードの確認**ボックス、パスワードを入力し、順にクリックします**OK**します。  
  
7. 書き留めて、**アカウント名**と**メール サーバー**にクリア テキスト認証で使用するために表示される情報のログオン、 **POP3 サービス** ダイアログ ボックスをクリック**OK**します。 この情報を使って、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信トランスポートの種類 POP3 で構成する場所。  
  
## <a name="create-the-receive-location"></a>受信場所を作成します。  
 受信場所を作成する次の手順に従います。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールは、既定のデータベースをダブルクリックして**\<** <em>machine_name</em>**\>します。>.biztalkmgmtdb.dbo**ここで、 *machine_name*コンピューターの名前を指定します。 クリックして**アプリケーション**、 をクリックし、 **biztalk.application.1**します。  
  
2. 右クリックして**受信ポート**、 をクリックして**新規**、 をクリックして**一方向受信ポート**します。  
  
3. **受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **POP3Receive**します。  
  
4. クリックして**受信場所**、 をクリックし、**新規**します。  **受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **POP3Receive**します。  
  
5. **トランスポートの種類**ボックスで、 **POP3**します。  
  
6. **受信ハンドラー**ボックスで、 **BizTalkServerApplication**します。  
  
7. **受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**します。  
  
8. **トランスポート**ボックスで、、**構成**ボタンをクリックします。  
  
9. **POP3 トランスポートのプロパティ** ダイアログ ボックスで、 **MIME デコードの適用**ボックスで、 **False**します。  
  
10. **メール サーバー**ボックスに、メールボックスを作成した Windows Server ベースのサーバーの名前を入力します。  
  
11. **認証スキーム**ボックスで、**基本的な**します。  
  
12. **パスワード**ボックスで、ドロップダウン矢印をクリックし、メールボックスのパスワードを入力します。  
  
13. **ユーザー名**ボックスに、たとえば、メールボックスの完全修飾ユーザー名を入力<em>username@host.domain.toplevel_domainします。</em>  
  
14. **のポーリング間隔**ボックスに「 **1**、 をクリックして**ok**順にクリックします**OK**もう一度です。  
  
## <a name="create-the-send-port-and-destination-folder-on-the-biztalk-server"></a>BizTalk server に送信ポートと送信先フォルダーを作成します。  
 送信ポートと送信先のフォルダを作成する次の手順に従って、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
1. フォルダーを作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ファイル システム。 送信ポートの送信先になります。  
  
2. 右クリック**送信ポート**、 をクリックして**新規、**  をクリックし、**静的な一方向送信ポート。**  
  
3. **送信ポートのプロパティ** ダイアログ ボックスで、**トランスポートの種類**ボックスで、**ファイル**します。  
  
4. **名前**ボックスに「 **SendToFile**します。  
  
5. **トランスポート**ボックスで、、**構成**ボタンをクリックします。  
  
6. 横に、**先フォルダー**ボックスで、**参照**、上に作成したフォルダーを選択して、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順にクリックします **[ok]**。  
  
7. **ファイル名**ボックスに「 **%MessageID%.txt**、順にクリックします**OK**します。  
  
8. **送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**します。  
  
9. **[フィルター]** をクリックします。  
  
10. **プロパティ**ボックスで、 **BTS します。ReceivePortName**します。  
  
11. **値**ボックスに「 **POP3Receive**、順にクリックします**OK**します。  
  
## <a name="enable-the-receive-location-and-start-the-send-port"></a>受信場所を有効にして、送信ポートの開始  
 受信場所を有効にして、送信ポートを開始する次の手順に従います。  
  
1. 右クリックし、 **POP3Receive**受信場所をクリックして**を有効にする**します。  
  
2. 右クリックし、 **SendToFile**送信ポート、およびクリックして**開始**します。  
  
   次の手順では、テスト メッセージを受信場所で監視するメールボックスに送信することによって、アプリケーションをテストします。  
  
## <a name="configure-outlook-express-to-send-an-e-mail-message-to-the-mailbox"></a>Outlook Express メールボックスへの電子メール メッセージの送信を構成します。  
 Outlook Express メールボックスへの電子メール メッセージの送信を構成するこれらの手順に従います。  
  
1.  クリックして**開始**、 をポイント**プログラム**、順にクリックします**Outlook Express**します。  
  
2.  Outlook Express での**ツール** メニューのをクリックして**アカウント**します。  
  
3.  クリックして**追加** をクリックし、**メール**します。  
  
4.  **表示名**ボックスで、表示名を入力し、 をクリックし、**次**します。  
  
5.  **インターネット電子メール アドレス** ダイアログ ボックスで、**電子メール アドレス**ボックスに「 **EmailTest @< domain_name >**、順にクリックします**次**.  
  
     適切な値を入力してください *< domain_name >* します。 この値は、Windows サーバーの POP3 サービスの管理インターフェイスでこのメールボックスが作成されるドメインの名前と一致する必要があります。  
  
6.  **電子メール サーバー名** ダイアログ ボックスで、**受信メール**と**送信メール**ボックス、サーバー名または Windows server の IP アドレスを入力および順にクリックします**次へ**します。  
  
7.  **インターネット メール ログオン** ダイアログ ボックスで、**アカウント名**ボックスに「 **EmailTest**します。  
  
8.  **パスワード**ボックスに、選択、EmailTest アカウントのパスワードを入力、**パスワードを保存**オプションで、をクリックして**次**、順にクリックします **[完了]**.  
  
9. 作成したアカウントの選択をクリックし、クリックして**プロパティ**します。  
  
10. **プロパティ**ダイアログ ボックスで、をクリックして、 **[詳細設定]** ] タブでオプションを選択する [**メッセージのコピーをサーバーに置く**、順にクリックします **[ok]**.  
  
11. **インターネット アカウント**ダイアログ ボックスで、をクリックして**閉じる**します。  
  
12. Outlook Express を使用して、テスト メッセージを作成する型**テスト**に、**サブジェクト**フィールド、および種類**EmailTest @< domain_name >** に、 **に**フィールド。  
  
13. クリックして**送信**テスト メッセージを送信します。 確実に、Outlook Express メッセージを送信テストすぐに、次のようにクリックします。、**送受信**、Outlook Express ツールバーのボタンをクリックします。  
  
## <a name="view-the-message"></a>メッセージを表示します。  
 メッセージを表示する次の手順に従います。  
  
1.  Windows エクスプ ローラーを使用して、として指定したフォルダーを開き、**先フォルダー**送信ポートの。  
  
2.  メモ帳で、ドキュメントの内容を表示するフォルダー内のドキュメントをダブルクリックします。  
  
## <a name="see-also"></a>参照  
 [POP3 アダプターについて](../core/what-is-the-pop3-adapter.md)