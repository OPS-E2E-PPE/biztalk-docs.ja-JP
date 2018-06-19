---
title: SQL Server Management Studio を使用して SAP データのインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- SQL Server Management Studio, importing data
ms.assetid: c8151c6d-4b33-40fe-9b83-9bed27df9a99
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28981d2130e82a094e470de1e2b6904382be56b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217834"
---
# <a name="import-sap-data-using-sql-server-management-studio"></a>SQL Server Management Studio を使用して SAP データのインポート
このセクションでは、SQL Server Management Studio を使用して SAP システムから SQL Server データベースにデータをインポートする方法について説明します。 このセクションでは、データをインポートする実行可能な SSIS パッケージを作成する方法の命令を提供します。 このセクションでは、SSIS パッケージを実行する方法についても情報を提供します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックに記載されている手順を実行する前に確認します。  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]コンピューターにインストールされます。  
  
-   SQL Server Business Intelligence Development Studio は、コンピューターにインストールします。  
  
### <a name="to-import-data-using-sql-server-management-studio"></a>SQL Server Management Studio を使用してデータをインポートするには  
  
1.  SQL Server Management Studio を起動します。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、SQL Server データベースに接続し、をクリックする値を指定**接続**です。 **Microsoft SQL Server Management Studio**が開きます。  
  
3.  **オブジェクト エクスプ ローラー**、SQL Server 名を展開し、**データベース**、しをエクスポートするテーブルの SAP システムからデータベースを右クリックします。 コンテキスト メニューのをポイント**タスク**、 をクリック**データのインポート**です。 起動、 **SQL Server インポートおよびエクスポート ウィザード**です。  
  
4.  クリックして [ようこそ] 画面の情報を読み取る**次**です。  
  
5.  **データ ソースを選択** ダイアログ ボックスから、**データ ソース**ドロップ ダウン リスト **.NET Framework Data Provider 用 mySAP Business Suite**です。 ダイアログ ボックスは、SAP システムへの接続に別の接続パラメーターを一覧表示します。 使用して SAP システムへの接続に一般的な接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が必要です。  
  
    -   接続の接続パラメーターを入力します。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] A、B、および D の接続の種類をサポートしていますSAP システムへの接続には、いずれかの接続パラメーターを指定する必要があります*1*種類の接続をします。 たとえば、接続の種類、システム数と、アプリケーション サーバーのホストの名前を指定する必要があります。  
  
    -   ユーザー名やパスワードなど、SAP システムへの接続にログイン情報。  
  
     使用して SAP システムへの接続への接続文字列の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 接続文字列のデータ プロバイダーの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)です。  
  
     **データ ソースを選択** ダイアログ ボックスで指定します。  
  
    -   任意の 1 つの接続の接続パラメーターを入力します。  
  
    -   SAP システムへの接続にログイン情報。  
  
    -   SAP GUI のデバッグを有効にするかどうか。  
  
    -   RFC SDK トレースを使用するかどうか。  
  
     **[次へ]** をクリックします。  
  
6.  **先選択** ダイアログ ボックス。  
  
    1.  **先**ドロップダウン リストで、 **SQL Native Client**です。  
  
    2.  **サーバー名**ドロップダウン リストで、SQL server 名を選択します。  
  
    3.  認証モードを選択します。  
  
    4.  **データベース**ドロップダウン リストで、SAP テーブルをインポートするデータベースを選択します。  
  
    5.  **[次へ]** をクリックします。  
  
7.  **テーブルのコピーを指定またはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプションし、をクリックして**次**です。  
  
8.  **ソース クエリを指定する** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。 クエリを SELECT の文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[選択ステートメント SAP の構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)です。  
  
     をクリックして、**解析**クエリを検証し、をクリックするボタン **[ok]** ポップアップ ダイアログ ボックスにします。 **[次へ]** をクリックします。  
  
9. **[ソース テーブルおよびビュー** ] ダイアログ ボックスで、ソース テーブルと対象テーブルに対してチェック ボックスをオンにします。 ソースは、SAP からデータを取得するように指定したクエリを示します。 変換先は、SQL Server データベースに作成されるテーブルです。  
  
