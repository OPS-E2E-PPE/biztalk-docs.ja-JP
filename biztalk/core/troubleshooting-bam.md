---
title: BAM のトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: d068b3f669400f2f7b55a3279aa40090adc8689f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243263"
---
# <a name="troubleshooting-bam"></a>BAM のトラブルシューティング
このトピックでは、ビジネス アクティビティ監視 (BAM) を使用する場合に発生する可能性が問題のトラブルシューティングに役立つ情報を提供します。  
  
## <a name="bam-deployment-failed"></a>BAM を展開できませんでした。  
 SQL Server Analysis Services が利用できない場合は、リアルタイム集計 (RTA) を含む BAM 定義を展開しようとした場合、Bm.exe コマンドには、次のメッセージが表示されます。  
  
 ERROR:BAM の展開に失敗しました。 接続できません。 サーバーが実行中であることを確認してください。 ターゲット コンピューターによって拒否されたため、接続は行われません *\<IP アドレス\>* します。  
  
 これには、SQL Server Analysis Services が既にインストールされている必要があります、構成されているし、RTA を含む BAM 定義を展開するために実行されている必要がありますが発生します。  
  
## <a name="cannot-refresh-the-live-data-workbook"></a>ライブ データ ブックを更新することはできません。  
 ライブ データ ブックのデータを更新しようとすると、Microsoft Office Excel には、次のエラーが表示されます。  
  
 `XML for Analysis parser: The CurrentCatalog XML/A property was not specified.`  
  
 これには、BAM アドインが追加されていない Excel にために発生します。  
  
#### <a name="add-the-bam-add-in-to-excel"></a>Excel に BAM アドインを追加します。  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリックします**Microsoft Office Excel**します。  
  
2.  をクリックして、 **Microsoft Office ボタン**、順にクリックします**Excel オプション**します。  
  
3.  **Excel オプション**ダイアログ ボックスで、をクリックして**アドイン**。  
  
4.  **アドイン**ウィンドウで、をクリックして**移動**します。  
  
