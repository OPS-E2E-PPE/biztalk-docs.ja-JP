---
title: "チュートリアル: モジュール 3 - オーケストレーションからの SharePoint プロパティへのアクセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, orchestrations
- Windows SharePoint Services adapter tutorials, accessing SharePoint properties
ms.assetid: 310c4002-3416-44c6-b409-1d5467063e28
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a44fd7e30bf511ee77cc1f3e79f6ba63908259ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-module-3---accessing-sharepoint-properties-from-an-orchestration"></a>チュートリアル: モジュール 3 - オーケストレーションからの SharePoint プロパティへのアクセス
このチュートリアルでは、継続の[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)し、受信メッセージでの Windows SharePoint Services コンテキスト プロパティにアクセスする方法を示します実行時間とし、動的ポート、オーケストレーションでのプロパティに基づいてメッセージの送信先を判断します。 概要については、Windows SharePoint Services アダプターを参照してください。 [Windows SharePoint Services アダプターは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件は、次のとおりです。  
  
-   [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] で完全インストール済みの [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] が稼働している形のシングル サーバー展開が必要です。  
  
-   次のチュートリアルを完了する必要があります:[チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信する](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)と[チュートリアル: モジュール 2 - Windows と Office の統合SharePoint Services アダプター](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)  
  
 複数のサーバーの展開で Windows SharePoint Services アダプターを使用する方法については、次を参照してください。[の設定と Windows SharePoint Services アダプターを展開する](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)です。  
  
## <a name="modify-the-biztalk-project"></a>BizTalk プロジェクトの変更  
 PurchaseOrder スキーマを変更するこの手順で[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)です。 この手順は、スキーマ プロパティを昇格させ、BizTalk オーケストレーションで容易にアクセスできるようにする方法を示しています。  
  
#### <a name="modify-the-purchaseorderxsd-schema"></a>PurchaseOrder.xsd スキーマの変更  
  
1.  開始**Microsoft Visual Studio**です。  
  
2.  をクリックして**ファイル**、 をクリックして**開く**、順にクリック**プロジェクト/ソリューション**です。  
  
3.  参照、`OrderProcess.sln`ファイルを開き、をクリックして**開く**です。  
  
4.  **ソリューション エクスプ ローラー**を右クリックし、`OrderProcessSchema.xsd`ファイルを開き、をクリックして**開く**です。  
  
5.  **BizTalk エディター**、展開`PurchaseOrder`です。  
  
6.  右クリック`Amount`をクリックして**昇格**、順にクリック**クイック昇格**です。  
  
7.  **[OK]**をクリックします。  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、これに対応するプロパティ スキーマが現在のプロジェクト内に作成されます。  
  
8.  `PurchaseOrder.xsd` を保存します。  
  
## <a name="create-an-orchestration"></a>オーケストレーションの作成  
 ここでは、新しい BizTalk オーケストレーションを作成します。 この手順により、Windows SharePoint Services アダプターが受信したメッセージを処理するためのオーケストレーションが作成されます。  
  
#### <a name="add-a-biztalk-orchestration"></a>BizTalk オーケストレーションの追加  
  
1.  **ソリューション エクスプ ローラー**を右クリックし、`OrderProcess`プロジェクトで、をクリックして**追加**、クリックして**新しい項目の**します。  
  
2.  **カテゴリ****オーケストレーション ファイル**です。  
  
3.  **テンプレート** **BizTalk オーケストレーション**です。  
  
4.  型`MyCompanyOrderProcessing`で、**名前**フィールドをクリックして**追加**です。  
  
## <a name="create-receive-information"></a>受信情報の作成  
 ここでは、オーケストレーションの新しいメッセージ、受信ポート、受信図形を作成します。 この手順は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からメッセージを受信するオーケストレーションの構成方法を示しています。  
  
#### <a name="create-a-new-message"></a>新しいメッセージの作成  
  
1.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。 `Message_1` という名前の新しいメッセージが生成されます。  
  
2.  右クリック`Message_1`をクリックして**の名前を変更**、し、入力`Message_PO`です。  
  
3.  右クリック`Message_PO`、クリックして**プロパティ ウィンドウ**します。  
  
4.  **メッセージの種類**プロパティ、展開**スキーマ**、し、`OrderProcess.OrderProcessSchema`スキーマです。  
  
#### <a name="add-a-receive-port-to-the-orchestration"></a>オーケストレーションへの受信ポートの追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグ、**ポート**図形をポート画面にします。 ポート構成ウィザードが起動します。  
  
2.  [ようこそ] 画面で、をクリックして**次**です。  
  
3.  型`ReceivePurchaseOrder`で、**名前**フィールド、およびをクリックして**次**です。  
  
4.  選択**新しいポートの種類を作成する**です。  
  
5.  型`PurchaseOrderPT`で、**ポートの種類名**フィールドをクリックして**次**です。  
  
6.  **画面のポートのバインド**で、既定値のままにし、クリックして**次**です。  
  
7.  **[完了]**をクリックします。  
  
8.  **オーケストレーション****ポートの種類**、展開、`PurchaseOrderPT`ポートの種類。  
  
9. 右クリック`Operation_1`をクリックして**の名前を変更**、し、入力`PurchaseOrderOperation`です。  
  
#### <a name="add-a-receive-shape-to-the-orchestration"></a>オーケストレーションへの受信図形の追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグ、**受信**オーケストレーションへの図形です。  
  
2.  受信図形を右クリックし、をクリックして**プロパティ ウィンドウ**します。  
  
3.  設定、 **Activate**プロパティを`True`です。  
  
    > [!NOTE]
    >  "アクティブ化" プロパティを false に設定すると、"エラー X2214: 自己関連付けを行わないポート上での非アクティベーション受信に対して、既に初期化されている関連付けセットを少なくとも 1 つ指定する必要があります" というエラーが表示されます。  
  
4.  型`Receive_PO`で、**名前**フィールドです。  
  
5.  **プロパティ] ウィンドウ**[`Message_PO`メッセージ プロパティのです。  
  
6.  選択`ReceivePurchaseOrder.PurchaseOrderOperation.Request`の**操作**プロパティです。 オーケストレーション デザイナの受信図形にポートが連結されます。  
  
## <a name="create-send-information"></a>送信情報の作成  
 ここでは、オーケストレーションに新しいメッセージ、送信ポート、判断構造を作成します。 この手順は、判断ロジックを使ったオーケストレーションの構成方法、および、メッセージを送信ポートに送るようにオーケストレーションを構成する方法を示しています。  
  
#### <a name="create-a-new-message"></a>新しいメッセージの作成  
  
1.  **オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。 `Message_1` という名前の新しいメッセージが生成されます。  
  
2.  右クリック`Message_1`をクリックして**の名前を変更**、し、入力`Message_Task`です。  
  
3.  右クリック`Message_Task`、クリックして**プロパティ ウィンドウ**します。  
  
4.  **メッセージの種類**プロパティ、展開**スキーマ**、し、`OrderProcess.OrderProcessSchema`スキーマです。  
  
#### <a name="add-a-send-port-to-the-orchestration"></a>オーケストレーションへの送信ポートの追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグ、**ポート**図形をポート画面にします。 ポート構成ウィザードが起動します。  
  
2.  [ようこそ] 画面で、をクリックして**次**です。  
  
3.  型`SendPurchaseOrder`で、**名前**フィールド、およびをクリックして**次**です。  
  
4.  選択**既存のポートの種類を使用して**です。  
  
5.  **使用可能なポートの種類** `OrderProcess.PurchaseOrderPT`、順にクリック**次へ**です。  
  
6.  **画面のポートのバインド****ポートの通信方向** `I'll always be sending messages on this port`、順にクリック**次へ**です。  
  
7.  **[完了]**をクリックします。  
  
#### <a name="add-a-send-shape-to-the-orchestration"></a>オーケストレーションへの送信図形の追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグ、**送信**図形をオーケストレーション デザイナにします。 `Receive_PO` 受信図形の下に配置します。  
  
2.  送信図形を右クリックし、をクリックして**プロパティ ウィンドウ**します。  
  
3.  型`Send_PO`で、**名前**フィールドです。  
  
4.  選択`Message_PO`の**メッセージ**プロパティです。  
  
5.  選択`SendPurchaseOrder.PurchaseOrderOperation.Request`の**操作**プロパティです。 オーケストレーション デザイナの送信図形にポートが連結されます。  
  
#### <a name="add-a-decide-shape-to-the-orchestration"></a>オーケストレーションへの判断図形の追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグ、**判断**図形をオーケストレーション デザイナにします。 `Send_PO` 送信図形の下に配置します。  
  
2.  判断図形を右クリックし、をクリックして**プロパティ ウィンドウ。**  
  
3.  型`NeedsApproval`で、**名前**フィールドです。  
  
4.  オーケストレーション デザイナーで、をクリックして**Rule_1**判断図形にします。  
  
5.  プロパティ ウィンドウで、次のように入力します。`ApprovalRequired`の、**名前**プロパティです。  
  
6.  クリックして、**式**プロパティ フィールドに、クリックして、省略記号 (**.**) ボタンをクリックします。  
  
7.  BizTalk 式エディターに、以下の式を入力またはコピーします。  
  
    ```  
    Message_PO(OrderProcess.PropertySchema.Amount) > 1000  
    ```  
  
8.  **[OK]**をクリックします。  
  
#### <a name="add-another-send-port-to-the-orchestration"></a>オーケストレーションへの別の送信ポートの追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグ、**ポート**図形をポート画面にします。 ポート構成ウィザードが起動します。  
  
2.  [ようこそ] 画面で、をクリックして**次**です。  
  
3.  型`SendToTasksList`で、**名前**フィールド、およびをクリックして**次**です。  
  
4.  選択**既存のポートの種類を使用して**です。  
  
5.  **使用可能なポートの種類** `OrderProcess.PurchaseOrderPT`、順にクリック**次へ**です。  
  
6.  **画面のポートのバインド****ポートの通信方向**`I'll always be sending messages on this port`です。  
  
7.  **ポートのバインド** `Dynamic`、順にクリック**次へ**です。  
  
8.  **[完了]**をクリックします。  
  
#### <a name="add-a-send-shape-to-the-decide-shape"></a>判断図形への送信図形の追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグ、**送信**図形をオーケストレーション デザイナにします。 `ApprovalRequired` 図形の下に配置します。  
  
2.  送信図形を右クリックし、をクリックして**プロパティ ウィンドウ**  
  
3.  型`CreateApprovalTask`で、**名前**フィールドです。  
  
4.  選択`Message_Task`の**メッセージ**プロパティです。  
  
5.  選択`SendToTasksList.PurchaseOrderOperation.Request`の**操作**プロパティです。 オーケストレーション デザイナの送信図形にポートが連結されます。  
  
## <a name="create-an-expression"></a>式の作成  
 ここでは、To Do パス値を変数に代入する式図形をソリューションに追加します。 この手順は、動的送信ポートのプロパティを変更するためのロジックをオーケストレーションに追加する方法を示しています。  
  
#### <a name="create-a-new-expression"></a>新しい式の作成  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグ、**式**図形の前に、`CreateApprovalTask`送信図形。  
  
2.  式図形を右クリックし、をクリックして**プロパティ ウィンドウ。**  
  
3.  型`SetPortDestination`で、**名前**フィールドです。  
  
4.  クリックして、**式**プロパティ フィールドに、クリックして、省略記号 (**.**) ボタンをクリックします。  
  
5.  **BizTalk 式エディタ**次を入力します。  
  
    ```  
    SendToTasksList(Microsoft.XLANGs.BaseTypes.Address) = "wss://localhost/sites/WSSAdapterWalkthrough/Lists/Tasks/";  
    ```  
  
6.  **[OK]**をクリックします。  
  
## <a name="construct-a-new-message"></a>新しいメッセージの構築  
 ここでは、ある種類のメッセージの新しいインスタンスをオーケストレーションに構築する、メッセージ構築図形をソリューションに追加します。 この手順は、受信メッセージをコピーして新しいメッセージを作成し、そのコンテキスト プロパティを変更する方法を示しています。 BizTalk 内ではメッセージは不変である、つまり、作成した後に元のメッセージに変更を加えることはできないため、この手順が必要になります。  
  
#### <a name="add-a-construct-shape"></a>メッセージ構築図形の追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグ、**メッセージの構築**図形の前に、`SetPortDestination`式図形です。  
  
2.  メッセージの構築図形を右クリックし、をクリックして**プロパティ ウィンドウ。**  
  
3.  型`ConstructTaskMessage`で、**名前**フィールドです。  
  
4.  選択`Message_Task`の**構築メッセージ**プロパティです。  
  
5.  **BizTalk オーケストレーション**、ツールボックスのドラッグ、**メッセージの割り当て**図形を`ConstructTaskMessage`**メッセージの構築**図形です。  
  
6.  **プロパティ ウィンドウ**、型`InitTaskMessage`で、**名前**フィールドです。  
  
7.  クリックして、**式**プロパティ フィールドに、クリックして、省略記号 (**.**) ボタンをクリックします。  
  
8.  **BizTalk 式エディタ**を入力するか、以下をコピーします。  
  
    ```  
    Message_Task = Message_PO;  
    Message_Task(WSS.ConfigOverwrite) = "no";  
    Message_Task(WSS.ConfigNamespaceAliases)= "orchns='http://OrderProcess.PurchaseOrder'";  
    Message_Task(WSS.ConfigPropertiesXml) = "<ConfigPropertiesXml><PropertyName1>Title</PropertyName1><PropertySource1>Approve %XPATH=//orchns:PurchaseOrder/orchns:PurchaseOrderID%</PropertySource1><PropertyName3>Status</PropertyName3><PropertySource3>Not Started</PropertySource3><PropertyName4>Priority</PropertyName4><PropertySource4>(1) High</PropertySource4></ConfigPropertiesXml>";  
    ```  
  
    > [!IMPORTANT]
    >  上記のコンテキスト プロパティに指定する値は、大文字と小文字が区別されます。 コンテキスト プロパティと動的なポートの構成値を設定するときに正しい大文字小文字を使用するか、送信ポートを BizTalk の試行を指定したドキュメントをルーティングする場合は、エラーが発生することを確認する必要があります。  
  
9. **[OK]**をクリックします。  
  
10. をクリックして**ファイル**、クリックして**すべてを保存**です。  
  
## <a name="build-the-biztalk-project"></a>BizTalk プロジェクトのビルド  
 ここでは、BizTalk プロジェクトをビルドして配置します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって実行時に使用されるアセンブリを作成および配置するために、この手順が必要になります。  
  
#### <a name="build-and-deploy-the-solution"></a>ソリューションのビルドおよび配置  
  
1.  をクリックして**ビルド**、クリックして**orderprocess のビルド**です。  
  
2.  をクリックして**ビルド**、クリックして**orderprocess の配置**です。  
  
3.  [Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]] を閉じます。  
  
