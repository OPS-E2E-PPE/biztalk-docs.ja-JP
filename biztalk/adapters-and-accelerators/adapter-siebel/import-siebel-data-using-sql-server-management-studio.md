---
title: Siebel を SQL Server Management Studio を使用してデータをインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Management Studio, importing data by using
- how to, import data by using SQL Server Management Studio
ms.assetid: 67da7f7b-37ea-4a31-89ef-a9f6974ff976
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a17d3061721006c9e98517a7bf2bf7ab11d7052d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223722"
---
# <a name="import-siebel-data-using-sql-server-management-studio"></a>Siebel を SQL Server Management Studio を使用してデータをインポートします。
このセクションでは、SQL Server Management Studio を使用して、Siebel システムから SQL Server データベースにデータをインポートする方法に関する情報を提供します。 また、作成し、このデータをインポートする SSIS パッケージを実行する方法の手順についても提供します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックに記載されている手順を実行する前に確認します。  
  
-   [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]がコンピューターにインストールされています。  
  
-   SQL Server Business Intelligence Development Studio は、コンピューターにインストールします。  
  
## <a name="importing-data-by-using-sql-server-management-studio"></a>SQL Server Management Studio を使用してデータをインポートします。  
 使用して Siebel システムからデータをインポートする次の手順を実行[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]SQL Server Management Studio を使用します。  
  
#### <a name="to-import-data-by-using-sql-server-management-studio"></a>SQL Server Management Studio を使用してデータをインポートするには  
  
1.  SQL Server Management Studio を起動します。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、SQL Server データベースに接続し、をクリックする値を指定**接続**です。 Microsoft SQL Server Management Studio を開きます。  
  
3.  オブジェクト エクスプ ローラーで、SQL Server 名を展開し、**データベース**、しをエクスポートするテーブル、Siebel システムからデータベースを右クリックします。 コンテキスト メニューのをポイント**タスク**、クリックして**データのインポート**です。 これは、SQL Server インポートおよびエクスポート ウィザードを起動します。  
  
4.  [ようこそ] 画面で、情報を参照し、をクリックして**次**です。  
  
5.  **データ ソースを選択** ダイアログ ボックスから、**データソース**ドロップダウン リストで、 **.NET Framework Data Provider 用 Siebel eBusiness Applications**です。 さまざまな接続のプロパティの値を指定、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]接続文字列。 接続文字列プロパティの詳細については、次を参照してください。 [Siebel 接続文字列のデータ プロバイダーのプロパティ](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)です。  
  
     **[次へ]** をクリックします。  
  
6.  **先選択** ダイアログ ボックス。  
  
    1.  **先**ドロップダウン リストで、 **SQL Native Client**です。  
  
    2.  **サーバー名**ドロップダウン リストで、SQL Server 名を選択します。  
  
    3.  認証モードを選択します。  
  
    4.  **データベース**ドロップダウン リストで、Siebel テーブルをインポートするデータベースを選択します。  
  
    5.  **[次へ]** をクリックします。  
  
7.  **テーブルのコピーを指定またはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプション。  
  
8.  **ソース クエリを指定する** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。 クエリを SELECT の文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)です。  
  
     をクリックして、**解析**クエリを検証します をクリックするボタンを**OK**をクリックしてポップアップ ダイアログ ボックスで、 **次へ**です。  
  
9. **[ソース テーブルおよびビュー** ] ダイアログ ボックスで、ソース テーブルと対象テーブルに対してチェック ボックスをオンにします。 ソースは、Siebel からデータを取得するように指定したクエリを示します。 変換先は、SQL Server データベースに作成されるテーブルです。  
  