10. ウィザードでは、テーブルのフィールド、ソースと移行先の既定のマッピングを作成します。 ただし、要件に従って、マッピングを変更することができます。 フィールド マッピングを変更する をクリックして**マッピングの編集**です。  
  
     ![SAP テーブルと SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")  
  
11. **列マッピング**ダイアログ ボックスで、することができます。  
  
    -   変換先テーブル内の列の名前を変更します。  
  
    -   変換先テーブル内の特定の列を無視します。  
  
    -   コピー先のテーブル内のフィールドのデータ型を変更します。  
  
    -   Nullable、サイズ、有効桁数、小数点以下桁数などその他のフィールドの属性を変更します。  
  
    -   **[OK]** をクリックします。  
  
12. **ソース テーブルおよびビュー**ダイアログ ボックスで、をクリックして**次へ**です。  
  
13. **パッケージの実行を保存して** ダイアログ ボックス  
  
    -   選択、**をすぐに実行**クエリを実行する チェック ボックスです。  
  
    -   選択、 **SSIS パッケージの保存**パッケージとしてクエリを保存し、後で実行する チェック ボックスです。 パッケージの保存先を選択した場合も、SQL Server またはファイル システムにパッケージを保存するかどうかを指定する必要があります。  
  
    -   **パッケージの保護レベル**-ドロップダウン リスト、選択、保護は、パッケージ レベルし、資格情報を指定必要な場所です。  
  
    -   **[次へ]** をクリックします。  
  
     パッケージを保存することを選択する場合は、次の手順に進みます。 それ以外の場合、手順 15 に進みます。  
  
14. **SSIS パッケージの保存** ダイアログ ボックスで指定します。  
  
    -   パッケージの名前  
  
    -   パッケージの説明  
  
    -   SQL server にパッケージを保存する場合は、選択から SQL Server、**サーバー名**ドロップダウン リスト。  
  
    -   ファイル システムにパッケージを保存する場合は、指定のファイルの場所と名前、**ファイル名**テキスト ボックス。  
  
    -   **[次へ]** をクリックします。  
  
15. **ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**です。  
  
16. **操作の実行**SAP から情報を SQL Server データベース テーブルにインポートするタスクを実行してダイアログ ボックスで、ウィザードを起動します。 各タスクの状態は、ウィザードに表示されます。  
  
17. すべてのタスクが正常に実行される、クリックして**閉じる**です。 タスクが失敗した場合、対応するエラー メッセージを参照してください、問題を修正、ウィザードを再実行します。  
  
## <a name="running-the-ssis-package"></a>SSIS パッケージを実行します。  
 SSIS パッケージを保存する場合を実行すると、SAP システムから最新の情報を取得できます。 このセクションでは、ファイル システムに保存する場合は、パッケージを実行する方法について説明します。  
  
#### <a name="to-run-the-package-from-windows-explorer"></a>Windows エクスプ ローラーからパッケージを実行するには  
  
1.  **Windows エクスプ ローラー**パッケージを保存した場所に移動し、パッケージをダブルクリックします。  
  
2.  **パッケージ実行ユーティリティ**ダイアログ ボックスで、をクリックして**Execute**です。  
  
3.  **パッケージ実行の進行状況** ダイアログ ボックスには、さまざまなタスクの進行状況が表示されます。  
  
4.  すべてのタスクが正常に実行される、クリックして**閉じる**です。  
  
5.  **パッケージ実行ユーティリティ**ダイアログ ボックスで、をクリックして**閉じる**です。  
  
 パッケージの実行の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)です。 SSIS パッケージに関連するその他の情報を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)です。  
  
## <a name="verifying-the-results"></a>結果の確認  
 パッケージを実行すると、SAP データのインポート先となる SQL Server データベースに移動して、結果を確認する必要があります。 パッケージの実行がコピー先データベースにテーブルを作成し、SAP テーブルから値を挿入します。  
  
## <a name="see-also"></a>参照  
 [SAP と SSIS のデータ プロバイダーを使用します。](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)