## <a name="modify-the-receive-location-and-send-port"></a>受信場所と送信ポートの変更  
 ここでは、既存の受信場所と送信ポートを、パイプラインで XML 処理を行うように変更します。 受信 XML パイプラインでは、オーケストレーション処理中に使用されたメッセージ プロパティが保持されます。また、送信 XML パイプラインでは、オーケストレーションで適用されたメッセージ プロパティ (後でメッセージ ルーティングに使用される) が保持されます。  
  
#### <a name="modify-the-receive-location"></a>受信場所を変更します。  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソールです。**  
  
2.  展開**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理スナップイン**、展開**BizTalk グループ**、展開**アプリケーション**の展開**BizTalk アプリケーション 1**、をクリックし、**受信場所**ノード。  
  
3.  右クリック`SourceLocation`、クリックして**プロパティ**です。  
  
4.  **受信場所のプロパティ**ダイアログ ボックスで、**全般**`XMLReceive`の**受信パイプライン**プロパティです。  
  
5.  **[OK]**をクリックします。  
  
#### <a name="modify-the-send-port"></a>送信ポートの変更  
  
1.  クリックして、**送信ポート**ノード。  
  
2.  右クリック`SendToDestination`、クリックして**プロパティ**です。  
  
3.  **送信ポートのプロパティ**ダイアログ ボックスで、**全般**`XMLTransmit`の**送信パイプライン**プロパティです。  
  
