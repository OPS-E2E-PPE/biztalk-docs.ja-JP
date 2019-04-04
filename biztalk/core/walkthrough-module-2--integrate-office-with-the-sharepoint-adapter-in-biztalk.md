---
title: 'チュートリアル: モジュール 2 - Office の統合、Windows sharepoint Services アダプター |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, InfoPath forms
- InfoPath forms, creating
- InfoPath forms, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, integrating Microsoft Office
- Windows SharePoint Services, document libraries
ms.assetid: 2f81a712-bb20-4c32-bbac-fb438deded38
caps.latest.revision: 48
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79297c55152688821ba5b472335eade1d31b0ffe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022392"
---
# <a name="walkthrough-module-2---integrating-office-with-the-windows-sharepoint-services-adapter"></a>チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合
このチュートリアルの続きでは、[チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信する](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)Microsoft Office と統合する方法と、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンテンツ ベースルーティング (CBR) アプリケーションを作成します。 Windows SharePoint Services アダプターの概要についてを参照してください。 [、Windows SharePoint Services アダプターとは何ですか?](../core/what-is-the-windows-sharepoint-services-adapter.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件は、次のとおりです。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が完全インストールされたシングル サーバー展開が必要です。  
  
- 次のチュートリアルを完了する必要があります:[チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信します。](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)  
  
  マルチ サーバー展開で、Windows SharePoint Services アダプターを使用する方法の詳細については、[設定と、Windows SharePoint Services アダプターを展開する](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)を参照してください。  
  
## <a name="create-a-biztalk-project"></a>BizTalk プロジェクトの作成  
 ここでは、BizTalk エディターを使用して、空の BizTalk プロジェクトとスキーマを作成します。 これは、後で使用する InfoPath フォームのスキーマを作成するために必要な手順です。  
  
#### <a name="create-a-strong-name-key-file"></a>厳密な名前のキー ファイルの作成  
  
1.  開始**Visual Studio コマンド プロンプト**します。  
  
2.  型`sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`、し、キーを押します**Enter**します。 キー ペアが書き込まれます。  
  
3.  コマンド プロンプトを閉じます。  
  
#### <a name="create-an-empty-biztalk-project"></a>空の BizTalk プロジェクトを作成します。  
  
1.  開始**Microsoft Visual Studio**します。  
  
2.  クリックして**ファイル**、**新規**、 をクリックし、**プロジェクト**します。  
  
3.  **プロジェクトの種類**、 **BizTalk プロジェクト**します。  
  
4.  **テンプレート**、**空の BizTalk Server プロジェクト**します。  
  
5.  型`OrderProcess`で、**名前**フィールド。  
  
6.  作業ディレクトリにファイル パスを入力、**場所**フィールド。 たとえば、 `C:\WSSAdapterWalkthrough\`のようにします。  
  
7.  **[OK]** をクリックします。  
  
#### <a name="associate-the-key-file-with-the-assembly"></a>アセンブリとキー ファイルの関連付け  
  
1.  ソリューション エクスプ ローラーで右クリックし、`OrderProcess`プロジェクトをクリックして**プロパティ**プロジェクト デザイナーを起動します。  
  
2.  **[署名]** タブをクリックします。  
  
3.  **[アセンブリの署名]** オプションを選択し、 **[厳密な名前のキー ファイルを選択してください]** オプションのドロップダウン リストをクリックして、 **[参照]** をクリックします。  
  
4.  「`C:\WSSAdapterWalkthrough\OrderProcess.snk`.  
  
5.  **[開く]** をクリックします。  
  
#### <a name="create-an-xsd-schema-by-using-the-biztalk-editor"></a>BizTalk エディタを使用した XSD スキーマの作成  
  
1. ソリューション エクスプ ローラーで右クリックし、`OrderProcess`プロジェクトで、をクリックして**追加**、 をクリックし、**新しい項目の**します。  
  
2. [**カテゴリ**、] をクリックして**スキーマ ファイル**します。  
  
3. [**テンプレート**、] をクリックして**スキーマ**します。  
  
4. 型`OrderProcessSchema`で、**名前**フィールドをクリックして**追加**します。  
  
5. [プロパティ] ウィンドウで`OrderProcessSchema`、`Qualified`の**Element FormDefault**プロパティ。  
  
6. [プロパティ] ウィンドウで`OrderProcessSchema`、型`http://OrderProcess.PurchaseOrder`で、 **Target Namespace**フィールド。  
  
7. **BizTalk エディター**、右クリックして`Root`、 をクリックして**の名前を変更**、し、入力`PurchaseOrder`します。  
  
8. 右クリックし、 **PurchaseOrder**ノード、をクリックして**スキーマ ノードの挿入**、 をクリックし、**子フィールド要素**。  
  
9. 「`PurchaseOrderID`」という名前を入力します。  
  
10. 別の子フィールド要素を作成し、「`BillTo`」という名前を付けます。  
  
11. 別の子フィールド要素を作成し、「`Amount`」という名前を付けます。  
  
12. [プロパティ] ウィンドウで次のように設定します。、**データ型**プロパティ`Amount`[xs:unsignedint] にします。  
  
13. 別の子フィールド要素を作成し、「`PurchaseOrderDate`」という名前を付けます。  
  
14. [プロパティ] ウィンドウで次のように設定します。、**データ型**プロパティ`PurchaseOrderDate`xs:dateTime にします。  
  
15. をクリックして**ファイル**、 をクリックし、**すべて保存**します。  
  
16. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を終了します。  
  
## <a name="create-an-infopath-form"></a>InfoPath フォームの作成  
 ここでは、既に作成したスキーマを基に、別のドキュメント ライブラリと InfoPath フォームを作成します。 ドキュメントを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信するときは、この InfoPath フォームが使用されます。  
  
> [!NOTE]
>  このチュートリアルでは Microsoft Office InfoPath 2007 が必要です  
  
#### <a name="create-a-new-document-library"></a>新しいドキュメント ライブラリの作成  
  
1.  Web ブラウザを開き、作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2.  上部のナビゲーション バーでクリックして**作成**です。  
  
3.  [**ドキュメント ライブラリ**、] をクリックして**ドキュメント ライブラリ**します。  
  
4.  **名前と説明**セクションで、入力`InfoPathSolutions`で、**名前フィールド**します。  
  
5.  **ナビゲーション**セクションで、**はい**このフォーム ライブラリをクイック起動バーに表示します。  
  
6.  **ドキュメント テンプレート**セクションで、`None`の**ドキュメント テンプレート**します。  
  
7.  **[作成]** をクリックします。 作成した空のライブラリにリダイレクトされます。  
  
8.  左側にある クリックして**設定の変更と列**します。  
  
9. [**列**、] をクリックして**新しい列を追加**します。  
  
10. **名前と種類**、型`Namespace`で、**名前**フィールド。  
  
11. **[OK]** をクリックします。  
  
12. `WSSAdapterWalkthrough` Web サイトを閉じます。  
  
#### <a name="create-an-infopath-form-based-on-the-orderprocessschema-schema-file"></a>OrderProcessSchema スキーマ ファイルを基にした InfoPath フォームの作成  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリックします**Microsoft Office InfoPath 2007**します。  
  
2.  **フォームの入力**ダイアログ ボックスで、**フォームをデザインします。**  
  
3.  **フォームをデザイン**タスク ウィンドウで、 **XML ドキュメントまたはスキーマから新規**します。  
  
4.  **データ ソース ウィザード**、 をクリックして**参照**最後の手順で作成したスキーマ ファイルを選択します。 たとえば、 `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`のようにします。  
  
5.  **[次へ]** をクリックし、 **[完了]** をクリックします。  
  
6.  **データ ソース**タスク ウィンドウで、右クリックし、 **PurchaseOrder**ノード、およびクリック**コントロール付きセクション**。 テンプレートにフォームが作成されます。  
  
7.  クリックして**ファイル**、 をクリックして**保存**、順にクリックします**保存**します。  
  
8.  **名前を付けて保存**ダイアログ ボックスに「`PurchaseOrder.xsn`で、**ファイル名**フィールドをクリックして**保存**します。  
  
9. クリックして**ファイル**、 をクリックし、**発行**します。  
  
10. **公開ウィザード**、 をクリックして**次**します。  
  
11. 選択**Web サーバーに**、順にクリックします**次**します。  
  
12. パスとファイル名を入力、`InfoPathSolutions`ドキュメント ライブラリ、およびクリックして**次**します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`のようにします。  
  
13. クリックして**完了**、順にクリックします**閉じる**します。  
  
14. Microsoft InfoPath を終了します。  
  
## <a name="modify-the-sharepoint-document-libraries"></a>SharePoint ドキュメント ライブラリの変更  
 ここでは、PurchaseOrder.xsn ファイルの名前空間プロパティを更新し、アップロード先のドキュメント ライブラリを変更します。 この名前空間は、コンテンツ ベースのルーティング シナリオで、パブリッシュされたドキュメントのサブスクライバーを特定するときに変数として使用されます。  
  
#### <a name="update-the-namespace-for-purchaseorderxsn"></a>PurchaseOrder.xsn の名前空間の更新  
  
1.  Web ブラウザを開き、作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2.  左側にある [**ドキュメント**、] をクリック`InfoPathSolutions`します。  
  
3.  ポインターを置く`PurchaseOrder.xsn`を右クリックし、クリックして**プロパティの編集**します。  
  
4.  型`http://OrderProcess.PurchaseOrder`で、 **Namespace**フィールドをクリックして**を保存して閉じます**します。  
  
#### <a name="modify-the-destination-document-library"></a>アップロード先のドキュメント ライブラリの変更  
  
1.  上部のナビゲーション バーでクリックして**ドキュメントし、リスト**します。  
  
2.  [**ドキュメント ライブラリ**、] をクリックして**先**します。  
  
3.  左側にある クリックして**設定の変更と列**します。  
  
4.  [**列**、] をクリックして**新しい列の追加**します。  
  
5.  **名前と種類**、型`Partner Name`で、**列名**フィールド。  
  
6.  **[OK]** をクリックします。  
  
7.  `WSSAdapterWalkthrough` Web サイトを閉じます。  
  
## <a name="modify-the-send-port-from-walkthrough-1"></a>チュートリアル 1 の送信ポートの変更  
 ここでは、チュートリアル 1 の送信ポートを変更します。 このチュートリアルで処理したドキュメントを確実に送信ポートへとルーティングするために、この手順が必要になります。  
  
#### <a name="modify-the-send-port"></a>送信ポートの変更  
  
1. 開いている**BizTalk Server 管理します。**  
  
2. 展開**Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリックし、**送信ポート**ノード。  
  
3. 右クリックして`SendToDestination`、 をクリックし、**プロパティ**します。  
  
4. [**トランスポート**、] をクリックして**構成**します。  
  
5. **Filename**フィールドに「`PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`します。  
  
6. **Namespace エイリアス**フィールドに「`pons="http://OrderProcess.PurchaseOrder"`します。  
  
7. **テンプレート ドキュメント ライブラリ**、型`InfoPathSolutions`します。  
  
8. **テンプレート Namespace 列**、型`Namespace`します。  
  
9. 選択`Yes`の**Microsoft Office 統合**プロパティ。  
  
10. **Windows SharePoint Services の統合**、型`Partner Name`で、**列 01**フィールド。  
  
11. 型`%XPATH=//pons:PurchaseOrder/pons:BillTo%`で、**列 01 の値**フィールドに、をクリックして **[ok]**、順にクリックします**OK**を終了するには、もう一度、**送信ポートのプロパティ**ダイアログ ボックス。  
  
#### <a name="restart-the-send-port"></a>送信ポートを再起動します。  
  
1.  **BizTalk 管理コンソール**、クリックして、**送信ポート**ノード。  
  
2.  右クリックして`SendToDestination`、 をクリックし、**参加解除**します。  
  
3.  右クリック`SendToDestination`、 をクリックし、**開始**します。  
  
4.  閉じる、 **BizTalk 管理コンソール**します。  
  
## <a name="send-a-message-through-the-system"></a>システムからのメッセージ送信  
 ここでは、InfoPath フォームを作成し、Windows SharePoint Services Web サイトにアップロードします。 そのメッセージは Windows SharePoint Services アダプターによって取得され、アーカイブ ドキュメント ライブラリにアーカイブされた後、アップロード先のドキュメント ライブラリに送信されます。 この手順は、Windows SharePoint Services アダプターを使用し、SharePoint Web サイトから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を経由して SharePoint サービス Web サイトへと送信されるドキュメント フローを示しています。  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a>システムから送信する InfoPath フォームの作成  
  
1.  Web ブラウザを開き、作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2.  左側にある [**ドキュメント**、] をクリック`InfoPathSolutions`します。  
  
3.  をクリックして、`PurchaseOrder`ファイルを表示する、**ファイルのダウンロード**クリックしてダイアログ ボックスで、**オープン**します。 フォームが読み込まれます。  
  
4.  **Purchase Order ID**フィールドに「`1002`します。  
  
5.  **請求先**フィールドに「`John Doe`します。  
  
6.  **量**フィールドに「`750`します。  
  
7.  **発注書日付**フィールドに「`1/2/2005`します。  
  
8.  **[保存]** をクリックします。  
  
9. **名前を付けて保存**ダイアログ ボックスに「`http://<server_name>/sites/WSSAdapterWalkthrough/Source`で、**ファイル名**フィールドしし、Enter キーを押します。  
  
10. 型`PurchaseOrder2.xml`で、**ファイル名**フィールドをクリックして**保存**します。  
  
11. Microsoft Office InfoPath を終了します。  
  
12. 上部のナビゲーション バーで、Web ブラウザーで次のようにクリックします。**ドキュメントとリスト**します。  
  
13. [**ドキュメント ライブラリ**、] をクリックして**先**します。  
  
14. アップロード先のドキュメント ライブラリには、メッセージの一覧が表示されます。 アーカイブ ドキュメント ライブラリにアーカイブされたコピーも紹介します。  
  
15. [アップロード先のドキュメント ライブラリ] で `PurchaseOrder1.xml` をクリックします。 この XML ファイルは Microsoft Internet Explorer で開かれます。  
  
16. [アップロード先のドキュメント ライブラリ] で `PurchaseOrder2.xml` をクリックします。 この XML ファイルは Microsoft Office InfoPath で開かれます。  
  
> [!NOTE]
>  アップロード先のドキュメント ライブラリでは、PurchaseOrderID フィールドの値がファイル名列に、BillTo フィールドの値がパートナー名列に格納されます。  
  
## <a name="summary"></a>まとめ  
 このチュートリアルでは、Windows SharePoint Services アダプターとコンテンツ ベースのルーティング (CBR) を使用して、Microsoft Office InfoPath とのより緊密な統合を実現する方法を確認しました。  
  
## <a name="next-steps"></a>次の手順  
 これで、このチュートリアルを完了すると、実行、[チュートリアル: モジュール 3 - オーケストレーションからの SharePoint プロパティへのアクセス](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)チュートリアルでは、このチュートリアルでは、行った作業の発展を統合します。プロジェクトに、オーケストレーション内から SharePoint プロパティにアクセスする方法について説明します。  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services アダプターとは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services アダプターのチュートリアル](../core/windows-sharepoint-services-adapter-walkthroughs.md)