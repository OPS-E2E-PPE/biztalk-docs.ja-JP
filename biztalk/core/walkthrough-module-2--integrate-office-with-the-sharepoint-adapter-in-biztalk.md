---
title: "チュートリアル: モジュール 2 - Windows SharePoint と Office の統合サービスのアダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, InfoPath forms
- InfoPath forms, creating
- InfoPath forms, Windows SharePoint Services adapters
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, integrating Microsoft Office
- Windows SharePoint Services, document libraries
ms.assetid: 2f81a712-bb20-4c32-bbac-fb438deded38
caps.latest.revision: "48"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64e23cef8b362accba726c60945548a3345c9c45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-module-2---integrating-office-with-the-windows-sharepoint-services-adapter"></a>チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合
このチュートリアルでは、継続の[チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信する](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)Microsoft Office と統合する方法を説明し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンテンツ ベースルーティング (CBR) アプリケーションを作成します。 概要については、Windows SharePoint Services アダプターを参照してください。 [Windows SharePoint Services アダプターは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件は、次のとおりです。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が完全インストールされたシングル サーバー展開が必要です。  
  
-   次のチュートリアルを完了する必要があります:[チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信します。](../core/walkthrough-module-1--send-and-receive-messages-with-the-sharepoint-adapter.md)  
  
 マルチ サーバー展開で Windows SharePoint Services アダプターを使用する方法については、次を参照してください。[の設定と Windows SharePoint Services アダプターを展開する](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)です。  
  
## <a name="create-a-biztalk-project"></a>BizTalk プロジェクトの作成  
 ここでは、BizTalk エディターを使用して、空の BizTalk プロジェクトとスキーマを作成します。 これは、後で使用する InfoPath フォームのスキーマを作成するために必要な手順です。  
  
#### <a name="create-a-strong-name-key-file"></a>厳密な名前のキー ファイルの作成  
  
1.  開始**Visual Studio コマンド プロンプト**です。  
  
2.  型`sn -k C:\WSSAdapterWalkthrough\OrderProcess.snk`、キーを押します**Enter**です。 キー ペアが書き込まれます。  
  
3.  コマンド プロンプトを閉じます。  
  
#### <a name="create-an-empty-biztalk-project"></a>空の BizTalk プロジェクトを作成します。  
  
1.  開始**Microsoft Visual Studio**です。  
  
2.  をクリックして**ファイル**、**新規**、クリックして**プロジェクト**です。  
  
3.  **プロジェクトの種類** **BizTalk プロジェクト**です。  
  
4.  **テンプレート****空の BizTalk Server プロジェクト**です。  
  
5.  型`OrderProcess`で、**名前**フィールドです。  
  
6.  内の作業ディレクトリへのファイル パスを入力、**場所**フィールドです。 たとえば、 `C:\WSSAdapterWalkthrough\`のようにします。  
  
7.  **[OK]**をクリックします。  
  
#### <a name="associate-the-key-file-with-the-assembly"></a>アセンブリとキー ファイルの関連付け  
  
1.  ソリューション エクスプ ローラーで右クリックし、`OrderProcess`プロジェクトをクリックして**プロパティ**プロジェクト デザイナーを起動します。  
  
2.  **[署名]** タブをクリックします。  
  
3.  **[アセンブリの署名]** オプションを選択し、 **[厳密な名前のキー ファイルを選択してください]** オプションのドロップダウン リストをクリックして、 **[参照]**をクリックします。  
  
4.  「`C:\WSSAdapterWalkthrough\OrderProcess.snk`.  
  
5.  **[開く]**をクリックします。  
  
#### <a name="create-an-xsd-schema-by-using-the-biztalk-editor"></a>BizTalk エディタを使用した XSD スキーマの作成  
  
1.  ソリューション エクスプ ローラーで右クリックし、`OrderProcess`プロジェクトで、をクリックして**追加**、クリックして**新しい項目の**します。  
  
2.  **カテゴリ**をクリックして**スキーマ ファイル**です。  
  
3.  **テンプレート**をクリックして**スキーマ**です。  
  
4.  型`OrderProcessSchema`で、**名前**フィールドをクリックして**追加**です。  
  
5.  プロパティ ウィンドウで`OrderProcessSchema``Qualified`の**Element FormDefault**プロパティです。  
  
6.  [プロパティ] ウィンドウで`OrderProcessSchema`、型`http://OrderProcess.PurchaseOrder`で、 **Target Namespace**フィールドです。  
  
7.  **BizTalk エディター**を右クリックして`Root`をクリックして**の名前を変更**、し、入力`PurchaseOrder`です。  
  
8.  右クリックし、 **PurchaseOrder**ノード、をクリックして**スキーマ ノードの挿入**、順にクリックして**子フィールド要素**です。  
  
9. 「`PurchaseOrderID`」という名前を入力します。  
  
10. 別の子フィールド要素を作成し、「`BillTo`」という名前を付けます。  
  
11. 別の子フィールド要素を作成し、「`Amount`」という名前を付けます。  
  
12. [プロパティ] ウィンドウで、設定、**データ型**プロパティを`Amount`を xs:unsignedInt にします。  
  
13. 別の子フィールド要素を作成し、「`PurchaseOrderDate`」という名前を付けます。  
  
14. [プロパティ] ウィンドウで、設定、**データ型**プロパティを`PurchaseOrderDate`xs:dateTime にします。  
  
15. をクリックして**ファイル**、クリックして**すべてを保存**です。  
  
16. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を終了します。  
  
## <a name="create-an-infopath-form"></a>InfoPath フォームの作成  
 ここでは、既に作成したスキーマを基に、別のドキュメント ライブラリと InfoPath フォームを作成します。 ドキュメントを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信するときは、この InfoPath フォームが使用されます。  
  
> [!NOTE]
>  このチュートリアルでは Microsoft Office InfoPath 2007 が必要です  
  
#### <a name="create-a-new-document-library"></a>新しいドキュメント ライブラリの作成  
  
1.  Web ブラウザを開き、作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2.  上部のナビゲーション バーで、をクリックして**作成**です。  
  
3.  **ドキュメント ライブラリ**をクリックして**ドキュメント ライブラリ**です。  
  
4.  **名前と説明**セクションで、入力`InfoPathSolutions`で、 **Name フィールド**です。  
  
5.  **ナビゲーション**セクションで、**はい**クイック起動バーにこのフォーム ライブラリを表示します。  
  
6.  **ドキュメント テンプレート**セクションで、`None`の**ドキュメント テンプレート**です。  
  
7.  **[作成]**をクリックします。 作成した空のライブラリにリダイレクトされます。  
  
8.  左側にある、をクリックして**設定の変更と列**です。  
  
9. **列**をクリックして**新しい列を追加**です。  
  
10. **名前と種類**、型`Namespace`で、**名前**フィールドです。  
  
11. **[OK]**をクリックします。  
  
12. `WSSAdapterWalkthrough` Web サイトを閉じます。  
  
#### <a name="create-an-infopath-form-based-on-the-orderprocessschema-schema-file"></a>OrderProcessSchema スキーマ ファイルを基にした InfoPath フォームの作成  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリック**Microsoft Office InfoPath 2007**です。  
  
2.  **フォームの入力**ダイアログ ボックスで、**フォームをデザインします。**  
  
3.  **フォームをデザイン**作業ウィンドウで、 **XML ドキュメントまたはスキーマから新規**です。  
  
4.  **データ ソース ウィザード**、 をクリックして**参照**最後の手順で作成したスキーマ ファイルを選択します。 たとえば、 `C:\WSSAdapterWalkthrough\OrderProcess\OrderProcess\OrderProcessSchema.xsd`のようにします。  
  
5.  **[次へ]**をクリックし、 **[完了]**をクリックします。  
  
6.  **データ ソース**タスク ウィンドウで、右クリックし、 **PurchaseOrder**ノードをクリックして**コントロール付きセクション**です。 テンプレートにフォームが作成されます。  
  
7.  をクリックして**ファイル**、 をクリックして**保存**、順にクリック**保存**です。  
  
8.  **名前を付けて保存** ダイアログ ボックスで、「`PurchaseOrder.xsn`で、**ファイル名**フィールドをクリックして**保存**です。  
  
9. をクリックして**ファイル**、クリックして**発行**です。  
  
10. **発行ウィザード**、 をクリックして**次**です。  
  
11. 選択**Web サーバーに**、クリックして**[次へ]**です。  
  
12. パスとファイル名を入力、`InfoPathSolutions`ドキュメント ライブラリをクリックして**次**です。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough/InfoPathSolutions/PurchaseOrder.xsn`のようにします。  
  
13. をクリックして**完了**、順にクリック**閉じる**です。  
  
14. Microsoft InfoPath を終了します。  
  
## <a name="modify-the-sharepoint-document-libraries"></a>SharePoint ドキュメント ライブラリの変更  
 ここでは、PurchaseOrder.xsn ファイルの名前空間プロパティを更新し、アップロード先のドキュメント ライブラリを変更します。 この名前空間は、コンテンツ ベースのルーティング シナリオで、パブリッシュされたドキュメントのサブスクライバーを特定するときに変数として使用されます。  
  
#### <a name="update-the-namespace-for-purchaseorderxsn"></a>PurchaseOrder.xsn の名前空間の更新  
  
1.  Web ブラウザを開き、作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2.  左側にある、下にある**ドキュメント**をクリックして`InfoPathSolutions`です。  
  
3.  ポインターを合わせる`PurchaseOrder.xsn`、右クリックし、をクリックして**プロパティの編集**です。  
  
4.  型`http://OrderProcess.PurchaseOrder`で、 **Namespace**フィールドをクリックして**を保存して閉じます**です。  
  
#### <a name="modify-the-destination-document-library"></a>アップロード先のドキュメント ライブラリの変更  
  
1.  上部のナビゲーション バーで、をクリックして**ドキュメントし、リスト**です。  
  
2.  **ドキュメント ライブラリ**をクリックして**先**です。  
  
3.  左側にある、をクリックして**設定の変更と列**です。  
  
4.  **列**をクリックして**新しい列の追加**です。  
  
5.  **名前と種類**、型`Partner Name`で、**列名**フィールドです。  
  
6.  **[OK]**をクリックします。  
  
7.  `WSSAdapterWalkthrough` Web サイトを閉じます。  
  
## <a name="modify-the-send-port-from-walkthrough-1"></a>チュートリアル 1 の送信ポートの変更  
 ここでは、チュートリアル 1 の送信ポートを変更します。 このチュートリアルで処理したドキュメントを確実に送信ポートへとルーティングするために、この手順が必要になります。  
  
#### <a name="modify-the-send-port"></a>送信ポートの変更  
  
1.  開いている**BizTalk Server 管理します。**  
  
2.  展開**Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、をクリックし、**送信ポート**ノード。  
  
3.  右クリック`SendToDestination`、クリックして**プロパティ**です。  
  
4.  **トランスポート**をクリックして**構成**です。  
  
5.  **Filename**フィールドに「`PurchaseOrder2-%XPATH=//pons:PurchaseOrder/pons:PurchaseOrderID%.xml`です。  
  
6.  **Namespace エイリアス**フィールドに「`pons="http://OrderProcess.PurchaseOrder"`です。  
  
7.  **テンプレート ドキュメント ライブラリ**、型`InfoPathSolutions`です。  
  
8.  **テンプレート Namespace 列**、型`Namespace`です。  
  
9. 選択`Yes`の**Microsoft Office 統合**プロパティです。  
  
10. **Windows SharePoint Services 統合**、型`Partner Name`で、**列 01**フィールドです。  
  
11. 型`%XPATH=//pons:PurchaseOrder/pons:BillTo%`で、**列 01 の値**フィールドで、をクリックして**OK**、順にクリック**[ok]**を終了するには、もう一度、**送信ポートのプロパティ**ダイアログ ボックス。  
  
#### <a name="restart-the-send-port"></a>送信ポートを再起動します。  
  
1.  **BizTalk 管理コンソール**をクリックして、**送信ポート**ノード。  
  
2.  右クリック`SendToDestination`、クリックして**参加解除**です。  
  
3.  右クリック`SendToDestination`、クリックして**開始**です。  
  
4.  閉じる、 **BizTalk 管理コンソール**です。  
  
## <a name="send-a-message-through-the-system"></a>システムからのメッセージ送信  
 ここでは、InfoPath フォームを作成し、Windows SharePoint Services Web サイトにアップロードします。 そのメッセージは Windows SharePoint Services アダプターによって取得され、アーカイブ ドキュメント ライブラリにアーカイブされた後、アップロード先のドキュメント ライブラリに送信されます。 この手順は、Windows SharePoint Services アダプターを使用し、SharePoint Web サイトから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を経由して SharePoint サービス Web サイトへと送信されるドキュメント フローを示しています。  
  
#### <a name="create-an-infopath-form-to-send-through-the-system"></a>システムから送信する InfoPath フォームの作成  
  
1.  Web ブラウザを開き、作成したサイトの URL に移動します。 たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。  
  
2.  左側にある、下にある**ドキュメント**をクリックして`InfoPathSolutions`です。  
  
3.  クリックして、`PurchaseOrder`に表示されるファイル、**ファイルのダウンロード**クリックしてダイアログ ボックスで、**開く**です。 フォームが読み込まれます。  
  
4.  **Purchase Order ID**フィールドに「`1002`です。  
  
5.  **請求先**フィールドに「`John Doe`です。  
  
6.  **量**フィールドに「`750`です。  
  
7.  **Purchase Order Date**フィールドに「`1/2/2005`です。  
  
8.  **[保存]**をクリックします。  
  
9. **名前を付けて保存** ダイアログ ボックスで、「`http://<server_name>/sites/WSSAdapterWalkthrough/Source`で、**ファイル名**フィールド、および enter キー押しです。  
  
10. 型`PurchaseOrder2.xml`で、**ファイル名**フィールドをクリックして**保存**です。  
  
11. Microsoft Office InfoPath を終了します。  
  
12. 上部のナビゲーション バーで、Web ブラウザーでをクリックして**ドキュメントし、リスト**です。  
  
13. **ドキュメント ライブラリ**をクリックして**先**です。  
  
14. アップロード先のドキュメント ライブラリには、メッセージの一覧が表示されます。 アーカイブ ドキュメント ライブラリにアーカイブされたコピーも紹介します。  
  
15. [アップロード先のドキュメント ライブラリ] で `PurchaseOrder1.xml` をクリックします。 この XML ファイルは Microsoft Internet Explorer で開かれます。  
  
16. [アップロード先のドキュメント ライブラリ] で `PurchaseOrder2.xml` をクリックします。 この XML ファイルは Microsoft Office InfoPath で開かれます。  
  
> [!NOTE]
>  アップロード先のドキュメント ライブラリでは、PurchaseOrderID フィールドの値がファイル名列に、BillTo フィールドの値がパートナー名列に格納されます。  
  
## <a name="summary"></a>概要  
 このチュートリアルでは、Windows SharePoint Services アダプターとコンテンツ ベースのルーティング (CBR) を使用して、Microsoft Office InfoPath とのより緊密な統合を実現する方法を確認しました。  
  
## <a name="next-steps"></a>次の手順  
 これで、このチュートリアルを完了すると、実行、[チュートリアル: モジュール 3 - オーケストレーションからの SharePoint プロパティへのアクセス](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)このチュートリアルを完了したら作業にまで拡張できるチュートリアルの統合、プロジェクトに、オーケストレーション内から SharePoint プロパティにアクセスする方法について説明します。  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services アダプターとは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services アダプタのチュートリアル](../core/windows-sharepoint-services-adapter-walkthroughs.md)