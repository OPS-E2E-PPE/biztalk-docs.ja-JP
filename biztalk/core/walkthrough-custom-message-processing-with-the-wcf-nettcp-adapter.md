---
title: 'チュートリアル: カスタム メッセージを Wcf-nettcp アダプターを使用した処理 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b56b7492-2ea0-4c63-8f1b-430eb277517d
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39f765e1e99363440d6c122f5e5f174ea50dd761
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826346"
---
# <a name="walkthrough-custom-message-processing-with-the-wcf-nettcp-adapter"></a>チュートリアル: カスタム メッセージを Wcf-nettcp アダプターを使用した処理
このチュートリアルでは、WCF-NetTcp アダプターを使用して、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] クライアントから BizTalk 受信場所に、バイナリ JPEG イメージ データが埋め込まれた [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージを送信します。 バイナリ エンコードされた JPEG イメージを取得による (Base64 ノード エンコード) と XPath ステートメントを使用して、抽出された、**受信メッセージの本文**アダプターの構成で設定します。 XPath 処理は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で受信メッセージの処理に使用される既定の方法とは異なります。 既定の方法で、アダプターはのすべての内容を取得します、**本文**の要素、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]メッセージ、および BizTalk メッセージ ボックス データベースに送信します。 XPath メッセージ処理では、受信 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] メッセージの特定の部分が抽出されてカスタム BizTalk メッセージが作成されます。 このサンプルで XPath 処理がという名前の XML 要素を検索**SendPicture**着信[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]メッセージ (これは XML 形式)。 この要素が検出されると、Base64 エンコードされたバイナリ オブジェクトとしての要素の値が抽出され、そのバイナリ値が BizTalk メッセージに配置されます。 このメッセージはメッセージ ボックス データベースに発行された後、送信ポート フィルター サブスクリプションを使用して FILE 送信ポートに出力されます。 このサンプルでオーケストレーションは使用されず、すべての処理は XPath を使用して BizTalk メッセージング経由で行われます。  

 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターは、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] クライアントと [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] リモート サービスの通信に使用されます。  これによりオーケストレーションおよびスキーマを [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスとして公開することが可能になります。また、オーケストレーションで外部 WCF サービスを使用できるようになります。 Wcf-nettcp アダプターを使用して、 **NetTcpBinding**バインディングで、最適化されたバイナリ メッセージ エンコーディングを使用して、TCP トランスポートを意味します。 WCF-NetTcp アダプターは、送信アダプターと受信アダプターの 2 つで構成されます。 このアダプタからは、SOAP セキュリティ、信頼性、およびトランザクションの各機能にフル アクセスできます。  

 このチュートリアルを完了すると、次のタスクを実行できるようになります。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して MSI ファイルをインポートし、送信ポート、受信ポート、および受信場所を作成する。  

- 使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、構成、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]受信場所からデータを抽出する XPath ステートメントを実行する、 **SendPicture**の要素、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]メッセージ。  

> [!NOTE]
>  **Hosttrusted**要素は、受信ハンドラーに関連付けられているホストが信頼されているかどうかを指定します。 bindings.xml ファイルでは、この要素は既定の `false` に設定されています。これは、このサンプルでは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンタープライズ シングル サインオン サービス (SSO) を使用しないためです。 SSO を使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でユーザー資格情報を渡してサードパーティのアプリケーションを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と統合することができます。 `false` に設定されている場合、BizTalk サービスの SSO 処理の一環として BizTalk メッセージが渡されることはありません。  

## <a name="prerequisites"></a>前提条件  
 このサンプルではを手順がを環境に次の前提条件がインストールされることを確認を実行するには  

- アセンブリをビルドし、展開プロセスを実行するコンピューターと、サンプルを実行しているコンピューターの両方の必要な Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、Microsoft [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]、および Microsoft BizTalk Server です。  

- アセンブリのビルドと展開プロセスの実行に使用するコンピューターには、Microsoft Visual Studio が必要です。  

