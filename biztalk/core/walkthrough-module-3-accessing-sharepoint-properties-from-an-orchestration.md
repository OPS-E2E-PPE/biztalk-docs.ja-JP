---
title: 'チュートリアル: モジュール 3 - オーケストレーションからの SharePoint プロパティへのアクセス |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, orchestrations
- Windows SharePoint Services adapter tutorials, accessing SharePoint properties
ms.assetid: 310c4002-3416-44c6-b409-1d5467063e28
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0d66a381403f8649174046cb249ff92a644ac15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006827"
---
# <a name="walkthrough-module-3---accessing-sharepoint-properties-from-an-orchestration"></a>チュートリアル: モジュール 3 - オーケストレーションからの SharePoint プロパティへのアクセス
このチュートリアルの続きでは、[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)で受信メッセージの Windows SharePoint Services コンテキスト プロパティにアクセスする方法を示します実行時間とし、オーケストレーションでの動的ポートを使用してプロパティに基づいてメッセージの送信先を判断します。 Windows SharePoint Services アダプターの概要についてを参照してください。 [、Windows SharePoint Services アダプターとは何ですか?](../core/what-is-the-windows-sharepoint-services-adapter.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件は、次のとおりです。  
  
- シングル サーバー配置で実行されている BizTalk Server の完全インストールする必要があります[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]します。  
  
- 次のチュートリアルを完了する必要があります:[チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信する](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)と[チュートリアル: モジュール 2 -、Windows と Office の統合SharePoint Services アダプター](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)  
  
  マルチ サーバー展開で、Windows SharePoint Services アダプターを使用する方法の詳細については、次を参照してください。[設定と、Windows SharePoint Services アダプターを展開する](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)します。  
  
## <a name="modify-the-biztalk-project"></a>BizTalk プロジェクトの変更  
 この手順を PurchaseOrder スキーマを変更して[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)します。 この手順は、スキーマ プロパティを昇格させ、BizTalk オーケストレーションで容易にアクセスできるようにする方法を示しています。  
  
#### <a name="modify-the-purchaseorderxsd-schema"></a>PurchaseOrder.xsd スキーマの変更  
  
1. 開始**Microsoft Visual Studio**します。  
  
2. クリックして**ファイル**、 をクリックして**オープン**、順にクリックします**プロジェクト/ソリューション**します。  
  
3. 参照、`OrderProcess.sln`ファイルを開き、をクリックし、**オープン**します。  
  
4. **ソリューション エクスプ ローラー**を右クリックし、`OrderProcessSchema.xsd`ファイルを開き、をクリックし、**オープン**します。  
  
5. **BizTalk エディター**、展開`PurchaseOrder`します。  
  
6. 右クリック`Amount`、 をクリックして**昇格**、 をクリックし、**クイック昇格**します。  
  
7. **[OK]** をクリックします。  
  
   > [!NOTE]
   >  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、これに対応するプロパティ スキーマが現在のプロジェクト内に作成されます。  
  
8. `PurchaseOrder.xsd` を保存します。  
  
## <a name="create-an-orchestration"></a>オーケストレーションの作成  
 ここでは、新しい BizTalk オーケストレーションを作成します。 この手順により、Windows SharePoint Services アダプターが受信したメッセージを処理するためのオーケストレーションが作成されます。  
  
#### <a name="add-a-biztalk-orchestration"></a>BizTalk オーケストレーションの追加  
  
1.  **ソリューション エクスプ ローラー**を右クリックし、`OrderProcess`プロジェクトで、をクリックして**追加**、 をクリックし、**新しい項目の**します。  
  
2.  **カテゴリ**、**オーケストレーション ファイル**します。  
  
3.  **テンプレート**、 **BizTalk オーケストレーション**します。  
  
4.  型`MyCompanyOrderProcessing`で、**名前**フィールドをクリックして**追加**します。  
  
## <a name="create-receive-information"></a>受信情報の作成  
 ここでは、オーケストレーションの新しいメッセージ、受信ポート、受信図形を作成します。 この手順は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からメッセージを受信するオーケストレーションの構成方法を示しています。  
  
#### <a name="create-a-new-message"></a>新しいメッセージの作成  
  
1.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。 `Message_1` という名前の新しいメッセージが生成されます。  
  
2.  右クリックして`Message_1`、 をクリックして**の名前を変更**、し、入力`Message_PO`します。  
  
3.  右クリック`Message_PO`、 をクリックし、**プロパティ ウィンドウ**します。  
  
4.  **メッセージの種類**プロパティ、展開**スキーマ**、し、`OrderProcess.OrderProcessSchema`スキーマ。  
  
#### <a name="add-a-receive-port-to-the-orchestration"></a>オーケストレーションへの受信ポートの追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグを**ポート**図形をポート画面にします。 ポート構成ウィザードが起動します。  
  
2.  [ようこそ] 画面で、次のようにクリックします。**次**します。  
  
3.  型`ReceivePurchaseOrder`で、**名前**フィールドをクリックして**次**します。  
  
4.  選択**新しいポートの種類を作成する**します。  
  
5.  型`PurchaseOrderPT`で、**ポートの種類名**フィールドをクリックして**次**。  
  
6.  **画面のポートのバインド**、既定値のままにし、クリックして**次**します。  
  
7.  **[完了]** をクリックします。  
  
8.  **オーケストレーション****ポートの種類**、展開、`PurchaseOrderPT`ポートの種類。  
  
9. 右クリックして`Operation_1`、 をクリックして**の名前を変更**、し、入力`PurchaseOrderOperation`します。  
  
#### <a name="add-a-receive-shape-to-the-orchestration"></a>オーケストレーションへの受信図形の追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグを**受信**オーケストレーションへの図形。  
  
2.  受信図形を右クリックし、**プロパティ ウィンドウ**します。  
  
3.  設定、 **Activate**プロパティを`True`します。  
  
    > [!NOTE]
    >  "アクティブ化" プロパティを false に設定すると、"エラー X2214: 自己関連付けを行わないポート上での非アクティベーション受信に対して、既に初期化されている関連付けセットを少なくとも 1 つ指定する必要があります" というエラーが表示されます。  
  
4.  型`Receive_PO`で、**名前**フィールド。  
  
5.  **プロパティ ウィンドウ**を選択します`Message_PO`メッセージ プロパティ。  
  
6.  選択`ReceivePurchaseOrder.PurchaseOrderOperation.Request`の**操作**プロパティ。 オーケストレーション デザイナの受信図形にポートが連結されます。  
  
## <a name="create-send-information"></a>送信情報の作成  
 ここでは、オーケストレーションに新しいメッセージ、送信ポート、判断構造を作成します。 この手順は、判断ロジックを使ったオーケストレーションの構成方法、および、メッセージを送信ポートに送るようにオーケストレーションを構成する方法を示しています。  
  
#### <a name="create-a-new-message"></a>新しいメッセージの作成  
  
1.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。 `Message_1` という名前の新しいメッセージが生成されます。  
  
2.  右クリックして`Message_1`、 をクリックして**の名前を変更**、し、入力`Message_Task`します。  
  
3.  右クリック`Message_Task`、 をクリックし、**プロパティ ウィンドウ**します。  
  
4.  **メッセージの種類**プロパティ、展開**スキーマ**、し、`OrderProcess.OrderProcessSchema`スキーマ。  
  
#### <a name="add-a-send-port-to-the-orchestration"></a>オーケストレーションへの送信ポートの追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグを**ポート**図形をポート画面にします。 ポート構成ウィザードが起動します。  
  
2.  [ようこそ] 画面で、次のようにクリックします。**次**します。  
  
3.  型`SendPurchaseOrder`で、**名前**フィールドをクリックして**次**します。  
  
4.  選択**既存のポートの種類を使用して、** します。  
  
5.  **使用可能なポートの種類**を選択します`OrderProcess.PurchaseOrderPT`、順にクリックします**次**します。  
  
6.  **画面のポートのバインド****ポートの通信方向**を選択します`I'll always be sending messages on this port`、順にクリックします**次**します。  
  
7.  **[完了]** をクリックします。  
  
#### <a name="add-a-send-shape-to-the-orchestration"></a>オーケストレーションへの送信図形の追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグを**送信**図形をオーケストレーション デザイナにします。 `Receive_PO` 受信図形の下に配置します。  
  
2.  送信図形を右クリックし、**プロパティ ウィンドウ**します。  
  
3.  型`Send_PO`で、**名前**フィールド。  
  
4.  選択`Message_PO`の**メッセージ**プロパティ。  
  
5.  選択`SendPurchaseOrder.PurchaseOrderOperation.Request`の**操作**プロパティ。 オーケストレーション デザイナの送信図形にポートが連結されます。  
  
#### <a name="add-a-decide-shape-to-the-orchestration"></a>オーケストレーションへの判断図形の追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグを**判断**図形をオーケストレーション デザイナにします。 `Send_PO` 送信図形の下に配置します。  
  
2.  判断図形を右クリックし、**プロパティ ウィンドウ。**  
  
3.  型`NeedsApproval`で、**名前**フィールド。  
  
4.  オーケストレーション デザイナーで、次のようにクリックします。 **[rule_1]** 判断図形にします。  
  
5.  プロパティの Windows、入力`ApprovalRequired`の**名前**プロパティ。  
  
6.  をクリックして、**式**プロパティ、フィールドし、省略記号をクリックし、(**.**) ボタンをクリックします。  
  
7.  BizTalk 式エディターに、以下の式を入力またはコピーします。  
  
    ```  
    Message_PO(OrderProcess.PropertySchema.Amount) > 1000  
    ```  
  
8.  **[OK]** をクリックします。  
  
#### <a name="add-another-send-port-to-the-orchestration"></a>オーケストレーションへの別の送信ポートの追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグを**ポート**図形をポート画面にします。 ポート構成ウィザードが起動します。  
  
2.  [ようこそ] 画面で、次のようにクリックします。**次**します。  
  
3.  型`SendToTasksList`で、**名前**フィールドをクリックして**次**します。  
  
4.  選択**既存のポートの種類を使用して、** します。  
  
5.  **使用可能なポートの種類**を選択します`OrderProcess.PurchaseOrderPT`、順にクリックします**次**します。  
  
6.  **画面のポートのバインド****ポートの通信方向**を選択します`I'll always be sending messages on this port`します。  
  
7.  [**ポートのバインド**を選択します`Dynamic`、] をクリックし、**次**。  
  
8.  **[完了]** をクリックします。  
  
#### <a name="add-a-send-shape-to-the-decide-shape"></a>判断図形への送信図形の追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグを**送信**図形をオーケストレーション デザイナにします。 `ApprovalRequired` 図形の下に配置します。  
  
2.  送信図形を右クリックし、**プロパティ ウィンドウ**  
  
3.  型`CreateApprovalTask`で、**名前**フィールド。  
  
4.  選択`Message_Task`の**メッセージ**プロパティ。  
  
5.  選択`SendToTasksList.PurchaseOrderOperation.Request`の**操作**プロパティ。 オーケストレーション デザイナの送信図形にポートが連結されます。  
  
## <a name="create-an-expression"></a>式の作成  
 ここでは、To Do パス値を変数に代入する式図形をソリューションに追加します。 この手順は、動的送信ポートのプロパティを変更するためのロジックをオーケストレーションに追加する方法を示しています。  
  
#### <a name="create-a-new-expression"></a>新しい式の作成  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグ、**式**図形の前に、`CreateApprovalTask`送信図形。  
  
2.  式図形を右クリックし、をクリックし、**プロパティ ウィンドウ。**  
  
3.  型`SetPortDestination`で、**名前**フィールド。  
  
4.  をクリックして、**式**プロパティ、フィールドし、省略記号をクリックし、(**.**) ボタンをクリックします。  
  
5.  **BizTalk 式エディタ**次を入力します。  
  
    ```  
    SendToTasksList(Microsoft.XLANGs.BaseTypes.Address) = "wss://localhost/sites/WSSAdapterWalkthrough/Lists/Tasks/";  
    ```  
  
6.  **[OK]** をクリックします。  
  
## <a name="construct-a-new-message"></a>新しいメッセージの構築  
 ここでは、ある種類のメッセージの新しいインスタンスをオーケストレーションに構築する、メッセージ構築図形をソリューションに追加します。 この手順は、受信メッセージをコピーして新しいメッセージを作成し、そのコンテキスト プロパティを変更する方法を示しています。 BizTalk 内ではメッセージは不変である、つまり、作成した後に元のメッセージに変更を加えることはできないため、この手順が必要になります。  
  
#### <a name="add-a-construct-shape"></a>メッセージ構築図形の追加  
  
1.  **BizTalk オーケストレーション**、ツールボックスのドラッグを**メッセージの構築**図形の前に、`SetPortDestination`式図形。  
  
2.  メッセージの構築図形を右クリックし、**プロパティ ウィンドウ。**  
  
3.  型`ConstructTaskMessage`で、**名前**フィールド。  
  
4.  選択`Message_Task`の**構築メッセージ**プロパティ。  
  
5.  **BizTalk オーケストレーション**、ツールボックスのドラッグを**メッセージの割り当て**図形を`ConstructTaskMessage`**メッセージの構築**図形。  
  
6.  **プロパティ ウィンドウ**、型`InitTaskMessage`で、**名前**フィールド。  
  
7.  をクリックして、**式**プロパティ、フィールドし、省略記号をクリックし、(**.**) ボタンをクリックします。  
  
8.  **BizTalk 式エディタ**を入力するか、以下をコピーします。  
  
    ```  
    Message_Task = Message_PO;  
    Message_Task(WSS.ConfigOverwrite) = "no";  
    Message_Task(WSS.ConfigNamespaceAliases)= "orchns='http://OrderProcess.PurchaseOrder'";  
    Message_Task(WSS.ConfigPropertiesXml) = "<ConfigPropertiesXml><PropertyName1>Title</PropertyName1><PropertySource1>Approve %XPATH=//orchns:PurchaseOrder/orchns:PurchaseOrderID%</PropertySource1><PropertyName3>Status</PropertyName3><PropertySource3>Not Started</PropertySource3><PropertyName4>Priority</PropertyName4><PropertySource4>(1) High</PropertySource4></ConfigPropertiesXml>";  
    ```  
  
    > [!IMPORTANT]
    >  上記のコンテキスト プロパティに指定する値は、大文字と小文字が区別されます。 コンテキスト プロパティが正しい大文字小文字を使用することも、BizTalk を指定したドキュメントをルーティングしようとしたときにエラーが発生することを確認する必要がありますと動的なポートの構成値を設定するときに、ポートを送信します。  
  
9. **[OK]** をクリックします。  
  
10. をクリックして**ファイル**、 をクリックし、**すべて保存**します。  
  
## <a name="build-the-biztalk-project"></a>BizTalk プロジェクトのビルド  
 ここでは、BizTalk プロジェクトをビルドして配置します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって実行時に使用されるアセンブリを作成および配置するために、この手順が必要になります。  
  
#### <a name="build-and-deploy-the-solution"></a>ソリューションのビルドおよび配置  
  
1. をクリックして**ビルド**、 をクリックし、 **orderprocess のビルド**します。  
  
2. をクリックして**ビルド**、 をクリックし、 **orderprocess の配置**します。  
  
3. [Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]] を閉じます。  
  