4.  選択、**フィルター**タブです。  
  
5.  既存の条件を選択して、del キー、およびをクリックして**OK**です。  
  
#### <a name="start-a-new-send-port"></a>新しい送信ポートの開始  
  
1.  クリックして、**送信ポート**ノード。  
  
2.  右クリック`OrderProcess_1.0.0.0_OrderProcess.MyCompanyOrderProcess_SendToTasksList_<GUID>`、クリックして**開始**です。  
  
> [!NOTE]
>  これが表示されない場合は、コンソールを更新する必要があります。  
  
## <a name="bind-the-orchestration"></a>オーケストレーションをバインドします  
 ここでは、指定したポートにオーケストレーションをバインドします。 ビルドと配置が済んだオーケストレーションに対し、物理ポートを関連付けるために、この手順が必要になります。  
  
#### <a name="bind-the-orchestration"></a>オーケストレーションをバインドします  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**オーケストレーション**ノード。  
  
2.  右クリックし、`OrderProcess.MyCompanyOrderProcessing`オーケストレーション、およびクリック**プロパティ**です。  
  
3.  選択、**バインド**タブです。  
  
4.  **ホスト**`BizTalkServerApplication`で、**ホスト**フィールドです。  
  
5.  **バインド**`FromSource`の`ReceivePurchaseOrder`受信論理ポートです。  
  