5.  **アドイン**ダイアログ ボックスで、**ビジネス アクティビティ監視**チェック ボックスをオンにし**OK**。  
  
     ![追加&#45;アドイン ダイアログ ボックス](../core/media/addins.gif "AddIns")  
  
## <a name="errorobject-library-invalid-or-contains-references-to-object-definitions-that-could-not-be-found-with-bam-excel-add-in-in-office"></a>エラー:「オブジェクト ライブラリが無効または見つかりませんでしたオブジェクト定義への参照が含まれています」と BAM Excel アドインで Office  
 Microsoft Excel をアップグレードした後に BAM Excel アドイン使用しようとすると、このエラーが表示される可能性があります。  
  
 **解決方法:** BAM アドインには、ActiveX コントロールを使用するため、次のディレクトリからキャッシュされている .exd ファイルを削除する必要があります。  
  
-   C:\Documents and Settings\\< ユーザー名\>\Application Data\Microsoft\Forms  
  
-   C:\Documents and Settings\\< ユーザー名\>\AppData\Local\Temp\VBE  
  
## <a name="bam-portal-cannot-connect"></a>BAM ポータルが接続できません。  
BAM ポータルを管理者として実行します。  
  
#### <a name="run-the-bam-portal"></a>BAM ポータルを実行します。
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**を右クリックして**Internet Explorer**、順にクリックします**管理者として実行**します。  
  
2.  **ユーザー アカウント制御**ダイアログ ボックスで、をクリックして**続行**します。  
  
3.  Internet Explorer アドレス バーに「`http://<server>/BAM`ここで、 *\<server\>* BAM ポータルを実行しているコンピューター名前を指定します。  
  
## <a name="bam-portal-does-not-work-if-invalid-users-are-granted-permissions"></a>BAM ポータルでは、無効なユーザーのアクセス許可が与えられる場合は機能しません  
 BAM ビューのアクセス許可を持つ AD ユーザーは、AD から削除する場合、BAM ポータル正しく読み込まれません (DBO) を除くすべてのユーザー。  
  
 この問題を解決するには、対応する bam _ {ビュー名} view セキュリティ ロールから無効なユーザーを削除します。  
  
## <a name="cannot-export-or-import-a-bam-definition-to-localhost"></a>エクスポートまたは localhost に BAM 定義をインポートできません。  
 BAM 定義を XML としてエクスポートするときに localhost にエクスポートしようとする場合は、次のエラー メッセージが表示されます。  
  
 `The system cannot find the path specified.`  
  
 Localhost に BAM 定義のエクスポートはサポートされていません。 同様に、localhost から BAM 定義をインポートすることはサポートされていません。  
  
## <a name="alerts-do-not-work-after-upgrading-sql-server-editions"></a>SQL Server のエディションのアップグレード後にアラートが機能しません。  
 (たとえば、Enterprise Edition を Standard Edition) から別のエディションに 1 つのエディションの SQL Server からアップグレードした場合、BAM 警告は再起動されません。 この問題を解決するには、BAM 警告を削除および再作成するには、または、SQL Server Notification Service をアップグレードします。  
  
#### <a name="upgrade-the-sql-server-notification-service"></a>SQL Server の通知サービスをアップグレードします。  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2005**、順にクリックします**Notification Service のコマンド プロンプト**します。  
  
2.  コマンド プロンプトで次のコマンドを入力します。  
  
     `nscontrol.exe upgrade -name <instanceName>`  
  
## <a name="objectdisposedexception-exception"></a>ObjectDisposedException 例外  
 アプリケーションが BAM WF 3.5 インターセプターを使用している場合、次のエラー メッセージが表示される可能性があります。**System.ObjectDisposedException:破棄されたオブジェクトにアクセスできません**します。 このエラー メッセージの詳細については、次を参照してください。 [ObjectDisposedException 例外](https://support.microsoft.com/help/960754)します。 

この問題を解決するには、インストール、[修正プログラム 960754](https://support.microsoft.com/help/960754)します。 
  
## <a name="workbook-has-lost-its-vba-project-activex-controls-and-other-programmability-related-features"></a>ブックは、VBA プロジェクト、ActiveX コントロールおよびその他のプログラミング関連の機能に失われています  
 BAM.xla を Excel で使用しようとすると、次のエラーが発生した可能性があります。  
  
 `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`  
  
 この問題を解決するには、インストール、**アプリケーション用の Visual Basic**オプションで  **Office 共有機能**Microsoft Office とします。  
  
## <a name="pivot-table-fails-to-get-the-data"></a>ピボット テーブルがデータの取得に失敗しました。  
 デプロイされているビューに、BAM データベースともロールへのアクセス許可とアクセス許可があります。 アクティビティの検索ページが期待どおりに動作し、データを確認できます。 ただし、ピボット テーブルで、次のエラーが表示されます。  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* The following system error occurred:  No connection could be made because the target machine actively refused it.  
```  
  
 この問題を解決するには、対応する DNS を追加するには、設定として次に示します。  
  
1.  クリックして**開始**に移動し、**コントロール パネルの **します。  
  
2.  クリックして**ネットワークとインターネット** をクリックし、**ネットワーク接続**します。  
  
3.  (ローカル エリア接続) のようなネットワーク接続を右クリックし、選択**プロパティ**します。  
  
4.  **Local Area Connection**  ページで、**インターネット プロトコル バージョン 4 (Tcp/ipv4)**、 をクリック**プロパティ**します。  
  
5.  **[詳細設定]** をクリックします。 **TCP/IP 詳細設定** ページで、をクリックして、 **DNS**タブ。  
  
6.  選択**これらの DNS サフィックスを追加する**し、必要な DNS サフィックスを追加します。  
  
7.  クリックして**OK**し、すべての開いているウィンドウを閉じます。  
  
## <a name="pivot-table-view-shows-all-values-as-0"></a>ピボット テーブル ビューは、「0」としてすべての値を示しています  
 BAM ポータルを展開するときに、アクティビティの検索ページには、期待どおりの結果が表示されます。 ただし、ピボット テーブルのビューには、すべての値が「0」として表示されます。 次のエラーが表示されます。  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* Safety settings on this machine prohibit accessing a data source on another domain.  
```  
  
 この問題を解決するには、ようゾーンにサイトを追加します。  
  
1.  Internet Explorer のウィンドウで次のようにクリックします。**ツール**、 をクリックし、**インターネット オプション**します。 をクリックして、**セキュリティ**、タブを選び、**信頼済みサイト**ゾーン。  
  
2.  クリックして**レベルのカスタマイズ**ゾーンのセキュリティ レベルを設定します。  
  
3.  **設定**ページの**ドメイン間でデータ ソースにアクセス**オプションで、**プロンプト**。 コンポーネントは、このアクセス許可を必要とする場合を求められます。  
  
## <a name="see-also"></a>参照  
 [ビジネス アクティビティの使用の監視](../core/using-business-activity-monitoring.md)