10. ウィザードでは、テーブルのフィールド、ソースと移行先の既定のマッピングを作成します。 ただし、要件に従って、マッピングを変更することができます。 フィールド マッピングを変更する をクリックして**マッピングの編集**です。  
  
     ![Siebel テーブルと SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")  
  
11. **列マッピング**ダイアログ ボックスで、することができます。  
  
    -   変換先テーブル内の列の名前を変更します。  
  
    -   変換先テーブル内の特定の列を無視します。  
  
    -   コピー先のテーブル内のフィールドのデータ型を変更します。  
  
    -   Nullable、サイズ、有効桁数、小数点以下桁数などその他のフィールドの属性を変更します。  
  
         終了したら **[OK]** をクリックします。  
  
12. **ソース テーブルおよびビュー**ダイアログ ボックスで、をクリックして**次へ**です。  
  
13. **パッケージの実行を保存して** ダイアログ ボックス。  
  
    -   選択、**をすぐに実行**クエリを実行する チェック ボックスです。  
  
    -   選択、 **SSIS パッケージの保存**パッケージとしてクエリを保存し、後で実行する チェック ボックスです。 パッケージの保存先を選択した場合も、SQL Server またはファイル システムにパッケージを保存するかどうかを指定する必要があります。  
  
    -   **パッケージの保護レベル**-ドロップダウン リスト、選択、保護は、パッケージ レベルし、資格情報を指定必要な場所です。  
  
    -   **[次へ]** をクリックします。  
  
     パッケージを保存することを選択する場合は、次の手順に進みます。 それ以外の場合、手順 15 に進みます。  
  
14. **SSIS パッケージの保存** ダイアログ ボックスで、次を指定します。  
  
    -   パッケージの名前  
  
    -   パッケージの説明  
  
    -   SQL Server にパッケージを保存する場合は、選択から SQL Server、**サーバー名**ドロップダウン リスト。  
  
    -   ファイル システムにパッケージを保存する場合は、指定のファイルの場所と名前、**ファイル名**テキスト ボックス。  
  
         終了したら **[次へ]** をクリックします。  
  
15. **ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**です。  
  
16. **操作の実行**Siebel から SQL Server データベース テーブルに情報をインポートするタスクを実行してダイアログ ボックスで、ウィザードを起動します。 各タスクの状態は、ウィザードに表示されます。  
  
17. すべてのタスクが正常に実行される、クリックして**閉じる**です。 タスクが失敗した場合、対応するエラー メッセージを参照してください、問題を修正、ウィザードを再実行します。  
  
## <a name="running-the-ssis-package"></a>SSIS パッケージを実行します。  
 SSIS パッケージを保存する場合を実行すると、Siebel システムの最新の情報を取得できます。 このセクションでは、ファイル システムに保存する場合は、パッケージを実行する方法に関する情報を提供します。  
  
#### <a name="to-run-the-package-from-windows-explorer"></a>Windows エクスプ ローラーからパッケージを実行するには  
  
1.  **Windows エクスプ ローラー**パッケージを保存した場所に移動し、パッケージをダブルクリックします。  
  
2.  **[パッケージ実行ユーティリティ]** ダイアログ ボックスで **[実行]** をクリックします。 **パッケージ実行の進行状況** ダイアログ ボックスには、さまざまなタスクの進行状況が表示されます。  
  
3.  すべてのタスクが正常に実行される、クリックして**閉じる**です。  
  
4.  **[パッケージ実行ユーティリティ]** ダイアログ ボックスで **[閉じる]** をクリックします。  
  
 パッケージの実行に関する詳細についてでパッケージの実行」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)です。 いずれかの SSIS パッケージに関連するその他の情報を参照してください"パッケージ操作方法に関するトピック (SSIS)"で[http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)です。  
  
## <a name="verifying-the-results"></a>結果の確認  
 パッケージを実行すると、Siebel データのインポート先となる SQL Server データベースに移動して、結果を確認する必要があります。 パッケージを実行する必要がありますテーブルを作成したコピー先データベースにします。 このテーブルは、Siebel テーブルからの値に設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [Siebel と SSIS のデータ プロバイダーを使用します。](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)