6.  **バインド**`SendToDestination`の`SendPurchaseOrder`論理送信ポート。  
  
7.  **[OK]**をクリックします。  
  
8.  右クリックして`OrderProcess.MyCompanyOrderProcessing`オーケストレーション、およびクリック**開始**です。  
  
## <a name="send-a-message-through-the-system"></a>システムからのメッセージ送信  
 ここでは、InfoPath フォームを作成し、Windows SharePoint Services Web サイトにアップロードします。 そのメッセージは Windows SharePoint Services アダプターによって取得され、アーカイブ ドキュメント ライブラリにアーカイブされた後、アップロード先のドキュメント ライブラリに送信されます。 このメッセージを処理する間、送信先を判断するために Windows SharePoint Services のコンテキスト プロパティにアクセスします。  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a>システムから送信する InfoPath フォームの作成  
  
1.  Web ブラウザを開き、作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2.  クイック起動メニューの `InfoPathSolutions` をクリックします。  
  
3.  クリックして、`PurchaseOrder`に表示されるファイル、**ファイルのダウンロード**クリックしてダイアログ ボックスで、**開く**です。 フォームが読み込まれます。  
  
4.  **Purchase Order ID**フィールドに「`1003`です。  
  
5.  **請求先**フィールドに「`John Doe`です。  
  