## <a name="modify-the-receive-location-and-send-port"></a>受信場所と送信ポートの変更  
 ここでは、既存の受信場所と送信ポートを、パイプラインで XML 処理を行うように変更します。 受信 XML パイプラインでは、オーケストレーション処理中に使用されたメッセージ プロパティが保持されます。また、送信 XML パイプラインでは、オーケストレーションで適用されたメッセージ プロパティ (後でメッセージ ルーティングに使用される) が保持されます。  
  
#### <a name="modify-the-receive-location"></a>受信場所を変更します。  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理コンソール。**  
  
2. 展開**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理スナップイン**、展開**BizTalk グループ**、展開**アプリケーション**の展開**BizTalk アプリケーション 1**、 をクリックし、**受信場所**ノード。  
  
3. 右クリックして`SourceLocation`、 をクリックし、**プロパティ**します。  
  
4. **受信場所のプロパティ**ダイアログ ボックスで、**全般**、`XMLReceive`の**受信パイプライン**プロパティ。  
  
5. **[OK]** をクリックします。  
  
#### <a name="modify-the-send-port"></a>送信ポートの変更  
  
1.  をクリックして、**送信ポート**ノード。  
  
2.  右クリックして`SendToDestination`、 をクリックし、**プロパティ**します。  
  
