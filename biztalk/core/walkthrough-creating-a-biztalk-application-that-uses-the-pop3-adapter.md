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
ms.openlocfilehash: c3bd79682f78591b066fe1e6db671c3dab4a8333
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985307"
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter"></a>チュートリアル: POP3 アダプターを使用する BizTalk アプリケーションの作成
このセクションでは、POP3 アダプタを使用する簡単な Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを作成する手順について説明します。  
  
> [!NOTE]
>  このアプリケーションは、Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] が実行されていて電子メール サービスがインストールおよび構成されているコンピューターに、アクセスできることを前提としています。 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を電子メール サービスと共に構成する方法の詳細については、Windows Server のヘルプを参照してください。  
> 
> [!NOTE]
>  この例では、電子メール クライアントに Microsoft Outlook Express を、電子メール サーバーに [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用します。 ただし、このシナリオでは任意の POP3 電子メール クライアントと RFC 準拠の POP3 サーバーを使用できます。  
  
 このアプリケーションは、まだ送信ポートまたは受信場所を作成していないことを前提としています。 既存の送信ポートまたは受信場所がある場合、手順を実行する際に適切な名前に置き換えてください。  
  
 このアプリケーションは、受信場所と送信ポートのみを使用する、コンテンツベースの単純なルーティング アプリケーションです。 受信場所を実行しているサーバー上のメールボックスから読み取り[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("Windows server"\)します。 送信ポートは、受信場所からメッセージを取得して、そのメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のローカル ファイル システム上のフォルダーに送信します。  
  
 このアプリケーションを作成するには、メールボックスの作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所と送信ポートの設定、送信ポートの開始と受信場所の有効化、およびメールボックスへのテスト メッセージの送信を行う必要があります。 次の手順に従って、アプリケーションを作成してください。  
  
## <a name="create-a-mailbox-on-windows-server-2003"></a>Windows Server 2003 でのメールボックスの作成  
 電子メール サービスがインストールされた Windows Server 2003 でメールボックスを作成するには、次の手順を実行します。  
  
1. クリックして**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、順にクリックします**POP3 サービス**します。  
  
2. 展開*\<servername\>* メールボックスを作成するドメインをクリックします。  
  
3. **POP3 サービス**ダイアログ ボックスの右側のウィンドウで、クリックして、**メールボックスの追加**オプション。  
  
4. **メールボックスの追加** ダイアログ ボックスで、**メールボックス名**ボックスに「 **EmailTest**します。  
  
5. 選択、**を作成するには、このメールボックスのユーザーが関連付けられている**チェック ボックスをオンします。  
  
6. **パスワード**と**パスワードの確認**ボックス、パスワードを入力し、順にクリックします**OK**します。  
  
7. 書き留めて、**アカウント名**と**メール サーバー**にクリア テキスト認証で使用するために表示される情報のログオン、 **POP3 サービス** ダイアログ ボックスをクリック**OK**します。 この情報は、トランスポートの種類 POP3 で構成する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所によって使用されます。  
  
## <a name="create-the-receive-location"></a>受信場所を作成します。  
 受信場所を作成するには、次の手順を実行します。  
  
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
  
## <a name="create-the-send-port-and-destination-folder-on-the-biztalk-server"></a>BizTalk サーバーでの送信ポートと送信先フォルダの作成  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信ポートと送信先フォルダーを作成するには、次の手順を実行します。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ファイル システムにフォルダーを作成します。 このフォルダが送信ポートの送信先になります。  
  
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
 受信場所を有効にし、送信ポートを開始するには、次の手順を実行します。  
  
1. 右クリックし、 **POP3Receive**受信場所をクリックして**を有効にする**します。  
  
2. 右クリックし、 **SendToFile**送信ポート、およびクリックして**開始**します。  
  
   次の手順では、受信場所によって監視されているメールボックスにテスト メッセージを送信することにより、アプリケーションをテストします。  
  
## <a name="configure-outlook-express-to-send-an-e-mail-message-to-the-mailbox"></a>電子メール メッセージをメールボックスに送信するように Outlook Express を構成  
 電子メール メッセージをメールボックスに送信するように Outlook Express を構成するには、次の手順を実行します。  
  
1.  クリックして**開始**、 をポイント**プログラム**、順にクリックします**Outlook Express**します。  
  
2.  Outlook Express での**ツール** メニューのをクリックして**アカウント**します。  
  
3.  クリックして**追加** をクリックし、**メール**します。  
  
4.  **表示名**ボックスで、表示名を入力し、 をクリックし、**次**します。  
  
5.  **インターネット電子メール アドレス** ダイアログ ボックスで、**電子メール アドレス**ボックスに「 **EmailTest @< domain_name >**、順にクリックします**次**.  
  
     適切な値を入力してください *< domain_name >* します。 この値は、Windows サーバーの POP3 サービスの管理インターフェイスでこのメールボックスを作成したドメインの名前と一致する必要があります。  
  
6.  **電子メール サーバー名** ダイアログ ボックスで、**受信メール**と**送信メール**ボックス、サーバー名または Windows server の IP アドレスを入力および順にクリックします**次へ**します。  
  
7.  **インターネット メール ログオン** ダイアログ ボックスで、**アカウント名**ボックスに「 **EmailTest**します。  
  
8.  **パスワード**ボックスに、選択、EmailTest アカウントのパスワードを入力、**パスワードを保存**オプションで、をクリックして**次**、順にクリックします **[完了]**.  
  
9. 作成したアカウントの選択をクリックし、クリックして**プロパティ**します。  
  
10. **プロパティ**ダイアログ ボックスで、をクリックして、 **[詳細設定]** ] タブでオプションを選択する [**メッセージのコピーをサーバーに置く**、順にクリックします **[ok]**.  
  
11. **インターネット アカウント**ダイアログ ボックスで、をクリックして**閉じる**します。  
  
12. Outlook Express を使用して、テスト メッセージを作成する型**テスト**に、**サブジェクト**フィールド、および種類**EmailTest @< domain_name >** に、 **に**フィールド。  
  
13. クリックして**送信**テスト メッセージを送信します。 確実に、Outlook Express メッセージを送信テストすぐに、次のようにクリックします。、**送受信**、Outlook Express ツールバーのボタンをクリックします。  
  
## <a name="view-the-message"></a>メッセージを表示します。  
 メッセージを表示するには、次の手順を実行します。  
  
1.  Windows エクスプ ローラーを使用して、として指定したフォルダーを開き、**先フォルダー**送信ポートの。  
  
2.  フォルダ内のドキュメントをダブルクリックし、ドキュメントの内容をメモ帳で表示します。  
  
## <a name="see-also"></a>参照  
 [POP3 アダプターについて](../core/what-is-the-pop3-adapter.md)