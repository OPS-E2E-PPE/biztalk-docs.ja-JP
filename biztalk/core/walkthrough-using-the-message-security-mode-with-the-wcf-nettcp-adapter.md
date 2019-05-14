---
title: 'チュートリアル: Wcf-nettcp アダプターでメッセージ セキュリティ モードの使用 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7f6e892-34ce-4132-8867-54cc3bbfe507
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52936b6110e5e04610e1a215103b558dcbe4c1e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399435"
---
# <a name="walkthrough-using-the-message-security-mode-with-the-wcf-nettcp-adapter"></a>チュートリアル: Wcf-nettcp アダプターでメッセージ セキュリティ モードの使用

> [!NOTE]
>  アダプターの詳細については、次を参照してください。 [BizTalk Server のアダプター](../core/adapters-in-biztalk-server.md)します。  

## <a name="introduction"></a>概要

 このチュートリアルでは、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] メッセージ セキュリティ モードを使用するように WCF-NetTcp アダプターを構成する方法について説明します。このモードでは、WS-Security 仕様を使用してアダプターが送信するメッセージを保護します。 この仕様は、SOAP メッセージ レベルでの機密性、整合性、および認証を実現する SOAP メッセージング プロトコルの機能強化を示しています。 メッセージ セキュリティ モードでは、セキュリティ モードの組み合わせに応じて、暗号化/解読や署名/検証を目的とするオペレーションに対して、サービス証明書を指定する必要があります。  

 WCF-NetTcp アダプターは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアントと [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] リモート サービスの間の通信に NetTcpBinding バインドを使用します。 このアダプタからは、SOAP セキュリティ、信頼性、およびトランザクションの各機能にフル アクセスできます。 これによりオーケストレーションおよびスキーマを [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスとして公開することが可能になります。また、オーケストレーションで外部 WCF サービスを使用できるようになります。 このアダプタは、TCP トランスポートを使用し、メッセージではバイナリ エンコードを使用します。 WCF-NetTcp アダプターは、送信アダプターと受信アダプターの 2 つで構成されます。  

 このチュートリアルでは、Active Directory 証明書サービスを使用して、メッセージ セキュリティ モードの証明書を作成する方法について説明します。 サーバー用とクライアント用の証明書を作成してから、メッセージ セキュリティ モードでそれらの証明書を使用するように WCF-NetTcp 受信場所を構成します。 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアントを使用して、W3C の勧告である「XML Encryption Syntax and Processing」に従って暗号化した状態のメッセージをその受信場所に送信します。  

 このチュートリアルを完了すると、次のタスクを実行できるようになります。  

- Active Directory 証明書サービスを使用して証明書要求を作成し、証明書を発行してプロセスを完了する。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから、メッセージ セキュリティ モードを使用するように WCF-NetTcp アダプターを構成する。  

## <a name="prerequisites"></a>必須コンポーネント  
 このサンプルではを手順がを環境に次の前提条件がインストールされることを確認を実行するには  

- アセンブリをビルドし、展開プロセスを実行するコンピューターと、サンプルを実行しているコンピューターの両方の必要な Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]、および Microsoft BizTalk Server です。  

- アセンブリのビルドと展開プロセスの実行に使用するコンピューターには、Microsoft Visual Studio が必要です。  