6.  **量**フィールドに「`1750`です。  
  
7.  **Purchase Order Date**フィールドに「`1/3/2005`です。  
  
8.  **[保存]**をクリックします。  
  
9. **名前を付けて保存** ダイアログ ボックスで、「`http://<server_name>/sites/WSSAdapterWalkthrough/Source`で、**ファイル名**フィールド、および ENTER キーを押します。  
  
10. 型`PurchaseOrder3.xml`で、**ファイル名**フィールドをクリックして**保存**です。  
  
11. InfoPath を終了します。  
  
12. Web ブラウザーで、をクリックして**ドキュメントし、リスト**です。  
  
13. **ドキュメント ライブラリ**をクリックして**先**です。  
  
14. 移行先ドキュメント ライブラリに表示されます、メッセージのこのライブラリの一覧です。 アーカイブ ドキュメント ライブラリにアーカイブされたコピーも紹介します。  
  
15. **[ホーム]**をクリックします。  
  
16. **を一覧表示**をクリックして**タスク**です。  
  
17. To Do リストに、新しく作成した承認済みのアイテムが表示されます。  
  
> [!NOTE]
>  注文書の総額が $1,000.00 を超えていたので、タスクが作成されます。  
  
## <a name="summary"></a>概要  
 このチュートリアルでは、Windows SharePoint Services のコンテキスト プロパティにアクセスする方法、および動的ポートを経由してメッセージの送信先を判断する方法を確認しました。  
  
## <a name="next-steps"></a>次の手順  
 Windows SharePoint Services アダプター セクションの残りの部分に進んでください。 詳細については、「関連項目」の該当するトピックを参照してください。  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services アダプターとは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services アダプタのチュートリアル](../core/windows-sharepoint-services-adapter-walkthroughs.md)