3.  **送信ポートのプロパティ**ダイアログ ボックスで、**全般**を選択します`XMLTransmit`の**送信パイプライン**プロパティ。  
  
4.  選択、**フィルター**タブ。  
  
5.  既存の条件を選択、del キー、および順にクリックします**OK**します。  
  
#### <a name="start-a-new-send-port"></a>新しい送信ポートの開始  
  
1.  をクリックして、**送信ポート**ノード。  
  
2.  右クリック`OrderProcess_1.0.0.0_OrderProcess.MyCompanyOrderProcess_SendToTasksList_<GUID>`、 をクリックし、**開始**します。  
  
> [!NOTE]
>  これが表示されない場合は、コンソールを更新する必要があります。  
  
## <a name="bind-the-orchestration"></a>オーケストレーションをバインドします。  
 ここでは、指定したポートにオーケストレーションをバインドします。 ビルドと配置が済んだオーケストレーションに対し、物理ポートを関連付けるために、この手順が必要になります。  
  
#### <a name="bind-the-orchestration"></a>オーケストレーションをバインドします。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**オーケストレーション**ノード。  
  
2. 右クリックし、`OrderProcess.MyCompanyOrderProcessing`オーケストレーション、およびクリック**プロパティ**します。  
  
3. 選択、**バインド**タブ。  
  
