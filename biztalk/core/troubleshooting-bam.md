---
title: BAM のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e63299a8-5c74-4337-ba20-3213e0c6ea1f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12cd08ae9bee686946c8db14039504411506035f
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710257"
---
# <a name="troubleshooting-bam"></a>BAM のトラブルシューティング
このトピックでは、ビジネス アクティビティ監視 (BAM) の使用時に生じる問題のトラブルシューティングに役立つ情報について説明します。  
  
## <a name="bam-deployment-failed"></a>BAM を展開できない  
 SQL Server Analysis Services が使用できないときにリアルタイム集計 (RTA) を含む BAM 定義を展開しようとすると、Bm.exe コマンドで次のメッセージが表示されます。  
  
 エラー: BAM の展開に失敗しました。 接続できません。 サーバーが実行中であることを確認してください。 対象のコンピューターによって拒否されたため接続は行われません *\<IP アドレス\>* です。  
  
 このエラーは、SQL Server Analysis Services がインストールされ構成済みであり、RTA を含む BAM 定義を展開するために実行されている必要があるために発生します。  
  
## <a name="cannot-refresh-the-live-data-workbook"></a>ライブ データ ブックを更新できない  
 ライブ データ ブックのデータを更新しようとすると、Microsoft Office Excel で次のエラーが表示される場合があります。  
  
 `XML for Analysis parser: The CurrentCatalog XML/A property was not specified.`  
  
 このエラーは、BAM アドインが Excel に追加されていないために発生します。  
  
#### <a name="add-the-bam-add-in-to-excel"></a>Excel に BAM アドインを追加します。  
  
1.  をクリックして **開始**, 、 をポイント **すべてのプログラム**, 、 をポイント **Microsoft Office**, 、 をクリックし、 **Microsoft Office Excel**します。  
  
2.  クリックして、 **Microsoft Office ボタン**, 、 をクリックし、 **Excel のオプション**します。  
  
3.  **Excel のオプション** ダイアログ ボックスで、をクリックして **アドイン**します。  
  
4.  **アドイン**  ウィンドウで、をクリックして **移動**します。  
  