- サンプルを実行するコンピューターには、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アダプターと [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 管理ツールが必要です。 これらは、Microsoft BizTalk Server のセットアップ時にインストールするオプションです。  

- 管理タスクの実行に使用するコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション設定を構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーであるユーザー アカウントとして実行する必要があります。 また、アプリケーションの展開、ホスト インスタンスの管理、およびその他の必要なタスクを実行するには、このユーザー アカウントはローカル管理者グループのメンバーである必要もあります。  

- 必要とする任意のコンピューターで[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]機能により、1 回限りのセットアップの手順を完了、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サンプル[ http://go.microsoft.com/fwlink/?LinkId=135510](http://go.microsoft.com/fwlink/?LinkId=135510)します。  

- サンプルを実行して .msi ファイルを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にインポートするコンピューターで、ホストが信頼されたホストではないことを確認します。信頼されているホストの場合、インポートは失敗します。  

- チュートリアルのコードをダウンロードし、コンピューターに展開する必要があります。  このチュートリアルでは全体の一部[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]アダプター チュートリアル パッケージ。 ファイルをダウンロードする**WCFAdapterWalkthroughs.exe**から、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]デベロッパー センター [ http://go.microsoft.com/fwlink/?LinkId=194140](http://go.microsoft.com/fwlink/?LinkId=194140)します。  

### <a name="configure-the-wcfcustommessageprocessing-application-and-artifacts"></a>WCFCustomMessageProcessing アプリケーションとアイテムを構成する  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**アプリケーション**を選択します**インポート**、し、 **MSI ファイル**します。 移動して、 **C:\WCFCustomMessageProcessing\WCFCustomMessageProcessing.msi**ファイルを開き、をクリックし、**オープン**します。 これにより、このアプリケーションに次のアイテムが作成されます。  

   - **FileSP**送信ポート: のローカル ファイル システム上の場所**C:\WCFCustomMessageProcessing\Out**によって JPEG イメージ データの送信先[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]としてサンプルの処理の最終的な出力。 送信ポート フィルターを表示する**BTS します。ReceivePortName = NetTcpRP**で構成されている、 **FileSP プロパティ**ダイアログ ボックスで **フィルター**します。 このフィルターは、NetTcp 受信ポートに関連付けられています。 受信ポートに、FileSP 送信 NetTcpRP で受け取ったメッセージの送信ポートの出力場所**C:\WCFCustomMessageProcessing\Out**後、受信場所がメッセージで XPath 処理を実行します。  

   - **NetTcpRP**受信ポート: を論理的に含むポート、 **NetTcpRL**受信場所。  

   - **NetTcpRL**受信場所: 既定値を使用してこの**PassThroughTransmit**イメージから受信したデータのパイプラインと Wcf-nettcp アダプターを JPEG をプルする XPath ステートメントを実行する[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]メッセージ。  

### <a name="alternative-steps-to-configure-the-wcfcustommessageprocessing-application"></a>WCFCustomMessageProcessing アプリケーションを構成する別の手順  

- また、ここで、手動の手順を使用せず、アプリケーションを構成するのには、 **C:\WCFCustomMessageProcessing\bindings.xml**ファイル。 前のバインド ファイル インポート プロセスが正しく機能する場合はこれを実行する必要はありません。  しかし、目をとおしておくことで、MSI ファイルの役割について理解を深めることができます。  

- 一方向の受信ポートの作成 (**NetTcpRP**) と受信場所 (**NetTcpRL**)。  

  1. 展開、 **WCFCustomMessageProcessing**アプリケーションを右クリックして**受信ポート**を選択します**新規**を選択し、**一方向の受信ポート**. **受信ポートのプロパティ** ダイアログ ボックスに、入力`NetTcpRP`の**名前**、 をクリック**OK**します。  

  2. 右クリックし、 **NetTcpRP**受信ポートを選択します**新規**、選択および**受信場所**します。 **受信場所のプロパティ** ダイアログ ボックスに、入力`NetTcRL`の**名前**します。 **トランスポート**セクションで、、**型**ドロップダウン リスト ボックスで、 **Wcf-nettcp**クリックしてドロップダウン リストから**構成**.  

  3. **全般** タブで、入力**net.tcp://localhost/NetTcpRL/Image**で、**アドレス (uri)** フィールド。  

  4. **セキュリティ**タブで、設定、**セキュリティ モード**に**なし。**  

  5. **メッセージ**] タブで、[、**パス**オプション、**受信 BizTalk メッセージ本文**、入力と`/*[local-name()="SendPicture" and namespace-uri()='http://tempuri.org/']/*[local-name()="stream"]`ボディ パス式の。 選択**Base64**として、**ノード エンコード**します。 **パス**オプションが値に設定されているための本文、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]メッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を受け取る次の形式では、:  **\<SendPicture xmlns ="http://tempuri.org/"\>\<ストリーム\>*でエンコードされたバイナリの画像データを実際の base 64*\<ストリーミング/\>\</SendPicture\>**  

  6. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**します。  

- NetTcpRP 受信ポートをサブスクライブする一方向のファイル送信ポート (FileSP) を作成します。  

  1.  右クリック**送信ポート**を選択します**新規**、選び**一方向の受信ポート**します。 選択**静的な一方向ポート**します。 入力`FileSP`の**名前**します。  

  2.  **トランスポート**セクションで、、**型**ドロップダウン リスト ボックスで、**ファイル**クリックしてドロップダウン リストから**構成**します。  

  3.  [**先フォルダー**入力`C:\WCFCustomMessageProcessing\Out`、] をクリック **[ok]** します。  

  4.  クリックして**フィルター**を選択します`BTS.ReceivePortName == NetTcpRP`、順にクリックします**ok をクリックします。**  

### <a name="configure-the-send-port-and-run-the-application"></a>送信ポートを構成してアプリケーションを実行する  

1. 右クリックし、 **WCFCustomMessageProcessing**アプリケーションと選択**開始**します。 これにより、NetTcpRL 受信場所が有効になり、FileSP 送信ポートが開始されます。  

2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を開き、`Client.sln`ファイルから、 **C:WCFCustomMessageProcessing\Client**フォルダー。 ソリューション エクスプ ローラーで右クリックし、**クライアント**順に選択して**ビルド**します。  

3. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] **デバッグ**、し、 **デバッグなしで開始**Client.exe アプリケーションを実行します。 イメージが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信されたというメッセージがコマンド プロンプトに表示されます。  

4. 確認の送信ポート ファイル フォルダーに正常な {GUID} .jpg ファイル出力**C:\WCFCustomMessageProcessing\Out**します。これは、JPEG ファイルを抽出して FILE 送信ポートに書き込むというアプリケーションの処理が正常に終了したことを示しています。