4. **ホスト**、`BizTalkServerApplication`で、**ホスト**フィールド。  
  
5. **バインド**、`FromSource`の`ReceivePurchaseOrder`受信論理ポート。  
  
6. **バインド**、`SendToDestination`の`SendPurchaseOrder`論理送信ポート。  
  
7. **[OK]** をクリックします。  
  
8. 右クリックして`OrderProcess.MyCompanyOrderProcessing`オーケストレーション、およびクリック**開始**します。  
  
## <a name="send-a-message-through-the-system"></a>システムからのメッセージ送信  
 ここでは、InfoPath フォームを作成し、Windows SharePoint Services Web サイトにアップロードします。 そのメッセージは Windows SharePoint Services アダプターによって取得され、アーカイブ ドキュメント ライブラリにアーカイブされた後、アップロード先のドキュメント ライブラリに送信されます。 このメッセージを処理する間、送信先を判断するために Windows SharePoint Services のコンテキスト プロパティにアクセスします。  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a>システムから送信する InfoPath フォームの作成  
  
1.  Web ブラウザを開き、作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2.  クイック起動メニューの `InfoPathSolutions` をクリックします。  
  
3.  をクリックして、`PurchaseOrder`ファイルを表示する、**ファイルのダウンロード**クリックしてダイアログ ボックスで、**オープン**します。 フォームが読み込まれます。  
  