5.  **アドイン** ダイアログ ボックスで、 **ビジネス アクティビティ監視** チェック ボックスをオンにし **[ok]** します。  
  
     ![追加 (& a) #45; アドイン ダイアログ ボックス](../core/media/addins.gif "AddIns")  
  
## <a name="errorobject-library-invalid-or-contains-references-to-object-definitions-that-could-not-be-found-with-bam-excel-add-in-in-office"></a>Office の BAM Excel アドインで「オブジェクト ライブラリが無効、または見つからないオブジェクト定義への参照が含まれています」というエラーが表示される  
 Microsoft Excel をアップグレードした後に BAM Excel アドインを使用しようとすると、このエラーが表示される場合があります。  
  
 **解決方法:** キャッシュされている .exd ファイルを次のディレクトリから削除する必要がある BAM アドインには、ActiveX コントロールを使用するため。  
  
-   C:\Documents and Settings\\< ユーザー名\>\Application Data\Microsoft\Forms  
  
-   C:\Documents and Settings\\< ユーザー名\>\AppData\Local\Temp\VBE  
  
## <a name="bam-portal-cannot-connect"></a>BAM ポータルに接続できない  
BAM ポータルを管理者として実行します。  
  
#### <a name="run-the-bam-portal"></a>BAM ポータルを実行します。
  
1.  をクリックして **開始**, 、 をポイント **すべてのプログラム**, を右クリックして **Internet Explorer**, 、 をクリックし、 **管理者として実行**します。  
  
2.  **ユーザー アカウント制御** ダイアログ ボックスで、をクリックして **続行**します。  
  
3.  Internet Explorer のアドレス バーで、次のように入力します。`http://<server>/BAM`ここで、 *\<サーバー\>*  、BAM ポータルを実行しているコンピューターの名前を指定します。  
  
## <a name="bam-portal-does-not-work-if-invalid-users-are-granted-permissions"></a>無効なユーザーにアクセス許可が付与されていると BAM ポータルは機能しない  
 BAM の表示アクセスが許可されている AD ユーザーの 1 人が AD から削除されると、BAM ポータルは、DBO を除き、どのユーザーに対しても正しく読み込まれなくなります。  
  
 この問題を解決するには、無効なユーザーを、対応する bam_{ビュー名}view セキュリティ ロールから削除してください。  
  
## <a name="cannot-export-or-import-a-bam-definition-to-localhost"></a>BAM 定義をローカルホストにエクスポートまたはインポートできない  
 BAM 定義を XML としてエクスポートする際に、ローカルホストにエクスポートしようとすると、次のエラーメッセージが表示されます。  
  
 `The system cannot find the path specified.`  
  
 BAM 定義のローカルホストへのエクスポートはサポートされていません。 同様に、BAM 定義のローカルホストからのインポートもサポートされていません。  
  
## <a name="alerts-do-not-work-after-upgrading-sql-server-editions"></a>SQL Server エディションのアップグレード後に警告が実行されない  
 (たとえば、Enterprise Edition を Standard Edition) から別のエディションへの 1 つのエディションの SQL Server からアップグレードした後は、BAM 警告は再起動されません。 この問題を解決するには、BAM 警告を削除し、それらを再作成または SQL Server Notification Service をアップグレードします。  
  
#### <a name="upgrade-the-sql-server-notification-service"></a>SQL Server Notification Service をアップグレードします。  
  
1.  をクリックして **開始**, 、 をクリックして **すべてのプログラム**, 、 をクリックして **Microsoft SQL Server 2005**, 、 をクリックし、 **通知サービスのコマンド プロンプト**します。  
  
2.  コマンド プロンプトで次のコマンドを入力します。  
  
     `nscontrol.exe upgrade -name <instanceName>`  
  
## <a name="objectdisposedexception-exception"></a>ObjectDisposedException 例外  
 アプリケーションが BAM WF 3.5 インターセプターを使用している場合、次のエラー メッセージが表示される場合があります: **System.ObjectDisposedException: 破棄されたオブジェクトにアクセスできません**します。 このエラー メッセージの詳細については、次を参照してください。 [ObjectDisposedException 例外](https://support.microsoft.com/help/960754)です。 

この問題を解決するには、インストール、[修正プログラム 960754](https://support.microsoft.com/help/960754)です。 
  
## <a name="workbook-has-lost-its-vba-project-activex-controls-and-other-programmability-related-features"></a>ブックにある VBA プロジェクト、ActiveX コントロール、およびその他のプログラミング関連の機能が失われている  
 Microsoft Excel で BAM.xla を使用しようとすると、次のエラーが表示されます。  
  
 `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`  
  
 この問題を解決するには、インストール、 **アプリケーション用の Visual Basic** オプションで  **Office 共有機能** Microsoft Office とします。  
  
## <a name="pivot-table-fails-to-get-the-data"></a>ピボットテーブルのデータ取得に失敗する  
 BAM データベースへのアクセス権がユーザーに付与されており、展開されるビューに対するロールとアクセス許可もこのユーザーに付与されているとします。 [アクティビティの検索] ページの動作は期待どおりであり、ユーザーはデータを見ることができます。 ただし、ピボットテーブルには次のエラーが表示されます。  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* The following system error occurred:  No connection could be made because the target machine actively refused it.  
```  
  
 この問題を解決するには、次の手順に従って対応する DNS 設定を追加してください。  
  
1.  をクリックして **開始** にして **コントロール パネルの** します。  
  
2.  クリックして **ネットワークとインターネット**  をクリックし、 **ネットワーク接続**します。  
  
3.  (ローカル エリア接続) のようなネットワーク接続を右クリックし、選択 **プロパティ**します。  
  
4.  **Local Area Connection**  ページで、 **インターネット プロトコル バージョン 4 (Tcp/ipv4)**, 、 をクリック **プロパティ**します。  
  
5.  **[詳細設定]** をクリックします。 **TCP/IP 詳細設定** ページで、クリックして、 **DNS**  タブをクリックします。  
  
6.  選択 **これらの DNS サフィックスを追加する** し、必要な DNS サフィックスを追加します。  
  
7.  をクリックして **OK** し、すべての開いているウィンドウを閉じます。  
  
## <a name="pivot-table-view-shows-all-values-as-0"></a>ピボットテーブルのすべての値が "0" と表示される  
 BAM ポータルを展開したときに、[アクティビティの検索] ページには期待したとおりの結果が表示されます。 ただし、ピボットテーブル ビューの値はすべて "0" と表示されます。 次のエラーが表示されます。  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* Safety settings on this machine prohibit accessing a data source on another domain.  
```  
  
 この問題を解決するには、次の手順に従ってサイトをゾーンに追加してください。  
  
1.  Internet Explorer ウィンドウで  **ツール**, 、クリックして **インターネット オプション**します。 クリックして、 **セキュリティ** タブをクリックし、選択、 **信頼済みサイト** ゾーンです。  
  
2.  クリックして **レベルのカスタマイズ** 、ゾーンのセキュリティ レベルを設定します。  
  
3.  **設定**  ページで、、 **ドメイン間でデータ ソースにアクセス** オプションで、 **プロンプト**します。 コンポーネントは、このアクセス許可を必要とする場合を求められます。  
  
## <a name="see-also"></a>参照  
 [ビジネス アクティビティの使用の監視](../core/using-business-activity-monitoring.md)