- サンプルを実行するコンピューターには、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターと [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理ツールが必要です。 これらは、Microsoft BizTalk Server のセットアップ時にインストールするオプションです。  

- 管理タスクの実行に使用するコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション設定を構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーであるユーザー アカウントとして実行する必要があります。 また、アプリケーションの展開、ホスト インスタンスの管理、およびその他の必要なタスクを実行するには、このユーザー アカウントはローカル管理者グループのメンバーである必要もあります。  

- 必要とする任意のコンピューターで[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]機能により、1 回限りのセットアップの手順を完了、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サンプル[ http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510)します。  

- サンプルを実行してバインドまたは .msi ファイルを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にインポートするコンピューターで、ホストが信頼されているホストではないことを確認します。信頼されているホストの場合、インポートは失敗します。  

- このサンプルを実行するコンピューターに、Active Directory 証明書サービスがインストールされていることを確認します。  

- チュートリアルのコードをダウンロードし、コンピューターに展開する必要があります。  このチュートリアルでは全体の一部[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]アダプター チュートリアル パッケージ。 ファイルをダウンロードする**WCFAdapterWalkthroughs.exe**から、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デベロッパー センター [ http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140)します。  

## <a name="create-the-certificates-for-this-walkthrough"></a>このチュートリアル用の証明書を作成します。  

1. このセクションでは、サービスとクライアントの証明書を要求、証明書の発行が適切なストアにインストールします。 信頼されている証明書チェーンを使用して証明書を作成するには、Active Directory 証明書サービスを使用します。 「前提条件」において Active Directory 証明書サービスをインストールしていない場合は、コンピューターに Active Directory 証明書サービスをインストールします。 既にインストールされている場合は、手順 2. に進みます。  

   1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**サーバー マネージャー**します。  

   2.  下、**サーバー マネージャー**ノード、をクリックして**追加**、順にクリックします**ロール**します。  

   3.  すると、**開始する前に**のダイアログ、**役割の追加ウィザード**します。 **[次へ]** をクリックします。  

   4.  **サーバーの役割の選択**ページで、選択**Active Directory Certificate Services**、 をクリックして**次へ**、しに従って、画面上を完了する手順については、インストールします。  

2. 次の手順に従って、サービス認証の証明書要求を作成します。  

   1. Internet Explorer で、Web サイトを参照してください。`http://localhost/certsrv`します。 **ようこそ**] ページで [**証明書を要求**、順にクリックします**高度な証明書の要求**で、**証明書を要求**ページです。  

      > [!NOTE]
      >  使用する場合[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]証明機関から証明書の要求を要求すると、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター、エラーが発生する可能性があります **"証明書の登録を完了するには、CA の Web サイト構成必要がある HTTPS を使用するには認証"** します。 このエラーが発生した場合、登録 web サイトは Web 証明書 (SSL) を構成する必要があります。 この作業の詳細については、次のリンクを参照してください。  
      > 
      >  [AD CS:Web 登録](http://technet.microsoft.com/library/cc732517.aspx)  
      > 
      >  [IIS サーバー証明書のインストール手順](http://msdn.microsoft.com/library/ms751408.aspx)  

   2. **証明書要求の高度な**] ページで [**作成し、この CA に要求を送信**。  

   3. **証明書の要求の高度な**ページで、入力`localhost`で、**名前**テキスト ボックスで、**サーバー認証証明書**から、 **必要な証明書の種類**ドロップダウン リスト、およびクリック**送信**します。  

3. 次の手順に従って、クライアント認証の証明書要求を作成します。  

   1.  Internet Explorer で、Web サイトを参照してください。`http://localhost/certsrv`します。 **ようこそ**] ページで [**証明書を要求**、順にクリックします**高度な証明書の要求**で、**証明書を要求**ページです。  

   2.  **証明書要求の高度な**] ページで [**作成し、この CA に要求を送信**。  

   3.  **証明書の要求の高度な**ページで、入力`contoso`で、**名前**テキスト ボックスで、**クライアント認証証明書**から、 **必要な証明書の種類**ドロップダウン リスト、およびクリック**送信**します。  

   > [!NOTE]
   >  クライアント認証証明書は、ドメイン コント ローラー以外のコンピューターで BizTalk Server を実行している場合に使用されます。 これは、アダプターのプロパティ ダイアログで構成されます。  

4. 次の手順に従って、証明機関管理コンソールを使用して、証明書を発行します。  

   1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**証明機関**します。  

   2.  **証明機関**管理コンソールでは、証明機関の名前を展開し、ダブルクリック**保留中の要求**します。  

   3.  右側のウィンドウで、**証明機関**管理コンソールで、サービス認証証明書の要求を右クリックし、[**すべてのタスク**、] をクリックし、**問題**.  

   4.  右側のウィンドウで、**証明機関**管理コンソールで、クライアント認証証明書の要求を右クリックし、[**すべてのタスク**、] をクリックし、**問題**.  

   5.  閉じる、**証明機関**管理コンソール。  

5. 次の手順に従って、発行した証明書をコンピューターにインストールします。  

   1.  Internet Explorer で、Web サイトを参照してください。`http://localhost/certsrv`します。  

   2.  **ようこそ**] ページで [**保留中の証明書の要求の状態を表示**します。  

   3.  **保留中の証明書要求の状態を表示** ページで、サーバー認証証明書をクリックします。  

   4.  **証明書は発行**] ページで [**この証明書をインストール**します。  

   5.  Internet Explorer で、Web サイトを参照してください。`http://localhost/certsrv`します。  

   6.  **ようこそ**] ページで [**保留中の証明書の要求の状態を表示**します。  

   7.  **保留中の証明書要求の状態を表示** ページで、クライアント認証証明書をクリックします。  

   8.  **証明書は発行**] ページで [**この証明書をインストール**します。  

6. 次の手順に従って、発行した証明書が正しくインストールされたことを確認します。  

   1.  Microsoft 管理コンソール (MMC) を開きます。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、型`mmc`、順にクリックします**OK**します。  

   2.  MMC で、上、**ファイル** メニューのをクリックして**スナップインの追加と削除**します。  

   3.  **[スナップインの追加と削除]** ダイアログ ボックスで **[追加]** をクリックします。  

   4.  **スタンドアロン スナップインの追加**ダイアログ ボックスで、**証明書**から、**利用できるスタンドアロン スナップイン**ボックスの一覧をクリックして**追加**.  

   5.  **証明書スナップイン**ダイアログ ボックスで、 **ユーザー アカウント**オプションをクリックして**完了**します。  

   6.  開いているダイアログ ボックスをすべて閉じます。  

   7.  MMC のコンソール ルート] ウィンドウで [**証明書 - 現在のユーザー**、展開**個人**、展開**証明書**、いることを確認し、証明書を前の手順でインストールされているが表示されます。  

## <a name="create-the-biztalk-application-for-this-walkthrough"></a>このチュートリアルでは、BizTalk アプリケーションを作成します。  

1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**を右クリックして**アプリケーション**、 をポイント**新規**、 をクリックし、**アプリケーション**.  

3. **アプリケーション プロパティ** ダイアログ ボックスで、**全般** タブで、入力`WcfMessageSecurity`、順にクリックします**ok**。  

4. 次の手順に従って、BizTalk アプリケーションの WCF-NetTcp アダプターを使用する受信場所を作成します。  

   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **WcfMessageSecurity**を右クリックして**受信ポート**、 をポイント**新規**、 をクリックし、 **一方向受信ポート。**  

   2. **受信ポートのプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスに「 `WcfMessageSecurity.OrderRequest.Receive`、順にクリックします**OK**します。 この受信ポートの名前は厳密には任意ですが、わかりやすい名前にする必要があります。  

   3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリック**受信場所**、 をクリックして**新規**、 をクリックし、**一方向の受信場所**。 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアントは [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージをこの受信場所に送信します。 選択、 **WcfMessageSecurity.OrderRequest.Receive**受信ポートをクリック**OK**します。  

   4. **受信場所のプロパティ** ダイアログ ボックスで、**名前**テキスト ボックスに「`WcfMessageSecurity.OrderRequest.Receive.NetTcp`します。 この受信場所の名前は厳密には任意ですが、わかりやすい名前にする必要があります。  

   5. **受信場所のプロパティ** ダイアログ ボックスで、**トランスポート**の横**型**を選択します**Wcf-nettcp**ドロップダウン リストからボックスの一覧をクリックして**構成**します。  

   6. **Wcf-nettcp トランスポートのプロパティ** ダイアログ ボックスで、**全般** タブで、**アドレス (URI)** テキスト ボックスに「 `net.tcp://localhost/WcfMessageSecurity`。  

   7. **Wcf-nettcp トランスポートのプロパティ** ダイアログ ボックスで、**セキュリティ** タブで **メッセージ**から、**セキュリティ モード**ドロップダウンボックスの一覧を選び**証明書**から、**クライアント資格情報の種類のメッセージ**ドロップダウン リスト。 これにより、メッセージ セキュリティ モードを使用するように WCF-NetTcp アダプターが構成されます。  

   8. メッセージ セキュリティ モードで使用するサービス証明書を構成します。 **Wcf-nettcp トランスポートのプロパティ**] ダイアログ ボックスで、**サービス証明書**セクションで、[**参照**します。 **サービス証明書** ダイアログ ボックスでは、前の手順でインストールしたサーバー認証証明書を選択しをクリックして**OK**  ダイアログ ボックスを閉じて、変更を保存します。  

   9. 開いているダイアログ ボックスをすべて閉じます。  

      > [!NOTE]
      >  [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 受信アダプターでクライアント証明書を認証するには、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターのホスト インスタンスを実行するこのコンピューターの "信頼済みルート証明機関" 証明書ストアに、クライアント証明書の CA 証明書チェーンがインストールされている必要があります。 このチュートリアルでは、証明書サービスが [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] クライアントおよび [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターと同じコンピューターにインストールされていると想定しているため、コンピューターに CA 証明書チェーンをインストールする必要はありません。  

5. BizTalk アプリケーションの FILE 送信ポートを作成します。 これは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスを表すオーケストレーションによって注文要求の出力メッセージが送信される場所です。  

   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **WcfMessageSecurity**を右クリックして**送信ポート**、 をポイント**新規**、 をクリックし、**静的一方向の送信ポートです。**  

   2. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、**名**テキスト ボックスに「 `WcfMessageSecurity.OrderRequest.Send.FILE`。  

   3. **送信ポートのプロパティ** ダイアログ ボックスで、**トランスポート**の横**型**を選択します**ファイル**ドロップダウン リストからしクリックして**構成**します。  

   4. **FILE トランスポートのプロパティ** ダイアログ ボックスの 、**一般的な** タブで、入力`C:\WCFMessageSecurity\OrderRequestOut`で、**先フォルダー**テキスト ボックス、およびクリック**ok**.  

   5. **送信ポートのプロパティ** ダイアログ ボックスで、**フィルター**  タブで  **BTS します。ReceivePortName**の**プロパティ**フィールドに、入力`WcfMessageSecurity.OrderRequest.Receive`の**値**フィールドをクリックして**OK**します。 このフィルタ式により、着信[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]にクライアントからのメッセージ、 **WcfMessageSecurity.OrderRequest.Receive**この送信ポートにポートを受信します。  

## <a name="test-the-wcf-client-against-the-biztalk-application"></a>BizTalk アプリケーションに対して WCF クライアントをテストします。  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**WcfMessageSecurity**、順にクリックします**開始**します。 **開始**ダイアログ ボックスで、をクリックして**開始**します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**プラットフォームの設定**、展開**ホスト インスタンス**を右クリックして**BizTalkServerApplication**またはその他クリックして、ホスト インスタンスを適切な**再起動**します。  

3. という名前のフォルダーを作成する**C:\WCFMessageSecurity**のこのチュートリアルの作業フォルダー。 チュートリアルのファイルをこのフォルダーに展開します。  

4. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、オープン、 **WcfMessageSecurity.sln**ファイル、 **C:\WCFMessageSecurity**フォルダー。  

5. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、 **WcfClient**を開き**Program.cs**を確認します。  

   - クライアントから、前の手順で作成した WCF-NetTcp 受信場所にメッセージが送信されます。  

   - クライアントのチャネルの作成、 **NetTcpBinding**、クライアント資格情報の種類の証明書を使用するバインディングを構成します。  

   - クライアントは、前の手順でインストールしたクライアント認証証明書をクライアント認証に使用するようにエンドポイント動作を構成します。  

   - クラス、**プログラム**、実装、 **IClientMessageInspector**と**IEndpointBehavior**送信を表示するインターフェイス[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]これからのメッセージコマンド プロンプトでのクライアント。  

6. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリックし、 **WcfMessageSecurity**ソリューション、およびクリック**リビルド**。  

7. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**デバッグ** メニューのをクリックして**デバッグなしで開始**にメッセージを Wcf-nettcp 受信場所を送信する WcfClient を実行します。 コマンド プロンプトに実行結果が表示されます。  

   1. コマンド プロンプトで、注文要求メッセージを確認します。 注意してください、 **OrderId**フィールドと、メッセージの構造体。  

   2. コマンド プロンプトに移動、`C:\WCFMessageSecurity\OrderRequestOut`フォルダーから送信された注文要求メッセージを確認して、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]クライアントが表示されます。  

   3. コマンド プロンプトを閉じます。