4.  **Purchase Order ID**フィールドに「`1003`します。  
  
5.  **請求先**フィールドに「`John Doe`します。  
  
6.  **量**フィールドに「`1750`します。  
  
7.  **発注書日付**フィールドに「`1/3/2005`します。  
  
8.  **[保存]** をクリックします。  
  
9. **付けて**ダイアログ ボックスに「`http://<server_name>/sites/WSSAdapterWalkthrough/Source`で、**ファイル名**フィールド、および ENTER キーを押します。  
  
10. 型`PurchaseOrder3.xml`で、**ファイル名**フィールドをクリックして**保存**します。  
  
11. InfoPath を終了します。  
  
12. Web ブラウザーで次のようにクリックします。**ドキュメントとリスト**します。  
  
13. [**ドキュメント ライブラリ**、] をクリックして**先**します。  
  
14. アップロード先のドキュメント ライブラリで表示されます、メッセージをこのライブラリに一覧表示します。 アーカイブ ドキュメント ライブラリにアーカイブされたコピーも紹介します。  
  
15. **[ホーム]** をクリックします。  
  
16. [**一覧**、] をクリックして**タスク**します。  
  
17. To Do リストに、新しく作成した承認済みのアイテムが表示されます。  
  
> [!NOTE]
>  注文書の総額が $1,000.00 を超えていたので、タスクが作成されます。  
  
## <a name="summary"></a>まとめ  
 このチュートリアルでは、Windows SharePoint Services のコンテキスト プロパティにアクセスする方法、および動的ポートを経由してメッセージの送信先を判断する方法を確認しました。  
  
## <a name="next-steps"></a>次の手順  
 Windows SharePoint Services アダプター セクションの残りの部分に進んでください。 詳細については、「関連項目」の該当するトピックを参照してください。  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services アダプターとは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services アダプターのチュートリアル](../core/windows-sharepoint-services-adapter-walkthroughs.md)